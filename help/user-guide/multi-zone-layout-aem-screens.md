---
title: Mehrzonen-Layout
seo-title: Mehrzonen-Layout
description: Mehrzonen-Layout ermöglicht es Ihnen, Inhalte für mehrere Bereiche zu erstellen und eine Vielzahl von Assets wie Videos, Bilder und Text zu verwenden, die in einem einzigen Bildschirm kombiniert werden können. Auf dieser Seite erfahren Sie mehr.
seo-description: Mehrzonen-Layout ermöglicht es Ihnen, Inhalte für mehrere Bereiche zu erstellen und eine Vielzahl von Assets wie Videos, Bilder und Text zu verwenden, die in einem einzigen Bildschirm kombiniert werden können. Auf dieser Seite erfahren Sie mehr.
uuid: 2ad689ef-700a-4eed-b5e2-fc57f2288388
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 4c073172-d93c-4b73-87ab-0b08789193a3
noindex: true
translation-type: tm+mt
source-git-commit: ae05d169dce9d02562159524f9bf43e88a29e43f
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 54%

---


# Mehrzonen-Layout {#multi-zone-layout}

Die folgende Seite beschreibt die Verwendung des Mehrzonen-Layouts und behandelt die folgenden Themen:

* Überblick
* Erstellen eines Mehrzonen-Layouts
* Voraussetzungen
* Verwenden einzelner Assets in einem oder mehreren Bereichen
* Verwenden sequenzieller Inhalte in einem oder mehreren Bereichen

## Überblick {#overview}

***Mehrzonen-Layout ermöglicht es Ihnen, Inhalte für mehrere Bereiche zu erstellen und eine Vielzahl von Assets wie Videos, Bilder und Text zu verwenden, die in einem einzigen Bildschirm kombiniert werden können.*** Sie können Bilder, Videos und Text einblenden, sodass alles miteinander verschmelzen und ein intuitives digitales Erlebnis schaffen kann.

Abhängig von den Projektanforderungen sind ggf. mehrere Bereiche in einem Kanal erforderlich, die dann zusammen als Einheit bearbeitet werden. Beispiel: eine Produktsequenz mit entsprechendem Social-Media-Feed, die in drei separaten Bereichen in einem Kanal läuft.

## Erstellen eines Mehrzonen-Layouts {#creating-multi-zone-layout}

Beim Erstellen eines Kanals können Sie mithilfe verschiedener Vorlagen Bereiche in Ihrem Kanal erstellen. Sie können ein einzelnes Bild, Video oder einen eingebetteten Kanal hinzufügen, sodass mehrere Assets in einer Sequenz angezeigt werden können.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktion beginnen, stellen Sie sicher, dass Sie ein Projekt als Voraussetzung für die Implementierung des Mehrzonen-Layouts vorbereitet haben. Beispiel:

* Erstellen eines AEM Screens-Projekts mit dem Titel **Bereiche**
* Erstellen einer Anzeige unter **Standorte** mit dem Namen **MultiZoneDisplay**.

Erstellen Sie einen Kanal mit dem Titel **MultiZone** im Projekt **Bereiche**. Führen Sie dazu folgende Schritte durch:

**Erstellen des Kanals**

1. Wählen Sie den Adobe Experience Manager-Link (oben links) und dann **Screens** aus. Sie haben auch die Möglichkeit, direkt zur folgenden URL zu wechseln: `http://localhost:4502/screens.html/content/screens`.
1. Navigieren Sie zum Ordner **Kanäle** und klicken Sie in der Aktionsleiste auf **Erstellen**.

1. Wählen Sie im Assistenten &quot; **Erstellen** &quot;den Kanal **** &quot;Geteilter Bildschirm&quot;aus.

1. Klicken Sie auf **Weiter** und geben Sie unter **Titel** den Wert **MultiZone** ein.

1. Klicken Sie auf **Erstellen**, um die Kanalerstellung abzuschließen.

### Verwenden einzelner Assets in einem oder mehreren Bereichen {#using-single-assets-in-one-or-more-zones}

Sie können einzelne Assets wie ein Bild oder ein Video in allen drei verschiedenen Bereichen verwenden. Gehen Sie zur Implementierung wie folgt vor:

