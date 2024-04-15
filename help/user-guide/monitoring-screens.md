---
title: Problembehebung in der Gerätesteuerung
description: Erfahren Sie, wie Sie mithilfe des Geräte-Dashboards die Leistung Ihrer AEM Screens-Player-Aktivität und Ihres Geräts überwachen und Fehler beheben können.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 37%

---

# Problembehebung in der Gerätesteuerung {#troubleshooting-device-control-center}

Sie können die Leistung Ihrer AEM Screens-Player-Aktivität und Ihres Geräts über das Geräte-Dashboard überwachen und Fehler beheben. Auf dieser Seite finden Sie Informationen zur Überwachung und Fehlerbehebung bei erkannten Leistungsproblemen des Screens-Players und der zugeordneten Geräte.

## Durchführen der Überwachung und Fehlerbehebung über das Geräte-Kontrollzentrum {#monitor-and-troubleshoot-from-device-control-center}

Über das Geräte-Dashboard können Sie die Aktivität überwachen und damit Fehler Ihres AEM Screens-Players beheben.

### Geräte-Dashboard {#device-dashboard}

Führen Sie die folgenden Schritte aus, um zum Geräte-Dashboard zu navigieren:

1. Navigieren Sie in Ihrem Projekt zum Device Dashboard, ***z. B. Test Projekt*** > ***Geräten***.

   Wählen Sie in der Aktionsleiste die Optionen **Geräte** und **Geräte-Manager** aus.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. Die Liste zeigt die zugewiesenen und nicht zugewiesenen Geräte an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Wählen Sie das Gerät (**NewTestDevice**) und wählen Sie **Dashboard** in der Aktionsleiste aus.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. Im Seite werden die Device Informationen, Aktivität und die Device Details angezeigt, mit denen Sie die Device Aktivitäten und Funktionen überwachen können.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Überwachen der Geräteaktivität {#monitor-device-activity}

Das **Bedienfeld &quot;Aktivität** &quot; zeigt den letzten Ping Ihres AEM Screens Players mit dem Zeitstempel an. Das letzte Ping entspricht dem letzten Zeitpunkt, zu dem der Device den Server kontaktiert hat.

![chlimage_1](assets/chlimage_1.png)

Wählen Sie außerdem in der oberen rechten Ecke des Bedienfelds &quot;**Aktivität**&quot; die Option **&quot;Protokolle** sammeln&quot; aus, um die Protokolle für Ihren Player zu Ansicht.

### Aktualisieren der Gerätedetails {#update-device-details}

Überprüfen Sie die **Gerätedetails** -Bedienfeld, damit Sie die Geräte-IP, Speicherverwendung, Firmware-Version und Player-Betriebszeit für Ihr Gerät anzeigen können.

![chlimage_1-1](assets/chlimage_1-1.png)

Wählen Sie außerdem **Cache löschen** und **Aktualisieren** , um den Cache Ihres Geräts zu löschen und die [Firmware](screens-glossary.md) -Version aus diesem Bedienfeld aus.

Wählen Sie außerdem **...** oben rechts im **Gerätedetails** um den Status Ihres Players neu zu starten oder zu aktualisieren.

![chlimage_1-2](assets/chlimage_1-2.png)

### Aktualisieren der Geräte Informationen {#update-device-information}

Überprüfen Sie das **Bedienfeld GERÄTEINFORMATIONEN** . Hier können Sie die Konfigurationsaktualisierung, Device Modell, Device Betriebssystem und die Shell-Informationen Ansicht.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Wählen Sie außerdem (**...)** in der oberen rechten Ecke des Bedienfelds &quot;Device Informationen&quot; aus, um Eigenschaften zu Ansicht oder die Device zu aktualisieren.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Wählen Sie **Eigenschaften** aus, damit Sie das **Dialogfeld Gerät Eigenschaften** Ansicht können. Sie können den Gerätenamen bearbeiten oder die Option für Konfigurationsaktualisierungen als **Manuell** oder **Automatisch**.

>[!NOTE]
>
>Weitere Informationen zu den Ereignissen, die den automatischen oder manuellen Aktualisierungen des Geräts zugeordnet sind, finden Sie im Abschnitt ***Automatische oder manuelle Aktualisierungen über das Geräte-Dashboard*** unter [Verwalten von Kanälen](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Anzeigen des Player-Screenshots {#view-player-screenshot}

Sie können den Player-Screenshot für das Gerät im Bedienfeld **PLAYER-SCREENSHOT** anzeigen.

Wählen Sie (**...)** in der oberen rechten Ecke des Bedienfelds &quot;Player-Screenshot&quot; und wählen Sie &quot;Aktualisieren Screenshot&quot; aus **, um den Schnappschuss** des ausgeführten Players zu Ansicht.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Voreinstellungen verwalten {#manage-preferences}

Im Bedienfeld **VOREINSTELLUNGEN** können Benutzer die Voreinstellungen des Geräts für **Administrator-Benutzeroberfläche**, **Kanalschalter** und **Remote-Debugging** ändern.

>[!NOTE]
>Weitere Informationen zu diesen Optionen finden Sie unter [AEM Screens](working-with-screens-player.md) Player.

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Wählen Sie außerdem **Einstellungen** oben rechts, um die Gerätevoreinstellungen zu aktualisieren. Sie können die folgenden Voreinstellungen aktualisieren:

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

## Fehlerbehebung bei OSGi Einstellungen {#troubleshoot-osgi-settings}

Aktivieren Sie den leeren Referrer, damit das Gerät Daten an den Server posten kann. Wenn die Eigenschaft für den leeren Referrer deaktiviert ist, kann das Gerät keine Screenshots zurückgeben.

Derzeit sind einige dieser Funktionen nur verfügbar, wenn der *Apache Sling Referrer-Filter „Allow Empty“* in der OSGi-Konfiguration aktiviert ist. Im Dashboard wird ggf. eine Warnung angezeigt, dass einige dieser Funktionen aufgrund der Sicherheitseinstellungen nicht funktionieren.

Führen Sie die nachfolgenden Schritte aus, um den Apache Sling Referrer-Filter „Allow Empty“ zu aktivieren

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**: `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Aktivieren Sie die Option **allow.empty**.
1. Wählen Sie **Speichern** aus.

![chlimage_1-3](assets/chlimage_1-3.png)

### Empfehlungen {#recommendations}

Im folgenden Abschnitt wird empfohlen, die Netzwerkverbindungen, Server und Player zu überwachen, um den Zustand zu verstehen und auf Probleme zu reagieren.

AEM ermöglicht die integrierte Überwachung für:

* *Heartbeat* alle 5 Sekunden, um anzugeben, dass der AEM Screens-Player aktiv ist.
* *Screenshot* aus dem Player, der anzeigt, was auf dem Player angezeigt wird.
* Die *AEM Screens Player-Firmware* auf dem Player installiert ist.
* *Freier Speicherplatz* auf dem Player.

Recommendations für die Fernüberwachung mit Software von Drittanbietern:

* CPU-Auslastung auf den Playern.
* Prüfen Sie, ob AEM Screens Player-Prozess ausgeführt wird.
* Neustart des Players per Remote-Zugriff
* Echtzeit-Benachrichtigungen.

Es wird empfohlen, die Player-Hardware und das Betriebssystem so bereitzustellen, dass Remote-Log-in Probleme diagnostizieren und den Player neu starten können.

#### Sonstige Ressourcen {#additional-resources}

Siehe [Konfiguration der Videowiedergabe und Fehlerbehebung](troubleshoot-videos.md) , wenn Sie die Videowiedergabe in Ihrem Kanal debuggen und Fehler beheben möchten.
