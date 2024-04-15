---
title: Mehrzonen-Layout
description: Erfahren Sie, wie Sie Inhalte für mehrere Bereiche erstellen und verschiedene Assets wie Videos, Bilder und Text verwenden, die in einem einzigen Bildschirm in AEM Screens kombiniert werden können.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 901ed50e-d3f0-4c85-ad79-6c4595382759
source-git-commit: c440527b80a3899fd45ec2d20d8cb48ffe85f6f3
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 47%

---

# Mehrzonen-Layout {#multi-zone-layout}

Die folgende Seite beschreibt die Verwendung des Mehrzonen-Layouts und behandelt die folgenden Themen:

* Überblick
* Erstellen eines Mehrzonen-Layouts
* Voraussetzungen
* Verwenden einzelner Assets in einem oder mehreren Bereichen
* Verwenden sequenzieller Inhalte in einem oder mehreren Bereichen

## Überblick {#overview}

***Mehrzonen-Layout*** Ermöglicht die Erstellung von Inhalten mit mehreren Bereichen und die Verwendung verschiedener Assets wie Videos, Bilder und Text, die in einem einzigen Bildschirm kombiniert werden können. Sie können Bilder, Videos und Text einblenden, sodass alles miteinander verschmelzen und ein intuitives digitales Erlebnis schaffen kann.

Abhängig von den Projektanforderungen sind ggf. mehrere Bereiche in einem Kanal erforderlich, die dann zusammen als Einheit bearbeitet werden. Beispiel: eine Produktsequenz mit entsprechendem Social-Media-Feed, die in drei separaten Zonen auf einem einzigen Kanal läuft.

>[!NOTE]
>In Mehrzonen-Kanälen wird die Zeitplanung auf Asset-Ebene aufgrund potenzieller Konflikte und unbeabsichtigten Verhaltens nicht empfohlen. Wenn eine Planung auf Asset-Ebene erforderlich ist, wird empfohlen, einen separaten Sequenzkanal zu erstellen und innerhalb dieses Kanals eine Planungslogik anzuwenden. Betten Sie als Nächstes den Sequenzkanal in den Mehrzonen-Kanal ein.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktion beginnen, sollten Sie über grundlegende Kenntnisse in folgenden Bereichen verfügen:

* [Erstellen eines AEM Screens-Projekts](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/creating-a-screens-project)
* [Erstellen einer Anzeige](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/managing-displays)
* [Zuweisen eines Kanals zu einem Display](/help/user-guide/channel-assignment.md)

## Erstellen eines Mehrzonen-Layouts {#creating-multi-zone-layout}

Beim Erstellen eines Kanals können Sie verschiedene Vorlagen verwenden, um Bereiche in Ihrem Kanal zu erstellen. Sie können ein einzelnes Bild, Video oder einen eingebetteten Kanal hinzufügen, sodass mehrere Assets in einer Sequenz angezeigt werden können.

**Erstellen eines Kanals**

1. Wählen Sie den Adobe Experience Manager-Link (oben links) und dann **Screens** aus. Sie haben auch die Möglichkeit, direkt zur folgenden URL zu wechseln: `http://localhost:4502/screens.html/content/screens`.
1. Navigieren Sie zum Ordner **Kanäle** und klicken Sie in der Aktionsleiste auf **Erstellen**.

1. Wählen Sie im Assistenten **Erstellen** die Option **1x2-Splitscreen-Kanal**.

1. Klicken Sie auf **Weiter** und geben Sie unter **Titel** den Wert **MultiZone** ein.

1. Klicken Sie auf **Erstellen**, um die Kanalerstellung abzuschließen.

### Verwenden einzelner Assets in einem oder mehreren Bereichen {#using-single-assets-in-one-or-more-zones}

Sie können einzelne Assets wie ein Bild oder ein Video in allen Bereichen verwenden. Gehen Sie zur Implementierung wie folgt vor:

1. **Hinzufügen von Inhalten zum Kanal**

   1. Navigieren Sie zu **Bereiche** > **Kanäle**> **MultiZone**.
   1. Wählen Sie die **MultiZone** channel und click **Bearbeiten** in der Aktionsleiste aus.

