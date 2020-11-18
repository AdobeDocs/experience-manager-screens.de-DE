---
title: Zehn Player
description: Diese Seite beschreibt die Installation und die Arbeit von Tizen Player.
translation-type: tm+mt
source-git-commit: baefade9fa013bc77ed1f112d0ad2098c992dde5
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 1%

---


# Implementieren von Zehn Player {#tizen-player}

## Tizen Player installieren {#installing-tizen-player}

Gehen Sie wie folgt vor, um Tizen Player für AEM Screens zu implementieren:

1. Navigieren Sie zur Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) , um den Tizen Player herunterzuladen.

1. Installieren Sie die ZIP-Datei (.zip) vom lokalen Computer.

1. Rufen Sie die IP-Adresse Ihres lokalen Computers ab.

   >[!NOTE]
   >Geben Sie im Terminal Ihres Computers die folgenden Befehle ein:
   >**Mac** verwenden, Befehl `ifconfig`
   >**Windows**, Befehl verwenden `ipconfig`

1. Navigieren Sie im Terminal zum selben Ordner des entpackten Installationsordners und überprüfen Sie, ob der localhost funktioniert.

   >[!NOTE]
   >Geben Sie für **Mac** den gewünschten Wert ein `http://localhost` und überprüfen Sie, ob der `http` Server ausgeführt wird.

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

1. Kopieren Sie die beiden extrahierten Dateien `AEMScreensPlayer.wgt` und `sssp_config.xml` in `/Library/WebServer/Documents`.

### Konfigurationsaktualisierungen auf dem SamSung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, um die Installation des AEM Screens Players auf dem Gerät abzuschließen:

1. Klicken Sie im Samsung Remote auf die Schaltfläche **Start** .
1. Wählen Sie **URL-Starter** aus den **Einstellungen**.
1. Wählen Sie **Remote** im Entwicklermodus.
1. Installieren Sie die Web-App und geben Sie die IP-Adresse Ihres Computers ein.
Der AEM Screens Player sollte automatisch auf Samsung installiert werden.


