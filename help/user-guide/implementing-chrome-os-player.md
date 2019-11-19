---
title: Implementieren des Chrome OS Players
seo-title: Implementieren des Chrome OS Players
description: Auf dieser Seite erfahren Sie mehr über die Implementierung von Chrome OS Player mithilfe der Chrome Management Console.
seo-description: Auf dieser Seite erfahren Sie mehr über die Implementierung von Chrome OS Player mithilfe der Chrome Management Console.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Implementieren des Chrome OS Players  {#implementing-chrome-os-player}

In diesem Abschnitt wird beschrieben, wie Sie den Chrome OS Player mit der Chrome Management Console implementieren.

## Verwenden der Chrome Management Console {#using-chrome-management-console}

Führen Sie die nachfolgenden Schritte aus, um die Chrome Management Console einzurichten:

1. Registrieren Sie sich bei der Chrome Management Console. Sie müssen eine Lizenz für die Chrome Management Console erwerben. Contact [Google Support](https://support.google.com/chrome/a/answer/1375678?hl=en&ref_topic=2935995) to Manage Chrome device settings for more information.
1. Registrieren Sie Ihr Chrome OS-Gerät in der Domäne und warten Sie 15 Minuten, damit sich das Gerät mit der Chrome Management Console synchronisieren kann. Weitere Informationen zur Registrierung von Chrome-Geräten erhalten Sie, wenn Sie [hier](https://support.google.com/chrome/a/answer/1360534?hl=en) klicken.
1. Der Chrome Player ist im Chrome Webstore verfügbar.

>[!NOTE]
>
>Es wird empfohlen, eine Geräteverwaltungslösung wie die Chrome Management Console für die Bereitstellung und Verwaltung von Chrome OS-Geräten zu verwenden. In diesem Dokument wird die Implementierung mithilfe der Chrome Management Console beschrieben, es gibt jedoch auch andere Anbieter, die Produkte mit ähnlicher Funktionalität anbieten. Wenden Sie sich an den Anbieter Ihrer Geräteverwaltungssoftware.

### Aktivieren des Kioskmodus {#enabling-kiosk-mode}

Gehen Sie wie folgt vor, um den Kioskmodus zu aktivieren:

1. Melden Sie sich bei der Chrome Developer Console an.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Browse to **Device management** &gt; **Chrome Management** &gt; **Device Settings**.
1. Scrollen Sie nach unten zur Option **Kiosk-Einstellungen** und klicken Sie dann auf **Kiosk-Anwendungen verwalten**.

   ![Kiosk](assets/kiosk.png)

1. Wählen Sie den AEM Screens Player aus dem Chrome Webstore aus.

   >[!NOTE]
   >
   >Es kann rund 15 Minuten dauern, bis eine erst kürzlich veröffentlichte App in dieser Liste angezeigt wird.

1. Select **AEM Screens Player** from the **Auto Launch Kiosk App** dropdown.

   Es kann je nach Netzwerk mehrere Minuten dauern, bis die Änderungen übernommen sind. Es wird empfohlen, einen Neustart durchzuführen.

#### Überprüfen des Ferngeräte-Status {#checking-remote-device-status}

1. Melden Sie sich bei der Chrome Developer Console an.
1. Browse to **Device management** &gt; **Chrome Devices** and select the device you wish to control.
1. Klicken Sie auf **Systemaktivität und Fehlerbehebung**.
1. Überprüfen Sie die Eigenschaften **Gerät neu starten** und **Bildschirmaufnahme** des Geräts. Sie können auch die Status- und Konsistenzinformationen des Geräts überprüfen.

>[!NOTE]
>
>Beachten Sie, dass diese Einstellungen möglicherweise mehrere Minuten nach der Registrierung des Geräts aktiviert werden. Jede Option wird möglicherweise mit der Zeit aktiviert.

### Konfigurieren der Fernkonfiguration von Chrome OS Playern {#configuring-remote-configuration-of-chrome-os-players}

Der AEM Screens Player ist eine Kiosk-fähige Anwendung, die auch die Konfiguration von Remote-Richtlinien für Chrome OS Player aktiviert.

Gehen Sie wie folgt vor, um verschiedene Player-Optionen zu konfigurieren:

1. Melden Sie sich bei der Chrome Management Console an.
1. Click **Device management** &gt; **Chrome Management** &gt; **App Management**. Der AEM Screens Player wird in der Liste angezeigt.
1. Klicken Sie auf die Anwendung **AEM Screens Player**.
1. Klicken Sie auf **Kiosk-Einstellungen** und wählen Sie Ihr Unternehmen aus (*wenn eine Testumgebung verwendet wird*).
1. Click on **upload configuration file** and upload the configuration policy (*Json file*).
1. Klicken Sie auf **Speichern**. Sie müssen das Gerät neu starten, um die Richtlinie zu synchronisieren.

>[!NOTE]
>
>Starten Sie das Gerät, um die Richtlinienänderungen zu synchronisieren.

#### Beispielhafte JSON-Richtliniendatei {#example-policy-json-file}

```java
{
  "server": {
    "Value": "https://aemscreensdemo.adobeitc.com"
  },
  "resolution": {
    "Value": "auto"
  },
  "rebootSchedule": {
    "Value": "at 4:00am"
  },
  "enableAdminUI": {
    "Value": true
  },
  "enableOSD": {
    "Value": true
  },
  "enableActivityUI": {
    "Value": true
  }
}
```

### Richtlinienattribute und Zweck {#policy-attributes-and-purpose}

In der folgenden Tabelle sind die Richtlinien und deren Funktionen aufgeführt.

| **Richtlinienname** | **Zweck** |
|---|---|
| *server* | Die URL des Adobe Experience Manager-Servers |
| *resolution* | Die Auflösung des Chrome OS-Geräts |
| *rebootSchedule* | Der Zeitplan für den Neustart des Chrome Players |
| *enableAdminUI* | Aktiviert die Administrator-Benutzeroberfläche, damit Techniker das Gerät vor Ort konfigurieren können. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| *enableOSD* | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| *enableActivityUI* | Aktivierung zum Anzeigen des Fortschritts von Aktivitäten wie Downloads und Synchronisierungen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |

>[!NOTE]
>
>Richtlinienkonfigurationen werden streng durchgesetzt und können nicht manuell auf der Admin-Benutzeroberfläche des Players überschrieben werden. To allow manual player configuration for a particular policy, do not specify the policy in the ***policy configuration,*** for example, if you want to allow manual configuration for reboot schedule, do not specify the key ***rebootSchedule*** in the policy configuration.