1. **Hinzufügen von Bildern zum Kanal**

   Um ein einzelnes Bild oder Video in zwei Bereichen abzuspielen, ziehen Sie das Bild einfach per Drag-and-Drop in jeden Bereich des Kanal-Editors, wie in der folgenden Abbildung dargestellt:

   ![image](/help/user-guide/assets/multi-zone/multizone-img3.png)

### Verwenden sequenzieller Inhalte in einem oder mehreren Bereichen {#using-sequenced-content-in-one-or-more-zones}

Wenn Sie möchten, dass eine Bildsequenz und ein Video in verschiedenen Bereichen angezeigt werden, führen Sie die folgenden Schritte aus, um mehr zu erfahren.

1. **Erstellen eines Kanalordners**

   1. Navigieren Sie zu **Bereiche** > **MultiZone** > **Kanäle** und klicken **Erstellen** in der Aktionsleiste aus.
   1. Wählen Sie im Assistenten **Erstellen** die Option **Kanalordner** aus und klicken Sie auf **Weiter**.
   1. Geben Sie **EmbeddedChannels** als Titel ein und klicken Sie auf **Erstellen**.

   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Hinzufügen von zwei weiteren Kanälen zum Kanalordner**

   1. Navigieren Sie zu **Bereiche** > **Kanäle** > **EmbeddedChannels** und klicken **Erstellen** in der Aktionsleiste aus.
   1. Auswählen **Sequenzkanal** aus dem **Erstellen** Assistent zum Erstellen eines Kanals mit dem Titel **`Zone1`**.
   1. Auswählen **`Zone1`** und klicken **Bearbeiten** in der Aktionsleiste aus.
   1. Ziehen Sie einige Bilder in diesen Kanal.
   1. Erstellen Sie auf ähnliche Weise einen weiteren Sequenzkanal mit dem Titel **`Zone2`** in **EmbeddedChannels** Ordner.
   1. Ziehen Sie einige Bilder per Drag-and-Drop in diesen Kanal.

   Die folgende Abbildung zeigt die Kanäle **`Zone1`** und **`Zone2`**:

   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

   Die Bilder, die dem Editor von **`Zone1`** Sequenzkanal sind unten dargestellt:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img4.png)

   Das Video, das zum Editor von **`Zone2`** Sequenzkanal ist unten dargestellt:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img5.png)

1. **Hinzufügen eingebetteter Sequenzen (Komponenten) zum Hauptkanal (MultiZone)**

   1. Navigieren Sie zu **Bereiche** > **Kanäle** > **MultiZone**.
   1. Klicks **Bearbeiten** in der Aktionsleiste aus.
   1. Ziehen Sie die Komponente **Eingebettete Sequenz** per Drag-and-Drop in beide Bereiche.
   1. Wählen Sie die eingebettete Sequenz in einem der Bereiche aus.
   1. Klicken Sie auf das Symbol **Konfigurieren** (Schraubenschlüssel), um eine der eingebetteten Sequenzen im Editor zu konfigurieren.
   1. Wählen Sie den Kanalpfad als **Bereiche** > **Kanäle** > **EmbeddedChannels** > **`Zone1`**, wie in der folgenden Abbildung dargestellt.
   1. Fügen Sie auf ähnliche Weise **`Zone2`** in eine andere eingebettete Sequenzkomponente im Editor.

      ![Bild](/help/user-guide/assets/multi-zone/multizone-3.png)

### Erstellen eines Standorts und eines Displays {#creating-location}

Erstellen Sie einen Ort und eine Anzeige, damit Sie den Inhalt im AEM Screens-Player anzeigen können.

1. **Erstellen eines Standorts**

   1. Navigieren Sie zu **Bereiche** > **Standorte** Ordner.
   1. Wählen Sie die **Standorte** Ordner und auswählen **Erstellen** in der Aktionsleiste aus.
   1. Auswählen **Standort** aus dem **Erstellen** Assistent und wählen Sie **Nächste**.
   1. Geben Sie die **Titel** as **SanJose** und wählen **Erstellen**.

1. **Erstellen einer Anzeige**

   1. Navigieren Sie zu **Bereiche** > **Standorte** Ordner.
   1. Wählen Sie die **SanJose** Standort und Auswahl **Erstellen** in der Aktionsleiste aus.
   1. Auswählen **Anzeige** aus dem **Erstellen** Assistent und wählen Sie **Nächste**.
   1. Geben Sie die **Titel** as **Lobby** und wählen **Erstellen**.

