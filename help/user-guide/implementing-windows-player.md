---
title: Implementieren von Windows 10 Player
seo-title: Implementing Windows 10 Player
description: Auf dieser Seite erfahren Sie, wie Sie den Windows 10 Player für AEM Screens konfigurieren.
seo-description: Follow this page to learn about configuring AEM Screens Windows 10 player.
uuid: da7e88bf-c251-481e-9029-f8fc4768b309
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 4228e8a1-9749-49a6-a1bb-365492bc2a3d
docset: aem65
feature: Administering Screens, Windows Player
role: Admin
level: Intermediate
exl-id: 50b6d9ba-e672-4f4d-a9a8-fb8387685057
source-git-commit: d8c420c289452e3ddb1be42c8f170758385ff7af
workflow-type: ht
source-wordcount: '1148'
ht-degree: 100%

---

# Implementieren von Windows 10 Player {#implementing-windows-player}

Dieser Abschnitt beschreibt, wie der Windows 10 Player für AEM Screens konfiguriert wird. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

## Installieren des Windows Players {#installing-windows-player}

Installieren Sie Windows Player für AEM Screens, um den Windows Player für AEM Screens zu implementieren.

Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

>[!NOTE]
>Der Windows-Player verfügt über keinen Fenstermodus. Der Vollbildmodus ist immer aktiviert.

### Einrichten der Umgebung für das AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Wenn Sie das AEM Screens 6.5.5 Service Pack verwenden, müssen Sie eine Umgebung für den Windows-Player einrichten.

Setzen Sie in der **Konfiguration der Adobe Experience Manager-Web-Konsole** das **SameSite-Attribut für die Anmeldungs-Token-Cookies** auf allen AEM-Autoren- und Veröffentlichungsinstanzen von **Lax** (Gering) auf **None** (Keine).

Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole** über `http://localhost:4502/system/console/configMgr`.

1. Suchen Sie nach *Adobe Granite Token Authentication Handler*.

1. Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** von **Lax** (Gering) auf **None** (Keine) fest.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Klicken Sie auf **Speichern**.

### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-hoc-Methode können Sie den aktuellen Windows Player (*.exe*) installieren. Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:

1. Halten Sie die linke obere Ecke gedrückt, um den Admin-Bereich zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.
1. Navigieren Sie im linken Aktionsmenü zum Link **Geräteregistrierung**, um den Status des Prozesses zur Geräteregistrierung zu prüfen **.**

>[!NOTE]
>
>Wenn der **Status** **REGISTRIERT** ist, wird das Feld **Geräte-ID** ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Benennen des Windows-Players {#name-windows}

Sie können Ihrem Windows-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Windows-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Sobald der Player registriert ist, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Windows-Player zu konfigurieren:

1. Klicken Sie auf **Start** > **Ausführen**
1. Geben Sie `system.cpl` ein
1. Verwenden Sie die Registerkarte „Computername“, um den Hostnamen des Computers festzulegen

## Ändern der Standardoptionen im Windows-Installationsprogramm {#changing-default-options}

In diesem Abschnitt erfahren Sie, wie Sie die Standardoptionen im Windows-Installationsprogramm und die Liste der verfügbaren Anpassungen ändern.

## Installation mit CLI (PowerShell) {#install-powershell}

1. Erstellen Sie einen benutzerdefinierten Speicherort **dediziert** für den Screens-Player, z. B.:
   `C:\Users\User\screens-player`)
1. Installieren
   `aem-screens-player-electron-xxx-signed.exe /S /D=C:\Users\User\screens-player`
1. Öffnen
   `Start-Process C:\Users\User\screens-player\AEMScreensPlayer.exe`

**Beispiel**

```shell
C:\Users\User\Downloads> mkdir screens-player

C:\Users\User\Downloads> .\aem-screens-player-electron-xxx-signed.exe /S /D=C:\Users\User\Downloads\screens-player

C:\Users\User\Downloads> Start-Process C:\Users\User\Downloads\screens-player\AEMScreensPlayer.exe
```

## Massenregistrierung von Windows-Playern {#bulk-registration}

Beim Implementieren von Windows-Playern müssen Sie nicht jeden einzelnen Player manuell konfigurieren. Stattdessen können Sie die JSON-Konfigurationsdatei aktualisieren, wenn sie getestet wurde und für die Bereitstellung bereit ist.

Die Konfiguration stellt sicher, dass alle Player denselben Server in der Konfigurationsdatei pingen. Sie müssen allerdings jeden Player manuell registrieren.

So konfigurieren Sie den Windows 10-Player:

1. Installieren Sie Windows Player.
1. Suchen Sie die Konfigurationsdatei unter ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Aktualisieren Sie die JSON-Konfigurationsdatei mit den nachstehenden Informationen und kopieren Sie sie dann bei allen Systemen, auf denen der Player vorhanden ist, in den gleichen Ordner.

### Richtlinienattribute {#policy-attributes}

Die folgende Tabelle fasst zur Referenz die Richtlinienattribute mit einer JSON-Beispielrichtlinie zusammen:


