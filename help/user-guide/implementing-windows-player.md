---
title: Implementieren des Windows-Players
description: Erfahren Sie mehr über die Konfiguration des Windows-Players in AEM Screens.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
docset: aem65
feature: Administering Screens, Windows Player
role: Admin
level: Intermediate
exl-id: 50b6d9ba-e672-4f4d-a9a8-fb8387685057
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 96%

---

# Implementieren des Windows-Players {#implementing-windows-player}

In diesem Abschnitt wird die Konfiguration des Windows-Players in AEM Screens beschrieben. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den Einstellungen, die zum Entwickeln und Testen verwendet werden müssen.

## Installieren des Windows Players {#installing-windows-player}

Um den Windows-Player für AEM Screens zu implementieren, müssen Sie ihn zunächst installieren.

Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

>[!NOTE]
>Der Windows-Player verfügt über keinen Fenstermodus. Er befindet sich immer im Vollbildmodus.

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

Mit der Ad-hoc-Methode können Sie den aktuellen Windows-Player (*.exe*) installieren. Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:

1. Halten Sie die linke obere Ecke eine Weile gedrückt, um das Admin-Bedienfeld zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.
1. Navigieren Sie im linken Aktionsmenü zum Link **Geräteregistrierung******, um den Status der Geräteregistrierung zu prüfen.

>[!NOTE]
>
>Wenn der **Status** **REGISTRIERT** lautet, ist das Feld **Geräte-ID** ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Benennen des Windows-Players {#name-windows}

Sie können Ihrem Windows-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Windows-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Nachdem der Player registriert wurde, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Windows-Player zu konfigurieren:

1. Klicken Sie auf **Start** > **Ausführen**.
1. Geben Sie `system.cpl` ein.
1. Legen Sie auf der Registerkarte „Computer-Name“ den Host-Namen des Computers fest.

## Ändern der Standardoptionen im Windows-Installationsprogramm {#changing-default-options}

In diesem Abschnitt erfahren Sie, wie Sie die Standardoptionen im Windows-Installationsprogramm und die Liste der verfügbaren Anpassungen ändern.

## Installation mit CLI (PowerShell) {#install-powershell}

1. Erstellen Sie einen benutzerdefinierten Speicherort, der für den Screens-Player **dediziert** ist, z. B.:
   `C:\Users\User\screens-player`
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
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzende zwischen Kanälen auf dem Gerät wechseln können. Erwägen Sie, ihn auf „false“ festzulegen, sobald er vollständig konfiguriert und in der Produktion verfügbar ist. |
| enableActivityUI | Aktivieren Sie diese Option, um den Fortschritt von Aktivitäten wie Herunterladen und Synchronisieren anzuzeigen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| cloudMode | Legen Sie den Wert auf „true“ fest, damit der Windows-Player eine Verbindung zu Screens as a Cloud Service herstellt. Legen Sie den Wert auf „false“ fest, um eine Verbindung zu AMS oder AEM On-Premise herzustellen. |
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

Bei der Bereitstellung des Windows-Players ist es wichtig, den Kiosk-Modus zu aktivieren, damit andere Anwendungen oder die Task-Leiste nicht auf dem Windows-Desktop angezeigt werden.

>[!CAUTION]
>
>Adobe empfiehlt eine Geräteverwaltungslösung, um Kiosk für Windows zu aktivieren. Gehen Sie wie folgt vor, wenn Sie keine Lösung zur Geräteverwaltung haben, um den Kiosk-Modus zu aktivieren. Diese Methode verwendet die Shell-Startprogramm-Funktion, die in Windows 10 Enterprise und Education verfügbar ist. Alle anderen von Microsoft empfohlenen Methoden für Nicht-UWP-Apps können auch angewendet werden, um den Kiosk-Modus zu aktivieren, insbesondere bei anderen Windows-Editionen.

Gehen Sie wie folgt vor, um den Kiosk-Modus zu aktivieren:

>[!NOTE]
>
>Bevor Sie die folgenden Schritte ausführen, stellen Sie sicher, dass Sie Windows 10 Enterprise oder Education verwenden.

1. Aktivieren Sie das Shell-Startprogramm.

   Weitere Informationen finden Sie im Abschnitt ***Konfigurieren des Shell-Startprogramms*** auf der Seite **[Shell-Startprogramm](https://learn.microsoft.com/en-us/windows/configuration/shell-launcher/)** des Microsoft® Windows-Supports.

1. Erstellen Sie eine Benutzerin oder einen Benutzer ohne Administratorrechte (falls Sie nicht schon welche haben), um sie für Kiosk zu verwenden. Dabei kann es sich um eine lokale Benutzerin oder einen lokalen Benutzer bzw. um eine Domain-Benutzerin oder einen Domain-Benutzer handeln.
1. Installieren Sie den Windows-Player für diese Kiosk-Benutzerin bzw. diesen Kiosk-Benutzer über die Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/).
1. Weitere Informationen zum Ändern des PowerShell-Skripts finden Sie unter [Verwenden des Shell-Startprogramms zum Erstellen eines Windows 10-Kiosks](https://learn.microsoft.com/en-us/windows/configuration/shell-launcher/?tabs=intune).

   Ändern Sie das PowerShell-Skript, um den Benutzernamen durch den von Ihnen erstellten zu ersetzen. Stellen Sie sicher, dass der Pfad zur ausführbaren Datei der Anwendung korrekt ist. Dadurch wird die benutzerdefinierte Shell als Windows-Player-Anwendung für die Kiosk-Benutzerin bzw. den Kiosk-Benutzer festgelegt und explorer.exe als Standard für andere Benutzende.

1. Führen Sie das PowerShell-Skript als Administrator aus.
1. Starten Sie neu und melden Sie sich als Kiosk-Benutzer an. Die Player-Anwendung sollte sofort starten.

### Fehlerbehebung {#troubleshooting}

Wird ein schwarzer Bildschirm angezeigt, nachdem Sie sich als Kiosk-Benutzerin bzw. -Benutzer angemeldet haben, bedeutet dies, dass Sie den Pfad zur ausführbaren Windows-Player-Datei womöglich falsch angegeben haben. Melden Sie sich wieder als Admin an, überprüfen Sie das Skript und führen Sie es erneut aus.

Der standardmäßige Installationspfad für den Windows-Player lautet:

***C:\Benutzer\&lt;Benutzerin oder Benutzer>\AppData\Local\Programme\@aem-screensscreens-player-electron\AEM Screens Player.exe***

Das Beispielskript in den Links aktiviert und deaktiviert die benutzerdefinierte Shell. Daher müssen Sie das Skript in zwei Teile aufteilen und die folgenden zutreffenden Zeilen aktivieren/deaktivieren:

>[!NOTE]
>
>Einige Windows-Umgebungen beschränken PowerShell-Skripte durch Richtlinien, insbesondere wenn die Skripte nicht signiert sind. Um Ihr Skript auszuführen, müssen Sie diese Einschränkung vorübergehend deaktivieren und wieder aktivieren. Öffnen Sie ein PowerShell-Fenster und verwenden Sie diese Befehle.
>
>*`set-executionpolicy unrestricted`* – zur vorübergehenden Aufhebung der Beschränkungen.
>
>*`set-executionpolicy restricted`* – zur erneuten Aktivierung der Einschränkungen nach der Ausführung des Skripts.

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)