---
title: Dauer der Massenwiedergabe von Bildern auf Kanalebene
description: Erfahren Sie, wie Sie die Wiedergabedauer einer bestimmten Bildkomponente in AEM Screens bearbeiten können.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 95aa761a-1449-4e18-8115-3b151036dc54
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 45%

---

# Dauer der Massenwiedergabe von Bildern auf Kanalebene {#channel-level-bulk-image-playback-duration}

## Übersicht {#overview}

Wenn Sie einen Sequenzkanal erstellen und ihm Bilder hinzufügen, gehen standardmäßig alle Bilder von der in der Konfiguration auf Kanalebene definierten Wiedergabedauer aus. Jedes einzelne Bild kann jedoch den Standard überschreiben und eine andere Wiedergabedauer haben. Dies wird durch Bearbeiten der Wiedergabedauer der jeweiligen Bildkomponente erreicht.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktion beginnen, stellen Sie sicher, dass Sie ein Projekt als Voraussetzung für die Implementierung dieser Funktion eingerichtet haben. Zum Beispiel:

1. Erstellen eines AEM Screens-Projekts (in diesem Beispiel **ChannelLevelPlayback**).

1. Erstellen eines Sequenzkanals als **PlaybackChannel** im Ordner **Kanäle**.

1. Hinzufügen von Inhalten zum **PlaybackChannel**.

## Bearbeiten der Bildwiedergabedauer auf Kanalebene {#editing-channel-level-image-playback-duration-assignment}

Im folgenden Abschnitt erfahren Sie, wie Sie die Wiedergabedauer von Inhalten in einem AEM Screens-Kanal bearbeiten können.

### Aktualisieren der Wiedergabedauer für Bilder in einem Kanal {#updating-the-playback-duration-for-images-in-a-channel}

Gehen Sie wie folgt vor, um zu erfahren, wie Sie die Wiedergabedauer auf Kanalebene aktualisieren:

1. Navigieren Sie zum Sequenzkanal **PlaybackChannel**.

   ![screen_shot_2019-06-24at62818pm](assets/screen_shot_2019-06-24at62818pm.png)

1. Auswählen **Bearbeiten** in der Aktionsleiste aus.

   ![screen_shot_2019-06-24at70141pm](assets/screen_shot_2019-06-24at70141pm.png)

1. Fügen Sie im Kanaleditor zwei oder mehr Bilder hinzu, wie in der Abbildung unten gezeigt.

   ![screen_shot_2019-06-24at90534pm](assets/screen_shot_2019-06-24at90534pm.png)

1. Wählen Sie alle Bilder im Kanal aus und wählen Sie das Schraubenschlüsselsymbol oben links (wie in der Abbildung unten gezeigt), damit Sie das Dialogfeld &quot;Konfigurieren&quot;auf Kanalebene öffnen können.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. Die **Seite** wird geöffnet.

   >[!NOTE]
   >Standardmäßig sind die Bilder in einem Kanal auf eine Wiedergabedauer von 8 Sekunden eingestellt.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Bearbeiten Sie die **Dauer** von 8000 (Millisekunden) bis 3000 (Millisekunden), also 3 Sekunden. Markieren Sie das Häkchen oben rechts im **Seite** angezeigt, damit Sie Ihre Änderungen speichern können.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Anzeigen des Ergebnisses {#viewing-the-result}

Nachdem Sie die Dauer der Kanalwiedergabe (in diesem Beispiel alle drei Bilder) aktualisiert haben, beachten Sie, dass die Bilder jetzt für 3 Sekunden statt für 8 Sekunden wiedergegeben werden (Standardwert).

![channel_preview](assets/channel_preview.gif)
