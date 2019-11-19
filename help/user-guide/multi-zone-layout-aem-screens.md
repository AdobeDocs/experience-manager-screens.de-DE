---
title: Mehrzonenlayout
seo-title: Mehrzonenlayout
description: Mit dem Mehrzonenlayout können Sie Inhalte für mehrere Bereiche erstellen und eine Vielzahl von Assets wie Videos, Bilder und Text verwenden, die in einem einzigen Bildschirm kombiniert werden können. Auf dieser Seite erfahren Sie mehr.
seo-description: Mit dem Mehrzonenlayout können Sie Inhalte für mehrere Bereiche erstellen und eine Vielzahl von Assets wie Videos, Bilder und Text verwenden, die in einem einzigen Bildschirm kombiniert werden können. Auf dieser Seite erfahren Sie mehr.
uuid: 2ad689ef-700a-4eed-b5e2-fc57f2288388
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 4c073172-d93c-4b73-87ab-0b08789193a3
noindex: true
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Mehrzonenlayout {#multi-zone-layout}

Auf der folgenden Seite wird die Verwendung des Layouts für mehrere Zonen beschrieben und es werden folgende Themen behandelt:

* Überblick
* Erstellen eines Layouts mit mehreren Zonen
* Voraussetzungen
* Einzelne Assets in einem oder mehreren Zonen verwenden
* Verwenden von sequenzierten Inhalten in einem oder mehreren Zonen

## Überblick {#overview}

***Mit dem Mehrzonenlayout*** können Sie Inhalte für mehrere Bereiche erstellen und eine Vielzahl von Assets wie Videos, Bilder und Text verwenden, die in einem einzigen Bildschirm kombiniert werden können. Sie können Bilder, Videos und Text einbinden, um eine intuitive digitale Wiedergabe zu ermöglichen.

Abhängig von den Projektanforderungen sind ggf. mehrere Bereiche in einem Kanal erforderlich, die dann zusammen als Einheit bearbeitet werden. Beispiel: Eine Produktsequenz mit einem zugehörigen Social Media-Feed, die in drei separaten Zonen auf einem Kanal ausgeführt wird.

## Erstellen eines Layouts mit mehreren Zonen {#creating-multi-zone-layout}

Beim Erstellen eines Kanals können Sie verschiedene Vorlagen verwenden, um Zonen in Ihrem Kanal zu erstellen. Sie können ein einzelnes Bild, Video oder einen eingebetteten Kanal hinzufügen, sodass mehrere Assets in einer Sequenz angezeigt werden können.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktion beginnen, stellen Sie bitte sicher, dass Sie ein Projekt als Voraussetzung für die Implementierung des Mehrzonenlayouts vorbereitet haben. Zum Beispiel:

* Erstellen eines AEM Screens-Projekts mit dem Titel " **Zonen"**
* Erstellen Sie eine Anzeige unter **Speicherorten** mit **MultiZoneDisplay**

Erstellen Sie einen Kanal mit dem Titel **MultiZone** in **Zones** Projekt. Gehen Sie wie folgt vor:

**Erstellen des Kanals**

1. Wählen Sie den Link zu Adobe Experience Manager (oben links) und dann **Screens** aus. Alternatively, you can ﻿go directly to: `http://localhost:4502/screens.html/content/screens`.
1. Navigieren Sie zum Ordner " **Kanäle** "und klicken Sie in der Aktionsleiste auf " **Erstellen** ".

1. Wählen Sie **linken L-Balken-Teilungsbildschirm** aus dem Assistenten **Erstellen** .

1. Klicken Sie auf **Weiter** und geben Sie den **Titel** als **MultiZone** ein.

1. Klicken Sie auf **Erstellen** , um die Kanalerstellung abzuschließen.

![screen_shot_2018-12-07at120026pm](assets/screen_shot_2018-12-07at120026pm.png)

### Einzelne Assets in einem oder mehreren Zonen verwenden {#using-single-assets-in-one-or-more-zones}

Sie können einzelne Assets wie ein Bild oder ein Video in allen drei verschiedenen Zonen verwenden. Gehen Sie zur Implementierung wie folgt vor:

1. **Hinzufügen von Inhalten zum Kanal**

   1. Navigieren Sie zu **Zonen** —&gt; **Kanäle**—&gt;**MultiZone**.
   1. Select the **MultiZone** channel and click **Edit** from the action bar to open the editor.
   ![screen_shot_2018-12-07at14917pm](assets/screen_shot_2018-12-07at14917pm.png)

1. **Hinzufügen von Bildern zum Kanal**

   Um ein einzelnes Bild oder Video in allen drei Zonen abzuspielen, ziehen Sie das Bild einfach per Drag &amp; Drop in den Kanaleditor, wie unten dargestellt.

   ![new1-1](assets/new1-1.gif)

### Verwenden von sequenzierten Inhalten in einem oder mehreren Zonen {#using-sequenced-content-in-one-or-more-zones}

Wenn Sie möchten, dass in den Zonen eine Abfolge von Bildern oder Inhalten und ein statisches Bild in drei verschiedenen Zonen angezeigt werden, führen Sie die folgenden Schritte aus, um Einzelheiten zu erfahren.

1. **Erstellen eines Kanalordners**

   1. Navigieren Sie zu **Zonen** —&gt; **MultiZone** —&gt; **Kanäle** und klicken Sie in der Aktionsleiste auf **Erstellen** .
   1. Select **Channels Folder** from the **Create** wizard and click **Next**.
   1. Enter the title as **EmbeddedChannels** and click **Create**.
   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Hinzufügen von zwei weiteren Kanälen zum Kanalordner**

   1. Navigieren Sie zu **Zonen** —&gt; **Kanäle** —&gt; **EmbeddedChannels** und klicken Sie in der Aktionsleiste auf **Erstellen** .
   1. Wählen Sie **Sequenzkanal** aus dem Assistenten zum **Erstellen** , um einen Kanal mit dem Namen** Zone1* zu erstellen.
   1. Select **Zone1** and click **Edit** from the action bar to open the editor.
   1. Ziehen Sie einige Bilder in diesen Kanal.
   Erstellen Sie auf ähnliche Weise einen weiteren Sequenzkanal mit dem Namen **Zone2** im Ordner **EmbeddedChannels** .

   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

1. **Hinzufügen eingebetteter Sequenzen/Komponenten zum Hauptkanal (MultiZone)**

   1. Navigieren Sie zu **Zonen** —&gt; **Kanäle** —&gt; **MultiZone**.
   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
   1. Ziehen Sie die Komponente " **Eingebettete Sequenz** "in zwei der Zonen, wie in der Abbildung unten dargestellt.
   ![neu](assets/new.gif)

1. **Inhalt zu allen drei Zonen hinzufügen**

   1. Navigieren Sie zu **Zonen** —&gt; **Kanäle** —&gt; **MultiZone**.
   1. Wählen Sie die eingebettete Sequenz in einer der Zonen aus.
   1. Klicken Sie auf das Symbol " **Konfigurieren** "(Schraubenschlüssel), um eine der eingebetteten Sequenzen im Editor zu konfigurieren.
   1. Wählen Sie den Kanalpfad als **Zonen** —&gt; **Kanäle** —&gt; **EmbeddedChannels** —&gt; **Zone1**, wie in der Abbildung unten dargestellt.
   Fügen Sie auf ähnliche Weise die **Zone2** einer anderen eingebetteten Sequenzkomponente im Editor hinzu. Fügen Sie auch ein Bild zur dritten Zone am unteren Rand hinzu, wie unten dargestellt.

   ![new2-1](assets/new2-1.gif)

#### Anzeigen des Ergebnisses {#viewing-the-result}

Wenn Sie Layouts mit mehreren Zonen implementiert haben, wird die folgende Ausgabe angezeigt, wie in der folgenden Abbildung dargestellt.

Die folgende Ausgabe im Screens Player zeigt den Inhalt in drei verschiedenen Zonen an. Die linken und rechten Bereiche (beide verwenden eingebettete Sequenz als Komponente) zeigen eine Bildsequenz an, und die nachstehende Zone zeigt ein statisches Bild an.

![new2-2](assets/new2-2.gif)

