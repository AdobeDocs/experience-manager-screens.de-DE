---
title: Tizen-Player
description: Auf dieser Seite wird die Installation und Funktionsweise des Tizen-Players beschrieben.
translation-type: ht
source-git-commit: b3209d1dcce6defff347f288c704a1e7ea075ecf
workflow-type: ht
source-wordcount: '230'
ht-degree: 100%

---


# Implementieren des Tizen-Players {#tizen-player}

## Installieren des Tizen-Players {#installing-tizen-player}

Gehen Sie wie folgt vor, um den Tizen-Player für AEM Screens zu implementieren:

1. Navigieren Sie zur Seite [**AEM 6.5-Player-Downloads**](https://download.macromedia.com/screens/), um den Tizen-Player herunterzuladen.

1. Installieren Sie die Tizen-Player-Datei (.zip) vom lokalen Gerät.

## Einrichten des lokalen Servers und Extrahieren der ZIP-Dateien {#setting-local-server}

Gehen Sie wie folgt vor, um den lokalen Server einzurichten und die extrahierten Dateien zu kopieren:

1. Rufen Sie die IP-Adresse Ihres lokalen Geräts ab.
   >[!NOTE]
   >In der offiziellen Dokumentation erfahren Sie, wie Sie den lokalen Server auf Ihrer Plattform aktivieren.

1. Navigieren Sie vom Terminal zum selben Verzeichnis des entpackten Installationsordners und überprüfen Sie, ob der lokale Host funktioniert.

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

1. Kopieren Sie die beiden extrahierten Dateien wie `AEMScreensPlayer.wgt` und `sssp_config.xml` in das Stammverzeichnis Ihres lokalen Servers.

### Konfigurieren von Aktualisierungen auf dem Samsung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, um die Installation des AEM Screens-Players auf dem Gerät abzuschließen:

1. Gehen Sie zum Samsung-Gerät.

1. Klicken Sie mit der Fernbedienung des Geräts auf die Schaltfläche **Home** und wählen Sie **URL-Startereinstellungen** aus.

1. Geben Sie die IP-Adresse Ihres localhost-Servers ein.

1. Wählen Sie **Remote** im **Entwicklermodus** aus.

1. Klicken Sie auf der Fernbedienung des Geräts auf die Schaltfläche **Home** und wählen Sie **URL-Starter** aus.

1. Der AEM Screens-Player sollte jetzt automatisch auf Ihrem Samsung-Gerät installiert und gestartet werden.



