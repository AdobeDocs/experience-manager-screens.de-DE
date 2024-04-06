---
title: Problembehebung in der Gerätesteuerung
seo-title: Monitoring Screens
description: Auf dieser Seite wird beschrieben, wie Sie die Leistung Ihrer Screens-Player-Aktivität und -Geräte über das Geräte-Dashboard überwachen und Fehler beheben.
seo-description: Follow this page to monitor and troubleshoot performance for your Screens player activity and device usingtheDevice dashboard.
uuid: b6895d5d-c743-4e10-a166-de573e122335
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
discoiquuid: 3f130808-71e8-4710-8181-021d953660f8
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 68%

---

# Problembehebung in der Gerätesteuerung {#troubleshooting-device-control-center}

Über das Geräte-Dashboard können Sie die Leistung Ihrer Screens-Player-Aktivität und Ihres Geräts überwachen und Fehler beheben. Auf dieser Seite finden Sie Informationen zur Überwachung und Fehlerbehebung bei erkannten Leistungsproblemen des Screens-Players und der zugeordneten Geräte.

## Durchführen der Überwachung und Fehlerbehebung über das Geräte-Kontrollzentrum {#monitor-and-troubleshoot-from-device-control-center}

Über das Geräte-Dashboard können Sie die Aktivität überwachen und damit Fehler Ihres Screens-Players beheben.

### Geräte-Dashboard {#device-dashboard}

Führen Sie die folgenden Schritte aus, um zum Geräte-Dashboard zu navigieren:

