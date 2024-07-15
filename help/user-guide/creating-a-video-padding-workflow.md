---
title: Erstellen eines Workflows für Video-Padding
description: Erfahren Sie, wie Sie Video-Padding im Workflow für Ihre Assets erstellen.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 16180f96-2855-4250-9d55-24ed77a908b7
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 100%

---

# Erstellen eines Workflows für Video-Padding {#creating-a-video-padding-workflow}

In diesem Abschnitt werden folgende Themen behandelt:

* **Überblick**
* **Voraussetzungen**
* **Erstellen eines Workflows für den Videoabstand**
   * **Erstellen eines Workflows**
   * **Verwenden des Workflows im AEM Screens-Projekt**

* **Validieren der Ausgabe für den Workflow**

## Überblick {#overview}

Das folgende Nutzungsszenario beinhaltet das Platzieren eines Videos (Beispiel: 1280 x 720) in einem Kanal mit einer Anzeige von 1920 x 1080 und das Platzieren des Videos bei 0x0 (oben links). Das Video sollte in keiner Weise gestreckt oder modifiziert werden und kein **Abdecken** in der Videokomponente verwenden.

Das Video wird als Objekt von Pixel 1 bis Pixel 1280 waagerecht und von Pixel 1 bis Pixel 720 nach unten angezeigt. Der Rest des Kanals ist die Standardfarbe.

## Voraussetzungen {#prerequisites}

Bevor Sie einen Workflow für Videos erstellen, müssen Sie die folgenden Voraussetzungen erfüllen:

1. Laden Sie ein Video in den Ordner **Assets** in Ihrer AEM-Instanz.
1. Erstellen Sie ein AEM Screens-Projekt (z. B. **TestVideoRendition**) und einen Kanal mit dem Namen (**VideoRendering**), wie in der folgenden Abbildung dargestellt:

![screen_shot_2018-10-17at85307pm](assets/screen_shot_2018-10-17at85307pm.png)

## Erstellen eines Workflows für Video-Padding {#creating-a-video-padding-workflow-1}

Um einen Video-Padding-Workflow zu erstellen, erstellen Sie einen Workflow für Ihr Video und verwenden Sie diesen dann im Kanal Ihres AEM Screens-Projekts.

Gehen Sie wie folgt vor, um den Workflow zu erstellen und zu verwenden:

1. Erstellen eines Workflows
1. Verwenden des Workflows in einem AEM Screens-Projekt

### Erstellen eines Workflows {#creating-a-workflow}

Gehen Sie wie folgt vor, um einen Workflow für Ihr Video zu erstellen:

1. Navigieren Sie zu Ihrer AEM-Instanz.
1. Klicken Sie in der Seitenleiste auf „Tools“.
1. Klicken Sie auf **Workflow** > **Modelle**, um ein Modell zu erstellen.

   ![screen_shot_2018-10-17at90025pm](assets/screen_shot_2018-10-17at90025pm.png)

1. Klicken Sie auf **Modelle** > **Erstellen** > **Modell erstellen**. Geben Sie den **Titel** (als **VideoRendition**) und den **Namen** in **Workflow-Modell hinzufügen** ein. Klicken Sie auf **Fertig**, um das Workflow-Modell hinzuzufügen.

   ![screen_shot_2018-10-17at90747pm](assets/screen_shot_2018-10-17at90747pm.png)

1. Nachdem Sie das Workflow-Modell erstellt haben, klicken Sie auf das Modell (**VideoRendition**) und dann in der Aktionsleiste auf **Bearbeiten**.

   ![screen_shot_2018-10-17at91256pm](assets/screen_shot_2018-10-17at91256pm.png)

1. Ziehen Sie die Komponente **`Command Line`** per Drag-and-Drop in Ihren Workflow.

   ![screen_shot_2018-10-22at14846pm](assets/screen_shot_2018-10-22at14846pm.png)

1. Klicken Sie auf die Komponente **`Command Line`** und öffnen Sie das Dialogfeld „Eigenschaften“.

   ![screen_shot_2018-10-17at95752pm](assets/screen_shot_2018-10-17at95752pm.png)

1. Klicken Sie auf die Registerkarte **Argumente.**
1. Geben Sie im Dialogfeld **Befehlszeile – Schritt-Eigenschaften** unter **MIME-Typen** das Format (***video/mp4***) und unter „Befehle“ den Befehl (***/usr/local/Cellar/ffmpeg -i ${filename} -vf &quot;pad=1920:height=1080:x=0:y=0:color=black&quot; cq5dam.video.fullhd-hp.mp4**) ein. Mit diesem Befehl wird der Workflow im Feld **Befehle** gestartet.

   Einzelheiten zu **Mime-Typen** und **Befehlen** finden Sie in der unten stehenden Anmerkung.

   ![screen_shot_2018-10-18at105300am](assets/screen_shot_2018-10-18at105300am.png)

1. Klicken Sie auf den Workflow (**VideoRenditions**).
1. Klicken Sie in der Aktionsleiste auf **Workflow starten**.

   ![screen_shot_2018-10-18at105335am](assets/screen_shot_2018-10-18at105335am.png)

1. Wählen Sie im Dialogfeld **Workflow ausführen** unter **Nutzlast** (***/content/dam/huseinpeyda-crossroads01_512kb 2.mp4***) den Pfad Ihres Assets aus, geben Sie unter **Titel** den Wert ***RunVideo*** ein und klicken Sie auf **Ausführen**.

   ![screen_shot_2018-10-18at112043am](assets/screen_shot_2018-10-18at112043am.png)

### Verwenden des Workflows in einem AEM Screens-Projekt {#using-the-workflow-in-an-aem-screens-project}

Gehen Sie wie folgt vor, um den Workflow in Ihrem AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zu einem AEM Screens-Projekt (**TestVideoRendition** > **Kanäle** >**VideoRendition**).

   ![screen_shot_2018-10-17at100715pm](assets/screen_shot_2018-10-17at100715pm.png)

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**. Ziehen Sie das Video, das Sie ursprünglich in **Assets** hochgeladen haben, per Drag-and-Drop.

   ![screen_shot_2018-10-17at102806pm](assets/screen_shot_2018-10-17at102806pm.png)

1. Wenn Sie das Video hochgeladen haben, klicken Sie auf **Vorschau**, um die Ausgabe anzuzeigen.

   ![screen_shot_2018-10-22at15151pm](assets/screen_shot_2018-10-22at15151pm.png)

## Validieren der Ausgabe für den Workflow {#validating-the-output-for-the-workflow}

Sie können Ihre Ausgabe wie folgt validieren:

* Überprüfen Sie die Vorschau des Videos im Kanal
* Navigieren Sie zu ***/content/dam/testvideo.mp4/jcr:content/renditions/cq5dam.video.fullhd-hp.mp4*** in CRXDE Lite, wie in der folgenden Abbildung dargestellt:

![screen_shot_2018-10-22at14326pm](assets/screen_shot_2018-10-22at14326pm.png)
