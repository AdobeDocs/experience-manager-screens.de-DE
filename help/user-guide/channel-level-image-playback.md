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
TQID: https://experienceleague.adobe.com/6Cq6n8lfTfRC685rE4jWmnAQDPLsDJ4ptNTNjt-qmHc
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2: id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 0b0bfcd803c3da9298122200a0a1715fc2d5e49c
workflow-type: tm+mt
source-wordcount: 341
ht-degree: 100%

---

# Dauer der Massenwiedergabe von Bildern auf Kanalebene {#channel-level-bulk-image-playback-duration}

## Überblick {#overview}

Wenn Sie einen Sequenzkanal erstellen und Bilder hinzufügen, gilt für alle Bilder standardmäßig die in der Konfiguration auf Kanalebene definierte Wiedergabedauer. Jedes einzelne Bild kann den Standard weiterhin überschreiben und eine andere Wiedergabedauer aufweisen. Dies wird durch Bearbeiten der Wiedergabedauer der jeweiligen Bildkomponente erreicht.

### Voraussetzungen {#prerequisites}

Bevor Sie diese Funktionalität implementieren, vergewissern Sie sich, dass Sie ein Projekt eingerichtet haben. Dies ist die Voraussetzung für die Implementierung dieser Funktionalität. Zum Beispiel:

1. Erstellen eines AEM Screens-Projekts (in diesem Beispiel **ChannelLevelPlayback**).

1. Erstellen Sie einen Sequenzkanal als **PlaybackChannel** im Ordner **Kanäle**.

1. Hinzufügen von Inhalten zum **PlaybackChannel**.

## Bearbeiten der Bildwiedergabedauer auf Kanalebene {#editing-channel-level-image-playback-duration-assignment}

Im folgenden Abschnitt wird beschrieben, wie Sie die Wiedergabedauer von Inhalten in einem AEM Screens-Kanal bearbeiten können.

### Aktualisieren der Wiedergabedauer für Bilder in einem Kanal {#updating-the-playback-duration-for-images-in-a-channel}

Gehen Sie wie folgt vor, um zu erfahren, wie Sie die Wiedergabedauer auf Kanalebene aktualisieren:

1. Navigieren Sie zum Sequenzkanal **PlaybackChannel**.

   ![screen_shot_2019-06-24at62818pm](assets/screen_shot_2019-06-24at62818pm.png)

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   ![screen_shot_2019-06-24at70141pm](assets/screen_shot_2019-06-24at70141pm.png)

1. Fügen Sie im Kanaleditor zwei oder mehr Bilder hinzu, wie in der Abbildung unten gezeigt.

   ![screen_shot_2019-06-24at90534pm](assets/screen_shot_2019-06-24at90534pm.png)

1. Klicken Sie auf alle Bilder im Kanal und dann auf das Schraubenschlüsselsymbol oben links (wie in der Abbildung unten gezeigt), um das Dialogfeld zum Konfigurieren auf Kanalebene zu öffnen.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. Das Dialogfeld **Seite** wird geöffnet.

   >[!NOTE]
   >Standardmäßig sind die Bilder in einem Kanal auf eine Wiedergabedauer von 8 Sekunden eingestellt.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Ändern Sie die **Dauer** von 8000 (Millisekunden) in 3000 (Millisekunden), d. h. 3 Sekunden. Klicken Sie auf das Häkchen oben rechts im Dialogfeld **Seite**, um Ihre Änderungen zu speichern.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Anzeigen des Ergebnisses {#viewing-the-result}

Nachdem Sie die Dauer der Kanalwiedergabe (in diesem Beispiel alle drei Bilder) aktualisiert haben, werden Sie feststellen, dass die Bilder nun jeweils 3 Sekunden lang statt 8 Sekunden (Standardwert) wiedergegeben werden.

![channel_preview](assets/channel_preview.gif)