1. Navigieren Sie vom Projekt zum Geräte-Dashboard, z. B. ***Testprojekt*** > ***Geräte***.

   Wählen Sie in der Aktionsleiste die Optionen **Geräte** und **Geräte-Manager** aus.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. Die Liste zeigt die zugewiesenen und nicht zugewiesenen Geräte an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Wählen Sie das Gerät (**NewTestDevice**) aus und klicken Sie in der Aktionsleiste auf **Dashboard**.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. Auf der Seite werden die Geräteinformationen, die Aktivitäten und die Gerätedetails angezeigt, mit denen Sie die Geräteaktivitäten und -funktionen überwachen können.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Geräteaktivität überwachen {#monitor-device-activity}

Die **Aktivität** zeigt den letzten Ping Ihres Screens-Players mit dem Zeitstempel an. Der letzte Ping entspricht dem letzten Kontakt des Geräts mit dem Server.

![chlimage_1](assets/chlimage_1.png)

Klicken Sie außerdem oben rechts im Bedienfeld **Aktivität** auf **Protokolle erfassen**, um die Protokolle für Ihren Player anzuzeigen.

### Aktualisieren der Gerätedetails {#update-device-details}

Zeigen Sie im Bedienfeld **Gerätedetails** die Geräte-IP, Speicherverwendung, Firmware-Version und Player-Betriebszeit für Ihr Gerät an.

![chlimage_1-1](assets/chlimage_1-1.png)

Klicken Sie außerdem auf **Cache löschen** und **Aktualisieren** , um den Cache Ihres Geräts zu löschen und die [Firmware](screens-glossary.md) -Version aus diesem Bedienfeld aus.

Klicken Sie außerdem auf das **...** oben rechts im **Gerätedetails** um den Status Ihres Players neu zu starten oder zu aktualisieren.

![chlimage_1-2](assets/chlimage_1-2.png)

### Aktualisieren von Geräteinformationen {#update-device-information}

Überprüfen Sie das Bedienfeld **GERÄTEINFORMATIONEN**, um das Konfigurationsupdate, Gerätemodell, Betriebssystem des Geräts und die Shell-Informationen anzuzeigen.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Klicken Sie außerdem oben rechts im Bedienfeld „Geräteinformationen“ auf die Punkte (**...**), um Eigenschaften anzuzeigen oder das Gerät zu aktualisieren.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Klicks **Eigenschaften** , um die **Geräteeigenschaften** Dialogfeld. Sie können den Gerätenamen bearbeiten oder die Option für Konfigurationsaktualisierungen als **Manuell** oder **Automatisch**.

>[!NOTE]
>
>Weitere Informationen zu den Ereignissen, die den automatischen oder manuellen Aktualisierungen des Geräts zugeordnet sind, finden Sie im Abschnitt ***Automatische oder manuelle Aktualisierungen über das Geräte-Dashboard*** unter [Verwalten von Kanälen](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Anzeigen des Player-Screenshots {#view-player-screenshot}

Sie können den Player-Screenshot für das Gerät im Bedienfeld **PLAYER-SCREENSHOT** anzeigen.

Klicken Sie oben rechts im Bedienfeld „Player-Screenshot“ auf die Punkte (**...**) und wählen Sie die Option **Screenshot aktualisieren** aus, um den Screenshot des ausgeführten Players anzuzeigen.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Verwalten von Voreinstellungen {#manage-preferences}

Im Bedienfeld **VOREINSTELLUNGEN** können Benutzer die Voreinstellungen des Geräts für **Administrator-Benutzeroberfläche**, **Kanalschalter** und **Remote-Debugging** ändern.

>[!NOTE]
>Weitere Informationen zu dieser Option finden Sie unter [AEM Screens-Player](working-with-screens-player.md).

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Klicken Sie in der rechten oberen Ecke auf **Einstellungen**, um die Gerätevoreinstellungen zu aktualisieren. Sie können die folgenden Voreinstellungen aktualisieren:

* **Server-URL**
* **Auflösung**
* **Neustartzeitplan**
* **Max. Anzahl der beizubehalt. Prot.dateien**
* **Protokollebene**

![screen_shot_2019-09-05at14511pm](assets/screen_shot_2019-09-05at14511pm.png)

>[!NOTE]
>Sie können eine der folgenden Protokollebenen auswählen:
>* **Deaktivieren**
>* **Debug**
>* **Info**
>* **Warnung**
>* **Fehler**

![screen_shot_2019-09-05at15645pm](assets/screen_shot_2019-09-05at15645pm.png)

## Fehlerbehebung bei OSGi-Einstellungen {#troubleshoot-osgi-settings}

Sie müssen den leeren Referrer aktivieren, um dem Gerät das Bereitstellen von Daten auf dem Server zu erlauben. Wenn die Eigenschaft für den leeren Referrer deaktiviert ist, kann das Gerät keine Screenshots zurückgeben.

Derzeit sind einige dieser Funktionen nur verfügbar, wenn der *Apache Sling Referrer-Filter „Allow Empty“* in der OSGi-Konfiguration aktiviert ist. Im Dashboard wird ggf. eine Warnung angezeigt, dass einige dieser Funktionen aufgrund der Sicherheitseinstellungen nicht funktionieren.

Führen Sie die nachfolgenden Schritte aus, um den Apache Sling Referrer-Filter „Allow Empty“ zu aktivieren

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**: `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Aktivieren Sie die Option **allow.empty**.
1. Klicken Sie auf **Speichern**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Empfehlungen {#recommendations}

Im folgenden Abschnitt wird empfohlen, Netzwerklinks, Server und Player zu überwachen, um den Zustand zu verstehen und auf Probleme zu reagieren.

AEM bietet integrierte Überwachung für:

* *Heartbeat* alle 5 Sekunden, um anzuzeigen, dass der AEM Screens-Player aktiv ist.
* *Screenshot* aus dem Player, der anzeigt, was derzeit auf dem Player angezeigt wird.
* Die *AEM Screens Player-Firmware* auf dem Player installiert ist.
* *Freier Speicherplatz* auf dem Player.

Recommendations für Remote-Überwachung mit Drittanbietersoftware:

* CPU-Auslastung auf Playern.
* Überprüfen Sie, ob der AEM Screens Player-Prozess ausgeführt wird.
* Remote Neustart/Neustart des Players.
* Echtzeit-Benachrichtigungen.

Es wird empfohlen, die Player-Hardware und das Betriebssystem so bereitzustellen, dass die Remote-Anmeldung Probleme diagnostizieren und den Player neu starten kann.

#### Zusätzliche Ressourcen {#additional-resources}

Informationen zum Debuggen und Behandeln von Problemen beim Abspielen von Videos in Ihrem Kanal finden Sie unter [Konfiguration der Videowiedergabe und Fehlerbehebung](troubleshoot-videos.md).
