---
title: Spracherkennung in AEM Screens
description: Auf der Seite werden die Spracherkennungsfunktionen in AEM Screens beschrieben.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 6cf0aa9f-7bac-403f-a113-51727c1f5374
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 90%

---

# Spracherkennung in AEM Screens {#voice-recognition}

>[!IMPORTANT]
>
>**Wichtige Datenschutzinformationen**
>
>Beachten Sie bei der Verwendung der Spracherkennungsfunktion alle für Ihre Region geltenden rechtlichen und ethischen Richtlinien (insbesondere die sichtbare Benachrichtigung der Endbenutzer, dass der Player die Spracherkennung verwendet). Adobe Inc. erhält, speichert und verarbeitet keine der sprachbezogenen Informationen. Die AEM Screens-Player verwenden die standardmäßige Web Speech API, die in die Browser-Engine integriert ist. Hinter den Kulissen sendet diese API eine Wellenform des von Ihnen Gesprochenen an die Server von Google, um es von Sprache in Text umzuwandeln. Dieser Text wird vom Player mit den konfigurierten Schlüsselwörtern abgeglichen.
>
>Siehe [Google-Datenschutz-Whitepaper zur Web Speech API](https://www.google.com/chrome/privacy/whitepaper.html#speech) für weitere Details.


Die Spracherkennungsfunktion ermöglicht Inhaltsänderungen in einem AEM Screens-Kanal via Sprachinteraktionen.

Ein Inhaltsautor kann eine Anzeige so konfigurieren, dass sie sprachaktiviert ist. Diese Funktion soll Kunden die Möglichkeit geben, Sprache als Methode der Interaktion mit ihren Anzeigen zu verwenden. Einige ähnliche Anwendungsfälle umfassen das Auffinden von Produktempfehlungen in Geschäften oder das Bestellen von der Speisekarte in Gaststätten und Restaurants. Diese Funktion erhöht die Zugänglichkeit für Benutzer und kann das Kundenerlebnis erheblich verbessern.

>[!NOTE]
>Die Player-Hardware muss Spracheingabegeräte wie Mikrofone unterstützen.

## Implementieren der Spracherkennung {#implementing}

>[!IMPORTANT]
> Die Spracherkennungsfunktion ist nur bei Chrome- und Windows-Playern verfügbar.

Um die Spracherkennung in Ihrem AEM Screens-Projekt zu implementieren, müssen Sie die Spracherkennung für die Anzeige aktivieren und jeden Kanal mit einem eindeutigen Tag verknüpfen, um einen Kanalübergang auszulösen.

Im folgenden Abschnitt wird beschrieben, wie Sie die Spracherkennungsfunktion in einem AEM Screens-Projekt aktivieren und verwenden können.

## Anzeigen von Inhalten im Vollbild- oder Splitscreen-Kanalschalter {#sequence-channel}

Bevor Sie die Funktion zur Spracherkennung verwenden, stellen Sie sicher, dass Sie ein Projekt und einen Kanal mit Inhalten für Ihr Projekt eingerichtet haben.

1. Im folgenden Beispiel sehen Sie ein Demoprojekt mit dem Namen **VoiceDemo** und drei Kanälen **Main**, **ColdDrinks** und **HotDrinks**.

   ![image](assets/voice-recognition/vr-1.png)

   >[!NOTE]
   >
   >Informationen zum Erstellen eines Kanals oder Hinzufügen von Inhalten zu einem Kanal finden Sie unter [Erstellen und Verwalten von Kanälen](/help/user-guide/managing-channels.md)

   Oder

   Sie können drei Sequenzkanäle **Main**, **ColdDrinks** und **HotDrinks** sowie einen zusätzlichen 1x2-Splitscreen-Kanal **SplitScreen** erstellen, wie in der Abbildung unten dargestellt.

   ![image](assets/voice-recognition/vr-emb-1.png)

1. Navigieren Sie zu jedem Kanal und fügen Sie Inhalt hinzu. Navigieren Sie beispielsweise zu **VoiceDemo** > **Kanäle** > **Main** und wählen Sie den Kanal aus. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen und den gewünschten Inhalt (Bilder/Videos) hinzuzufügen. Fügen Sie auf ähnliche Weise den Kanälen **ColdDrinks** und **HotDrinks** Inhalt hinzu.

   Die Kanäle enthalten nun Assets (Bilder), wie in den folgenden Abbildungen dargestellt.

   **Main**:

   ![image](assets/voice-recognition/vr-4.png)

   **ColdDrinks**:

   ![image](assets/voice-recognition/vr-3.png)

   **HotDrinks**:

   ![image](assets/voice-recognition/vr-2.png)

   Wenn Sie dem Projekt den Splitscreen-Kanal hinzugefügt haben, navigieren Sie zu **SplitScreen**, ziehen Sie zwei eingebettete Sequenzen per Drag-and-Drop und fügen Sie Pfade zu den Kanälen **ColdDrinks** und **HotDrinks** hinzu, wie in der Abbildung unten dargestellt.
   ![image](assets/voice-recognition/vr-emb-6.png)


### Festlegen von Tags für Kanäle {#setting-tags}

Nachdem Sie Ihren Kanälen Inhalte hinzugefügt haben, müssen Sie zu jedem Kanal navigieren und entsprechende Tags hinzufügen, die die Spracherkennung auslösen würden.

Gehen Sie wie folgt vor, um Ihrem Kanal Tags hinzuzufügen:

1. Navigieren Sie zu jedem Kanal und fügen Sie Inhalt hinzu. Navigieren Sie beispielsweise zu **VoiceDemo** > **Kanäle** > **Main** und wählen Sie den Kanal aus.

1. Klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   ![image](assets/voice-recognition/vr-5.png)

1. Navigieren Sie zur Registerkarte **Grundlagen** und wählen Sie ein bereits vorhandenes Tag aus dem Feld **Tags** aus oder erstellen Sie ein neues.

   Sie können entweder ein neues Tag erstellen, indem Sie einen neuen Namen für das Tag eingeben und die `return`-Taste drücken, wie in der folgenden Abbildung gezeigt:

   ![image](assets/voice-recognition/vr-6.png)

   Oder

   Sie können vorab Tags aus Ihrer AEM-Instanz für Ihr Projekt erstellen und diese ebenfalls auswählen. Nachdem Sie die unter [Erstellen von Tags](#creating-tags) erläuterten Schritte ausgeführt haben, können Sie das Tag an der gewünschten Stelle auswählen und dem Kanal hinzufügen, wie in der folgenden Abbildung dargestellt:

   ![image](assets/voice-recognition/vr-tag1.png)

1. Fügen Sie dem Kanal **HotDrinks** in ähnlicher Weise ein Tag mit dem Namen **heiß** hinzu.

1. Wenn Sie einen Splitscreen-Kanal verwenden, fügen Sie beide Tags (**hot** und **cold**) wie in der Abbildung unten dargestellt zu den Eigenschaften des Kanals **SplitScreen** hinzu.

   ![image](assets/voice-recognition/vr-emb-7.png)

1. Klicken Sie auf **Speichern und schließen**, wenn Sie fertig sind.


### Erstellen von Tags {#creating-tags}

Gehen Sie wie folgt vor, um Tags zu erstellen:

1. Navigieren Sie zu Ihrer AEM-Instanz.

1. Klicken Sie auf das Werkzeugsymbol > **Tagging**.
   ![Bild](assets/voice-recognition/vr-7.png)

1. Klicks **Erstellen** > **Namespace erstellen**.
   ![image](assets/voice-recognition/vr-tag3.png)

1. Geben Sie den Namen Ihres Projekts ein, z. B. **VoiceDemo**, und klicken Sie auf **Erstellen**.

1. Wählen Sie das Projekt **VoiceDemo** aus und klicken Sie in der Aktionsleiste auf **Tag erstellen**.
   ![image](assets/voice-recognition/vr-tag4.png)

1. Geben Sie den Namen Ihres Tags ein und klicken Sie auf **Senden**.
   ![image](assets/voice-recognition/vr-tag5.png)

Jetzt können Sie diese Tags in Ihrem AEM Screens-Projekt verwenden.

### Zuweisen eines Kanals zu einer Anzeige und Aktivieren der Spracherkennung {#channel-assignment}

1. Erstellen Sie eine Anzeige im Ordner **Standorte**, wie in der Abbildung unten dargestellt.

   ![image](assets/voice-recognition/vr-loc.png)

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md).

1. Weisen Sie die Kanäle **Main**, **ColdDrinks** und **HotDrinks** Ihrer Anzeige **LobbyDisplay** zu. Wenn Sie außerdem den Kanal **SplitScreen** für Ihr Projekt verwenden, stellen Sie sicher, dass Sie ihn auch der Anzeige zuweisen.

   >[!NOTE]
   >Wenn Sie einen Splitscreen-Kanal erstellt haben, weisen Sie Ihrer Anzeige den **SplitScreen**-Kanal zu.

1. Legen Sie beim Zuweisen des Kanals für jeden Kanal die folgenden Eigenschaften fest.

   | **Kanalname** | **Priorität** | **Unterstützte Ereignisse** |
   |---|---|---|
   | Main | 2 | Erster Ladevorgang, Bildschirm bei Untätigkeit, Timer |
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

Sobald die vorhergehenden Schritte abgeschlossen sind, können Sie Ihr Chrome-Gerät registrieren, um die Ausgabe anzusehen.

>[!NOTE]
>Siehe [Geräteregistrierung](device-registration.md) , um zu erfahren, wie Sie ein Gerät auf einem AEM Screens-Player registrieren.

**Gewünschte Ausgabe für den Sequenz-Kanal**

Der Kanal **Main** gibt seinen Inhalt wieder. Wenn Sie jedoch Wörter mit dem Keyword **heiß** verwenden, wie beispielsweise *ich möchte ein heißes Getränk*, beginnt der Kanal, den Inhalt des Kanals **HotDrinks** wiederzugeben.

Wenn Sie Wörter mit dem Keyword **kalt** verwenden, wie beispielsweise *Ich möchte etwas Kaltes*, beginnt der Kanal, den Inhalt des Kanals **ColdDrinks** wiederzugeben.

**Gewünschte Ausgabe für den Splitscreen-Kanal**

Der Kanal **Main** gibt seinen Inhalt wieder. Wenn Sie jedoch Wörter mit dem Keyword **heiß** und dem Keyword **kalt** zusammen verwenden, wie beispielsweise *Kann ich die Karte für warme und kalte Getränke sehen*, beginnt der Kanal, die Inhalte des **SplitScreen**-Kanals wiederzugeben. Wenn Sie *Zurück zum Hauptmenü* sagen, schaltet die Anzeige zurück zum Hauptkanal (Main).
