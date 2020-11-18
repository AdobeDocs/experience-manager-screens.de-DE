---
title: Zehn Player
description: Diese Seite beschreibt die Installation und die Arbeit von Tizen Player.
translation-type: tm+mt
source-git-commit: b3209d1dcce6defff347f288c704a1e7ea075ecf
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 1%

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
   >Bitte lesen Sie die offizielle Dokumentation, um zu erfahren, wie Sie den lokalen Server auf Ihrer Plattform aktivieren.

1. Navigieren Sie im Terminal zum selben Ordner des entpackten Installationsordners und überprüfen Sie, ob der localhost funktioniert.

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

1. Kopieren Sie die beiden extrahierten Dateien, z. B. `AEMScreensPlayer.wgt` und `sssp_config.xml` in den Stammordner Ihres lokalen Servers.

### Konfigurieren von Updates auf dem Samsung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, um die Installation des AEM Screens Players auf dem Gerät abzuschließen:

1. Gehen Sie zu Ihrem Samsung-Gerät.

1. Klicken Sie auf die Schaltfläche &quot; **Start** &quot;über die Remote-Verbindung des Geräts und wählen Sie &quot; **URL-Startereinstellungen&quot;**.

1. Geben Sie die IP-Adresse Ihres localhost-Servers ein.

1. Wählen Sie **Remote** aus dem **Entwicklermodus**.

1. Klicken Sie auf die Schaltfläche &quot; **Start** &quot;in der Fernbedienung des Geräts und wählen Sie &quot; **URL-Starter**&quot;aus.

1. Der AEM Screens Player sollte jetzt automatisch auf Ihrem Samsung-Gerät installiert und gestartet werden.



