---
title: Problembehebung in der Gerätesteuerung
description: Erfahren Sie, wie Sie mithilfe des Geräte-Dashboards die Leistung Ihrer AEM Screens Player-Aktivität und Ihres-Geräts überwachen und Fehler beheben können.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 35%

---

# Problembehebung in der Gerätesteuerung {#troubleshooting-device-control-center}

Über das Geräte-Dashboard können Sie die Leistung Ihrer AEM Screens Player-Aktivität und Ihres Geräts überwachen und Fehler beheben. Auf dieser Seite finden Sie Informationen zur Überwachung und Fehlerbehebung bei erkannten Leistungsproblemen des Screens-Players und der zugeordneten Geräte.

## Durchführen der Überwachung und Fehlerbehebung über das Geräte-Kontrollzentrum {#monitor-and-troubleshoot-from-device-control-center}

Sie können die Aktivität überwachen und somit mithilfe des Geräte-Dashboards Fehler in Ihrem AEM Screens-Player beheben.

### Geräte-Dashboard {#device-dashboard}

Führen Sie die folgenden Schritte aus, um zum Geräte-Dashboard zu navigieren:

1. Navigieren Sie vom Projekt zum Geräte-Dashboard, z. B. ***Testprojekt*** > ***Geräte***.

   Klicks **Geräte** und **Geräte-Manager** in der Aktionsleiste aus.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. Die Liste zeigt die zugewiesenen und nicht zugewiesenen Geräte an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Klicken Sie auf das Gerät (**NewTestDevice**) und klicken Sie auf **Dashboard** in der Aktionsleiste aus.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. Auf der Seite werden die Geräteinformationen, die Aktivität und die Gerätedetails angezeigt, mit denen Sie die Geräteaktivitäten und -funktionen überwachen können.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Geräteaktivität überwachen {#monitor-device-activity}

Die **Aktivität** zeigt den letzten Ping Ihres AEM Screens-Players mit dem Zeitstempel an. Der letzte Ping entspricht dem letzten Kontakt des Geräts mit dem Server.

![chlimage_1](assets/chlimage_1.png)

Klicken Sie außerdem auf **Protokolle erfassen** oben rechts im **Aktivität** angezeigt, um die Protokolle für Ihren Player anzuzeigen.

### Aktualisieren der Gerätedetails {#update-device-details}

Überprüfen Sie die **Gerätedetails** -Bedienfeld, damit Sie die Geräte-IP, Speicherverwendung, Firmware-Version und Player-Betriebszeit für Ihr Gerät anzeigen können.

![chlimage_1-1](assets/chlimage_1-1.png)

Klicken Sie außerdem auf **Cache löschen** und **Aktualisieren** , um den Cache Ihres Geräts zu löschen und die [Firmware](screens-glossary.md) -Version aus diesem Bedienfeld aus.

Klicken Sie außerdem auf **...** oben rechts im **Gerätedetails** um den Status Ihres Players neu zu starten oder zu aktualisieren.

![chlimage_1-2](assets/chlimage_1-2.png)

### Aktualisieren von Geräteinformationen {#update-device-information}

Überprüfen Sie die **GERÄTEINFORMATIONEN** Bedienfeld. Hier können Sie die Konfigurationsaktualisierung, das Gerätemodell, das Betriebssystem des Geräts und die Shell-Informationen anzeigen.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Klicken Sie außerdem auf (**...**) oben rechts im Bedienfeld &quot;Geräteinformationen&quot;klicken, um Eigenschaften anzuzeigen oder das Gerät zu aktualisieren.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Klicks **Eigenschaften** so können Sie die **Geräteeigenschaften** Dialogfeld. Sie können den Gerätenamen bearbeiten oder die Option für Konfigurationsaktualisierungen als **Manuell** oder **Automatisch**.

>[!NOTE]
>
>Weitere Informationen zu den Ereignissen, die den automatischen oder manuellen Aktualisierungen des Geräts zugeordnet sind, finden Sie im Abschnitt ***Automatische oder manuelle Aktualisierungen über das Geräte-Dashboard*** unter [Verwalten von Kanälen](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Anzeigen des Player-Screenshots {#view-player-screenshot}

Sie können den Player-Screenshot für das Gerät im Bedienfeld **PLAYER-SCREENSHOT** anzeigen.

Klicken Sie auf (**...**) oben rechts im Bedienfeld &quot;Player-Screenshot&quot;auf und klicken Sie auf **Screenshot aktualisieren** , um den Schnappschuss des ausgeführten Players anzuzeigen.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Verwalten von Voreinstellungen {#manage-preferences}

Im Bedienfeld **VOREINSTELLUNGEN** können Benutzer die Voreinstellungen des Geräts für **Administrator-Benutzeroberfläche**, **Kanalschalter** und **Remote-Debugging** ändern.

>[!NOTE]
>Weitere Informationen zu diesen Optionen finden Sie unter [AEM Screens Player](working-with-screens-player.md).

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Klicken Sie außerdem auf **Einstellungen** oben rechts, um die Gerätevoreinstellungen zu aktualisieren. Sie können die folgenden Voreinstellungen aktualisieren:

* **Server-URL**
* **Auflösung**
* **Neustartzeitplan**
* **Max. Anzahl der beizubehalt. Prot.dateien**
* **Protokollebene**

![screen_shot_2019-09-05at14511pm](assets/screen_shot_2019-09-05at14511pm.png)

>[!NOTE]
>Sie können auf eine der folgenden Protokollebenen klicken:
>* **Deaktivieren**
>* **Debug**
>* **Info**
>* **Warnung**
>* **Fehler**

![screen_shot_2019-09-05at15645pm](assets/screen_shot_2019-09-05at15645pm.png)

## Fehlerbehebung bei OSGi-Einstellungen {#troubleshoot-osgi-settings}

Aktivieren Sie den leeren Referrer, damit das Gerät Daten an den Server posten kann. Wenn die Eigenschaft für den leeren Referrer deaktiviert ist, kann das Gerät keine Screenshots zurückgeben.

Derzeit sind einige dieser Funktionen nur verfügbar, wenn der *Apache Sling Referrer-Filter „Allow Empty“* in der OSGi-Konfiguration aktiviert ist. Im Dashboard wird ggf. eine Warnung angezeigt, dass einige dieser Funktionen aufgrund der Sicherheitseinstellungen nicht funktionieren.

Führen Sie die nachfolgenden Schritte aus, um den Apache Sling Referrer-Filter „Allow Empty“ zu aktivieren

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**: `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Aktivieren Sie die Option **allow.empty**.
1. Klicken Sie auf **Speichern**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Empfehlungen {#recommendations}

Im folgenden Abschnitt wird empfohlen, die Netzwerklinks, Server und Player zu überwachen, um den Zustand zu verstehen und auf Probleme zu reagieren.

AEM bietet integrierte Überwachung für:

* *Heartbeat* alle 5 Sekunden, um anzugeben, dass der AEM Screens-Player aktiv ist.
* *Screenshot* aus dem Player, der anzeigt, was auf dem Player angezeigt wird.
* Die *AEM Screens Player-Firmware* auf dem Player installiert ist.
* *Freier Speicherplatz* auf dem Player.

Recommendations für Remote-Überwachung mit Drittanbietersoftware:

* CPU-Auslastung auf Playern.
* Überprüfen Sie, ob der AEM Screens Player-Prozess ausgeführt wird.
* Remote Neustart/Neustart des Players.
* Echtzeit-Benachrichtigungen.

Es wird empfohlen, die Player-Hardware und das Betriebssystem so bereitzustellen, dass die Remote-Anmeldung Probleme diagnostizieren und den Player neu starten kann.

#### Sonstige Ressourcen {#additional-resources}

Siehe [Konfiguration der Videowiedergabe und Fehlerbehebung](troubleshoot-videos.md) , wenn Sie die Videowiedergabe in Ihrem Kanal debuggen und Fehler beheben möchten.
