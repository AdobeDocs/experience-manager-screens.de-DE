---
title: Verwenden des Chrome-Players als Erweiterung
description: Erfahren Sie mehr über die Installation des Chrome-Players als Browser-Erweiterung für AEM Screens.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 53d5bd81-0853-47b0-9798-01d8fd5612e6
TQID: https://experienceleague.adobe.com/ehBNwOmhu7ygOMHsEiD8DeGBEDFB0Asv7p8HVDteb8I
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 510
ht-degree: 90%

---

# Verwenden des Chrome-Players als Erweiterung {#using-chrome-player}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Im Entwicklermodus kann der ChromeOS-Player als Plug-in des Chrome-Browsers installiert werden, ohne dass ein echtes Chrome-Player-Gerät erforderlich ist.

>[!CAUTION]
>
> Eine Verwendung des Chrome-Players als Erweiterung zur Problembehebung wird für schnelle Demos, zum Debugging und auch zur Fehlerbehebung bei Kundenproblemen empfohlen. Verwenden Sie diesen Mechanismus nicht für Produktionsbereitstellungen, die den Kiosk-Modus und zentrale Verwaltung erfordern würden.

Auf dieser Seite finden Sie Informationen zur Installation des Chrome-Players als Browser-Erweiterung.

1. Klicken Sie [hier](https://download.macromedia.com/screens/), um den neuesten Chrome-Player herunterzuladen.

1. Entpacken Sie die Datei und speichern Sie sie auf der Festplatte.

1. Öffnen Sie den Chrome-Browser, klicken Sie oben rechts auf das Symbol mit den drei Punkten und wählen Sie **Weitere Tools** bzw. **Erweiterungen** oder navigieren Sie direkt zu `chrome://extensions`.

1. Aktivieren Sie den **Entwicklermodus** in der rechten oberen Ecke.

1. Klicken Sie oben links auf **Entpackte Erweiterung laden** und laden Sie den entpackten Chrome-Player.

1. Überprüfen Sie, ob in der Liste der Erweiterungen das Plug-in „AEM Screens Chrome Player“ aufgeführt wird.

1. Öffnen Sie eine neue Registerkarte und klicken Sie oben links auf das Symbol „Apps“ oder navigieren Sie direkt zu `chrome://apps`.

1. Klicken Sie auf das **AEM Screens-Plug-in**, damit Sie den Chrome-Player starten können.

   >[!NOTE]
   >
   > Standardmäßig wird der Player im Vollbildmodus gestartet. Drücken Sie **Esc**, um den Vollbildmodus zu beenden.


## Tipps zum erweiterten Debugging {#advanced-debugging-tips}

1. Sobald der Player Inhalte lokal heruntergeladen hat, können Sie diese durchsuchen, indem Sie zu `http://localhost:24502` navigieren.

   >[!NOTE]
   >
   > Wenn die oben genannte URL nicht funktioniert, bedeutet dies, dass dem Player keine Anzeige zugewiesen bzw. der Inhalt nicht erfolgreich heruntergeladen wurde. Überprüfen Sie auf der Registerkarte „Netzwerk“ die JSON der Player-Konfiguration, um zu sehen, ob der Player die korrekten Details empfängt oder ob beim Download Netzwerkprobleme aufgetreten sind.

1. Klicken Sie mit der rechten Maustaste und untersuchen Sie drei Ebenen des Chrome-Players.
   **Inhalte debuggen**: Klicken Sie mit der rechten Maustaste und überprüfen Sie den Inhalt, um den laufenden Inhalt zu debuggen (es sollte im Kontextmenü ein einzelnes Element namens „Inspizieren“ geben).

   **Firmware debuggen**: Rufen Sie die Administrator-Benutzeroberfläche auf, klicken Sie mit der rechten Maustaste darauf und überprüfen Sie, ob der Firmware-(Player)-Code das Debugging durchführt. (Es sollte eine Option geben, um die Hintergrundseite zu inspizieren und einen Neustart des Browsers zu simulieren).

   **Hintergrundseite debuggen**: Rufen Sie die Administrator-Benutzeroberfläche auf, klicken Sie mit der rechten Maustaste und überprüfen Sie die Hintergrundseite (für Hintergrunddienste wie HTTP-Server).

## Aktualisieren der Player-Erweiterung {#upgrading-player}

Gehen Sie wie folgt vor, um die Player-Erweiterung zu aktualisieren, wenn eine neue Version des Players veröffentlicht wird. Sie können auch folgende Anweisungen ausführen, um Aktualisierungsszenarien zu testen:

1. Schließen Sie alle laufenden Chrome- und Player-Instanzen.
1. Benennen Sie den alten Ordner mit Player-Dateien um.
1. Extrahieren Sie die neue Zip-Datei am selben Speicherort, an dem sich der alte Ordner befindet.
1. Starten Sie Chrome und navigieren Sie zu `chrome://extensions`.
1. Aktivieren Sie das Player-Symbol und klicken Sie auf die Schaltfläche „Aktualisieren“ oder „Neu laden“.

