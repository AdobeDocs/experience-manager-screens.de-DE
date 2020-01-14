---
title: Wiedergabedauer auf Projektebene
seo-title: Wiedergabedauer auf Projektebene
description: 'Mit dieser Funktion können Sie die Dauer der Bildwiedergabe auf Projektebene festlegen. '
seo-description: 'Mit dieser Funktion können Sie die Dauer der Bildwiedergabe auf Projektebene festlegen. '
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: ae1f7cab650f811ae03f0a2f3dfa49ec855997ee

---


# Wiedergabedauer auf Projektebene {#project-level-image-playback}

## Überblick {#overview}

Mit diesen Funktionen können Sie die Dauer der Bildwiedergabe auf Projektebene festlegen. Diese Wiedergabedauer wird standardmäßig von allen Bildern übernommen. Wenn keine Dauer auf Projektebene definiert ist, wird die Standardwiedergabe von 8 Sekunden fortgesetzt.

### Voraussetzungen {#prerequisites}

Bevor Sie diese Funktion verwenden, stellen Sie sicher, dass Sie ein Projekt als Voraussetzung für die Implementierung dieser Funktion einrichten. Beispiel:

1. Create an AEM Screens project (in this example, **ProjectLevelPlayback**)

1. Create a sequence channel as **PlayBackChannel** under **Channels** folder

1. Add content to **PlayBackChannel**

   ![Assets](assets/image_playback1.png)

   Die folgende Abbildung zeigt beispielsweise die Bilder, die dem **PlayBackChannel** -Editor hinzugefügt wurden:

   ![Assets](assets/image_playback2.png)

## Editing Project Level Image Playback Duration Assignment {#editing-project-level-image-playback-duration-assignment}

Im folgenden Abschnitt wird beschrieben, wie Sie die Wiedergabedauer von Inhalten in einem AEM Screens-Projekt bearbeiten.

### Aktualisieren der Wiedergabedauer für Bilder auf Projektebene {#updating-the-playback-duration-for-images-in-a-project}


>[!NOTE]
>Wenn Sie die Wiedergabedauer für ein Bild oder einen Kanal aktualisieren möchten, lesen Sie die Informationen unter [Kanalebene &quot;Wiedergabedauer](channel-level-image-playback.md)&quot;.

Gehen Sie wie folgt vor, um die Wiedergabedauer auf Projektebene zu aktualisieren:

1. Navigate to your project **ProjectLevelPlayback** and click **Properties** from the action bar.
   ![Assets](assets/image_playback3.png)

1. Wählen Sie alle Bilder im Kanal aus und klicken Sie auf das Schraubenschlüsselsymbol oben links (wie in der Abbildung unten gezeigt), um das Dialogfeld zum Konfigurieren auf Kanalebene zu öffnen.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. Das Dialogfeld **Seite** wird geöffnet.

   >[!NOTE]
   >
   >Standardmäßig sind die Bilder in einem Kanal auf eine Wiedergabedauer von 8 Sekunden eingestellt, und die Videos werden mit ihrer Standarddauer abgespielt.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Ändern Sie die **Dauer** von 8000 (ms) in 3000 (ms), d. h. 3 Sekunden. Klicken Sie auf das Häkchen oben rechts im Dialogfeld **Seite**, um Ihre Änderungen zu speichern.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Anzeigen des Ergebnisses {#viewing-the-result}

Nachdem Sie die Dauer der Kanalwiedergabe (in diesem Beispiel alle drei Bilder) aktualisiert haben, werden Sie feststellen, dass die Bilder jetzt für 3 Sekunden statt für 8 Sekunden (Standardwert) wiedergegeben werden.

![channel_preview](assets/channel_preview.gif)