| **Richtlinienname** | **Zweck** |
|---|---|
| Server | Die URL zum Adobe Experience Manager (AEM)-Server. |
| registrationKey | Wird für die Massenregistrierung von Geräten mit vorab freigegebenen Schlüsseln verwendet. |
| resolution | Die Auflösung des Geräts. |
| rebootSchedule | Der Zeitplan zum Neustarten des Players. |
| enableAdminUI | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableActivityUI | Aktivierung zum Anzeigen des Fortschritts von Aktivitäten wie Downloads und Synchronisierungen. Aktivieren Sie diese Option zur Fehlerbehebung und deaktivieren Sie sie, sobald sie vollständig konfiguriert ist und sich in der Produktion befindet. |
| cloudMode | Setzen Sie dies auf „wahr“, wenn Sie möchten, dass der Windows-Player eine Verbindung zu Screens as a Cloud Service herstellt. Legen Sie den Wert auf „false“ fest, um eine Verbindung zu AMS oder AEM On-Premise herzustellen. |
| cloudToken | Anmelde-Token zur Registrierung bei Screens as a Cloud Service. |

#### Beispielhafte JSON-Richtliniendatei {#example-policy-json-file}

```
{
    "server": "https://localhost:4502",
    "resolution": "auto",
    "rebootSchedule": "at 4:00 am",
    "enableAdminUI": false,
    "enableOSD": false,
    "enableActivityUI": false
}
```

## Aktivieren des Kiosk-Modus {#enabling-kiosk-mode}

Bei der Bereitstellung des Windows Players ist es wichtig, einen Kiosk-Modus zu aktivieren, damit andere Anwendungen oder die Task-Leiste nicht auf dem Windows-Desktop angezeigt werden.

>[!CAUTION]
>
>Adobe empfiehlt eine Geräteverwaltungslösung, um Kiosk für Windows zu aktivieren. Gehen Sie wie folgt vor, wenn Sie keine Lösung zur Geräteverwaltung haben, um den Kiosk-Modus zu aktivieren. Diese Methode verwendet die Shell-Starterfunktion, die in Windows 10 Enterprise und Education verfügbar ist. Alle anderen von Microsoft empfohlenen Methoden für Nicht-UWP-Apps können auch angewendet werden, um Kiosk zu aktivieren, insbesondere unter anderen Windows-Editionen.

Gehen Sie wie folgt vor, um den Kiosk-Modus zu aktivieren:

>[!NOTE]
>
>Bevor Sie die folgenden Schritte ausführen, stellen Sie sicher, dass Sie Windows 10 Enterprise oder Education verwenden.

1. Aktivieren Sie das Shell-Startprogramm.

   Weitere Informationen finden Sie im Abschnitt ***Shell-Startprogramm konfigurieren*** auf der Seite **[Shell-Startprogramm](https://docs.microsoft.com/de-de/windows-hardware/customize/enterprise/shell-launcher)** des Microsoft Windows-Supports.

1. Erstellen Sie einen Benutzer ohne Administratorrechte (falls Sie noch keinen haben), der für Kiosk verwendet werden soll. Dabei kann es sich um einen lokalen Benutzer oder einen Domänenbenutzer handeln.
1. Installieren Sie den Windows Player für diesen Kiosk-Benutzer von der Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/).
1. Weitere Informationen zur Modifikation des PowerShell-Skripts finden Sie unter [Verwenden des Shell-Startprogramms zum Erstellen eines Windows 10-Kiosks](https://docs.microsoft.com/de-de/windows/configuration/kiosk-shelllauncher).

   Ändern Sie das PowerShell-Skript, um den Benutzernamen durch den von Ihnen erstellten zu ersetzen. Stellen Sie sicher, dass der Pfad zur ausführbaren Datei der Anwendung korrekt ist. Dadurch wird die benutzerdefinierte Shell als Windows Player-Anwendung für den Kiosk-Benutzer festgelegt und die Standardeinstellung wird als explorer.exe für andere Benutzer festgelegt.

1. Führen Sie das PowerShell-Skript als Administrator aus.
1. Starten Sie neu und melden Sie sich als Kiosk-Benutzer an. Die Player-Anwendung sollte sofort starten.

### Fehlerbehebung {#troubleshooting}

Wenn Sie einen schwarzen Bildschirm sehen, wenn Sie sich als Kiosk-Benutzer anmelden, bedeutet dies, dass Sie den Pfad zur ausführbaren Windows Player-Datei falsch angegeben haben. Melden Sie sich wieder als Administrator an. Überprüfen Sie das Skript und führen Sie es erneut aus.

Der standardmäßige Installationspfad für Windows Player lautet:

***C:\Benutzer\&amp;lt;Ihr Benutzer>\AppData\Local\Programme\@aem-screensscreens-player-electron\AEM Screens Player.exe***

Das Beispielskript in den Links aktiviert und deaktiviert die benutzerdefinierte Shell. Daher müssen Sie das Skript möglicherweise in zwei Teile aufteilen und die folgenden zutreffenden Zeilen aktivieren/deaktivieren:

>[!NOTE]
>
>In einigen Windows-Umgebungen sind die PowerShell-Skripte möglicherweise durch Richtlinien eingeschränkt (insbesondere nicht signierte Skripte). Um Ihr Skript auszuführen, müssen Sie diese Einschränkung vorübergehend deaktivieren und wieder aktivieren. Öffnen Sie ein PowerShell-Fenster und verwenden Sie diese Befehle.
>
>*set-executionpolicy unrestricted* – zur vorübergehenden Aufhebung von Einschränkungen
>
>*set-executionpolicy restricted* - zur erneuten Aktivierung der Einschränkungen nach der Ausführung des Skripts

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)