### Zuweisen von Kanälen zur Anzeige {#channel-channel}

Weisen Sie die Kanäle dem Display zu, um den Inhalt anzuzeigen. Gehen Sie wie folgt vor, um einer Anzeige einen Kanal zuzuweisen.

1. **Zuweisen eines Kanals zur Anzeige**

   1. Navigieren Sie zu **Bereiche** > **Standorte** > **SanJose**> **Lobby**.
   1. Wählen Sie die **Lobby** anzeigen und auswählen **Kanal zuweisen** in der Aktionsleiste aus.
   1. Geben Sie den Pfad zum Kanal **MultiZone** unter **Kanalpfad** ein.
   1. Wählen Sie unter **Unterstützte Ereignisse** die Optionen **Erster Ladevorgang**, **Bildschirm bei Untätigkeit** und **Benutzerinteraktion**.
   1. Wählen Sie **Speichern** aus.

      ![Bild](/help/user-guide/assets/multi-zone/multizone-img9.png)
   1. Ebenso müssen Sie die beiden anderen eingebetteten Kanäle (**`Zone1`** und **`Zone2`**), um diese Anzeige anzuzeigen.
   1. Nachdem Sie alle drei Kanäle dem **Lobby** angezeigt werden, sollten Sie die zugewiesenen Kanäle im Anzeigen-Dashboard anzeigen können.

      ![Bild](/help/user-guide/assets/multi-zone/multizone-img8.png)


      >[!IMPORTANT]
      >
      >Nachdem Sie den Hauptkanal zugewiesen haben (in diesem Fall **MultiZone**) zur Anzeige hinzugefügt werden, müssen die beiden anderen eingebetteten Kanäle zugewiesen werden. **`Zone1`** und **`Zone2`** auch zur gleichen Anzeige.

### Registrieren des Geräts {#registering-device}

Wenn Sie einen Standort und eine Anzeige eingerichtet haben, führen Sie die folgenden Schritte aus, um das Gerät zu registrieren und dem Gerät eine Anzeige zuzuweisen.

1. **Registrieren des Geräts**

   1. Navigieren Sie zu **Bereiche** > **Geräte** Ordner.
   1. Wählen Sie die **Geräte** Ordner und auswählen **Geräte-Manager** in der Aktionsleiste aus.
   1. Auswählen **Geräteregistrierung** und wählen Sie das ausstehende Gerät aus der Liste aus.

      >[!NOTE]
      > Der Titel des Geräts muss mit dem Geräte-Token (Feld **Token**) übereinstimmen, das auf der Registerkarte **Geräteregistrierung** angezeigt wird.

   1. Wenn der Titel mit dem Geräte-Token übereinstimmt, wählen Sie das Gerät aus und wählen Sie **Gerät registrieren** in der Aktionsleiste aus.
   1. Wenn der Registrierungscode mit dem Code im Screens-Player übereinstimmt **Geräteregistrierung** Registerkarte auswählen **Bestätigen** in der Aktionsleiste aus.
      ![Bild](/help/user-guide/assets/multi-zone/multizone-img6.png)
   1. Geben Sie die **Titel** as **`Chrome-Device1`** und wählen **registrieren**.
   1. Wählen Sie **Anzeige zuweisen** und dann den Pfad zur Gerätekonfiguration.

   >[!NOTE]
   >Wenn Sie versuchen, den Inhalt im Screens-Player anzuzeigen, wählen Sie **Offline-Inhalt aktualisieren** aus dem Kanal-Dashboard für jeden der Anzeige zugewiesenen Kanal.

### Anzeigen des Ergebnisses {#viewing-the-result}

Wenn Sie Mehrzonen-Layouts mithilfe der vorhergehenden Schritte implementieren, wird die folgende Ausgabe angezeigt.

Überprüfen Sie den Screens-Player, damit Sie die Ausgabe anzeigen können, in der der Inhalt in zwei verschiedenen Bereichen angezeigt wird. Die linken und die rechten Zonen (beide verwenden eine eingebettete Sequenz als Komponente).

Der linke Bereich ist ein Sequenzkanal und der rechte Bereich enthält ein Video.

![new2-1](/help/user-guide/assets/multi-zone/Multi-gif.gif)
