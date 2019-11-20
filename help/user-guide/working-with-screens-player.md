---
title: Arbeiten mit AEM Screens Player
seo-title: Arbeiten mit dem Player für AEM Screens
description: Auf dieser Seite erhalten Sie Informationen zum Player für AEM Screens. Hier werden auch die Administrator-Benutzeroberfläche und der Kanalschalter erklärt.
seo-description: Auf dieser Seite erhalten Sie Informationen zum Player für AEM Screens. Hier werden auch die Administrator-Benutzeroberfläche und der Kanalschalter erklärt.
uuid: 93e113ea-fbef-4757-982b-b7dc52fc76a7
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 4ad51b5e-c628-4440-9f2e-41d17cb10bc3
translation-type: tm+mt
source-git-commit: 428e1dbaa1a252d2aa9bcbb02264a0076b95291b

---


# Working with AEM Screens Player {#working-with-aem-screens-player}

Sie können den Kanalinhalt und andere Einstellungen im AEM Screens Player verwalten.

>[!NOTE]
>
>Drücken Sie ***Ctrl + Befehl + F**, um den Vollbildmodus für Player für AEM Screens unter OS X zu beenden.*

Wenn Sie einen Kanal einer Anzeige zuweisen, wird im Player für AEM Screens der Inhalt angezeigt. Sie können die Einstellungen für den Player über die Voreinstellungen für die Administrator-Benutzeroberfläche (im Dashboard) oder im Player selbst konfigurieren.

## Verwenden des Geräte-Dashboards {#using-the-device-dashboard}

Sie können die Voreinstellungen für Ihr Gerät im Geräte-Dashboard konfigurieren, auf das Sie über Ihre AEM-Autoreninstanz zugreifen können.

1. Navigate to the device dashboard from your project, for example, ***Test Project*** --&gt; ***Devices***.

   Select **Devices** and **Device Manager** from the action bar.

   ![chlimage_1-66](assets/chlimage_1-66.png)

1. Klicken Sie auf das Gerät, um das Geräte-Dashboard zu öffnen.

   ![chlimage_1-67](assets/chlimage_1-67.png)

1. Check the **PREFERENCES** panel. You can enable/disable the **Admin UI** and **Channel Switcher** for your player from these two options.

   ![chlimage_1-68](assets/chlimage_1-68.png)

### Die Administrator-Benutzeroberfläche {#the-admin-ui}

Enabling the **Admin UI** from the preferences panel allows the user to open the admin settings from the Screens Player. Wenn Sie diese Option im Geräte-Dashboard deaktivieren, kann der Benutzer die Administrator-Benutzeroberfläche nicht im Player öffnen.

Um die Administrator-Benutzeroberfläche vom Screens-Player aus zu öffnen, halten Sie die linke obere Ecke gedrückt, um das Menü „Admin“ auf Ihrem Touch-optimierten Player zu öffnen, oder verwenden Sie eine Maus. Nachdem die Registrierung abgeschlossen ist und die Kanäle geladen sind, werden Informationen angezeigt.

>[!NOTE]
>
>Sie können jetzt die Betriebszeit der App für den Player für AEM Screens aufrufen, um ihren Zustand zu überprüfen.

![chlimage_1-3](assets/chlimage_1-3.gif)

Wenn Sie im Seitenmenü die Option " **Konfiguration** "auswählen, können Sie auch **Firmware**, **Voreinstellungen** oder **To Factory** zurücksetzen.

Darüber hinaus können Sie die Anzahl der maximalen Protokolldateien angeben, die für einen AEM Screens-Player in **Max. der zu speichernden** Protokolldateien. Weitere Informationen finden Sie im Screenshot unten.

>[!NOTE]
>
>Die Option "Firmware **aktualisieren** "funktioniert nur auf der Cordova-Konsole, z. B. Android-Playern.

![screen_shot_2018-10-15at101257am](assets/screen_shot_2018-10-15at101257am.png)

>[!NOTE]
>
>Es wird empfohlen, die **Admin-Benutzeroberfläche** in Produktionsbereitstellungen zu deaktivieren.

Sie können den Cache für Kanäle und Anwendungen über die Administrator-Benutzeroberfläche im Player für AEM Screens löschen.

Wählen Sie **Inhaltscache** in der Seitenleiste, um den Cache zu aktualisieren.

![screen_shot_2018-10-15at105717am](assets/screen_shot_2018-10-15at105717am.png)

### Der Kanalschalter {#the-channel-switcher}

Enabling the **Channel Switcher** from the preferences panel allows the user to open the channel selection/settings from the Screens Player.

Wenn Sie diese Option im Geräte-Dashboard deaktivieren, kann der Benutzer die Kanal-Voreinstellungen nicht vom Screens-Player aus steuern.

Sie können im Screens-Player die Einstellungen für Ihren Kanal wechseln und steuern.

Um den Kanalschalter vom Player aus aufzurufen, halten Sie die untere linke Ecke gedrückt, um den Kanalschalter zu öffnen. Dort können Sie Kanäle wechseln und auf sonstige Funktionen zugreifen.

![chlimage_1-69](assets/chlimage_1-69.png)

>[!NOTE]
>
>Sie können auch vom Screens-Player für AEM Screens aus das Menü „Admin“ und den Kanalschalter für den Player aktivieren oder deaktivieren.
>
>(Siehe *Ändern der Voreinstellungen im Player für AEM Screens* wie im Abschnitt weiter unten beschrieben).

### Verwalten von Voreinstellungen im Player für AEM Screens {#managing-preferences-from-the-aem-screens-player}

Sie können die Einstellungen für die Administrator-Benutzeroberfläche und den Kanalschalter auch im Player selbst ändern.

Führen Sie folgende Schritte aus, um die Voreinstellungen im Player zu ändern:

