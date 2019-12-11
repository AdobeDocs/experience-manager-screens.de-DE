---
title: MultiZone zu SingleZone-Übergangsfall
description: Auf dieser Seite erfahren Sie mehr über den Einsatzfall MultiZone zu SingleZone Transitions.
seo-description: MultiZone zu SingleZone Transitions Anwendungsfall.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 0cae7c19759fe3418a13ab2d7cc68f1b220f397d

---


# MultiZone zu SingleZone-Übergang {#multizone-to-singlezone-use-case}


## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Abschnitt wird ein Verwendungsfallbeispiel beschrieben, in dem hervorgehoben wird, wie ein Mehrzonenlayoutkanal eingerichtet wird, der mit einem Einzel-Layout-Kanal wechselt. Jeder Kanal verfügt über sequenzierende Bild-/Video-Assets.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Anwendungsfall beginnen, sollten Sie wissen, wie:

* **[Kanäle erstellen und verwalten](managing-channels.md)**
* **[Orte erstellen und verwalten](managing-locations.md)**
* **[Zeitpläne erstellen und verwalten](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Inhaltsersteller

## Setting up the Project {#setting-up-the-project}

Gehen Sie wie folgt vor, um ein Projekt einzurichten:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Namen **ChannelTransition**, wie unten dargestellt.



1. **Erstellen eines Teilungsbildschirms**

   1. Wählen Sie den Ordner " **Kanäle** "aus und klicken Sie in der Aktionsleiste auf " **Erstellen** ", um den Assistenten zum Erstellen eines Kanals zu öffnen.
   1. Wählen Sie im Assistenten die Option " **Linke Balkensplit Screen Channel** "und erstellen Sie den Kanal mit dem Namen **MultiZoneLayout**.



   1. Select the **MultiZoneLayout** channel and click **Edit** from the action bar to open the editor. Ziehen Sie die Assets per Drag &amp; Drop in die einzelnen Zonen. Das folgende Beispiel zeigt ein Video, ein Bild und ein Textbanner im Kanal, wie nachfolgend gezeigt.


1. **Erstellen eines 2X2-Kanals mit vier Bildern**

   1. Wählen Sie den Ordner " **Kanäle** "aus und klicken Sie in der Aktionsleiste auf " **Erstellen** ", um den Assistenten zum Erstellen eines Kanals zu öffnen.

   1. Wählen Sie im Assistenten die Vorlage " **2X2-Split Screen Channel** "und erstellen Sie den Kanal mit dem Titel " **TwobyTwoChannel**".


   1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf " **Bearbeiten** ", um den Editor zu öffnen und vier Bilder (vier verschiedene Bereiche) wie unten dargestellt zu diesem Kanal zu ziehen.


1. **Erstellen eines 1X2-Split-Screen-Kanals mit zwei Bildern**

   1. Wählen Sie den Ordner " **Kanäle** "aus und klicken Sie in der Aktionsleiste auf " **Erstellen** ", um den Assistenten zum Erstellen eines Kanals zu öffnen.

   1. Wählen Sie im Assistenten die Vorlage **1X2 Split Screen Channel** und erstellen Sie den Kanal mit dem Namen **OnebyTwoChannel**.


   1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf " **Bearbeiten** ", um den Editor zu öffnen und zwei Bilder (zwei verschiedene Bereiche) wie unten dargestellt zu diesem Kanal zu ziehen.


1. **Erstellen eines Kanals mit einem Vollbildvideo**

   1. Wählen Sie den Ordner " **Kanäle** "aus und klicken Sie in der Aktionsleiste auf " **Erstellen** ", um den Assistenten zum Erstellen eines Kanals zu öffnen.

   1. Wählen Sie im Assistenten die **Vorlage "Sequenzkanal** "und erstellen Sie den Kanal mit dem Titel **FullScreensVideo**.


   1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf " **Bearbeiten** ", um den Editor zu öffnen, ziehen Sie die Videokomponente auf den Kanal und fügen Sie dann das gewünschte Video hinzu, wie unten dargestellt.

