---
title: Spracherkennung in AEM Screens
description: Auf der Seite werden die Spracherkennungsfunktionen in AEM Screens beschrieben.
translation-type: tm+mt
source-git-commit: a9e13dca2ed8ac667356780db25cbe7e0c81c1c5
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 38%

---


# Spracherkennung in AEM Screens {#voice-recognition}

>[!IMPORTANT]
>
>**Wichtige Datenschutzinformationen**
>
>Bei Verwendung der Spracherkennungsfunktion folgen Sie allen geltenden rechtlichen und ethischen Richtlinien für Ihre Region (einschließlich, aber nicht darauf beschränkt, Endbenutzern einen sichtbaren Hinweis darauf zu geben, dass der Player die Spracherkennung verwendet). Adobe Inc. empfängt, speichert oder verarbeitet keine der sprachbezogenen Informationen. Die AEM Screens-Player verwenden die Standard-Web-Sprache-API, die in der Browsing-Engine integriert ist. Hinter den Kulissen sendet diese API eine Wellenform Ihrer Sprache an die Server von Google zur Konvertierung von Sprache in Text, und dieser Text wird vom Player mit den konfigurierten Suchbegriffen abgeglichen.
>
>Weitere Informationen finden Sie im Whitepaper zum Datenschutz von [Google über die Web-Sprach-API](https://www.google.com/chrome/privacy/whitepaper.html#speech) .


Die Spracherkennungsfunktion ermöglicht die Inhaltsänderung in einem AEM Screens-Kanal, der durch Sprachinteraktion gesteuert wird.

Ein Inhaltsautor kann eine Anzeige so konfigurieren, dass sie sprachaktiviert ist. Diese Funktion soll Kunden die Möglichkeit geben, Sprache als Methode der Interaktion mit ihren Displays zu verwenden. Einige ähnliche Anwendungsfälle umfassen das Auffinden von Produktempfehlungen in Geschäften, das Bestellen von Menüpunkten in Restaurants und Restaurants. Diese Funktion verbessert die Barrierefreiheit für Benutzer und kann die Kundenerfahrung erheblich verbessern.

>[!NOTE]
>Die Player-Hardware muss Spracheingabe-Geräte wie Mikrofone unterstützen.

## Implementieren der Spracherkennung {#implementing}

>[!IMPORTANT]
> Die Spracherkennungsfunktion ist nur für Chrome OS- und Windows-Player verfügbar.

Um die Spracherkennung in Ihrem AEM Screens-Projekt zu implementieren, müssen Sie die Spracherkennung für die Anzeige aktivieren und jeden Kanal mit einem eindeutigen Tag verknüpfen, um eine Kanal-Transition auszulösen.

Im folgenden Abschnitt wird beschrieben, wie Sie die Spracherkennungsfunktion in einem AEM Screens-Projekt aktivieren und verwenden können.

## Anzeigen von Inhalten im Vollbildmodus oder in einem geteilten Kanal-Switch {#sequence-channel}

Bevor Sie die Funktion zur Spracherkennung verwenden, stellen Sie sicher, dass Sie ein Projekt und einen Kanal mit Inhalten für Ihr Projekt eingerichtet haben.

1. Im folgenden Beispiel sehen Sie ein Demoprojekt mit dem Namen **VoiceDemo** und drei Kanälen **Main**, **ColdDrinks** und **HotDrinks**.

   ![image](assets/voice-recognition/vr-1.png)

   >[!NOTE]
   >
   >Informationen zum Erstellen eines Kanals oder Hinzufügen von Inhalten zu einem Kanal finden Sie unter [Erstellen und Verwalten von Kanälen](/help/user-guide/managing-channels.md)

   Oder

   Sie können drei Sequenz-Kanal **Main**, **ColdDrinks** und **HotDrinks** sowie einen weiteren 1x2 Split Screens-Kanal **SplitScreen** erstellen, wie in der folgenden Abbildung dargestellt.

   ![image](assets/voice-recognition/vr-emb-1.png)

1. Navigieren Sie zu jedem Kanal und fügen Sie Inhalt hinzu. Navigieren Sie beispielsweise zu **VoiceDemo** > **Kanäle** > **Main** und wählen Sie den Kanal aus. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen und den gewünschten Inhalt (Bilder/Videos) hinzuzufügen. Fügen Sie auf ähnliche Weise den Kanälen **ColdDrinks** und **HotDrinks** Inhalt hinzu.

   Die Kanäle enthalten jetzt Assets (Bilder), wie in den folgenden Abbildungen dargestellt.

   **Main**:

   ![image](assets/voice-recognition/vr-4.png)

   **ColdDrinks**:

   ![image](assets/voice-recognition/vr-3.png)

   **HotDrinks**:

   ![image](assets/voice-recognition/vr-2.png)

   Wenn Sie dem Projekt den Kanal &quot;Geteilte Bildschirme&quot;hinzugefügt haben, navigieren Sie zu &quot; **SplitScreen** &quot;und ziehen Sie zwei eingebettete Sequenzen per Drag &amp; Drop und fügen Sie Pfade zu den Kanälen &quot; **ColdDrinks** &quot;und &quot; **HotDrinks** &quot;hinzu, wie in der Abbildung unten dargestellt.
   ![image](assets/voice-recognition/vr-emb-6.png)


### Festlegen von Tags für Kanäle {#setting-tags}

Nachdem Sie Ihren Kanälen Inhalte hinzugefügt haben, müssen Sie zu jedem Kanal navigieren und entsprechende Tags hinzufügen, die die Spracherkennung auslösen würden.

Gehen Sie wie folgt vor, um Ihrem Kanal Tags hinzuzufügen:

1. Navigieren Sie zu jedem Kanal und fügen Sie Inhalt hinzu. Navigieren Sie beispielsweise zu **VoiceDemo** > **Kanäle** > **Main** und wählen Sie den Kanal aus.

1. Klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   ![image](assets/voice-recognition/vr-5.png)

1. Navigieren Sie zur Registerkarte **Grundlagen** und wählen Sie ein bereits vorhandenes Tag aus dem Feld **Tags** aus oder erstellen Sie ein neues.

   Sie können entweder ein neues Tag erstellen, indem Sie einen neuen Namen für das Tag eingeben und die `return` Eingabetaste drücken, wie in der folgenden Abbildung gezeigt:

   ![image](assets/voice-recognition/vr-6.png)

   Oder

   Sie können Tags auch zuvor aus Ihrer AEM für Ihr Projekt erstellen und diese auswählen. Nachdem Sie die unter [Erstellen von Tags](#creating-tags)erläuterten Schritte ausgeführt haben, können Sie das Tag an der gewünschten Stelle auswählen und dem Kanal hinzufügen, wie in der folgenden Abbildung dargestellt:

   ![image](assets/voice-recognition/vr-tag1.png)

1. Fügen Sie entsprechend dem Kanal **HotDrinks** das Tag **hot** hinzu.

1. Wenn Sie einen Kanal für geteilte Bildschirme verwenden, fügen Sie beide Tags (**hot** und **old**) wie in der Abbildung unten dargestellt zu den Eigenschaften des **SplitScreen** -Kanals hinzu.

   ![image](assets/voice-recognition/vr-emb-7.png)

1. Klicken Sie auf **Speichern und schließen**, sobald Sie fertig sind.


### Erstellen von Tags {#creating-tags}

Gehen Sie wie folgt vor, um Tags zu erstellen:

1. Navigieren Sie zu Ihrer AEM Instanz.

1. Klicken Sie auf das Symbol Werkzeuge —> **Tagging**.
   ![image](assets/voice-recognition/vr-7.png)

1. Click **Create** --> **Create Namespace**.
   ![image](assets/voice-recognition/vr-tag3.png)

1. Geben Sie den Namen Ihres Projekts ein, z. B. **VoiceDemo** , und klicken Sie auf **Erstellen**.

1. Select the **VoiceDemo** project and click **Create Tag** from the action bar.
   ![image](assets/voice-recognition/vr-tag4.png)

1. Geben Sie den Namen Ihres Tags ein und klicken Sie auf **Senden**.
   ![image](assets/voice-recognition/vr-tag5.png)

Jetzt können Sie diese Tags in Ihrem AEM Screens-Projekt verwenden.

### Zuweisen von Kanal zu einer Anzeige und Aktivieren der Spracherkennung {#channel-assignment}

1. Erstellen Sie eine Anzeige im Ordner **Standorte**, wie in der Abbildung unten dargestellt.

   ![image](assets/voice-recognition/vr-loc.png)

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md).

1. Weisen Sie die Kanäle **Main**, **ColdDrinks** und **HotDrinks** Ihrer Anzeige **LobbyDisplay** zu. Wenn Sie außerdem den **SplitScreen** -Kanal für Ihr Projekt verwenden, stellen Sie sicher, dass Sie ihn auch der Anzeige zuweisen.

   >[!NOTE]
   >Wenn Sie einen Kanal für einen geteilten Bildschirm erstellt haben, weisen Sie dem Bildschirm den Kanal **SplitScreen** zu.

1. Legen Sie beim Zuweisen des Kanals für jeden Kanal die folgenden Eigenschaften fest.

   | **Kanalname** | **Priorität** | **Unterstützte Ereignisse** |
   |---|---|---|
   | Allgemein | 2 | Initial Load, Idle Screen, Timer |
   | HotDrinks | 1 | Benutzerinteraktion |
   | ColdDrinks | 1 | Benutzerinteraktion |
   | SplitScreen | 1 | Benutzerinteraktion |

   >[!NOTE]
   >
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md).