1. **Hinzufügen von Inhalten zum Kanal**

   1. Navigieren Sie zu **Bereiche** > **Kanäle**>**MultiZone**.
   1. Wählen Sie den Kanal **Multizone** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.

1. **Hinzufügen von Bildern zum Kanal**

   Um ein einzelnes Bild oder Video in zwei Zonen abzuspielen, ziehen Sie einfach per Drag &amp; Drop ein Kanal in jeden Bereich des Editors, wie in der folgenden Abbildung dargestellt:

   MultiZone-img3

   ![image](/help/user-guide/assets/multi-zone/multizone-img3.png)

### Verwenden sequenzieller Inhalte in einem oder mehreren Bereichen {#using-sequenced-content-in-one-or-more-zones}

Wenn Sie möchten, dass die Zonen eine Abfolge von Bildern oder Inhalten und ein statisches Bild in zwei verschiedenen Zonen anzeigen, führen Sie die folgenden Schritte aus, um Einzelheiten zu erfahren.

1. **Erstellen eines Kanalordners**

   1. Navigieren Sie zu **Bereiche** > **MultiZone** > **Kanäle** und klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Wählen Sie im Assistenten **Erstellen** die Option **Kanalordner** aus und klicken Sie auf **Weiter**.
   1. Geben Sie **EmbeddedChannels** als Titel ein und klicken Sie auf **Erstellen**.
   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Hinzufügen von zwei weiteren Kanälen zum Kanalordner**

   1. Navigieren Sie zu **Bereiche** > **Kanäle** > **EmbeddedChannels** und klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Select **Sequence Channel** from the **Create** wizard to create a channel titled as **Zone1**.
   1. Wählen Sie **Zone1** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
   1. Ziehen Sie einige Bilder in diesen Kanal.
   Erstellen Sie auf ähnliche Weise einen weiteren Sequenzkanal mit dem Namen **Zone2** im Ordner **EmbeddedChannels**.

   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

   Die Bilder, die dem Editor des **Zone1** -Sequenzcodes hinzugefügt werden, sind im Folgenden dargestellt:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img4.png)

   Das Video, das zum Editor des **Zone2** -Sequenz-Kanals hinzugefügt wurde, wird unten gezeigt:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img5.png)

1. **Hinzufügen von eingebetteten Sequenzen (Komponenten) zum Haupt-Kanal (MultiZone)**

   1. Navigieren Sie zu **Bereiche** > **Kanäle** > **MultiZone**.
   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
   1. Ziehen Sie die Komponente &quot; **Eingebettete Sequenz** &quot;auf zwei Bereiche.

1. **Inhalt zu allen drei Bereichen hinzufügen**

   1. Navigieren Sie zu **Bereiche** > **Kanäle** > **MultiZone**.
   1. Wählen Sie die eingebettete Sequenz in einem der Bereiche aus.
   1. Klicken Sie auf das Symbol **Konfigurieren** (Schraubenschlüssel), um eine der eingebetteten Sequenzen im Editor zu konfigurieren.
   1. Wählen Sie als Kanalpfad **Bereiche** > **Kanäle** > **EmbeddedChannels** > **Zone1** aus, wie in der Abbildung unten dargestellt.
   Fügen Sie auf ähnliche Weise die **Zone2** einer anderen eingebetteten Sequenzkomponente im Editor hinzu.

   ![image](/help/user-guide/assets/multi-zone/multizone-3.png)

### Erstellen von Position und Anzeige {#creating-location}

Sie müssen einen Speicherort und eine Anzeige erstellen, um den Inhalt im Bildschirmplayer Ansicht. Gehen Sie wie folgt vor, um eine Position und eine Anzeige zu erstellen.

1. **Erstellen eines Standorts**

   1. Navigate to **Zones** --> **Locations** folder.
   1. Select the **Locations** folder and click **Create** from the action bar.
   1. Wählen Sie im Assistenten **Erstellen** die Option **Standort** aus und klicken Sie auf **Weiter**.
   1. Enter the **Title** as **SanJose** and click **Create**.

