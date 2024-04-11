---
title: Implementieren von Windows 10 Player
description: Erfahren Sie mehr über die Konfiguration des AEM Screens Windows 10-Players.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
docset: aem65
feature: Administering Screens, Windows Player
role: Admin
level: Intermediate
exl-id: 50b6d9ba-e672-4f4d-a9a8-fb8387685057
source-git-commit: a8055c5f859e401f7b1da4f5d95f1268dee243ad
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 57%

---

# Implementieren von Windows 10 Player {#implementing-windows-player}

Dieser Abschnitt beschreibt, wie der Windows 10 Player für AEM Screens konfiguriert wird. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

## Installieren des Windows Players {#installing-windows-player}

Um Windows Player für AEM Screens zu implementieren, installieren Sie Windows Player für AEM Screens.

Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

>[!NOTE]
>Der Windows-Player verfügt über keinen Fenstermodus. Der Vollbildmodus ist immer aktiviert.

### Einrichten der Umgebung für das AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Richten Sie eine Umgebung für den Windows-Player ein, wenn Sie das AEM Screens 6.5.5 Service Pack verwenden.

Setzen Sie in der **Konfiguration der Adobe Experience Manager-Web-Konsole** das **SameSite-Attribut für die Anmeldungs-Token-Cookies** auf allen AEM-Autoren- und Veröffentlichungsinstanzen von **Lax** (Gering) auf **None** (Keine).

Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole** über `http://localhost:4502/system/console/configMgr`.

1. Suchen Sie nach *Adobe Granite Token Authentication Handler*.

1. Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** von **Lax** (Gering) auf **None** (Keine) fest.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Klicken Sie auf **Speichern**.

### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-hoc-Methode können Sie den neuesten Windows Player (*.exe*). Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:

1. Halten Sie die linke obere Ecke gedrückt, um das Admin-Bedienfeld zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.
1. Navigieren Sie zum **Gerät** **Registrierung** im linken Aktionsmenü, damit Sie den Status des Prozesses zur Geräteregistrierung überprüfen können.

