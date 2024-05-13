---
title: Mehrzonen-Layout
description: Erfahren Sie, wie Sie in AEM Screens Inhalte für mehrere Zonen erstellen und verschiedene Assets wie Videos, Bilder und Text verwenden, die in einem einzigen Bildschirm kombiniert werden können.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 901ed50e-d3f0-4c85-ad79-6c4595382759
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '1124'
ht-degree: 76%

---

# Mehrzonen-Layout {#multi-zone-layout}

Die folgende Seite beschreibt die Verwendung des Mehrzonen-Layouts und behandelt die folgenden Themen:

* Überblick
* Erstellen eines Mehrzonen-Layouts
* Voraussetzungen
* Verwenden einzelner Assets in einem oder mehreren Bereichen
* Verwenden sequenzieller Inhalte in einem oder mehreren Bereichen

## Überblick {#overview}

Das ***Mehrzonen-Layout*** ermöglicht es Ihnen, Inhalte für mehrere Zonen zu erstellen und verschiedene Assets wie Videos, Bilder und Text zu verwenden, die in einem einzigen Bildschirm kombiniert werden können. Sie können Bilder, Videos und Text einblenden, sodass alles miteinander verschmelzen und ein intuitives digitales Erlebnis schaffen kann.

Abhängig von den Projektanforderungen sind ggf. mehrere Bereiche in einem Kanal erforderlich, die dann zusammen als Einheit bearbeitet werden. Beispiel: eine Produktsequenz mit entsprechendem Social-Media-Feed, die in drei separaten Zonen auf einem einzigen Kanal läuft.

>[!NOTE]
>In Mehrzonen-Kanälen wird die Zeitplanung auf Asset-Ebene aufgrund potenzieller Konflikte und unbeabsichtigten Verhaltens nicht empfohlen. Wenn eine Planung auf Asset-Ebene erforderlich ist, wird empfohlen, einen separaten Sequenzkanal zu erstellen und innerhalb dieses Kanals eine Planungslogik anzuwenden. Betten Sie als Nächstes den Sequenzkanal in den Mehrzonen-Kanal ein.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktionalität beginnen, vergewissern Sie sich, dass Sie mit folgenden Themen vertraut sind:

* [Erstellen eines AEM Screens-Projekts](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/creating-a-screens-project)
* [Erstellen einer Anzeige](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/managing-displays)
* [Zuweisen eines Kanals zu einem Display](/help/user-guide/channel-assignment.md)

## Erstellen eines Mehrzonen-Layouts {#creating-multi-zone-layout}

Beim Erstellen eines Kanals können Sie mithilfe verschiedener Vorlagen Zonen in Ihrem Kanal erstellen. Sie können ein einzelnes Bild, Video oder einen eingebetteten Kanal hinzufügen, sodass mehrere Assets in einer Sequenz angezeigt werden können.

**Erstellen eines Kanals**

1. Klicken Sie auf den Link Adobe Experience Manager (oben links) und dann **Screens**. Sie haben auch die Möglichkeit, direkt zur folgenden URL zu wechseln: `http://localhost:4502/screens.html/content/screens`.
1. Navigieren Sie zum Ordner **Kanäle** und klicken Sie in der Aktionsleiste auf **Erstellen**.

1. Klicks **1x2-Splitscreen-Kanal** aus dem **Erstellen** Assistent.

1. Klicken Sie auf **Weiter** und geben Sie unter **Titel** den Wert **MultiZone** ein.

1. Klicken Sie auf **Erstellen**, um die Kanalerstellung abzuschließen.

### Verwenden einzelner Assets in einem oder mehreren Bereichen {#using-single-assets-in-one-or-more-zones}

Sie können einzelne Assets wie ein Bild oder ein Video in allen Bereichen verwenden. Gehen Sie zur Implementierung wie folgt vor:

1. **Hinzufügen von Inhalten zum Kanal**

   1. Navigieren Sie zu **Zonen** > **Kanäle** > **MultiZone**.
   1. Klicken Sie auf **MultiZone** channel und click **Bearbeiten** in der Aktionsleiste aus.

