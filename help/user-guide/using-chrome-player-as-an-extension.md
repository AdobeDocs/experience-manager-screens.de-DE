---
title: Verwenden von Chrome-Player als Erweiterung
description: Erfahren Sie mehr über die Installation des Chrome-Players als Browsererweiterung für AEM Screens.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 53d5bd81-0853-47b0-9798-01d8fd5612e6
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 36%

---

# Verwenden von Chrome-Player als Erweiterung {#using-chrome-player}

Im Entwicklermodus kann der Chrome OS-Player als Chrome-Browser-Plug-in installiert werden, ohne dass ein echtes Chrome-Player-Gerät erforderlich ist.

>[!CAUTION]
>
> Eine Verwendung des Chrome-Players als Erweiterung zur Problembehebung wird für schnelle Demos, Debugging und auch zur Fehlerbehebung bei Kundenproblemen empfohlen. Verwenden Sie diesen Mechanismus nicht für Produktionsbereitstellungen, die den Kiosk-Modus und die zentrale Verwaltung erfordern würden.

Auf dieser Seite finden Sie Informationen zum Installieren des Chrome-Players als Browser-Erweiterung.

1. Auswählen [here](https://download.macromedia.com/screens/) , um den neuesten Chrome-Player herunterzuladen.

1. Entpacken Sie die Datei und speichern Sie sie auf der Festplatte.

1. Öffnen Sie den Chrome-Browser, wählen Sie das Menü mit den 3 Punkten aus und wählen Sie **Weitere Tools** von **Erweiterungen** oben rechts oder navigieren Sie direkt zu `chrome://extensions`.

1. Schalten Sie die **Entwickler** -Modus in der oberen rechten Ecke.

1. Auswählen **Entpacktes Laden** oben links und laden Sie den entpackten Chrome-Player.

1. Überprüfen Sie, ob das AEM Screens Chrome Player-Plug-in in der Liste der Erweiterungen verfügbar ist.

1. Öffnen Sie eine neue Registerkarte und wählen Sie oben links das Symbol Apps aus oder navigieren Sie direkt zu `chrome://apps`.

1. Auswählen **AEM Screens-Plugin** damit Sie den Chrome-Player starten können.

   >[!NOTE]
   >
   > Standardmäßig wird der Player im Vollbildmodus gestartet. Presse **Esc** , um den Vollbildmodus zu beenden.


## Tipps zum erweiterten Debugging {#advanced-debugging-tips}

1. Wenn der Player Inhalte lokal heruntergeladen hat, können Sie lokal heruntergeladene Inhalte durchsuchen, indem Sie `http://localhost:24502`.

   >[!NOTE]
   >
   > Wenn die oben genannte URL nicht funktioniert, bedeutet dies, dass dem Player keine Anzeige zugewiesen wird oder der Inhalt nicht erfolgreich heruntergeladen wurde. Überprüfen Sie auf der Registerkarte „Netzwerk“ die Player-Konfigurations-JSON, um zu sehen, ob der Player die korrekten Details übermittelt hat oder beim Download Netzwerkprobleme aufgetreten sind.

1. Klicken Sie mit der rechten Maustaste und überprüfen Sie drei Ebenen des Chrome-Players.
   **Inhalt debuggen**: Klicken Sie mit der rechten Maustaste und überprüfen Sie den Inhalt, um den laufenden Inhalt zu debuggen (im Kontextmenü sollte ein einzelnes Element namens &quot;Inspect&quot;vorhanden sein).

   **Firmware debuggen**: Rufen Sie die Administrator-Benutzeroberfläche auf, klicken Sie mit der rechten Maustaste darauf und überprüfen Sie, ob der Firmware(Player)-Code debuggt wird. (Es sollte eine Option zum Überprüfen und Überprüfen der Hintergrundseite und zum Simulieren des Neustart des Browsers geben.)

   **Debug-Hintergrundseite**: Rufen Sie die Administrator-Benutzeroberfläche auf, klicken Sie mit der rechten Maustaste darauf und überprüfen Sie die Hintergrundseite (für Hintergrunddienste wie HTTP-Server).

## Aktualisieren der Player-Erweiterung {#upgrading-player}

Gehen Sie wie folgt vor, um die Player-Erweiterung zu aktualisieren, wenn eine neue Version des Players veröffentlicht wird. Sie können auch folgende Anweisungen ausführen, um Aktualisierungsszenarien zu testen:

1. Schließen Sie alle laufenden Chrome- und Player-Instanzen.
1. Benennen Sie den alten Ordner mit Player-Dateien um.
1. Extrahieren Sie die neue Zip-Datei am selben Speicherort, an dem sich der alte Ordner befindet.
1. Starten Sie Chrome und navigieren Sie zu `chrome://extensions`.
1. Aktivieren Sie das Player-Symbol und wählen Sie die Schaltfläche &quot;Aktualisieren&quot;oder &quot;Neu laden&quot;
