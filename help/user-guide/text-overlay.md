---
title: Textüberlagerung
seo-title: Textüberlagerung
description: Text Overlay ist eine Funktion, die in AEM Screens zur Verfügung steht und mit der Sie in einem Sequenzkanal ein überzeugendes Erlebnis erstellen können, indem Sie einen Titel oder eine Beschreibung über einem Bild einfügen. Auf dieser Seite erfahren Sie mehr.
seo-description: Text Overlay ist eine Funktion, die in AEM Screens zur Verfügung steht und mit der Sie in einem Sequenzkanal ein überzeugendes Erlebnis erstellen können, indem Sie einen Titel oder eine Beschreibung über einem Bild einfügen. Auf dieser Seite erfahren Sie mehr.
uuid: 944477e8-0025-4cc7-aa61-6b72f4a245fd
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: b6fdb5a0-5601-4443-a3f4-85cc90c49914
noindex: true
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Textüberlagerung {#text-overlay}

Dieser Abschnitt behandelt die folgenden Themen:

* **Überblick**
* **Textüberlagerung verwenden**
* **Voraussetzungen**
* **Eigenschaften von Textüberlagerungen**

>[!CAUTION]
>
>Die **Funktion "Textüberlagerung** "ist nur verfügbar, wenn Sie AEM 6.3 Feature Pack 5 oder AEM 6.4 Feature Pack 3 installiert haben.

## Überblick {#overview}

Text Overlay ist eine Funktion, die in AEM Screens zur Verfügung steht und mit der Sie in einem Sequenzkanal ein überzeugendes Erlebnis erstellen können, indem Sie einen Titel oder eine Beschreibung über einem Bild einfügen.

Informationen zum Erstellen einer eigenen benutzerdefinierten Komponente finden Sie unter **Erweitern einer AEM Screens-Komponente**.

In diesem Abschnitt wird nur gezeigt, wie die Standkomponente in einem AEM Screens-Projekt verwendet und genutzt und als Textüberlagerung in einem Ihrer Sequenzkanäle verwendet werden kann.

## Textüberlagerung verwenden {#using-text-overlay}

Im folgenden Abschnitt wird die Verwendung von Textüberlagerungen in einem AEM Screens-Projekt beschrieben.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktion beginnen, stellen Sie sicher, dass Sie ein Projekt als Voraussetzung für die Implementierung der Textüberlagerung eingerichtet haben. Zum Beispiel:

* Erstellen eines AEM Screens-Projekts (in diesem Beispiel **TextOverlayDemo**)

* Kanal als **TextSample** unter **Kanalordner** erstellen

* Hinzufügen von Inhalten zu Ihrem **TextSample** -Kanal

Die folgende Abbildung zeigt das Projekt **TextOverlayDemo** mit dem Kanal **TextSample** im Ordner **Channels** .

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

1. Navigieren Sie zu **TextOverlayDemo** —&gt; **Channels** —&gt; **TextSample** und klicken Sie in der Aktionsleiste auf **Bearbeiten** , um den Editor zu öffnen.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Wählen Sie das Bild aus und klicken Sie auf " **Konfigurieren** "(Schraubenschlüsselsymbol), um das Dialogfeld "Eigenschaften"zu öffnen.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Wählen Sie die Option " **Textüberlagerung** "in der Navigationsleiste des Dialogfelds aus, wie in der Abbildung unten dargestellt.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Eigenschaften von Textüberlagerungen {#understanding-text-overlay-properties}

Mithilfe der Eigenschaften "Text-Überlagerung"können Sie einer beliebigen Komponente im Screens-Projekt Text hinzufügen. Im folgenden Abschnitt erhalten Sie eine Übersicht über die Eigenschaften, die in der Textüberlagerung verfügbar sind:

![text](assets/text.gif)

Sie können dem Textfeld einen Text hinzufügen und typografische Hervorhebungen wie Fett, Kursiv, Unterstrichen usw. hinzufügen.

**Farbvariante** Mit dieser Option kann der Text entweder dunkel (Text in schwarzer Farbe) oder hell (Text in weißer Farbe) sein.

**Größe und Positionierung** Diese Option ermöglicht es dem Benutzer, den Text horizontal oder vertikal auszurichten oder zusätzlich feine Werkzeuge für die Textausrichtung zu verwenden.

>[!NOTE]
>
>Um fein abgestimmte Werkzeuge ordnungsgemäß zu verwenden, müssen Sie die richtige Position in Pixel mit (px) als Suffix (z. B. 200 px) identifizieren. Das Ergebnis dieses Ausdrucks ist 200 Pixel vom Anfangspunkt entfernt.

