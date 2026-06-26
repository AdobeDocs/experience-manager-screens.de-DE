---
title: Fehlerbehebung über das Geräte-Kontrollzentrum
description: Erfahren Sie, wie Sie mit dem Geräte-Dashboard die Performance Ihrer AEM Screens-Player-Aktivitäten und -Geräte überwachen und Probleme beheben.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
TQID: https://experienceleague.adobe.com/mb21H-Ky-ySuMvkF75Vhm8Zxzc4zRB65RBVu8hUrFHA
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 827
ht-degree: 87%

---

# Fehlerbehebung über das Geräte-Kontrollzentrum {#troubleshooting-device-control-center}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Über das Geräte-Dashboard können Sie die Performance Ihrer AEM Screens-Player-Aktivitäten und -Geräte überwachen und Probleme beheben. Auf dieser Seite finden Sie Informationen zur Überwachung und Fehlerbehebung bei erkannten Leistungsproblemen des Screens-Players und der zugeordneten Geräte.

## Durchführen der Überwachung und Fehlerbehebung über das Geräte-Kontrollzentrum {#monitor-and-troubleshoot-from-device-control-center}

Über das Geräte-Dashboard können Sie Aktivitäten überwachen und somit Probleme mit Ihrem AEM Screens-Player beheben.

### Geräte-Dashboard {#device-dashboard}

Führen Sie die folgenden Schritte aus, um zum Geräte-Dashboard zu navigieren:

