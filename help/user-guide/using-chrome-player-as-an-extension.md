---
title: Verwenden von Chrome Player als Erweiterung
seo-title: Verwenden von Chrome Player als Erweiterung
description: 'null'
seo-description: 'null'
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Verwenden von Chrome Player als Erweiterung {#using-chrome-player}

Der ChromeOS-Player kann als Chrome-Browser-Plugin im Entwicklermodus installiert werden, ohne dass ein richtiges Chrome-Player-Gerät erforderlich ist.

>[!CAUTION]
>
> Die Verwendung des Chrome-Players als Erweiterung zur Fehlerbehebung wird für schnelle Demos, Debugging und auch zur Fehlerbehebung bei Kundenproblemen empfohlen. Dieser Mechanismus sollte nicht für Produktionsimplementierungen verwendet werden, die den Kiosk-Modus und die zentrale Verwaltung erfordern würden.

Auf dieser Seite erfahren Sie, wie Sie den Chrome-Player als Browsererweiterung installieren.

1. Klicken Sie hier, um den neuesten Chrome Player herunterzuladen.

1. Dekomprimieren Sie die Datei und speichern Sie sie auf der Festplatte.

1. Öffnen Sie den Chrome-Browser und klicken Sie auf das Menü mit 3 Punkten und wählen Sie **Mehr Tools** aus **Erweiterungen** , die sich oben rechts befinden, oder navigieren Sie direkt zu `chrome://extensions`.

1. Schalten Sie den **Entwicklermodus** oben rechts ein.

1. Klicken Sie auf "Entpackt **laden** "aus der oberen linken Ecke und laden Sie den entpackten Chrome Player.

1. Überprüfen Sie das AEM Screens Chrome Player-Plugin, wenn es in der Liste der Erweiterungen verfügbar ist.

1. Öffnen Sie eine neue Registerkarte und klicken Sie in der oberen linken Ecke auf das Symbol "Apps"oder navigieren Sie direkt zu `chrome://apps`.

1. Klicken Sie auf **AEM Screens Plugin** , um Chrome Player zu starten.
   >[!NOTE]
   >
   > Standardmäßig wird der Player im Vollbildmodus gestartet. Drücken Sie **esc** , um den Vollbildmodus zu beenden.


## Tipps zum erweiterten Debugging {#advanced-debugging-tips}

1. Sobald der Player Inhalte lokal heruntergeladen hat, können Sie lokal heruntergeladene Inhalte durchsuchen, indem Sie zu `http://localhost:24502`diesem navigieren.

   >[!NOTE]
   >
   > Wenn die oben genannte URL nicht funktioniert, bedeutet dies, dass dem Player keine Anzeige zugewiesen wurde oder der Inhalt nicht erfolgreich heruntergeladen wurde. Überprüfen Sie auf der Registerkarte Netzwerk, ob die Player-Konfiguration JSON die korrekten Details vom Player erhalten hat und ob Netzwerkprobleme beim Download auftreten.

1. Sie können mit der rechten Maustaste klicken und drei Ebenen des Chrome-Players überprüfen
   **Debuggen von Inhalten**: Klicken Sie mit der rechten Maustaste und überprüfen Sie den Inhalt, um den laufenden Inhalt zu debuggen (es sollte ein einzelnes Element namens "Inspect"im Kontextmenü geben)

   **Debug-Firmware**: Öffnen Sie die Admin-Benutzeroberfläche, klicken Sie mit der rechten Maustaste und überprüfen Sie den Firmware(Player)-Code (es sollte eine Option zum Überprüfen und Überprüfen der Hintergrundseite und zum Simulieren des Browser-Neustarts geben)

   **Debug-Hintergrundseite**: Rufen Sie die Admin-Benutzeroberfläche auf, klicken Sie mit der rechten Maustaste und überprüfen Sie die Hintergrundseite (für Hintergrunddienste wie HTTP-Server).

## Player-Erweiterung aktualisieren {#upgrading-player}

Gehen Sie wie folgt vor, um die Player-Erweiterung zu aktualisieren, wenn eine neue Version des Players veröffentlicht wird. Sie können auch die folgenden Anweisungen befolgen, um Aktualisierungsszenarien zu testen:

1. Schließen Sie alle laufenden Chrome- und Player-Instanzen
1. Alten Ordner mit Player-Dateien umbenennen
1. Extrahieren Sie die neue ZIP-Datei am selben Speicherort wie der alte Ordner
1. Starten Sie Chrome und navigieren Sie zu `chrome://extensions`
1. Markieren Sie das Player-Symbol und klicken Sie auf die Schaltfläche "Aktualisieren"oder "Neu laden".