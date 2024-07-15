---
title: Implementieren des Chrome OS-Players
description: Erfahren Sie mehr über die Implementierung des Chrome OS-Players mithilfe der Chrome Management Console.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4f16605b-aec1-45fa-a110-0af6925b74b0
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 100%

---

# Implementieren des Chrome OS-Players {#implementing-chrome-os-player}

In diesem Abschnitt wird beschrieben, wie Sie den Chrome OS-Player mit der Chrome Management Console implementieren.

## Verwenden der Chrome Management Console {#using-chrome-management-console}

Führen Sie die nachfolgenden Schritte aus, um die Chrome Management Console einzurichten:

1. Registrieren Sie sich für die Chrome Management Console. Sie müssen eine Lizenz für die Chrome Management Console erwerben. Für weitere Informationen zur Verwaltung der Chrome-Geräteeinstellungen wenden Sie sich an den [Google-Support](https://support.google.com/chrome/a/answer/1375678?hl=de&amp;ref_topic=2935995).
1. Melden Sie Ihr Chrome OS-Gerät in der Domain an und warten Sie 15 Minuten, bis das Gerät mit der Chrome Management Console synchronisiert ist. Um mehr über die Registrierung von Chrome-Geräten zu erfahren, klicken Sie [hier](https://support.google.com/chrome/a/answer/1360534?hl=de).
1. Der Chrome-Player ist im Chrome-Webstore verfügbar.

>[!NOTE]
>
>Eine Geräteverwaltungslösung wie die Chrome Management Console wird für die Bereitstellung und Verwaltung von Chrome OS-Geräten empfohlen. Auch wenn dieses Dokument eine Implementierung für die Chrome Management Console bietet, gibt es andere Anbieter, die behaupten, ähnliche Funktionen bereitzustellen. Wenden Sie sich an den Anbieter Ihrer Geräteverwaltungs-Software.

## Benennen des Chrome OS-Players {#name-chrome}

Sie können Ihrem Chrome-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Chrome-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Nachdem der Player registriert wurde, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Chrome-Player zu konfigurieren:

1. Sie können optional zulassen, dass die für die Audio-Video-Integration zuständigen Personen oder IT-Admins die Asset-ID und den Speicherort als Teil der Unternehmensregistrierung festlegen.

   ![Bild](/help/user-guide/assets/chrome-device/chrome1.png)

1. Wenn Sie das Gerät anmelden können, werden Ihnen die Optionen angezeigt.

   ![Bild](/help/user-guide/assets/chrome-device/chrome2.jpg)

1. Sie können die Asset-ID als Teil der Unternehmensregistrierung sowie in der Chrome Management Console festlegen.

   ![Bild](/help/user-guide/assets/chrome-device/chrome3.png)

   >[!NOTE]
   >Chrome-Player müssen bei der Unternehmensregistrierung registriert sein und der Chrome-Player muss über die Chrome Management Console bereitgestellt werden. Andernfalls wird die Asset-ID leer zurückgegeben (z. B. Chrome als Erweiterung). Der Gerätename wird erst zum Zeitpunkt der Registrierung aufgezeichnet. Zukünftige Änderungen werden von Adobe Experience Manager (AEM) nicht übernommen.

### Aktivieren des Kiosk-Modus {#enabling-kiosk-mode}

Gehen Sie wie folgt vor, um den Kiosk-Modus zu aktivieren:

1. Melden Sie sich bei der Chrome Developer Console an.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Navigieren Sie zu **Geräteverwaltung** > **Chrome Management** > **Geräteeinstellungen**.
1. Scrollen Sie nach unten zur Option **Kiosk-Einstellungen** und klicken Sie dann auf **Kiosk-Anwendungen verwalten**.

   ![kiosk](assets/kiosk.png)

1. Klicken Sie im Chrome-Webstore auf den AEM Screens-Player.

   >[!NOTE]
   >
   >Für eine erst kürzlich veröffentlichte App kann es rund 15 Minuten dauern, bis sie in dieser Liste angezeigt wird.

1. Klicken Sie im Dropdown-Menü **Kiosk-App automatisch starten** auf **AEM Screens-Player**.

   Es kann je nach Netzwerk mehrere Minuten dauern, bis die Änderungen übernommen werden. Es wird empfohlen, einen Neustart durchzuführen.

#### Überprüfen des Remote-Geräte-Status {#checking-remote-device-status}

1. Melden Sie sich bei der Chrome Developer Console an.
1. Navigieren Sie zu **Geräteverwaltung** > **Chrome-Geräte** und klicken Sie auf das zu kontrollierende Gerät.
1. Klicken Sie auf **Systemaktivität und Fehlerbehebung**.
1. Überprüfen Sie die Eigenschaften **Gerät neu starten** und **Bildschirmaufnahme** des Geräts. Sie können auch den Status und den Gesundheitszustand des Geräts überprüfen.

>[!NOTE]
>
>Diese Einstellungen können mehrere Minuten nach der Registrierung des Geräts aktiviert werden.  Jede Option kann mit der Zeit aktiviert werden.

### Konfigurieren der Fernkonfiguration von Chrome OS-Playern {#configuring-remote-configuration-of-chrome-os-players}

Der AEM Screens-Player ist eine Kiosk-fähige Anwendung, die auch eine Fernkonfiguration von Richtlinien für Chrome OS-Player gestattet.

Gehen Sie wie folgt vor, um verschiedene Player-Optionen zu konfigurieren:

1. Melden Sie sich bei der Chrome Developer Console an.
1. Klicken Sie auf **Geräteverwaltung** > **Chrome Management** > **App-Verwaltung**. Der AEM Screens-Player wird in der Liste angezeigt.
1. Klicken Sie auf die Anwendung **AEM Screens Player**.
1. Klicken Sie auf **Kiosk-Einstellungen** und dann auf Ihr Unternehmen (*wenn eine Testumgebung verwendet wird*).
1. Klicken Sie auf **Konfigurationsdatei hochladen** und laden Sie die Konfigurationsrichtlinie hoch (*JSON-Datei*).
1. Klicken Sie auf **Speichern**. Starten Sie das Gerät neu, um die Richtlinie zu synchronisieren.

>[!NOTE]
>
>Starten Sie das Gerät, um die Richtlinienänderungen zu synchronisieren.

#### Beispiel einer JSON-Richtliniendatei {#example-policy-json-file}

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
| Server | Die URL zum Adobe Experience Manager (AEM)-Server. |
| registrationKey | Wird für die Massenregistrierung von Geräten mit vorab freigegebenen Schlüsseln verwendet. |
| resolution | Die Auflösung des Geräts. |
| rebootSchedule | Der Zeitplan zum Neustarten des Players. |
| enableAdminUI | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzende zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableActivityUI | Aktivierung zum Anzeigen des Fortschritts von Aktivitäten wie Downloads und Synchronisierungen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| cloudMode | Setzen Sie dies auf „true“, wenn Sie möchten, dass der Chrome-Player eine Verbindung zu Screens as a Cloud Service herstellt.  Legen Sie den Wert auf „false“ fest, um eine Verbindung zu AMS oder AEM On-Premise herzustellen. |
| cloudToken | Anmelde-Token zur Registrierung bei Screens as a Cloud Service. |

>[!NOTE]
>
>Richtlinienkonfigurationen werden streng durchgesetzt und die Administrator-Benutzeroberfläche des Players überschreibt nicht manuell. Um eine manuelle Player-Konfiguration für eine bestimmte Richtlinie zu ermöglichen, geben Sie die Richtlinie nicht in der ***Richtlinienkonfiguration*** an. Wenn Sie beispielsweise eine manuelle Konfiguration für den Neustart-Zeitplan zulassen möchten, geben Sie den Schlüssel ***rebootSchedule*** nicht in der Richtlinienkonfiguration an.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
