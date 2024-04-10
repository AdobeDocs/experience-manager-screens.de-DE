---
title: Architektonischer Überblick zur Autoren- und Veröffentlichungsinstanz
description: Die AEM Screens-Architektur ähnelt einer traditionellen AEM Sites-Architektur. Inhalte werden in einer AEM Autoreninstanz erstellt und dann vorwärts an mehrere Veröffentlichungsinstanzen repliziert.
content-type: reference
topic-tags: administering
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: ba23eb8e-bbde-4a6e-8cfb-ae98176ed890
source-git-commit: 02929219a064e3b936440431e77e67e0bf511bf6
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 43%

---

# Architektonischer Überblick zur Autoren- und Veröffentlichungsinstanz {#author-and-publish-architectural-overview}

Auf dieser Seite werden folgende Themen vorgestellt:

* **Einführung in Veröffentlichungs-Server**
* **Architektonischer Überblick**
* **Registrierungsverfahren**

## Voraussetzungen {#prerequisites}

Bevor Sie mit Autoren- und Veröffentlichungsservern beginnen, sollten Sie über Folgendes verfügen:

* **AEM-Topologie**
* **Erstellen und Verwalten von AEM Screens-Projekten**
* **Verfahren zur Geräteregistrierung**

>[!NOTE]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.4 Screens Feature Pack 2 installiert haben. Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Nachdem Sie die Berechtigung erhalten haben, laden Sie sie von Package Share herunter.

## Einführung {#introduction}

Die AEM Screens-Architektur ähnelt einer traditionellen AEM Sites-Architektur. Inhalte werden in einer AEM-Autoreninstanz erstellt und dann vorwärts an mehrere Veröffentlichungsinstanzen repliziert. Geräte in AEM Screens können jetzt über den Lastenausgleich eine Verbindung zu einer AEM Veröffentlichungsfarm herstellen. Es lassen sich zur weiteren Skalierung der Veröffentlichungs-Farm mehrere AEM-Veröffentlichungsinstanzen hinzufügen.

*Beispiel*, gibt ein AEM Screens-Inhaltsautor einen Befehl auf dem Authoring-System für ein bestimmtes Gerät aus. Dieses Gerät ist für die Interaktion mit einer Veröffentlichungsfarm oder einem AEM Screens-Inhaltsautor konfiguriert, der Informationen über Geräte abruft, die für die Interaktion mit Veröffentlichungsfarmen konfiguriert sind.

Das folgende Diagramm zeigt sowohl die Autorenumgebung als auch die Veröffentlichungsumgebung.

![screen_shot_2019-03-04at30236pm](assets/screen_shot_2019-03-04at30236pm.png)

## Architektonisches Design {#architectural-design}

Es gibt fünf architektonische Komponenten, die diese Lösung ermöglichen:

* ***Replizieren von Inhalten*** von der Autoren- zur Veröffentlichungsinstanz für die Anzeige auf Geräten

* ***Umkehren*** das Replizieren binärer Inhalte aus der Veröffentlichungsumgebung (empfangen von Geräten) in die Authoring-Umgebung.
* ***Senden*** -Befehle von der Autoren- zur Veröffentlichungsinstanz über bestimmte REST-APIs.
* ***Messaging*** zwischen Veröffentlichungsinstanzen zur Synchronisierung von aktualisierten Geräteinformationen und Befehlen.
* ***Abruf*** durch den Autor von Veröffentlichungsinstanzen , um Geräteinformationen über bestimmte REST-APIs zu erhalten.

### Replikation (Weiterleitung) von Inhalten und Konfigurationen  {#replication-forward-of-content-and-configurations}

Mit standardmäßigen Replikationsagenten werden AEM Screens-Kanalinhalte, Standortkonfigurationen und Gerätekonfigurationen repliziert. So können Autoren den Inhalt eines Kanals aktualisieren und optional eine Art Genehmigungs-Workflow durchlaufen, bevor Kanalaktualisierungen veröffentlicht werden. Für jede Veröffentlichungsinstanz in der Veröffentlichungsfarm muss ein Replikationsagent erstellt werden.

Das folgende Diagramm veranschaulicht das Replikationsverfahren:

![screen_shot_2019-03-04at33935pm](assets/screen_shot_2019-03-04at33935pm.png)

>[!NOTE]
>
>Für jede Veröffentlichungsinstanz in der Veröffentlichungsfarm muss ein Replikationsagent erstellt werden.

### Screens-Replikationsagenten und -Befehle  {#screens-replication-agents-and-commands}

Benutzerdefinierte Screens-spezifische Replikationsagenten werden erstellt, um Befehle von der Autoreninstanz an das AEM Screens-Gerät zu senden. Die AEM-Veröffentlichungsinstanzen dienen als Vermittler, um diese Befehle an das Gerät weiterzuleiten.

Auf diese Weise können Autoren das Gerät weiter verwalten, z. B. Geräteaktualisierungen senden und Screenshots der Authoring-Umgebung erstellen. Die AEM Screens-Replikationsagenten verfügen über eine benutzerdefinierte Transportkonfiguration, wie standardmäßige Replikationsagenten.