1. Halten Sie die linke obere Ecke im inaktiven Kanal gedrückt, um das Administratorfenster zu öffnen.
1. Navigate to **Configuration** from the left action menu.
1. Enable/disable configuration for **Admin UI** or **Channel Switcher**.

![screen_shot_2018-10-15at101257am-1](assets/screen_shot_2018-10-15at101257am-1.png)

## Fehlerbehebung beim Player für AEM Screens {#troubleshooting-aem-screens-player}

Im Folgenden finden Sie empfohlene Maßnahmen bei Problemen mit dem Player für AEM Screens (Hard- und Software):

| **Probleme** | **Empfehlungen** |
|---|---|
| Player-Speicher ist voll | Beseitigung unnötiger Dateien |
| Player hat Netzwerk verloren | Verwenden Sie das Cat-5/Cat-6-Kabel. Bei WLAN-Verbindung müssen Sie den Abstand zwischen Router und Player verringern |
| AEM Screens Player abgestürzt | Es wird empfohlen, eine Watchdog-App zu verwenden, die sicherstellt, dass AEM Screens Player immer ausgeführt wird |
| Einstellungen für AEM Screens Player verloren | Verbindung zum AEM-Server überprüfen |
| AEM Screens Player startet nicht automatisch nach Neustart/Neustart des Players | Überprüfen des Startordners oder Initialisierungsverfahrens für das Betriebssystem |
| AEM Screens Player zeigt falschen/alten Inhalt an | Netzwerkverbindung überprüfen |

### Updates für Player für AEM Screens {#updates-for-aem-screens-player}

Für Player für AEM Screens gibt es zwei Arten von Updates:

| **Methode** | **Details** | **via Remote** | **Automatisiert** | **0 Ausfallzeit** |
|---|---|---|---|---|
| Firmware-Update | Wird über Remote-Befehl auf vorhandene installierte Player angewendet. Nach der Aktualisierung wird der Player mit dem vorhandenen Inhalt automatisch neu geladen. | Ja | Benutzerdefinierter | Fast - 1-3 Sekunden |
| Player-Shell-Aktualisierungen | Dies ist eine neue ausführbare Datei, die auf dem Player bereitgestellt werden soll. Dazu müssen neue Binärdaten remote auf den Player kopiert, der aktuelle Player angehalten und die neue Version gestartet werden. Die vorab geladenen Pakete müssen möglicherweise erneut heruntergeladen werden. | Ja (über Remote-Shell) | Benutzerdefinierter | Nein |

## Richtlinien zur Hardwareauswahl für das Player-Gerät {#hardware-selection-guidelines-for-player-device}

Der folgende Abschnitt enthält die Richtlinien zur Hardwareauswahl für ein Screens-Projekt:

* Immer Komponenten der ***kommerziellen*** oder ***industriellen*** Bewertung für PC-Player und Display-Panel oder Projektor beziehen.

* Interagieren Sie immer mit Anbietern, die den Markt für digitale Schilder bedienen.
* Berücksichtigen Sie immer Umgebungsfaktoren wie Umgebungstemperatur und relative Luftfeuchtigkeit.
* Überprüfen Sie stets die Stromanforderungen und die Energieversorgung.
* Überprüfen Sie sorgfältig die für die Anwendung erforderlichen Leistungsanforderungen und E/A-Anschlüsse.

In der folgenden Tabelle sind die Hardwarekonfigurationen mit typischen Anwendungsfällen für ein AEM Screens-Projekt zusammengefasst:

<table>
 <tbody>
  <tr>
   <td>Player-Konfiguration</td>
   <td>Prozessor</td>
   <td>Memory</td>
   <td>Speicher-SSD</td>
   <td>GPU</td>
   <td>Anzeige</td>
   <td>I/O</td>
   <td>Typische Anwendungsfälle</td>
  </tr>
  <tr>
   <td>Einfach</td>
   <td>Dualcore, i3 oder Quad-Core mit Intel® Atom Prozessor</td>
   <td><p>4 GB Speicher</p> <p>2 MB Cache</p> </td>
   <td><p>・ChromeOS 32 GB</p> <p>・Windows 128 GB</p> </td>
   <td>OnBoard</td>
   <td>1920 x 1080</td>
   <td>DVI,<br /> Ethernet/Wireless,<br /> 2x USB</td>
   <td>
    <ul>
     <li>Standardschleife im Vollbildmodus<br /> </li>
     <li>Tagesaufteilung</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Standard</td>
   <td>Quadcore, Intel® Core i5 Prozessor</td>
   <td><p>8 GB Speicher</p> <p>4 MB Cache</p> </td>
   <td>128 GBB</td>
   <td>OnBoard</td>
   <td>3840 x 2160 (4 K)</td>
   <td>DVI, HDMI<br /> Ethernet/Wireless,<br /> 2x USB</td>
   <td>
    <ul>
     <li>Dynamischer Inhalt einer Quelle</li>
     <li>Einfach interaktiv</li>
     <li>1-3 Zonenlayouts</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Erweitert</td>
   <td>Quadcore mit Hyperthreading, Intel® Core i7 Prozessor</td>
   <td><p>16 GB Speicher</p> <p>8 MB Cache</p> </td>
   <td>256 GB</td>
   <td>GPU für dedizierte Grafiken</td>
   <td>3840 x 2160 (4 K)</td>
   <td>DVI, HDMI<br /> -Ethernet/Wireless,<br /> 4xUSB</td>
   <td>
    <ul>
     <li>4 oder mehr Inhaltszonen, gleichzeitige Videowiedergabe</li>
     <li>Interaktiv auf mehreren Seiten</li>
     <li>Multi-Source-Datenauslöser</li>
    </ul> </td>
  </tr>
 </tbody>
</table>
