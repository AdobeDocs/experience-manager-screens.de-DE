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
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 56%

---

# Implementieren des Chrome OS-Players  {#implementing-chrome-os-player}

In diesem Abschnitt wird beschrieben, wie Sie den Chrome OS-Player mit der Chrome Management Console implementieren.

## Verwenden der Chrome Management Console {#using-chrome-management-console}

Führen Sie die nachfolgenden Schritte aus, um die Chrome Management Console einzurichten:

1. Registrieren Sie sich für die Chrome Management Console. Sie müssen eine Lizenz für die Chrome Management Console erwerben. Weitere Informationen zur Verwaltung von Chrome-Geräteeinstellungen finden Sie beim [Google-Support](https://support.google.com/chrome/a/answer/1375678?hl=de&amp;ref_topic=2935995).
1. Melden Sie Ihr Chrome OS-Gerät in der Domain an und warten Sie 15 Minuten, bis das Gerät mit der Chrome Management Console synchronisiert ist. Um mehr über die Registrierung von Chrome-Geräten zu erfahren, wählen Sie [here](https://support.google.com/chrome/a/answer/1360534?hl=de).
1. Der Chrome-Player ist im Chrome-Webstore verfügbar.

>[!NOTE]
>
>Eine Geräteverwaltungslösung wie die Chrome Management Console wird für die Bereitstellung und Verwaltung von Chrome OS-Geräten empfohlen. Obwohl dieses Dokument Implementierung für die Chrome Management Console bietet, gibt es andere Anbieter, die behaupten, ähnliche Funktionen bereitzustellen. Wenden Sie sich an den Anbieter Ihrer Geräteverwaltungssoftware.

## Benennen des Chrome OS-Players {#name-chrome}

Sie können Ihrem Chrome-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Chrome-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Nachdem der Player registriert wurde, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Chrome-Player zu konfigurieren:

1. Sie können optional zulassen, dass Audio-/Video-Integratoren oder IT-Administratoren die Asset-ID und den Speicherort als Teil der Unternehmensregistrierung festlegen.

   ![Bild](/help/user-guide/assets/chrome-device/chrome1.png)

1. Ihnen werden die Optionen angezeigt, mit denen Sie das Gerät registrieren können.

   ![Bild](/help/user-guide/assets/chrome-device/chrome2.jpg)

1. Sie können die Asset-ID als Teil der Unternehmensregistrierung und in der Chrome Management Console festlegen.

   ![Bild](/help/user-guide/assets/chrome-device/chrome3.png)

   >[!NOTE]
   >Chrome-Player müssen bei der Unternehmensregistrierung registriert sein und der Chrome-Player muss über die Chrome Management Console bereitgestellt werden. Andernfalls wird die Asset-ID leer zurückgegeben (z. B. Chrome als Erweiterung). Der Gerätename wird erst zum Zeitpunkt der Registrierung aufgezeichnet. Zukünftige Änderungen werden nicht von Adobe Experience Manager (AEM) übernommen.

### Aktivieren des Kiosk-Modus {#enabling-kiosk-mode}

Gehen Sie wie folgt vor, um den Kiosk-Modus zu aktivieren:

1. Melden Sie sich bei der Chrome Developer Console an.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Navigieren Sie zu **Geräteverwaltung** > **Chrome Management** > **Geräteeinstellungen**.
1. Nach unten scrollen zu **Kiosk-Einstellungen** und wählen **Kiosk-Anwendungen verwalten**.

   ![kiosk](assets/kiosk.png)

1. Wählen Sie den AEM Screens-Player aus dem Chrome Webstore aus.

   >[!NOTE]
   >
   >Es kann rund 15 Minuten dauern, bis eine erst kürzlich veröffentlichte App in dieser Liste angezeigt wird.

1. Wählen Sie **AEM Screens-Player** aus dem Dropdown-Menü **Kiosk-App automatisch starten** aus.

   Es kann je nach Netzwerk mehrere Minuten dauern, bis die Änderungen übernommen werden. Es wird empfohlen, einen Neustart durchzuführen.

#### Überprüfen des Remote-Geräte-Status {#checking-remote-device-status}

1. Melden Sie sich bei der Chrome Developer Console an.
1. Navigieren Sie zu **Geräteverwaltung** > **Chrome-Geräte** und wählen Sie das zu kontrollierende Gerät aus.
1. Auswählen **Systemaktivität und Fehlerbehebung**.
1. Überprüfen Sie die Eigenschaften **Gerät neu starten** und **Bildschirmaufnahme** des Geräts. Sie können auch den Status und den Gesundheitszustand des Geräts überprüfen.

>[!NOTE]
>
>Diese Einstellungen können mehrere Minuten nach der Registrierung des Geräts aktiviert werden. Jede Option kann im Laufe der Zeit aktiviert werden.

### Konfigurieren der Fernkonfiguration von Chrome OS-Playern {#configuring-remote-configuration-of-chrome-os-players}

AEM Screens-Player ist eine Kiosk-fähige Anwendung, die auch eine Fernkonfiguration von Richtlinien für Chrome OS-Player gestattet.

Gehen Sie wie folgt vor, um verschiedene Player-Optionen zu konfigurieren:

1. Melden Sie sich bei der Chrome Management Console an.
1. Auswählen **Geräteverwaltung** > **Chrome Management** > **App-Verwaltung**. Der AEM Screens-Player wird in der Liste angezeigt.
1. Anwendung auswählen **AEM Screens Player**.
1. Auswählen **Kiosk-Einstellungen** und wählen Sie Ihre Organisation (*bei Verwendung einer Testumgebung*).
1. Auswählen **Konfigurationsdatei hochladen** und laden Sie die Konfigurationsrichtlinie hoch (*JSon-Datei*).
1. Wählen Sie **Speichern** aus. Starten Sie das Gerät neu, damit Sie die Richtlinie synchronisieren können.

>[!NOTE]
>
>Starten Sie das Gerät neu, damit Sie Richtlinienänderungen synchronisieren können.

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
| Server | Die URL zum Adobe Experience Manager (AEM)-Server. |
| registrationKey | Wird für die Massenregistrierung von Geräten mit vorab freigegebenen Schlüsseln verwendet. |
| resolution | Die Auflösung des Geräts. |
| rebootSchedule | Der Zeitplan zum Neustarten des Players. |
| enableAdminUI | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableActivityUI | Aktivieren Sie diese Option, damit Sie den Fortschritt von Aktivitäten wie Download und Synchronisierung anzeigen können. Aktivieren Sie diese Option zur Fehlerbehebung und deaktivieren Sie sie, sobald sie vollständig konfiguriert ist und sich in der Produktion befindet. |
| cloudMode | Setzen Sie dies auf „wahr“, wenn Sie möchten, dass der Chrome-Player eine Verbindung zu Screens as a Cloud Service herstellt. Auf &quot;false&quot;setzen, um eine Verbindung zu AMS oder On-Premise-AEM herzustellen. |
| cloudToken | Anmelde-Token zur Registrierung bei Screens as a Cloud Service. |

>[!NOTE]
>
>Richtlinienkonfigurationen werden streng durchgesetzt und können nicht manuell auf der Admin-Benutzeroberfläche des Players überschrieben werden. Um eine manuelle Player-Konfiguration für eine bestimmte Richtlinie zu ermöglichen, geben Sie die Richtlinie nicht in der ***Richtlinienkonfiguration***. Wenn Sie beispielsweise eine manuelle Konfiguration für den Neustart-Zeitplan zulassen möchten, geben Sie den Schlüssel nicht an ***rebootSchedule*** in der Richtlinienkonfiguration.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