### Messaging zwischen Veröffentlichungsinstanzen  {#messaging-between-publish-instances}

Häufig soll ein Befehl nur einmal an ein Gerät gesendet werden. In einer Veröffentlichungsarchitektur mit Lastenausgleich ist jedoch nicht bekannt, mit welcher Veröffentlichungsinstanz das Gerät eine Verbindung herstellt.

Daher sendet die Autoreninstanz die Nachricht an alle Veröffentlichungsinstanzen. Es soll jedoch nur eine einzige Nachricht an das Gerät weitergeleitet werden. Um eine korrekte Benachrichtigung zu gewährleisten, muss die Kommunikation zwischen Veröffentlichungsinstanzen stattfinden. Dies wird mit *Apache ActiveMQ Artemis* erreicht. Jede Veröffentlichungsinstanz wird mit dem Oak-basierten Sling-Erkennungs-Service in einer locker gekoppelten Topologie platziert. ActiveMQ wird so konfiguriert, dass jede Veröffentlichungsinstanz kommunizieren und eine einzelne Nachrichtenwarteschlange erstellen kann. Das AEM Screens-Gerät fragt die AEM Veröffentlichungsfarm über den Lastenausgleich ab und übernimmt den Befehl oben in der Warteschlange.

### Rückwärtsreplikation {#reverse-replication}

Nach einem Befehl wird häufig eine Art Antwort vom Screens-Gerät erwartet, die an die Autoreninstanz weitergeleitet wird. Um dieses AEM zu erreichen ***Rückwärtsreplikation*** verwendet.

* Erstellen Sie für jede Veröffentlichungsinstanz einen Agenten für die Rückwärtsreplikation, der den standardmäßigen Replikationsagenten und den AEM Screens-Replikationsagenten entspricht.
* Eine Workflow-Starter-Konfiguration überwacht die in der AEM Veröffentlichungsinstanz geänderten Knoten und Trigger wiederum einen Workflow, um die Antwort des Geräts im Ausgang der AEM Veröffentlichungsinstanz zu platzieren.
* Eine Rückwärtsreplikation wird in diesem Kontext nur für binäre Daten (wie Protokolldateien und Screenshots) verwendet, die von den Geräten bereitgestellt werden. Nicht-binäre Daten werden per Abruf abgerufen.
* Umgekehrte Replikationsabfrage aus der AEM Autoreninstanz ruft die Antwort ab und speichert sie in der Autoreninstanz.

### Abrufen von Veröffentlichungsinstanzen  {#polling-of-publish-instances}

Die Autoreninstanz muss in der Lage sein, die Geräte abzurufen, um einen Heartbeat zu erhalten und den Gesundheitsstatus eines verbundenen Geräts zu kennen.

Geräte pingen den Load-Balancer und werden an eine Veröffentlichungsinstanz weitergeleitet. Der Status des Geräts wird dann von der AEM Veröffentlichungsinstanz über eine Veröffentlichungs-API bereitgestellt unter **api/screens-dcc/devices/static** für alle aktiven Geräte und **api/screens-dcc/devices/&lt;device_id>/status.json** für ein einzelnes Gerät.

Die Autoreninstanz fragt alle Veröffentlichungsinstanzen ab und führt die Antworten zum Gerätestatus in einem Status zusammen. Der geplante Auftrag, der die Autoreninstanz abfragt, lautet `com.adobe.cq.screens.impl.jobs.DistributedDevicesStatiUpdateJob` und kann auf Basis eines Cron-Ausdrucks konfiguriert werden.

## Registrierung {#registration}

Der Ursprung der Registrierung liegt weiterhin in der AEM-Autoreninstanz. Das AEM Screens-Gerät verweist auf die Autoreninstanz und die Registrierung ist abgeschlossen.

Nachdem ein Gerät in der AEM Autorenumgebung registriert wurde, werden die Gerätekonfiguration und die Kanal-/Zeitplanzuweisungen an die AEM Veröffentlichungsinstanzen repliziert. Anschließend wird die Konfiguration des AEM Screens-Geräts aktualisiert, um auf den Load-Balancer vor der AEM-Veröffentlichungs-Farm zu verweisen. Dies soll eine einmalige Einrichtung sein. Nachdem das Screens-Gerät erfolgreich mit der Veröffentlichungsumgebung verbunden ist, kann es weiterhin Befehle aus der Autorenumgebung erhalten. Es sollte nicht erforderlich sein, das AEM Screens-Gerät direkt mit der AEM Autorenumgebung zu verbinden.

![screen_shot_2019-02-25at15218pm](assets/screen_shot_2019-02-25at15218pm.png)

### Die nächsten Schritte {#the-next-steps}

Sobald Sie das architektonische Design der Autoren- und Veröffentlichungsinstanz in AEM Screens kennen, finden Sie weitere Informationen unter [Konfigurieren von Autoren- und Veröffentlichungsinstanz für AEM Screens](author-and-publish.md) für weitere Details.
