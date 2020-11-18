---
title: Zehn Player
description: Diese Seite beschreibt die Installation und die Arbeit von Tizen Player.
translation-type: tm+mt
source-git-commit: 8f8973c4fda8d40f919e199be3df15ba42f0a6c6
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 2%

---


# Implementieren von Zehn Player {#tizen-player}

## Tizen Player installieren {#installing-tizen-player}

Gehen Sie wie folgt vor, um Tizen Player für AEM Screens zu implementieren:

1. Navigieren Sie zur Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) , um den Tizen Player herunterzuladen.

1. Installieren Sie die ZIP-Datei (.zip) vom lokalen Computer.

## Einrichten des lokalen Servers und Extrahieren von ZIP-Dateien {#setting-local-server}

Gehen Sie wie folgt vor, um den lokalen Server einzurichten und die extrahierten Dateien zu kopieren:

1. Rufen Sie die IP-Adresse Ihres lokalen Computers ab.

   >[!NOTE]
   >Sie können die IP-Adresse vom Terminal Ihres Computers abrufen, indem Sie die folgenden Befehle eingeben:
   >* **Mac**: `ifconfig`
   >* **Windows**: `ipconfig`


1. Navigieren Sie im Terminal zum selben Ordner des entpackten Installationsordners und überprüfen Sie, ob der localhost funktioniert.

   >[!NOTE]
   >Geben Sie für **Mac** den gewünschten Wert ein `http://localhost` und überprüfen Sie, ob der `http` Server ausgeführt wird.

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

1. Kopieren Sie die beiden extrahierten Dateien `AEMScreensPlayer.wgt` und `sssp_config.xml` in `/Library/WebServer/Documents`.

### Konfigurieren von Updates auf dem Samsung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, um die Installation des AEM Screens Players auf dem Gerät abzuschließen:

1. Gehen Sie zu Ihrem Samsung-Gerät und zeigen Sie auf Ihren localhost-Server.
1. Wählen Sie **URL-Startereinstellungen** aus den **Einstellungen** und geben Sie die IP-Adresse des localhost-Servers ein.
1. Installieren Sie die Web-App.
1. Wählen Sie **Remote** aus dem **Entwicklermodus**.
1. Der AEM Screens Player sollte jetzt automatisch auf Ihrem Samsung-Gerät installiert werden.