>[!NOTE]
>
>Wenn die Variable **Bundesland** is **REGISTRIERT**, beachten Sie, dass die **Geräte-ID** -Feld gefüllt wird.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Benennen des Windows-Players {#name-windows}

Sie können Ihrem Windows-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Windows-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Sobald der Player registriert ist, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Windows-Player zu konfigurieren:

1. Klicks **start** > **run**.
1. Eingabe `system.cpl`.
1. Legen Sie auf der Registerkarte &quot;Computername&quot;den Hostnamen des Computers fest.

## Ändern der Standardoptionen im Windows-Installationsprogramm {#changing-default-options}

In diesem Abschnitt erfahren Sie, wie Sie die Standardoptionen in Windows Installer und die Liste der verfügbaren Anpassungen ändern können.

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

Bei der Implementierung des Windows-Players müssen Sie nicht jeden Player manuell konfigurieren. Stattdessen können Sie die JSON-Konfigurationsdatei aktualisieren, wenn sie getestet wurde und für die Bereitstellung bereit ist.

Die Konfiguration stellt sicher, dass alle Player denselben Server in der Konfigurationsdatei pingen. Registrieren Sie jeden Player manuell.

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
| enableActivityUI | Aktivieren Sie diese Option, damit Sie den Fortschritt von Aktivitäten wie Download und Synchronisierung anzeigen können. Aktivieren Sie diese Option zur Fehlerbehebung und deaktivieren Sie sie, sobald sie vollständig konfiguriert ist und sich in der Produktion befindet. |
| cloudMode | Setzen Sie dies auf „wahr“, wenn Sie möchten, dass der Windows-Player eine Verbindung zu Screens as a Cloud Service herstellt. Auf &quot;false&quot;setzen, um eine Verbindung zu AMS oder On-Premise-AEM herzustellen. |
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

Bei der Bereitstellung des Windows-Players ist es wichtig, einen Kiosk-Modus zu aktivieren, damit andere Anwendungen oder die Taskleiste nicht auf dem Windows-Desktop angezeigt werden.

>[!CAUTION]
>
>Adobe empfiehlt eine Geräteverwaltungslösung, um Kiosk für Windows zu aktivieren. Gehen Sie wie folgt vor, wenn Sie keine Lösung zur Geräteverwaltung haben, um den Kiosk-Modus zu aktivieren. Diese Methode verwendet die Shell-Starterfunktion, die in Windows 10 Enterprise und Education verfügbar ist. Alle anderen von Microsoft empfohlenen Methoden für Nicht-UWP-Apps können ebenfalls angewendet werden, um Kiosk zu aktivieren, insbesondere bei anderen Windows-Editionen.

Gehen Sie wie folgt vor, um den Kiosk-Modus zu aktivieren:

>[!NOTE]
>
>Bevor Sie die folgenden Schritte ausführen, stellen Sie sicher, dass Sie Windows 10 Enterprise oder Education verwenden.

1. Aktivieren Sie das Shell-Startprogramm.

   Siehe ***Konfigurieren des Shell-Starters*** in **[Shell-Starter](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/customize/shell-launcher)** Seite der Microsoft® Windows-Unterstützung für weitere Informationen.

1. Erstellen Sie einen Benutzer ohne Administratorrechte (falls Sie noch keinen haben), der für Kiosk verwendet werden soll. Dabei kann es sich um einen lokalen Benutzer oder einen Domänenbenutzer handeln.
1. Installieren Sie den Windows Player für diesen Kiosk-Benutzer von der Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/).
1. Siehe [Verwenden Sie Shell Launcher, um einen Windows 10-Kiosk zu erstellen](https://learn.microsoft.com/en-us/windows/configuration/assigned-access/shell-launcher/?tabs=intune) , um Ihr PowerShell-Skript zu ändern.

   Ändern Sie das PowerShell-Skript so, dass Sie den Benutzernamen durch den von Ihnen erstellten ersetzen können. Stellen Sie sicher, dass der Pfad zur ausführbaren Datei der Anwendung korrekt ist. Dadurch wird die benutzerdefinierte Shell als Windows Player-Anwendung für den Kiosk-Benutzer festgelegt und die Standardeinstellung wird als explorer.exe für andere Benutzer festgelegt.

1. Führen Sie das PowerShell-Skript als Administrator aus.
1. Starten Sie neu und melden Sie sich als Kiosk-Benutzer an. Die Player-Anwendung sollte sofort starten.

### Fehlerbehebung {#troubleshooting}

Wenn Sie nach der Anmeldung als Kiosk-Benutzer einen schwarzen Bildschirm erhalten, bedeutet dies, dass Sie den Pfad zur ausführbaren Windows Player-Datei falsch angegeben haben. Melden Sie sich wieder als Administrator an und überprüfen Sie das Skript und führen Sie es erneut aus.

Der standardmäßige Installationspfad für Windows Player lautet:

***C:\Users\&lt;your user=&quot;&quot;>\AppData\Local\Programs\@aem-screensscreens-player-electron\AEM Screens Player.exe***

Das Beispielskript in den Links aktiviert und deaktiviert die benutzerdefinierte Shell. Teilen Sie daher das Skript in zwei Zeilen auf und aktivieren/deaktivieren Sie die folgenden zutreffenden Zeilen:

>[!NOTE]
>
>In einigen Windows-Umgebungen sind die PowerShell-Skripte möglicherweise durch Richtlinien eingeschränkt (insbesondere nicht signierte Skripte). Um Ihr Skript auszuführen, deaktivieren und aktivieren Sie diese Einschränkung vorübergehend, um das Skript auszuführen. Öffnen Sie ein PowerShell-Fenster und verwenden Sie diese Befehle.
>
>*`set-executionpolicy unrestricted`* - vorübergehende Aufhebung der Beschränkungen.
>
>*`set-executionpolicy restricted`* - um die Einschränkung nach der Ausführung des Skripts erneut zu aktivieren.

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)