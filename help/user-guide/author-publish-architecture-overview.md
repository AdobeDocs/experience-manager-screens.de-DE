---
title: Architektonischer Überblick zur Autoren- und Veröffentlichungsinstanz
description: Die AEM Screens-Architektur ähnelt der traditionellen AEM Sites-Architektur. Inhalte werden in einer AEM-Autoreninstanz erstellt und dann vorwärts an mehrere Veröffentlichungsinstanzen repliziert.
content-type: reference
topic-tags: administering
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: ba23eb8e-bbde-4a6e-8cfb-ae98176ed890
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 59%

---

# Architektonischer Überblick zur Autoren- und Veröffentlichungsinstanz {#author-and-publish-architectural-overview}

Auf dieser Seite werden folgende Themen hervorgehoben:

* **Einführung in Veröffentlichungs-Server**
* **Architektonischer Überblick**
* **Registrierungsverfahren**

## Voraussetzungen {#prerequisites}

Bevor Sie Autoren- und Veröffentlichungs-Server verwenden, sollten Sie mit folgenden Themen vertraut sein:

* **AEM-Topologie**
* **Erstellen und Verwalten von AEM Screens-Projekten**
* **Verfahren zur Geräteregistrierung**

>[!NOTE]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie das Feature Pack 2 für AEM 6.4 Screens installiert haben.  Um Zugriff auf dieses Feature Pack zu erhalten, wenden Sie sich an den Adobe-Support und fordern Sie Zugriff an. Nachdem Sie die Berechtigung erhalten haben, laden Sie es von Package Share herunter.

## Einführung {#introduction}

Die AEM Screens-Architektur ähnelt der traditionellen AEM Sites-Architektur. Inhalte werden in einer AEM-Autoreninstanz erstellt und dann vorwärts an mehrere Veröffentlichungsinstanzen repliziert. Geräte in AEM Screens können jetzt über einen Lastenausgleich eine Verbindung zu einer AEM Veröffentlichungsfarm herstellen. Es lassen sich zur weiteren Skalierung der Veröffentlichungs-Farm mehrere AEM-Veröffentlichungsinstanzen hinzufügen.

*Beispiel*, gibt ein AEM Screens Content Author einen Befehl für ein bestimmtes Gerät im Authoring-System aus. Dieses Gerät ist für die Interaktion mit einer Veröffentlichungsfarm konfiguriert. Oder interagieren Sie mit einem AEM Screens Content Author, der Informationen über Geräte erhält, die für die Interaktion mit Veröffentlichungs-Farmen konfiguriert sind.

Die folgende Abbildung zeigt sowohl die Autorenumgebung als auch die Veröffentlichungsumgebung.

![screen_shot_2019-03-04at30236pm](assets/screen_shot_2019-03-04at30236pm.png)

## Architektonisches Design {#architectural-design}

Es gibt fünf architektonische Komponenten, die diese Lösung unterstützen:

* ***Replizieren von Inhalten*** von der Autoren- zur Veröffentlichungsinstanz für die Anzeige auf Geräten

* ***Rückwärtsreplikation*** binärer Inhalte aus der Veröffentlichungsumgebung (empfangen von Geräten) in die Authoring-Umgebung.
* ***Senden*** -Befehle vom Autor zur Veröffentlichung über bestimmte REST-APIs.
* ***Messaging*** zwischen Veröffentlichungsinstanzen zur Synchronisierung von aktualisierten Geräteinformationen und Befehlen.
* ***Abruf*** durch den Autor von Veröffentlichungsinstanzen, um Geräteinformationen über bestimmte REST-APIs zu erhalten.

### Replikation (Weiterleitung) von Inhalten und Konfigurationen {#replication-forward-of-content-and-configurations}

Mit den standardmäßigen Replikationsagenten werden AEM Screens-Kanalinhalte, -Standortkonfigurationen und -Gerätekonfigurationen repliziert. Mit dieser Funktion können Autoren den Inhalt eines Kanals aktualisieren und optional eine Art Genehmigungs-Workflow durchlaufen, bevor Kanalaktualisierungen veröffentlicht werden. Für jede Veröffentlichungsinstanz in der Veröffentlichungsfarm muss ein Replikationsagent eingerichtet werden.

Das folgende Diagramm veranschaulicht das Replikationsverfahren:

![screen_shot_2019-03-04at33935pm](assets/screen_shot_2019-03-04at33935pm.png)

>[!NOTE]
>
>Für jede Veröffentlichungsinstanz in der Veröffentlichungsfarm muss ein Replikationsagent eingerichtet werden.

### Screens-Replikationsagenten und -Befehle {#screens-replication-agents-and-commands}

Benutzerdefinierte Screens-spezifische Replikationsagenten werden erstellt, um Befehle von der Autoreninstanz an das AEM Screens-Gerät zu senden. Die AEM-Veröffentlichungsinstanzen dienen als Vermittler, um diese Befehle an das Gerät weiterzuleiten.

Mit diesem Workflow können Autoren das Gerät weiter verwalten, z. B. Geräteaktualisierungen senden und Screenshots aus der Autorenumgebung erstellen. Die AEM Screens-Replikationsagenten verfügen über eine benutzerdefinierte Transportkonfiguration, wie standardmäßige Replikationsagenten.