1. **Erstellen einer Anzeige**

   1. Navigate to **Zones** --> **Locations** folder.
   1. Select the **SanJose** location and click **Create** from the action bar.
   1. Wählen Sie im Assistenten **Erstellen** die Option **Anzeige** aus und klicken Sie auf **Weiter**.
   1. Enter the **Title** as **Lobby** and click **Create**.

### Kanal zur Anzeige zuweisen {#channel-channel}

Sie müssen die Kanal der Anzeige zuweisen, um den Inhalt Ansicht. Gehen Sie wie folgt vor, um den Kanal der Anzeige zuzuweisen.

1. **Kanal zur Anzeige zuweisen**

   1. Navigieren Sie zu **Zonen** —> **Orte** —> **SanJose**—> **Lobby**.
   1. Wählen Sie die **Lobby** -Anzeige aus und klicken Sie in der Aktionsleiste auf Kanal **** zuweisen.
   1. Geben Sie den Pfad zum **MultiZone** -Kanal im **Kanal-Pfad** ein.
   1. Set the **Supported Events** as **Initial Load**, **Idle Screen**, and **Timer**.
   1. Klicken Sie auf **Speichern**.

      ![image](/help/user-guide/assets/multi-zone/multizone-img9.png)
   1. Ebenso müssen Sie die anderen beiden eingebetteten Kanal (**Zone1** und **Zone2**) dieser Anzeige mit Schritt (2) zuweisen.
   1. Nachdem Sie alle drei Kanal der **Lobby** -Anzeige zugewiesen haben, sollten Sie die zugewiesenen Kanal aus dem Display-Dashboard Ansicht haben.

      ![image](/help/user-guide/assets/multi-zone/multizone-img8.png)
   >[!IWichtig]
   > Nachdem Sie der Anzeige den Kanal &quot;main&quot;(in diesem Fall &quot; **MultiZone**&quot;) zugewiesen haben, müssen die beiden anderen eingebetteten Kanal **Zone1** und **Zone2** ebenfalls derselben Anzeige zugewiesen werden.

### Registrieren des Geräts {#registering-device}

Nachdem Sie einen Speicherort und eine Anzeige eingerichtet haben, führen Sie die folgenden Schritte aus, um das Gerät zu registrieren und dem Gerät eine Anzeige zuzuweisen.

1. **Registrieren des Geräts**

   1. Navigieren Sie zum Ordner **Zonen** —> **Geräte** .
   1. Select the **Devices** folder and click **Device Manager** from the action bar.
   1. Klicken Sie auf **Geräteregistrierung** und wählen Sie in der Liste das ausstehende Gerät aus.
      >[!NOTE]
      > Der Titel des Geräts muss mit dem Gerätetoken (**Token** -Feld) übereinstimmen, das auf der Registerkarte &quot; **Geräteregistrierung** &quot;angezeigt wird.
   1. Wenn der Titel mit dem Gerätetoken übereinstimmt, wählen Sie das Gerät aus und klicken Sie in der Aktionsleiste auf &quot;Gerät **registrieren&quot;** .
   1. Wenn der Registrierungscode mit dem Code auf der Registerkarte &quot;Bildschirmplayer-Registrierung&quot;übereinstimmt, klicken Sie in der Aktionsleiste auf &quot; **Validieren** &quot;.
      ![image](/help/user-guide/assets/multi-zone/multizone-img6.png)
   1. Enter the **Title** as **Chrome-Device1** and click **Register**.
   1. Wählen Sie &quot; **Anzeige** zuweisen&quot;und dann den Pfad zur Gerätekonfiguration.

#### Anzeigen des Ergebnisses {#viewing-the-result}

Wenn Sie Mehrzonen-Layouts implementiert haben, wird die folgende Ausgabe angezeigt, wie in der folgenden Abbildung dargestellt.

Überprüfen Sie den Bildschirmplayer, um die Ausgabe, die den Inhalt in zwei verschiedenen Bereichen anzeigt, Ansicht. Die linke und die rechte Zone (beide verwenden eine eingebettete Sequenz als Komponente).

>[!NOTE]
>Wenn Sie versuchen, den Inhalt im Bildschirmplayer Ansicht, klicken Sie im Kanal-Dashboard auf &quot;Offline-Inhalte **** aktualisieren&quot;.

![new2-1](/help/user-guide/assets/multi-zone/Multi-gif.gif)


