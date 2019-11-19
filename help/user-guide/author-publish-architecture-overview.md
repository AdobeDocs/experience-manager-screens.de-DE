---
title: Architektonische Übersicht über Autoren und Veröffentlichungen
seo-title: Architektonische Übersicht über Autoren und Veröffentlichungen
description: Die AEM Screens-Architektur ähnelt einer traditionellen AEM-Sites-Architektur. Inhalte werden auf einer AEM-Autoreninstanz erstellt und dann in mehrere Instanzen im Veröffentlichungsmodus repliziert. Folgen Sie dieser Seite, um mehr über den Überblick über die Autoren- und Veröffentlichungsarchitektur zu erfahren.
seo-description: Die AEM Screens-Architektur ähnelt einer traditionellen AEM-Sites-Architektur. Inhalte werden auf einer AEM-Autoreninstanz erstellt und dann in mehrere Instanzen im Veröffentlichungsmodus repliziert. Folgen Sie dieser Seite, um mehr über den Überblick über die Autoren- und Veröffentlichungsarchitektur zu erfahren.
uuid: 19bac3de-8938-4339-82f0-6ccb932b6684
content-type: reference
topic-tags: administering
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
discoiquuid: 112404de-5a5a-4b37-b87c-d02029933c8a
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Architektonische Übersicht über Autoren und Veröffentlichungen {#author-and-publish-architectural-overview}

Auf dieser Seite werden die folgenden Themen hervorgehoben:

* **Einführung in die Veröffentlichungsserver**
* **Architekturüberblick**
* **Registrierungsprozess**

## Voraussetzungen {#prerequisites}

Bevor Sie mit Autor- und Veröffentlichungsservern beginnen, sollten Sie über Folgendes verfügen:

* **AEM-Topologie**
* **AEM Screens-Projekt erstellen und verwalten**
* **Geräteregistrierungsprozess**

>[!NOTE]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.4 Screens Feature Pack 2 installiert haben. Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

## Einführung {#introduction}

Die AEM Screens-Architektur ähnelt einer traditionellen AEM-Sites-Architektur. Inhalte werden auf einer AEM-Autoreninstanz erstellt und dann in mehrere Instanzen im Veröffentlichungsmodus repliziert. AEM Screens-Geräte können jetzt über den Lastenausgleich eine Verbindung zu einer AEM-Veröffentlichungsfarm herstellen. Es können mehrere AEM-Veröffentlichungsinstanzen hinzugefügt werden, um die Veröffentlichungsfarm weiter zu skalieren.

*Beispielsweise* gibt ein Autor von AEM Screens-Inhalten auf dem Authoring-System einen Befehl für ein bestimmtes Gerät aus, das für die Interaktion mit einer Veröffentlichungsfarm oder einem Autor von AEM Screens-Inhalten konfiguriert ist und Informationen über Geräte abruft, die für die Interaktion mit Veröffentlichungsfarmen konfiguriert sind.

Das folgende Diagramm zeigt die Autoren- und Veröffentlichungsumgebungen.

![screen_shot_2019-03-04at30236pm](assets/screen_shot_2019-03-04at30236pm.png)

## Architekturdesign {#architectural-design}

Es gibt fünf architektonische Komponenten, die diese Lösung erleichtern:

* ***Replizieren von Inhalten*** vom Autor zur Veröffentlichung für die Anzeige auf Geräten

* ***Rückgängigmachen*** der Replizierung binärer Inhalte von der Veröffentlichung (von Geräten empfangen) zum Autor
* ***Senden*** von Befehlen vom Autor zur Veröffentlichung über bestimmte REST-APIs
* ***Messaging*** zwischen Veröffentlichungsinstanzen zur Synchronisierung von Aktualisierungen und Befehlen der Geräteinformationen
* ***Abruf*** durch den Autor von Veröffentlichungsinstanzen zum Abrufen von Geräteinformationen über bestimmte REST-APIs

### Replikation (Weiterleitung) von Inhalten und Konfigurationen {#replication-forward-of-content-and-configurations}

Mit den standardmäßigen Replizierungsagenten werden Kanalinhalte, Standortkonfigurationen und Gerätekonfigurationen repliziert. Dadurch können Autoren den Inhalt eines Kanals aktualisieren und optional eine Art Genehmigungsvorgang durchlaufen, bevor sie Kanalaktualisierungen veröffentlichen. Für jede Instanz im Veröffentlichungsmodus in der Veröffentlichungsfarm muss ein Replizierungsagenten erstellt werden.

Das folgende Diagramm zeigt den Replikationsprozess:

![screen_shot_2019-03-04at3935pm](assets/screen_shot_2019-03-04at33935pm.png)

>[!NOTE]
>
>Für jede Instanz im Veröffentlichungsmodus in der Veröffentlichungsfarm muss ein Replizierungsagenten erstellt werden.

### Bildschirme Replizierungsagenten und Befehle {#screens-replication-agents-and-commands}

Benutzerdefinierte Bildschirme spezifische Replizierungsagenten werden erstellt, um Befehle von der Autoreninstanz an das AEM Screens-Gerät zu senden. Die AEM Publish-Instanzen dienen als Zwischenspeicher, um diese Befehle an das Gerät weiterzuleiten.

Auf diese Weise können Autoren das Gerät weiterhin verwalten, z. B. Geräteaktualisierungen senden und Screenshots aus der Autorenumgebung erstellen. Die AEM Screens Replizierungsagenten verfügen über eine benutzerdefinierte Transportkonfiguration, wie zum Beispiel standardmäßige Replizierungsagenten.

### Nachrichten zwischen Veröffentlichungsinstanzen {#messaging-between-publish-instances}

In vielen Fällen soll ein Befehl nur einmal an ein Gerät gesendet werden. In einer Veröffentlichungsarchitektur mit Lastenausgleich ist jedoch nicht bekannt, mit welcher Veröffentlichungsinstanz das Gerät verbunden ist.

Daher sendet die Autoreninstanz die Nachricht an alle Veröffentlichungsinstanzen. Es sollte jedoch nur eine einzige Meldung an das Gerät weitergeleitet werden. Um eine korrekte Benachrichtigung sicherzustellen, muss eine Kommunikation zwischen den Instanzen im Veröffentlichungsmodus stattfinden. Dies wird mit *Apache ActiveMQ Artemis erreicht. *Jede Instanz im Veröffentlichungsmodus wird mit dem Oak-basierten Sling Discovery-Dienst in eine locker gekoppelte Toplogie platziert und ActiveMQ ist so konfiguriert, dass jede Instanz im Veröffentlichungsmodus kommunizieren und eine einzige Meldungswarteschlange erstellen kann. Das Bildschirmgerät fragt die Veröffentlichungsfarm über den Lastenausgleich ab und nimmt den Befehl oben in der Warteschlange ab.

### Rückwärtsreplikation {#reverse-replication}

In vielen Fällen wird nach einem Befehl eine Antwort vom Bildschirmgerät erwartet, die an die Autoreninstanz weitergeleitet wird. Um diese AEM- ***Rückwärtsreplikation*** zu erreichen, wird verwendet.

* Erstellen Sie für jede Instanz im Veröffentlichungsmodus einen Agenten für die Rückwärtsreplikation, ähnlich wie bei den standardmäßigen Replizierungsagenten und den Replizierungsagenten im Anzeigebereich.
* Eine Workflow-Starter-Konfiguration überwacht die auf der Veröffentlichungsinstanz geänderten Knoten und löst dann einen Workflow aus, um die Antwort des Geräts im Postausgang der Veröffentlichungsinstanz zu platzieren.
* Eine umgekehrte Replizierung in diesem Kontext wird nur für binäre Daten (wie Protokolldateien und Screenshots) verwendet, die von den Geräten bereitgestellt werden. Nicht-binäre Daten werden durch Umfragen abgerufen.
* Die umgekehrte Replizierung, die von der AEM-Autoreninstanz abgefragt wurde, ruft die Antwort ab und speichert sie in der Autoreninstanz.

### Abruf von Veröffentlichungsinstanzen {#polling-of-publish-instances}

Die Autoreninstanz muss die Geräte abfragen können, um einen Heartbeat zu erhalten und den Gesundheitsstatus eines angeschlossenen Geräts zu kennen.

Geräte, die den Lastenausgleich durchführen und an eine Veröffentlichungsinstanz weitergeleitet werden. Der Status des Geräts wird dann von der Veröffentlichungsinstanz über eine Veröffentlichungs-API bereitgestellt, die für alle aktiven Geräte @ **api/screens-dcc/devices/stati** und für alle aktiven Geräte **api/screens-dcc/devices/&lt;device_id&gt;/status.json** für ein einzelnes Gerät bereitgestellt wird.

Die Autoreninstanz fragt alle Veröffentlichungsinstanzen ab und führt die Gerätestatusantworten in einem Status zusammen. Der geplante Auftrag, der zum Autor abfragt, ist `com.adobe.cq.screens.impl.jobs.DistributedDevicesStatiUpdateJob` und kann auf Basis eines Cron-Ausdrucks konfiguriert werden.

## Registrierung {#registration}

Die Registrierung erfolgt weiterhin in der AEM-Autoreninstanz. Das AEM-Bildschirmgerät wird auf die Autoreninstanz verwiesen und die Registrierung ist abgeschlossen.

Nachdem ein Gerät in der Autorenumgebung registriert wurde, werden die Gerätekonfiguration und die Kanal-/Planzuweisungen an die AEM-Veröffentlichungsinstanzen repliziert. Die Konfiguration des AEM Screens-Geräts wird dann aktualisiert, um auf den Lastenausgleich vor der AEM-Veröffentlichungsfarm zu verweisen. Es handelt sich dabei um eine einmalige Einrichtung, bei der das Bildschirmgerät nach erfolgreicher Verbindung mit der Veröffentlichungsumgebung weiterhin Befehle aus der Autorenumgebung erhalten kann, ohne dass das Bildschirmgerät direkt mit der Autorenumgebung verbunden werden muss.

![screen_shot_2019-02-25at15218pm](assets/screen_shot_2019-02-25at15218pm.png)

### Die nächsten Schritte {#the-next-steps}

Wenn Sie sich mit dem Architekturdesign der Einrichtung für Autoren und Veröffentlichungen in AEM Screens vertraut gemacht haben, finden Sie weitere Informationen unter [Konfigurieren von Authoring und Veröffentlichung für AEM Screens](author-and-publish.md) .
