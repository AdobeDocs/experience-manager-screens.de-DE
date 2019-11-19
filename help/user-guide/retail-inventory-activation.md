---
title: Zielgerichtete Aktivierung des Einzelhandelsinventars
seo-title: Zielgerichtete Aktivierung des Einzelhandelsinventars
description: Dieser Verwendungsfall zeigt den Lagerbestand für drei verschiedene farbige Pullover. Je nachdem, wie viele Sweatshirts auf Lager vorhanden sind, die in Google Sheets aufgezeichnet werden, wird das Bild (rot, grün oder blau) mit der höchsten Zahl auf dem Bildschirm angezeigt.
seo-description: Dieser Verwendungsfall zeigt den Lagerbestand für drei verschiedene farbige Pullover. Je nachdem, wie viele Sweatshirts auf Lager vorhanden sind, die in Google Sheets aufgezeichnet werden, wird das Bild (rot, grün oder blau) mit der höchsten Zahl auf dem Bildschirm angezeigt.
uuid: 8e7faa65-b004-42b3-8865-4f71eb5dc1b1
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 70147920-5bdb-401c-884e-51d268d40585
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Zielgerichtete Aktivierung des Einzelhandelsinventars {#retail-inventory-targeted-activation}

Im folgenden Anwendungsfall werden drei verschiedene Bilder basierend auf den Werten in Ihrem Google Sheet veranschaulicht.

## Beschreibung {#description}

Dieser Verwendungsfall zeigt den Lagerbestand für drei verschiedene farbige Pullover. Je nachdem, wie viele Sweatshirts auf Lager vorhanden sind, die in Google Sheets aufgezeichnet werden, wird das Bild (rot, grün oder blau) mit der höchsten Zahl auf dem Bildschirm angezeigt.

Für diesen Verwendungsfall wird der Pullover Rot, Grün oder Blau basierend auf der höchsten verfügbaren Anzahl an Pullovern auf Ihrem Bildschirm angezeigt.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der Targeting-Aktivierung für den Handel beginnen, müssen Sie lernen, wie Sie ***Data Store***, die ***Zielgruppensegmentierung*** und das Targeting für Kanäle ***in einem AEM Screens-Projekt*** aktivieren.

Detaillierte Informationen finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) .

## Grundfluss {#basic-flow}

Gehen Sie wie folgt vor, um den Anwendungsfall für die Aktivierung des Einzelhandelsbestands zu implementieren:

1. **Füllen der Google-Blätter**

   1. Navigieren Sie zum Google-Sheet "ContextHubDemo".
   1. Fügen Sie drei Spalten (Rot, Grün und Blau) mit entsprechenden Werten für drei verschiedene Sweatshirts hinzu.
   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Konfigurieren der Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** unter **[Konfigurieren von ContextHub auf der Seite "AEM Screens](configuring-context-hub.md)** ".

   1. Fügen Sie drei neue Segmente **für_Rot**, **für_Grün** und **für_Blau** hinzu.

   1. Wählen Sie **For_Red** und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   1. Ziehen Sie den **Vergleich per Drag &amp; Drop: Eigenschaft - Eigenschaft** des Editors und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im Namen der **Voreigenschaft**

   1. Wählen Sie den **Operator** als **größer als **aus dem Dropdownmenü aus.

   1. Wählen Sie **Datentyp** als **Zahl**

   1. Wählen Sie **googlesheets/value/1/1** aus der Dropdownliste unter Name der **zweiten Eigenschaft**

   1. Drag &amp; Drop **weiterer Vergleich: Eigenschaft - Eigenschaft **im Editor und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im Namen der **Voreigenschaft**

   1. Wählen Sie den **Operator** als **größer als **aus dem Dropdownmenü aus.

   1. **Datentyp** als **Nummer auswählen**

   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste unter Name der **zweiten Eigenschaft**
   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Bearbeiten Sie ähnliche Regeln und fügen Sie sie dem Segment **For_Blue** hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Bearbeiten Sie ähnliche Regeln und fügen Sie Vergleichseigenschaftsregeln zum Segment** For_Green **hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   >
   >Sie werden feststellen, dass Daten für Segmente **For_Green** und **For_Green** im Editor nicht aufgelöst werden können, da nur der erste Vergleich gemäß den Werten im Google-Blatt gültig ist.

1. Navigieren Sie zu Ihrem **DataDrivenRetail** -Kanal (einem Sequenzkanal) und wählen Sie ihn aus und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   >
   >Sie sollten Ihre **ContextHub** - **Konfigurationen** auf der Registerkarte "Kanaleigenschaften **"&gt; "** Personalisierung ****"eingerichtet haben.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   Sie müssen sowohl die **Marke** als auch den **Bereich** auswählen, damit die Aktivitäten beim Starten des Targeting-Prozesses korrekt aufgeführt werden.

1. **Hinzufügen eines Standardbilds**

   1. Fügen Sie Ihrem Kanal ein Standardbild hinzu und klicken Sie auf **Targeting**.
   1. Wählen Sie **Marke** und **Aktivität** aus dem Dropdownmenü und klicken Sie auf Targeting **starten**.

   1. Klicken Sie auf **Targeting starten**.
   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   Bevor Sie mit dem Targeting beginnen, müssen Sie die Segmente (**For_Green**, **For_Red** und **For_Blue**) hinzufügen, indem Sie auf **+ Erlebnis-Targeting** hinzufügen klicken, wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Fügen Sie die Bilder zu allen drei verschiedenen Szenarios hinzu, wie unten dargestellt.

   ![retail_targeting](assets/retail_targeting.gif)

1. **Überprüfen der Vorschau**

   1. Click **Preview.** Öffnen Sie außerdem Ihr Google-Blatt und aktualisieren Sie dessen Wert.
   1. Ändern Sie den Wert für alle drei verschiedenen Spalten und Sie werden feststellen, dass das Anzeigebild entsprechend dem höchsten Wert im Bestand aktualisiert wird.
   ![retail_result](assets/retail_result.gif)

