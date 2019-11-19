---
title: 'Erstellen und Verwalten von Anzeigen '
seo-title: Verwalten von Anzeigen
description: Folgen Sie dieser Seite, um sich zu informieren, wie eine neue Anzeige bzw. eine neue Gerätekonfiguration erstellt wird. Außerdem können Sie sich über das Anzeigen-Dashboard informieren.
seo-description: Folgen Sie dieser Seite, um sich zu informieren, wie eine neue Anzeige bzw. eine neue Gerätekonfiguration erstellt wird. Außerdem können Sie sich über das Anzeigen-Dashboard informieren.
uuid: dfde0740-5c8b-4e6c-bc83-bf8fbb31a16a
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: f8e2e7a3-f3a1-4c35-b055-166752c3fb86
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Erstellen und Verwalten von Anzeigen{#creating-and-managing-displays} 

Eine Anzeige ist eine virtuelle Gruppierung von Bildschirmen, die normalerweise nebeneinander angeordnet sind. Die Installation einer Anzeige ist in der Regel permanent. Dies ist das Objekt, mit dem Inhaltsautoren arbeiten und das sie immer als logische und nicht als physische Anzeige bezeichnen.

Nachdem Sie einen Ort erstellt haben, müssen Sie eine neue Anzeige für Ihren Ort erstellen.

Auf dieser Seite wird gezeigt, wie Anzeigen für Screens erstellt und verwaltet werden.

**Voraussetzungen**:

* [Konfigurieren und Bereitstellen von Screens](configuring-screens-introduction.md) 
* [Bildschirmprojekt erstellen und verwalten](creating-a-screens-project.md)
* [Kanäle erstellen und verwalten](managing-channels.md)
* [Orte erstellen und verwalten](managing-locations.md)

## Erstellen einer neuen Anzeige {#creating-a-new-display}

>[!NOTE]
>
>Sie müssen einen Ort erstellen, bevor Sie eine Anzeige erstellen können. To see how to create a location, see [Create and Manage Locations](managing-locations.md) for more information.

Um eine neue Anzeige an Ihrem Ort zu erstellen, gehen Sie wie folgt vor:

1. Navigate to the appropriate location, for example `http://localhost:4502/screens.html/content/screens/TestProject`.
1. Wählen Sie Ihren Speicherorte-Ordner aus und tippen/klicken Sie neben dem Pluszeichen in der Aktionsleiste auf **Erstellen**. Ein Assistent wird geöffnet.
1. Select **Display** from the **Create** wizard and click **Next**.

1. Enter **Name** and **Title** for your display location.

1. Under the **Display** tab, choose the details of the Layout. Choose the desired **Resolution** (example as, as **Full HD**). Darüber hinaus können Sie die Anzahl der Geräte horizontal und vertikal auswählen.

1. Klicken Sie auf **Erstellen**.

The display (*StoreDisplay*) is created and added to the location (*SanJose*).

![display](assets/display.gif)

Nachdem Sie die Anzeige positioniert haben, besteht der nächste Schritt darin, für die Anzeige eine Gerätekonfiguration zu erstellen. Folgen Sie dem nachstehenden Abschnitt, um eine neue Gerätekonfiguration zu erstellen.

>[!NOTE]
>
>**Der nächste Schritt**:
>
>Wenn Sie eine Anzeige für einen Ort erstellen, müssen Sie Ihrer Anzeige einen Kanal zuweisen, um den Inhalt verwenden zu können.
>
>See [Assign Channels](channel-assignment.md) section to learn how to assign a channel to the display.

## Erstellen einer neuen Gerätekonfiguration {#creating-a-new-device-config}

Eine Gerätekonfiguration fungiert als Platzhalter für ein digitales Beschilderungsgerät, das noch nicht installiert ist.

Gehen Sie wie folgt vor, um eine neue Gerätekonfiguration zu erstellen: 

1. Navigieren Sie beispielsweise zur entsprechenden Anzeige `http://localhost:4502/screens.html/content/screens/TestProject/locations/newlocation`.
1. Wählen Sie Ihren Anzeigenordner aus und tippen/klicken Sie in der Aktionsleiste auf **Dashboard anzeigen**.
1. Tap/click the **+ Add Device Config** on the top right of the **Devices** panel.

1. Select the **Device Config** as the required template as and tap/click **Next**.

1. Geben Sie die entsprechenden Eigenschaften ein und tippen/klicken Sie auf **Erstellen**.

The device config is created and added to the current display (in the following demonstration, the new device config is *DeviceConfig*).

![deviceconfig](assets/deviceconfig.gif)

Nach der Erstellung der Gerätekonfiguration für Ihre Anzeige am Ort besteht der nächste Schritt darin, Ihrer Anzeige einen Kanal zuzuweisen.

>[!NOTE]
>
>Nach der Erstellung der Gerätekonfiguration für Ihre Anzeige am Ort besteht der nächste Schritt darin, Ihrer Anzeige einen Kanal zuzuweisen.
>
>As shown in the figure below, if the device config is displayed as unassigned in the **DEVICES** pannel, if no channel is assigned to that particular device config.
>
>Sie sollten Vorkenntnisse im Erstellen und Verwalten von Kanälen haben. Weitere Informationen finden Sie unter Kanäle [erstellen und verwalten](managing-channels.md) .

![chlimage_1-9](assets/chlimage_1-9.png)

## Anzeigen-Dashboard {#display-dashboard}

Das Anzeigen-Dashboard bietet verschiedene Bedienfelder zum Verwalten von Anzeigegeräten und Gerätekonfigurationen für Ihr Gerät.

![screen_shot_2018-08-23at42810pm](assets/screen_shot_2018-08-23at42810pm.png)

>[!NOTE]
>
>Sie können die Dashboard-Listen auswählen und Massenaktionen für Elemente auslösen, statt jedes einzelne Element durchzugehen.
>
>Beispielsweise zeigt die folgende Abbildung, wie Sie mehrere Kanäle im Anzeigen-Dashboard auswählen können.

![cqdoc9456](assets/cqdoc9456.gif)

### Fenster „Anzeigeinformationen“{#display-information-panel}

Im Fenster **ANZEIGEINFORMATIONEN** werden die Anzeigeeigenschaften angezeigt.

Click on the (**...**) in the top right corner in the **DISPLAY INFORMATION **panel to view the properties and preview the display.

![chlimage_1-10](assets/chlimage_1-10.png)

#### Anzeigen von Eigenschaften {#viewing-properties}

Klicken Sie auf **Eigenschaften**, um die Eigenschaften Ihrer Anzeige anzuzeigen oder zu ändern.

Additionally, you can adjust the event timer value for your interactive channel in **Idle timeout **property under **Display** tab. Der Standardwert ist auf *300 Sekunden* eingestellt.

Use **CRXDE Lite**, to access the **idleTimeout** property, that is, `http://localhost:4502/crx/de/index.jsp#/content/screens/we-retail/locations/demo/flagship/single/jcr%3Acontent/channels` .

![chlimage_1-1](assets/chlimage_1-1.gif)

### Fenster „Zugewiesene Kanäle“{#assigned-channels-panel}

Das Fenster **ZUGEWIESENE KANÄLE** zeigt die zugewiesenen Kanäle des Geräts an.

![chlimage_1-11](assets/chlimage_1-11.png)

### Fenster „Geräte“{#devices-panel}

Das Fenster **GERÄTE** bietet Informationen zu den Gerätekonfigurationen.

Click on the (**...**) in the top right corner in the **DEVICES **panel to add device configs and update devices.

![chlimage_1-12](assets/chlimage_1-12.png)

Klicken Sie außerdem auf die Gerätekonfiguration, um Eigenschaften anzuzeigen, ein Gerät zuzuweisen oder es vollständig zu löschen.

![chlimage_1-13](assets/chlimage_1-13.png)

#### Die nächsten Schritte {#the-next-steps}

Nachdem Sie eine Anzeige für Ihren Ort erstellt haben, müssen Sie Ihrer Anzeige einen Kanal zuweisen.

See [Assign Channels](channel-assignment.md) for more details.