### Messaging zwischen Veröffentlichungsinstanzen {#messaging-between-publish-instances}

Häufig soll ein Befehl an ein Gerät nur einmal gesendet werden. In einer Veröffentlichungsarchitektur mit Lastenausgleich ist die Veröffentlichungsinstanz, mit der das Gerät eine Verbindung herstellt, jedoch unbekannt.

Daher sendet die Autoreninstanz die Nachricht an alle Veröffentlichungsinstanzen. Es sollte jedoch nur eine einzige Nachricht an das Gerät weitergeleitet werden. Um eine korrekte Benachrichtigung sicherzustellen, muss zwischen den Veröffentlichungsinstanzen kommuniziert werden. Diese Mitteilung wird mithilfe von *Apache ActiveMQ Artemis*. Jede Veröffentlichungsinstanz wird mithilfe des Oak-basierten Sling-Erkennungsdienstes in einer locker gekoppelten Topologie platziert. ActiveMQ ist so konfiguriert, dass jede Veröffentlichungsinstanz kommunizieren und eine einzelne Nachrichtenwarteschlange erstellen kann. Das AEM Screens-Gerät fragt über den Load-Balancer die AEM Veröffentlichungs-Farm ab und übernimmt den Befehl an der Spitze der Warteschlange.

### Rückwärtsreplikation {#reverse-replication}

In vielen Fällen wird nach einem Befehl eine bestimmte Antwort vom Screens-Gerät erwartet, die an die Autoreninstanz weitergeleitet wird. Dafür wird AEM-***Rückwärtsreplikation*** verwendet.

* Erstellen Sie für jede Veröffentlichungsinstanz einen Agenten für Rückwärtsreplikation, ähnlich wie bei den standardmäßigen Replikationsagenten und den AEM Screens-Replikationsagenten.
* Eine Workflow-Starter-Konfiguration überwacht die in der AEM-Veröffentlichungsinstanz geänderten Knoten und löst dann einen Workflow aus, um die Antwort des Geräts im Ausgang der AEM-Veröffentlichungsinstanz zu platzieren.
* Eine Rückwärtsreplikation wird in diesem Kontext nur für Binärdaten (wie Protokolldateien und Screenshots) verwendet, die von den Geräten bereitgestellt werden. Die Erfassung nicht binärer Daten wird abgerufen.
* Bei einer von der AEM-Autoreninstanz abgerufenen Rückwärtsreplikation wird die Antwort abgerufen und in der Autoreninstanz gespeichert.

### Abrufen von Veröffentlichungsinstanzen {#polling-of-publish-instances}

Die Autoreninstanzen müssen in der Lage sein, die Geräte abzurufen, um einen Heartbeat zu erhalten und den Gesundheitsstatus eines verbundenen Geräts zu kennen.

Geräte pingen den Load-Balancer und werden an eine Veröffentlichungsinstanz weitergeleitet. Der Status des Geräts wird dann von der AEM-Veröffentlichungsinstanz über eine Veröffentlichungs-API veröffentlicht, die für alle aktiven Geräte unter **api/screens-dcc/devices/static** und für einzelne Geräte unter **api/screens-dcc/devices/&lt;device_id>/status.json** bereitgestellt wird.

Die Autoreninstanz fragt alle Veröffentlichungsinstanzen ab und führt die Antworten zum Gerätestatus in einem Status zusammen. Der geplante Auftrag, der die Autoreninstanz abfragt, lautet `com.adobe.cq.screens.impl.jobs.DistributedDevicesStatiUpdateJob` und kann auf Basis eines Cron-Ausdrucks konfiguriert werden.

## Registrierung {#registration}

Der Ursprung der Registrierung liegt weiterhin in der AEM-Autoreninstanz. Das AEM Screens-Gerät verweist auf die Autoreninstanz und die Registrierung ist abgeschlossen.

Nachdem ein Gerät in der AEM-Autorenumgebung registriert wurde, werden die Gerätekonfiguration und die Kanal-/Zeitplanzuweisungen an die AEM-Veröffentlichungsinstanzen repliziert. Die AEM Screens-Gerätekonfiguration wird dann aktualisiert, um auf den Lastenausgleich vor der AEM Veröffentlichungsfarm zu verweisen. Diese Vereinbarung soll eine einmalige Einrichtung sein. Nachdem das Screens-Gerät erfolgreich mit der Veröffentlichungsumgebung verbunden ist, kann es weiterhin Befehle aus der Autorenumgebung erhalten. Es sollte nicht erforderlich sein, das AEM Screens-Gerät direkt mit der AEM Autorenumgebung zu verbinden.

![screen_shot_2019-02-25at15218pm](assets/screen_shot_2019-02-25at15218pm.png)

### Die nächsten Schritte {#the-next-steps}

Wenn Sie das architektonische Design der Autoren- und Veröffentlichungsinstanz in AEM Screens verstehen, lesen Sie [Konfigurieren von Autoren- und Veröffentlichungsinstanz für AEM Screens](author-and-publish.md) für weitere Details.