1. **Hinzufügen von Bildern zum Kanal**

   Um ein einzelnes Bild oder Video in zwei Bereichen abzuspielen, ziehen Sie das Bild einfach per Drag-and-Drop in jeden Bereich des Kanal-Editors, wie in der folgenden Abbildung dargestellt:

   ![image](/help/user-guide/assets/multi-zone/multizone-img3.png)

### Verwenden sequenzieller Inhalte in einem oder mehreren Bereichen {#using-sequenced-content-in-one-or-more-zones}

Wenn Sie möchten, dass eine Bildsequenz und ein Video in verschiedenen Bereichen angezeigt werden, führen Sie die folgenden Schritte aus, um mehr zu erfahren.

1. **Erstellen eines Kanalordners**

   1. Navigieren Sie zu **Zonen** > **MultiZone** > **Kanäle** und klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Klicks **Kanalordner** aus dem **Erstellen** Assistent und klicken Sie auf **Nächste**.
   1. Geben Sie **EmbeddedChannels** als Titel ein und klicken Sie auf **Erstellen**.

   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Hinzufügen von zwei weiteren Kanälen zum Kanalordner**

   1. Navigieren Sie zu **Zonen** > **Kanäle** > **EmbeddedChannels** und klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Klicks **Sequenzkanal** aus dem **Erstellen** Assistent zum Erstellen eines Kanals mit dem Titel **`Zone1`**.
   1. Klicks **`Zone1`** und klicken **Bearbeiten** in der Aktionsleiste aus.
   1. Ziehen Sie einige Bilder in diesen Kanal.
   1. Erstellen Sie auf ähnliche Weise einen weiteren Sequenzkanal mit dem Namen **`Zone2`** im Ordner **EmbeddedChannels**.
   1. Ziehen Sie einige Bilder per Drag-and-Drop in diesen Kanal.

   Die folgende Abbildung zeigt die Kanäle **`Zone1`** und **`Zone2`**:

   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

   Die Bilder, die dem Editor des Sequenzkanals **`Zone1`** hinzugefügt wurden, sind im Folgenden zu sehen:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img4.png)

   Das Video, das dem Editor des Sequenzkanals **`Zone2`** hinzugefügt wurde, ist im Folgenden zu sehen:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img5.png)

1. **Hinzufügen eingebetteter Sequenzen (Komponenten) zum Hauptkanal (MultiZone)**

   1. Navigieren Sie zu **Zonen** > **Kanäle** > **MultiZone**.
   1. Klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Ziehen Sie die Komponente **Eingebettete Sequenz** per Drag-and-Drop in beide Bereiche.
   1. Klicken Sie auf die eingebettete Sequenz in einem der Bereiche.
   1. Klicken Sie auf das Symbol **Konfigurieren** (Schraubenschlüssel), um eine der eingebetteten Sequenzen im Editor zu konfigurieren.
   1. Klicken Sie auf den Kanalpfad als **Bereiche** > **Kanäle** > **EmbeddedChannels** > **`Zone1`**, wie in der folgenden Abbildung dargestellt.
   1. Fügen Sie auf ähnliche Weise **`Zone2`** einer anderen eingebetteten Sequenzkomponente im Editor hinzu.

      ![Bild](/help/user-guide/assets/multi-zone/multizone-3.png)

### Erstellen eines Standorts und eines Displays {#creating-location}

Erstellen Sie einen Speicherort und eine Anzeige, damit Sie den Inhalt im AEM Screens-Player anzeigen können.

1. **Erstellen eines Standorts**

   1. Navigieren Sie zu **Zonen** > Ordner **Standorte**.
   1. Klicken Sie auf **Standorte** Ordner und klicken Sie auf **Erstellen** in der Aktionsleiste aus.
   1. Klicks **Standort** aus dem **Erstellen** Assistent und klicken Sie auf **Nächste**.
   1. Geben Sie unter **Titel** den Wert **SanJose** ein und klicken Sie auf **Erstellen**.

1. **Erstellen einer Anzeige**

   1. Navigieren Sie zu **Zonen** > Ordner **Standorte**.
   1. Klicken Sie auf **SanJose** Standort und Klicken **Erstellen** in der Aktionsleiste aus.
   1. Klicks **Anzeige** aus dem **Erstellen** Assistent und klicken Sie auf **Nächste**.
   1. Geben Sie unter **Titel** den Wert **Lobby** ein und klicken Sie auf **Erstellen**.

