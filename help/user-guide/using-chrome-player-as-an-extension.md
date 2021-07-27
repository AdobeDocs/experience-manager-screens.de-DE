---
title: Verwenden von Chrome-Player als Erweiterung
seo-title: Verwenden von Chrome-Player als Erweiterung
description: Auf dieser Seite erfahren Sie, wie Sie den Chrome-Player als Browser-Erweiterung installieren.
seo-description: 'null'
feature: Verwalten von Screens
role: Admin
level: Intermediate
exl-id: 53d5bd81-0853-47b0-9798-01d8fd5612e6
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: ht
source-wordcount: '467'
ht-degree: 100%

---

# Verwenden von Chrome-Player als Erweiterung {#using-chrome-player}

Im Entwicklermodus kann der Chrome OS-Player als Chrome-Browser-Plug-in installiert werden, ohne dass ein echtes Chrome-Player-Gerät erforderlich ist.

>[!CAUTION]
>
> Eine Verwendung des Chrome-Players als Erweiterung zur Problembehebung wird für schnelle Demos, Debugging und auch zur Fehlerbehebung bei Kundenproblemen empfohlen. Dieses Verfahren sollte nicht für Produktionsimplementierungen verwendet werden, die den Kiosk-Modus und zentrale Verwaltung erfordern würden.

Auf dieser Seite erfahren Sie, wie Sie den Chrome-Player als Browser-Erweiterung installieren.

1. Klicken Sie [hier](https://download.macromedia.com/screens/), um den neuesten Chrome-Player herunterzuladen.

1. Entpacken Sie die Datei und speichern Sie sie auf der Festplatte.

1. Öffnen Sie den Chrome-Browser, klicken Sie oben rechts auf das Menü mit den 3 Punkten und wählen Sie **Weitere Tools** > **Erweiterungen** oder navigieren Sie direkt zu `chrome://extensions`.

1. Aktivieren Sie oben rechts den **Entwicklermodus**.

1. Klicken Sie oben links auf **Entpackte Erweiterung laden** und laden Sie den entpackten Chrome-Player.

1. Überprüfen Sie, ob in der Liste der Erweiterungen das Plug-in AEM Screens Chrome Player aufgeführt wird.

1. Öffnen Sie eine neue Registerkarte und klicken Sie oben links auf das Symbol „Apps“ oder navigieren Sie direkt zu `chrome://apps`.

1. Klicken Sie auf das Plug-in **AEM Screens**, um den Chrome-Player zu starten.
   >[!NOTE]
   >
   > Standardmäßig wird der Player im Vollbildmodus gestartet. Drücken Sie **Esc**, um den Vollbildmodus zu beenden.


## Tipps zum erweiterten Debugging {#advanced-debugging-tips}

1. Sobald der Player Inhalte lokal heruntergeladen hat, können Sie diese durchsuchen, indem Sie zu `http://localhost:24502` navigieren.

   >[!NOTE]
   >
   > Wenn die oben genannte URL nicht funktioniert, bedeutet dies, dass dem Player keine Anzeige zugewiesen bzw. der Inhalt nicht erfolgreich heruntergeladen wurde. Überprüfen Sie auf der Registerkarte „Netzwerk“ die Player-Konfigurations-JSON, um zu sehen, ob der Player die korrekten Details übermittelt hat oder beim Download Netzwerkprobleme aufgetreten sind.

1. Sie können mit der rechten Maustaste klicken und drei Ebenen des Chrome-Players überprüfen.
   **Inhalte debuggen**: Klicken Sie mit der rechten Maustaste und überprüfen Sie den Inhalt, um den laufenden Inhalt zu debuggen (es sollte im Kontextmenü ein einzelnes Element namens „Überprüfen“ geben).

   **Firmware debuggen**: Öffnen Sie die Administrator-Benutzeroberfläche, klicken Sie mit der rechten Maustaste und überprüfen Sie den Firmware (Player)-Code (es sollte eine Option zum Überprüfen der Hintergrundseite und Simulieren des Browser-Neustarts geben).

   **Hintergrundseite debuggen**: Rufen Sie die Administrator-Benutzeroberfläche auf, klicken Sie mit der rechten Maustaste und überprüfen Sie die Hintergrundseite (für Hintergrund-Services wie HTTP-Server).

## Aktualisieren der Player-Erweiterung {#upgrading-player}

Gehen Sie wie folgt vor, um die Player-Erweiterung zu aktualisieren, wenn eine neue Version des Players veröffentlicht wird. Sie können auch folgende Anweisungen ausführen, um Aktualisierungsszenarien zu testen:

1. Schließen Sie alle laufenden Chrome- und Player-Instanzen.
1. Benennen Sie den alten Ordner mit Player-Dateien um.
1. Extrahieren Sie die neue Zip-Datei am selben Speicherort, an dem sich der alte Ordner befindet.
1. Starten Sie Chrome und navigieren Sie zu `chrome://extensions`.
1. Aktivieren Sie das Player-Symbol und klicken Sie auf die Schaltfläche „Aktualisieren“ oder „Neu laden“.
