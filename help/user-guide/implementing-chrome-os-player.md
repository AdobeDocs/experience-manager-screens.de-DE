---
title: Implementieren des Chrome OS-Players
seo-title: Implementing Chrome OS Player
description: Auf dieser Seite erfahren Sie mehr über die Implementierung des Chrome OS-Players mithilfe der Chrome Management Console.
seo-description: Follow  this page to learn about the implementation of the Chrome OS Player using the Chrome Management Console.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4f16605b-aec1-45fa-a110-0af6925b74b0
source-git-commit: 8d4a7b2bc436d822c673a00437ee895c8ef5cb6f
workflow-type: ht
source-wordcount: '846'
ht-degree: 100%

---

# Implementieren des Chrome OS-Players  {#implementing-chrome-os-player}

In diesem Abschnitt wird beschrieben, wie Sie den Chrome OS-Player mit der Chrome Management Console implementieren.

## Verwenden der Chrome Management Console {#using-chrome-management-console}

Führen Sie die nachfolgenden Schritte aus, um die Chrome Management Console einzurichten:

1. Registrieren Sie sich bei der Chrome Management Console. Sie müssen eine Lizenz für die Chrome Management Console erwerben. Weitere Informationen zur Verwaltung von Chrome-Geräteeinstellungen finden Sie beim [Google-Support](https://support.google.com/chrome/a/answer/1375678?hl=de&amp;ref_topic=2935995).
1. Registrieren Sie Ihr Chrome OS-Gerät in der Domäne und warten Sie 15 Minuten, damit sich das Gerät mit der Chrome Management Console synchronisieren kann. Weitere Informationen zur Registrierung von Chrome-Geräten erhalten Sie, wenn Sie [hier](https://support.google.com/chrome/a/answer/1360534?hl=de) klicken.
1. Der Chrome Player ist im Chrome Webstore verfügbar.

>[!NOTE]
>
>Es wird empfohlen, eine Geräteverwaltungslösung wie die Chrome Management Console für die Bereitstellung und Verwaltung von Chrome OS-Geräten zu verwenden. In diesem Dokument wird die Implementierung mithilfe der Chrome Management Console beschrieben, es gibt jedoch auch andere Anbieter, die Produkte mit ähnlicher Funktionalität anbieten. Wenden Sie sich an den Anbieter Ihrer Geräteverwaltungssoftware.

## Benennen des Chrome OS-Players {#name-chrome}

Sie können Ihrem Chrome-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Chrome-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Sobald der Player registriert ist, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Chrome-Player zu konfigurieren:

1. Sie können optional zulassen, dass AV-Integratoren oder IT-Administratoren die Asset-ID und den Speicherort als Teil der Unternehmensregistrierung festlegen.

   ![image](/help/user-guide/assets/chrome-device/chrome1.png)

1. Wenn Sie das Gerät anmelden können, werden Ihnen die Optionen angezeigt.

   ![image](/help/user-guide/assets/chrome-device/chrome2.jpg)

1. Sie können die Asset-ID als Teil der Unternehmensregistrierung sowie in der Verwaltungskonsole von Chrome festlegen.

   ![image](/help/user-guide/assets/chrome-device/chrome3.png)

   >[!NOTE]
   >Chrome-Player müssen bei der Unternehmensregistrierung registriert sein und der Chrome-Player muss über die Verwaltungskonsole von Chrome bereitgestellt werden. Andernfalls wird die Asset-ID leer zurückgegeben (z. B. Chrome als Erweiterung). Der Gerätename wird erst zum Zeitpunkt der Registrierung aufgezeichnet. Zukünftige Änderungen werden von Adobe Experience Manager (AEM) nicht übernommen.

### Aktivieren des Kiosk-Modus {#enabling-kiosk-mode}

Gehen Sie wie folgt vor, um den Kiosk-Modus zu aktivieren:

1. Melden Sie sich bei der Chrome Developer Console an.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Navigieren Sie zu **Geräteverwaltung** > **Chrome Management** > **Geräteeinstellungen**.
1. Scrollen Sie nach unten zur Option **Kiosk-Einstellungen** und klicken Sie dann auf **Kiosk-Anwendungen verwalten**.

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
1. Klicken Sie auf **Systemaktivität und Fehlerbehebung**.
1. Überprüfen Sie die Eigenschaften **Gerät neu starten** und **Bildschirmaufnahme** des Geräts. Sie können auch die Status- und Konsistenzinformationen des Geräts überprüfen.

>[!NOTE]
>
>Beachten Sie, dass diese Einstellungen möglicherweise mehrere Minuten nach der Registrierung des Geräts aktiviert werden. Jede Option wird möglicherweise mit der Zeit aktiviert.

### Konfigurieren der Fernkonfiguration von Chrome OS-Playern {#configuring-remote-configuration-of-chrome-os-players}

AEM Screens-Player ist eine Kiosk-fähige Anwendung, die auch eine Fernkonfiguration von Richtlinien für Chrome OS-Player gestattet.

Gehen Sie wie folgt vor, um verschiedene Player-Optionen zu konfigurieren:

1. Melden Sie sich bei der Chrome Management Console an.
1. Klicken Sie auf **Geräteverwaltung** > **Chrome Management** > **App-Verwaltung**. Der AEM Screens-Player wird in der Liste angezeigt.
1. Klicken Sie auf die Anwendung **AEM Screens Player**.
1. Klicken Sie auf **Kiosk-Einstellungen** und wählen Sie Ihr Unternehmen aus (*wenn eine Testumgebung verwendet wird*).
1. Klicken Sie auf **Konfigurationsdatei hochladen** und laden Sie die Konfigurationsrichtlinie hoch (*Json-Datei*).
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
| *enableAdminUI* | Aktiviert die Administrator-Benutzeroberfläche, damit Techniker das Gerät vor Ort konfigurieren können. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| *enableOSD* | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird |
| *enableActivityUI* | Aktivierung zum Anzeigen des Fortschritts von Aktivitäten wie Downloads und Synchronisierungen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |

>[!NOTE]
>
>Richtlinienkonfigurationen werden streng durchgesetzt und können nicht manuell auf der Admin-Benutzeroberfläche des Players überschrieben werden. Um manuelle Player-Konfigurationen für eine bestimmte Richtlinie zu gestatten, legen Sie die Richtlinie in der ***Richtlinienkonfiguration*** nicht fest. Wenn Sie beispielsweise eine manuelle Konfiguration des Neustart-Zeitplans gestatten wollen, legen Sie den Parameter ***rebootSchedule*** in der Richtlinienkonfiguration nicht fest.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Weitere Informationen zu dieser Funktion finden Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