1. Navigieren Sie ausgehend von Ihrem Projekt zum Geräte-Dashboard, z. B. über ***Testprojekt*** > ***Geräte***.

   Klicken Sie in der Aktionsleiste auf **Geräte** und **Geräte-Manager**.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. Die Liste zeigt die zugewiesenen und nicht zugewiesenen Geräte an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Klicken Sie auf das Gerät (**NewTestDevice**) und dann in der Aktionsleiste auf **Dashboard**.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. Auf der Seite werden die Geräteinformationen, die Aktivitäten und die Gerätedetails angezeigt, mit denen Sie die Geräteaktivitäten und -funktionen überwachen können.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Überwachen der Geräteaktivität {#monitor-device-activity}

Im Bedienfeld **Aktivität** wird der letzte Ping Ihres AEM Screens-Players mit dem dazugehörigen Zeitstempel angezeigt. Der letzte Ping entspricht dem letzten Zeitpunkt, zu dem das Gerät den Server kontaktiert hat.

![chlimage_1](assets/chlimage_1.png)

Klicken Sie außerdem oben rechts im Bedienfeld **Aktivität** auf die Option **Protokolle erfassen**, um die Protokolle für Ihren Player anzuzeigen.

### Aktualisieren der Gerätedetails {#update-device-details}

Rufen Sie das Bedienfeld **Gerätedetails** auf, um dort die Geräte-IP, Speichernutzung, Firmware-Version und Player-Betriebszeit für Ihr Gerät anzuzeigen.

![chlimage_1-1](assets/chlimage_1-1.png)

Klicken Sie außerdem auf **Zwischenspeicher löschen** und **Aktualisieren**, um über dieses Bedienfeld den Zwischenspeicher Ihres Geräts zu löschen bzw. die Version der [Firmware](screens-glossary.md) zu aktualisieren.

Klicken Sie darüber hinaus oben rechts im Bedienfeld **Gerätedetails** auf die Auslassungspunkte (**…**), um den Player neu zu starten bzw. den Status zu aktualisieren.

![chlimage_1-2](assets/chlimage_1-2.png)

### Aktualisieren der Geräteinformationen {#update-device-information}

Überprüfen Sie das Bedienfeld **GERÄTEINFORMATIONEN**. Dort können Sie die Konfigurationsaktualisierung, das Gerätemodell, das Betriebssystem des Geräts und die Shell-Informationen anzeigen.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Klicken Sie außerdem auf (**…**) in der rechten oberen Ecke des Bedienfelds Geräteinformationen , um die Eigenschaften anzuzeigen oder das Gerät zu aktualisieren.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Klicken Sie auf **Eigenschaften**, sodass das Dialogfeld **Geräteeigenschaften** angezeigt wird. Sie können den Gerätetitel bearbeiten oder als Option für Konfigurationsaktualisierungen **Manuell** oder **Automatisch** auswählen.

>[!NOTE]
>
>Weitere Informationen zu den Ereignissen, die den automatischen oder manuellen Aktualisierungen des Geräts zugeordnet sind, finden Sie im Abschnitt ***Automatische oder manuelle Aktualisierungen über das Geräte-Dashboard*** unter [Verwalten von Kanälen](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Anzeigen des Player-Screenshots {#view-player-screenshot}

Sie können den Player-Screenshot für das Gerät im Bedienfeld **PLAYER-SCREENSHOT** anzeigen.

Klicken (**…**) Klicken Sie oben rechts im Bedienfeld „Player-Screenshot“ auf **Screenshot aktualisieren** um den Schnappschuss des laufenden Players anzuzeigen.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Verwalten von Voreinstellungen {#manage-preferences}

Im Bedienfeld **VOREINSTELLUNGEN** können Benutzende die Voreinstellungen des Geräts für **Administrator-Benutzeroberfläche**, **Kanalschalter** und **Remote-Debugging** ändern.

>[!NOTE]
>Weitere Informationen zu diesen Optionen finden Sie unter [AEM Screens-Player](working-with-screens-player.md).

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Klicken Sie außerdem oben rechts auf die Option **Einstellungen**, um die Gerätevoreinstellungen zu aktualisieren. Sie können die folgenden Voreinstellungen aktualisieren:

* **Server-URL**
* **Auflösung**
* **Neustartzeitplan**
* **Max. Anzahl der beizubehalt. Prot.dateien**
* **Protokollebene**

![screen_shot_2019-09-05at14511pm](assets/screen_shot_2019-09-05at14511pm.png)

>[!NOTE]
>Sie können auf eine der folgenden Protokollebenen klicken:
>
>* **Deaktivieren**
>* **Debug**
>* **Info**
>* **Warnung**
>* **Fehler**

![screen_shot_2019-09-05at15645pm](assets/screen_shot_2019-09-05at15645pm.png)

## Durchführen der Fehlerbehebung für die OSGi-Einstellungen {#troubleshoot-osgi-settings}

Aktivieren Sie den leeren Referrer, um dem Gerät das Bereitstellen von Daten auf dem Server zu erlauben. Wenn die Eigenschaft für den leeren Referrer deaktiviert ist, kann das Gerät keine Screenshots zurückgeben.

Derzeit sind einige dieser Funktionen nur verfügbar, wenn die *`Apache Sling Referrer Filter Allow Empty`* in der OSGi-Konfiguration aktiviert ist. Im Dashboard wird ggf. eine Warnung angezeigt, dass einige dieser Funktionen aufgrund der Sicherheitseinstellungen nicht funktionieren.

Führen Sie die nachfolgenden Schritte aus, um den Apache Sling Referrer-Filter „Allow Empty“ zu aktivieren

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**: `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Aktivieren Sie die Option **allow.empty**.
1. Klicken Sie auf **Speichern**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Empfehlungen {#recommendations}

Im folgenden Abschnitt wird die Überwachung der Netzwerklinks, des Servers und der Player empfohlen, um Informationen zum Zustand zu erhalten und auf Probleme reagieren zu können.

AEM ermöglicht die integrierte Überwachung für:

* *Heartbeat* alle fünf Sekunden, um anzugeben, dass der AEM Screens-Player betriebsbereit ist.
* *Screenshot* des Players, um zu sehen, was derzeit im Player angezeigt wird.
* Die Version der *AEM Screens-Player-Firmware*, die auf dem Player installiert ist.
* *Freier Speicherplatz* auf dem Player.

Empfehlungen für die Remote-Überwachung mit Software von Drittanbietern:

* CPU-Auslastung auf den Playern.
* Überprüfung, ob der Prozess für AEM Screens-Player ausgeführt wird.
* Remote Neustart/Reboot des Players.
* Benachrichtigungen in Echtzeit.

Es wird empfohlen, die Player-Hardware und das Betriebssystem so bereitzustellen, dass eine Remote-Anmeldung möglich ist, um Probleme zu diagnostizieren und den Player neu zu starten.

#### Sonstige Ressourcen {#additional-resources}

Informationen zum Debuggen und Behandeln von Problemen beim Abspielen von Videos in Ihrem Kanal finden Sie unter [Konfiguration der Videowiedergabe und Fehlerbehebung](troubleshoot-videos.md).

