---
title: Implementieren von Windows 10 Player
seo-title: Implementieren von Windows 10 Player
description: Auf dieser Seite erfahren Sie, wie Sie den Windows 10 Player für AEM Screens konfigurieren.
seo-description: Auf dieser Seite erfahren Sie, wie Sie den Windows 10 Player für AEM Screens konfigurieren.
uuid: da7e88bf-c251-481e-9029-f8fc4768b309
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 4228e8a1-9749-49a6-a1bb-365492bc2a3d
docset: aem65
translation-type: tm+mt
source-git-commit: 2ab8496cebb81864a8354ad5dcb8d72bc1e44c13
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 93%

---


# Implementieren von Windows 10 Player {#implementing-windows-player}

Dieser Abschnitt beschreibt, wie der Windows 10 Player für AEM Screens konfiguriert wird. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

## Installieren des Windows Players {#installing-windows-player}

Installieren Sie Windows Player für AEM Screens, um den Windows Player für AEM Screens zu implementieren.

Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

>[!NOTE]
>Es gibt keinen Fenstermodus im Windows-Player. Der Vollbildmodus ist immer aktiviert.

### Einrichten der Umgebung für AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Sie müssen eine Umgebung für Windows Player einrichten, wenn Sie AEM Screens 6.5.5 Service Pack verwenden.

Setzen Sie das **Attribut SameSite für die Cookies** login-token von **Lax** auf **None** aus **Adobe Experience Manager Web ConsoleConfiguration** in allen AEM Autor- und Veröffentlichungsinstanzen.

Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zu **Konfiguration der Adobe Experience Manager-Web-Konsole** über `http://localhost:4502/system/console/configMgr`.

1. Suchen Sie nach *Adobe Granite Token Authentication Handler*.

1. Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** von **Lax** auf **Keine** fest.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Klicken Sie auf **Speichern**.

### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-hoc-Methode können Sie den aktuellen Windows Player (*.exe*) installieren. Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:

1. Halten Sie die linke obere Ecke gedrückt, um den Admin-Bereich zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.
1. Navigieren Sie im linken Aktionsmenü zum Link **Geräteregistrierung******, um den Status des Prozesses zur Geräteregistrierung zu prüfen.

>[!NOTE]
>
>Wenn der **Status** **REGISTRIERT** ist, wird das Feld **Geräte-ID** ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

### Massen-Server-Konfiguration: Registrieren mehrerer Windows 10 Player mit einer Konfiguration {#bulk-server-configuration-registering-multiple-windows-players-with-one-configuration}

Nachdem Sie den Windows Player installiert haben, können Sie mehrere Player mit einer Konfiguration registrieren.

>[!NOTE]
>
>**Massenregistrierung von Windows Playern**
>
>Beim Implementieren von Windows-Playern müssen Sie nicht jeden einzelnen Player manuell konfigurieren. Stattdessen können Sie auch die getestete und zur Bereitstellung bereite JSON-Konfigurationsdatei aktualisieren.
>
>Die Konfiguration stellt sicher, dass alle Player denselben in der Konfigurationsdatei angegebenen Server anpingen. Trotzdem müssen Sie noch jeden einzelnen Player manuell registrieren.

So konfigurieren Sie den Windows 10-Player:

1. Installieren Sie Windows Player.
1. Suchen Sie die Konfigurationsdatei unter ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Aktualisieren Sie die JSON-Konfigurationsdatei mit den nachstehenden Informationen und kopieren Sie sie dann bei allen Systemen, auf denen der Player vorhanden ist, in den gleichen Ordner.

### Richtlinienattribute         {#policy-attributes}

In der folgenden Tabelle finden Sie eine Zusammenfassung der Richtlinienattribute mit einer beispielhaften JSON-Richtliniendatei als Referenz:

| **Richtlinienname** | **Zweck** |
|---|---|
| server | Die URL zum Adobe Experience Manager(AEM)-Server. |
| resolution | Die Auflösung des Geräts. |
| rebootSchedule | Der Plan zum Neustarten des Players. |
| enableAdminUI | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| enableActivityUI | Aktivierung zum Anzeigen des Fortschritts von Aktivitäten wie Downloads und Synchronisierungen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |

#### Beispielhafte JSON-Richtliniendatei         {#example-policy-json-file}

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

