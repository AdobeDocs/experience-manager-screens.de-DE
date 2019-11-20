---
title: Implementieren von Windows 10 Player
seo-title: Implementieren von Windows 10 Player
description: Folgen Sie dieser Seite, um mehr über die Konfiguration des Windows 10-Players für AEM Screens zu erfahren.
seo-description: Folgen Sie dieser Seite, um mehr über die Konfiguration des Windows 10-Players für AEM Screens zu erfahren.
uuid: da7e88bf-c251-481e-9029-f8fc4768b309
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 4228e8a1-9749-49a6-a1bb-365492bc2a3d
docset: aem65
translation-type: tm+mt
source-git-commit: 66c741bb73bd5deb2bb5b06dd46f2e407d9c4b7e

---


# Implementieren von Windows 10 Player {#implementing-windows-player}

In diesem Abschnitt wird die Konfiguration des AEM Screens Windows 10-Players beschrieben. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

## Installieren von Windows Player {#installing-windows-player}

Um Windows Player für AEM Screens zu implementieren, installieren Sie Windows Player für AEM Screens.

Rufen Sie die Seite [**AEM 6.4 Player-Downloads**](https://download.macromedia.com/screens/) auf.

### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-Hoc-Methode können Sie den neuesten Windows Player (*.exe*) installieren. Besuchen Sie die Seite [**AEM 6.4 Player-Downloads**](https://download.macromedia.com/screens/) .

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte auf dem Player aus, um die Ad-hoc-Installation abzuschließen:

1. Drücken Sie die lange Taste oben links, um das Admin-Bedienfeld zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration** , geben Sie den Speicherort (die Adresse) der AEM-Instanz ein, mit der Sie eine Verbindung herstellen möchten, und klicken Sie auf **Speichern**.
1. Navigieren Sie im linken Aktionsmenü zum Link **Geräteregistrierung** , um den Status des Geräteregistrierungsprozesses zu prüfen ****.

>[!NOTE]
>
>Wenn der **Bundesstaat** **REGISTRIERT** ist, wird das Feld **Geräte-ID** ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

### Massenserverkonfiguration: Registrieren mehrerer Windows 10-Player mit einer Konfiguration {#bulk-server-configuration-registering-multiple-windows-players-with-one-configuration}

Nachdem Sie den Windows-Player installiert haben, können Sie mehrere Player mit einer Konfiguration registrieren.

>[!NOTE]
>
>**Massenregistrierung von Windows Player**
>
>Beim Implementieren von Windows-Playern müssen Sie nicht jeden einzelnen Player manuell konfigurieren. Stattdessen können Sie auch die getestete und zur Bereitstellung bereite JSON-Konfigurationsdatei aktualisieren.
>
>Die Konfiguration stellt sicher, dass alle Player denselben in der Konfigurationsdatei angegebenen Server anpingen. Trotzdem müssen Sie noch jeden einzelnen Player manuell registrieren.

So konfigurieren Sie den Windows 10-Player:

1. Installieren Sie Windows Player.
1. Suchen Sie die Konfigurationsdatei unter ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Aktualisieren Sie die JSON-Konfigurationsdatei mit den nachstehenden Informationen und kopieren Sie sie dann bei allen Systemen, auf denen der Player vorhanden ist, in den gleichen Ordner.

### Richtlinienattribute {#policy-attributes}

In der folgenden Tabelle finden Sie eine Zusammenfassung der Richtlinienattribute mit einer beispielhaften JSON-Richtliniendatei als Referenz:

| **Richtlinienname** | **Zweck** |
|---|---|
| server | Die URL zum Adobe Experience Manager(AEM)-Server. |
| resolution | Die Auflösung des Geräts. |
| rebootSchedule | Der Plan zum Neustarten des Players. |
| enableAdminUI | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| enableActivityUI | Aktivierung zum Anzeigen des Fortschritts von Aktivitäten wie Downloads und Synchronisierungen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |

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

## Aktivieren des Kioskmodus {#enabling-kiosk-mode}

Bei der Bereitstellung des Windows-Players ist es wichtig, einen Kiosk-Modus zu aktivieren, damit andere Anwendungen oder die Taskleiste nicht auf dem Windows-Desktop angezeigt werden.

>[!CAUTION]
>
>Adobe empfiehlt eine Geräteverwaltungslösung, um Kiosk für Windows zu aktivieren. Gehen Sie wie folgt vor, wenn Sie keine Lösung zur Geräteverwaltung haben, um den Kiosk-Modus zu aktivieren. Diese Methode verwendet die Shell-Starterfunktion, die in Windows 10 Enterprise und Edu verfügbar ist. Alle anderen von Microsoft empfohlenen Methoden für Nicht-UWP-Apps können auch angewendet werden, um Kiosk zu aktivieren, insbesondere auf anderen Windows-Editionen.

Gehen Sie wie folgt vor, um den Kiosk-Modus zu aktivieren:

>[!NOTE]
>
>Bevor Sie die folgenden Schritte ausführen, stellen Sie sicher, dass Sie Windows 10 Enterprise oder Education verwenden.

1. Aktivieren Sie Shell Launcher.

   Weitere Informationen finden Sie im Abschnitt ***Shell Launcher*** konfigurieren auf der Seite **[Shell Launcher](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/shell-launcher)** von Microsoft Windows-Unterstützung.

1. Erstellen Sie einen Benutzer ohne Administratorrechte (falls Sie bereits keinen haben), der für Kiosk verwendet werden soll. Dabei kann es sich um einen lokalen Benutzer oder einen Domänenbenutzer handeln.
1. Installieren Sie den Windows Player für diesen Kiosk-Benutzer von der Seite [AEM Screens Player-Downloads](https://download.macromedia.com/screens/) .
1. Weitere Informationen finden Sie unter [Verwenden Sie Shell Launcher, um ein Windows 10-Kiosk](https://docs.microsoft.com/en-us/windows/configuration/kiosk-shelllauncher) zu erstellen, um Ihr PowerShell-Skript zu ändern.

   Ändern Sie das PowerShell-Skript, um den Benutzernamen durch den von Ihnen erstellten zu ersetzen. Stellen Sie sicher, dass der Pfad zur ausführbaren Datei der Anwendung korrekt ist. Dadurch wird die benutzerdefinierte Shell als Windows Player-Anwendung für den Kiosk-Benutzer festgelegt und die Standardeinstellung wird als explorer.exe für andere Benutzer festgelegt.

1. Führen Sie das PowerShell-Skript als Administrator aus.
1. Starten Sie neu und melden Sie sich als Kiosk-Benutzer und Player-Anwendung sofort an.

### Fehlerbehebung {#troubleshooting}

Wenn Sie einen schwarzen Bildschirm erhalten, wenn Sie sich als Kiosk-Benutzer anmelden, bedeutet dies, dass Sie den Pfad zur ausführbaren Datei Windows Player falsch angegeben haben. Melden Sie sich wieder als Administrator an und überprüfen und führen Sie das Skript erneut aus.

Der standardmäßige Installationspfad für Windows Player lautet:

***C:\Users\&amp;lt;your user&gt;\AppData\Local\Programs\@aem-screensscreens-player-eleon\AEM Screens Player.exe***

Das Beispielskript in den Links aktiviert und deaktiviert die benutzerdefinierte Shell. Daher müssen Sie das Skript möglicherweise in zwei Zeilen unterteilen und die folgenden Zeilen aktivieren/deaktivieren:

>[!NOTE]
>
>In einigen Windows-Umgebungen sind die PowerShell-Skripten möglicherweise durch Richtlinien eingeschränkt (insbesondere nicht signierte Skripte). Um Ihr Skript auszuführen, müssen Sie diese Einschränkung vorübergehend deaktivieren und erneut aktivieren, um das Skript auszuführen. Öffnen Sie ein PowerShell-Fenster und verwenden Sie diese Befehle.
>
>*set-Executionpolicy unlimited* - zum vorübergehenden Entfernen von Einschränkungen
>
>*set-executePolicy eingeschränkt* - Beschränkung erneut aktivieren, nachdem das Skript ausgeführt wurde

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

