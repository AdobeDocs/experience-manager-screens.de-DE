---
title: Erstellen eines Arbeitsablaufs zum Hinzufügen von Videos
seo-title: Erstellen eines Arbeitsablaufs zum Hinzufügen von Videos
description: Auf dieser Seite erfahren Sie, wie Sie im Workflow für Ihre Assets eine Videofüllung erstellen.
seo-description: Auf dieser Seite erfahren Sie, wie Sie im Workflow für Ihre Assets eine Videofüllung erstellen.
uuid: c0f004ca-c934-47f8-bcdc-da58ea62118e
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: a90e3950-c95a-4aff-8cb3-9229c660a815
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Erstellen eines Arbeitsablaufs zum Hinzufügen von Videos {#creating-a-video-padding-workflow}

Dieser Abschnitt behandelt die folgenden Themen:

* **Überblick**
* **Voraussetzungen**
* **Erstellen eines Arbeitsablaufs zum Hinzufügen von Videos**
   * **Erstellen eines Workflows**
   * **Verwenden des Workflows im AEM Screens-Projekt**

* **Überprüfen der Ausgabe für den Workflow**

## Überblick {#overview}

Im folgenden Anwendungsfall wird ein Video platziert (Beispiel: 1280 x 720) in einem Kanal, in dem die Anzeige 1920 x 1080 ist und das Video bei 0 x 0 platziert wird (oben links). Das Video sollte in keiner Weise gestreckt oder modifiziert werden und **Deckblatt** in der Videokomponente nicht verwenden.

Das Video wird als Objekt von Pixel 1 bis Pixel 1280 über und von Pixel 1 bis Pixel 720 nach unten angezeigt und der Rest des Kanals ist Standardfarbe.

## Voraussetzungen {#prerequisites}

Bevor Sie einen Workflow für Videos erstellen, müssen Sie die folgenden Voraussetzungen erfüllen:

1. Hochladen eines Videos im Ordner " **Assets** "in Ihrer AEM-Instanz
1. Erstellen Sie ein AEM Screens-Projekt (z. B. **TestVideoRendering**) und einen Kanal mit dem Namen (**VideoRendering**), wie in der folgenden Abbildung dargestellt:

![screen_shot_2018-10-17at85307pm](assets/screen_shot_2018-10-17at85307pm.png)

## Erstellen eines Arbeitsablaufs zum Hinzufügen von Videos {#creating-a-video-padding-workflow-1}

Zum Erstellen eines Arbeitsablaufs für die Videoverfüllung müssen Sie einen Arbeitsablauf für Ihr Video erstellen und dann im AEM Screens-Projektkanal dasselbe verwenden.

Gehen Sie wie folgt vor, um den Workflow zu erstellen und zu verwenden:

1. Erstellen eines Workflows
1. Verwenden des Workflows in einem AEM Screens-Projekt

### Creating a Workflow {#creating-a-workflow}

Gehen Sie wie folgt vor, um einen Workflow für Ihr Video zu erstellen:

1. Navigieren Sie zu Ihrer AEM-Instanz und klicken Sie in der Seitenleiste auf Werkzeuge. Wählen Sie **Workflow** -&gt; **Modelle** , um ein neues Modell zu erstellen.

   ![screen_shot_2018-10-17at90025pm](assets/screen_shot_2018-10-17at90025pm.png)

1. Klicken Sie auf **Modelle** —&gt; **Erstellen** —&gt; Modell **erstellen**. Geben Sie den **Titel** (als **VideoRendition**) und den **Namen** im **Add Workflow Model** ein. Klicken Sie auf **Fertig** , um das Workflow-Modell hinzuzufügen.

   ![screen_shot_2018-10-17at90747pm](assets/screen_shot_2018-10-17at90747pm.png)

1. Nachdem Sie das Workflow-Modell erstellt haben, wählen Sie das Modell (**VideoRendition**) und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   ![screen_shot_2018-10-17at91256pm](assets/screen_shot_2018-10-17at91256pm.png)

1. Ziehen Sie die Komponente **Befehlszeile **in Ihren Workflow.

   ![screen_shot_2018-10-22at14846pm](assets/screen_shot_2018-10-22at14846pm.png)

1. Wählen Sie die Komponente **Befehlszeile** aus und öffnen Sie das Dialogfeld Eigenschaften.

   ![screen_shot_2018-10-17at95752pm](assets/screen_shot_2018-10-17at95752pm.png)

1. Wählen Sie die Registerkarte **Argumente** aus, um die Felder im Dialogfeld **Befehlszeile - Schritt-Eigenschaften** einzugeben.

   Geben Sie das Format in den **Mime-Typen** (als ***Video/MP4***) und den Befehl als (***/usr/local/Cellar/ffmpeg -i ${filename} -vf "pad=1920:height=1080:x=0:y=0:color=black" cq5dam.video.fullhd-hd ein. p.mp4***), um den Workflow im Feld " **Befehle** "zu starten.

   Einzelheiten zu **Mime-Typen** und - **Befehlen** finden Sie in der unten stehenden Anmerkung.

   ![screen_shot_2018-10-18at105300am](assets/screen_shot_2018-10-18at105300am.png)

1. Wählen Sie den Workflow (**VideoRenditions**) aus und klicken Sie in der Aktionsleiste auf "Workflow **starten** ", um das Dialogfeld "Arbeitsablauf **ausführen** "zu öffnen.

   ![screen_shot_2018-10-18at105335am](assets/screen_shot_2018-10-18at105335am.png)

1. Wählen Sie den Pfad Ihres Assets in der **Payload** aus (als ***/content/dam/huseinpeyda-cross01_512kb 2.mp4***) und geben Sie den **Title ** (als ***RunVideo***) ein und klicken Sie auf **Ausführen**.

   ![screen_shot_2018-10-18at112043am](assets/screen_shot_2018-10-18at112043am.png)

### Verwenden des Workflows in einem AEM Screens-Projekt {#using-the-workflow-in-an-aem-screens-project}

Gehen Sie wie folgt vor, um den Workflow in Ihrem AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zu einem AEM Screens-Projekt (**TestVideoRendition** —&gt; **Kanäle** —&gt;**VideoRendition**).

   ![screen_shot_2018-10-17at100715pm](assets/screen_shot_2018-10-17at100715pm.png)

1. Click **Edit** from the action bar. Ziehen Sie das Video, das Sie ursprünglich in **Assets** hochgeladen haben, per Drag &amp; Drop.

   ![screen_shot_2018-10-17at102806pm](assets/screen_shot_2018-10-17at102806pm.png)

1. Nachdem Sie das Video hochgeladen haben, klicken Sie auf **Vorschau** , um die Ausgabe anzuzeigen.

   ![screen_shot_2018-10-22at15151pm](assets/screen_shot_2018-10-22at15151pm.png)

## Überprüfen der Ausgabe für den Workflow {#validating-the-output-for-the-workflow}

Sie können Ihre Ausgabe wie folgt validieren:

* Vorschau des Videos im Kanal überprüfen
* Navigieren Sie zum Ordner ***/content/dam/testvideo.mp4/jcr:content/renditions/cq5dam.video.fullhd-hp.mp4*** in CRXDE Lite, wie in der folgenden Abbildung dargestellt:

![screen_shot_2018-10-22at14326pm](assets/screen_shot_2018-10-22at14326pm.png)