1. Nachdem Sie einer Anzeige Kanäle zugewiesen haben, navigieren Sie zu **LobbyDisplay** und wählen Sie die Anzeige aus. Wählen Sie in der Aktionsleiste **Eigenschaften** aus.

1. Navigieren Sie zur Registerkarte **Anzeige** und aktivieren Sie die Option **Sprachaktiviert** unter **Inhalt**.

   ![image](assets/voice-recognition/vr-disp.png)

   >[!IMPORTANT]
   >Die Spracherkennungsfunktion muss von der Anzeige aus aktiviert werden.

### Anzeigen von Inhalten im Chrome-Player {#viewing-content}

Nach Abschluss der obigen Schritte können Sie Ihr Chrome-Gerät registrieren, um die Ausgabe Ansicht.

>[!NOTE]
>Informationen zum Registrieren eines Geräts auf einem AEM Screens-Player finden Sie unter [Geräteregistrierung](device-registration.md).

**Gewünschte Ausgabe für Sequence Kanal**

Der **Main** Kanal spielt seinen Inhalt, aber wenn Sie Wörter mit Suchbegriff **heiß** , wie *ich möchte ein warmes Getränk*, den Kanal Beginn spielen den Inhalt des **HotDrinks** Kanal.

Ebenso, wenn Sie Wörter mit einem Suchbegriff **kalt** , wie *ich gerne hätte etwas kalt*, der Kanal Beginn spielen den Inhalt des **ColdDrinks** Kanal.

**Gewünschte Ausgabe für Kanal &quot;Geteilte Bildschirme&quot;**

Der **Main** -Kanal spielt seinen Inhalt ab, aber wenn Sie Wörter mit Stichwörtern **heiß** und **kalt** zusammen verwenden, wie *ich möchte, dass das Menü für warme und kalte Getränke* angezeigt wird, spielen die Kanal Beginn den Inhalt des **SplitScreen** -Kanals. Wenn Sie *zum Hauptmenü* zurückkehren, wird der Kanal wieder angezeigt.