### Zuweisen von Kanälen zur Anzeige {#channel-channel}

Weisen Sie die Kanäle dem Display zu, um den Inhalt anzuzeigen. Gehen Sie wie folgt vor, um einer Anzeige einen Kanal zuzuweisen.

1. **Zuweisen eines Kanals zur Anzeige**

   1. Navigieren Sie zu **Zonen** > **Standorte** > **SanJose** > **Lobby**.
   1. Klicken Sie auf **Lobby** anzeigen und klicken **Kanal zuweisen** in der Aktionsleiste aus.
   1. Geben Sie den Pfad zum Kanal **MultiZone** unter **Kanalpfad** ein.
   1. Wählen Sie unter **Unterstützte Ereignisse** die Optionen **Erster Ladevorgang**, **Bildschirm bei Untätigkeit** und **Benutzerinteraktion**.
   1. Klicken Sie auf **Speichern**.

      ![image](/help/user-guide/assets/multi-zone/multizone-img9.png)
   1. Weisen Sie die anderen beiden eingebetteten Kanäle zu (**`Zone1`** und **`Zone2`**), um diese Anzeige anzuzeigen.
   1. Nachdem Sie alle drei Kanäle der Anzeige **Lobby** zugewiesen haben, sollten Sie die zugewiesenen Kanäle im Anzeigen-Dashboard sehen.

      ![Bild](/help/user-guide/assets/multi-zone/multizone-img8.png)


      >[!IMPORTANT]
      >
      >Nachdem Sie den Hauptkanal (in diesem Fall **MultiZone**) der Anzeige zugewiesen haben, müssen Sie die anderen beiden eingebetteten Kanäle **`Zone1`** und **`Zone2`** derselben Anzeige zuweisen.

### Registrieren des Geräts {#registering-device}

Nachdem Sie einen Standort und eine Anzeige eingerichtet haben, gehen Sie wie folgt vor, um das Gerät zu registrieren und dem Gerät eine Anzeige zuzuweisen.

1. **Registrieren des Geräts**

   1. Navigieren Sie zu **Zonen** > Ordner **Geräte**.
   1. Klicken Sie auf **Geräte** Ordner und klicken Sie auf **Geräte-Manager** in der Aktionsleiste aus.
   1. Klicks **Geräteregistrierung** und klicken Sie in der Liste auf das ausstehende Gerät.

      >[!NOTE]
      > Der Titel des Geräts muss mit dem Geräte-Token (Feld **Token**) übereinstimmen, das auf der Registerkarte **Geräteregistrierung** angezeigt wird.

   1. Wenn der Titel mit dem Geräte-Token übereinstimmt, klicken Sie auf das Gerät und klicken Sie auf **Gerät registrieren** in der Aktionsleiste aus.
   1. Wenn der Registrierungs-Code mit dem Code auf der Registerkarte **Geräteregistrierung** im Screens-Player übereinstimmt, klicken Sie in der Aktionsleiste auf **Validieren**.
      ![image](/help/user-guide/assets/multi-zone/multizone-img6.png)
   1. Geben Sie die **Titel** as **`Chrome-Device1`** und klicken **registrieren**.
   1. Klicks **Anzeige zuweisen** und klicken Sie auf den Pfad zur Gerätekonfiguration.

   >[!NOTE]
   >Wenn Sie versuchen, den Inhalt im Screens-Player anzuzeigen, klicken Sie unbedingt für jeden der Anzeige zugewiesenen Kanal im Kanal-Dashboard auf **Offline-Inhalt aktualisieren**.

### Anzeigen des Ergebnisses {#viewing-the-result}

Wenn Sie Mehrzonen-Layouts mit den vorhergehenden Schritten implementiert haben, wird die folgende Ausgabe angezeigt.

Überprüfen Sie den Screens-Player, um die Ausgabe zu sehen, in der der Inhalt in zwei verschiedenen Zonen angezeigt wird. Die linken und die rechten Zonen (beide verwenden eine eingebettete Sequenz als Komponente).

Der linke Bereich ist ein Sequenzkanal und der rechte Bereich enthält ein Video.

![new2-1](/help/user-guide/assets/multi-zone/Multi-gif.gif)
