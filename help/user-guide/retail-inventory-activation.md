---
title: Zielgerichtete Aktivierung des Einzelhandelsinventars
seo-title: Retail Inventory Targeted Activation
description: In diesem Anwendungsbeispiel wird der Lagerbestand für drei verschiedenfarbige Pullover veranschaulicht. Je nachdem, wie viele Pullover auf Lager vorhanden sind (erfasst in Google Tabellen), wird das Bild (roter, grüner oder blauer Pullover) mit der höchsten Zahl auf dem Bildschirm angezeigt.
seo-description: This Use Case showcases the retail inventory stock for three different colored sweatshirts. Depending on the number of sweatshirts available in stock that is recorded in Google Sheets, the image (red, green, or blue sweatshirt) with highest number is displayed on the screen.
uuid: 8e7faa65-b004-42b3-8865-4f71eb5dc1b1
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 70147920-5bdb-401c-884e-51d268d40585
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 926f529b-f3cf-471d-83b4-6ccb628cf160
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 95%

---

# Zielgerichtete Aktivierung des Einzelhandelsinventars {#retail-inventory-targeted-activation}

Im folgenden Anwendungsbeispiel werden je nach den Werten in Ihrer Google Tabelle drei verschiedene Bilder dargestellt.

## Beschreibung {#description}

In diesem Anwendungsbeispiel wird der Lagerbestand für drei verschiedenfarbige Pullover veranschaulicht. Je nachdem, wie viele Pullover auf Lager vorhanden sind (erfasst in Google Tabellen), wird das Bild (roter, grüner oder blauer Pullover) mit der höchsten Zahl auf dem Bildschirm angezeigt.

Für dieses Anwendungsbeispiel wird je nach der höchsten verfügbaren Anzahl an Pullovern der rote, grüne oder blaue Pullover auf dem Bildschirm angezeigt.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der zielgerichteten Aktivierung des Einzelhandelsinventars beginnen, müssen Sie wissen, wie man ***Datenspeicher***, ***Zielgruppensegmentierung*** und das ***Targeting für Kanäle*** in einem AEM Screens-Projekt aktiviert.

Genaue Informationen dazu finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md).

## Grundlegender Ablauf {#basic-flow}

Gehen Sie wie folgt vor, um das Anwendungsbeispiel zur Aktivierung des Einzelhandelsinventars zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zur Google Tabelle „ContextHubDemo“.
   1. Fügen Sie drei Spalten (Rot, Grün und Blau) mit entsprechenden Werten für drei verschiedene Pullover hinzu.

   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Konfigurieren der Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** auf der Seite **[Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)**, um mehr zu erfahren).

   1. Fügen Sie drei neue Segmente **Für_Rot**, **Für_Grün** und **Für_Blau** hinzu.

   1. Wählen Sie **Für_Rot** und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   1. Ziehen Sie den **Vergleich: Eigenschaft - Eigenschaft** per Drag-and-Drop in den Editor und klicken Sie auf das Konfigurationssymbol, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdown-Liste in **Name der ersten Eigenschaft** aus.

   1. Wählen Sie unter **Operator** den Wert **größer als** aus dem Dropdown-Menü aus.

   1. Wählen Sie als **Datentyp** die Option **Zahl**.

   1. Auswählen **googlesheets/value/1/1** aus der Dropdown-Liste **Zweiter Eigenschaftsname**.

   1. Ziehen Sie **Weiterer Vergleich: Eigenschaft - Eigenschaft** per Drag-and-Drop in den Editor und klicken Sie auf das Konfigurationssymbol, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdown-Liste in **Name der ersten Eigenschaft** aus.

   1. Wählen Sie unter **Operator** den Wert **größer als** aus dem Dropdown-Menü aus.

   1. Wählen Sie als **Datentyp** die Option **Zahl**.

   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Name der zweiten Eigenschaft**.

   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Bearbeiten und fügen Sie auf gleiche Weise Vergleichseigenschaftsregeln zum Segment **Für_Blau** hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Bearbeiten und fügen Sie auf gleiche Weise Vergleichseigenschaftsregeln zum Segment „Für_Grün“ hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   >
   >Sie werden feststellen, dass sich Daten für die Segmente **Für_Grün** und **Für_Grün** im Editor nicht auflösen lassen, da gemäß den Werten in der Google Tabelle nur der erste Vergleich gültig ist.

1. Navigieren Sie zum Kanal **DataDrivenRetail** (einem Sequenzkanal), wählen Sie ihn aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   >
   >Sie sollten Ihre **ContextHub** **Konfigurationen** über den Kanal **Eigenschaften** > **Personalisierung** Registerkarte.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   >
   >Sie müssen sowohl die **Marke** als auch den **Bereich** auswählen, damit die Aktivitäten beim Starten des Targeting-Prozesses korrekt aufgeführt werden.

1. **Hinzufügen eines Standardbilds**

   1. Fügen Sie Ihrem Kanal ein Standardbild hinzu und klicken Sie auf **Targeting**.
   1. Wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü und klicken Sie auf **Targeting starten**.

   1. Klicken Sie auf **Targeting starten**.

   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   >
   >Bevor Sie mit dem Targeting beginnen, müssen Sie die Segmente (**Für_Grün**, **Für_Rot** und **Für_Blau**) hinzufügen, indem Sie auf **+ Erlebnis-Targeting hinzufügen** klicken (wie in der folgenden Abbildung dargestellt).

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Fügen Sie die Bilder den drei verschiedenen Szenarien hinzu, wie unten dargestellt.

   ![retail_targeting](assets/retail_targeting.gif)

1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau**. Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Ändern Sie den Wert für die drei verschiedenen Spalten und Sie werden sehen, dass das Anzeigebild entsprechend dem höchsten Wert im Bestand aktualisiert wird.

   ![retail_result](assets/retail_result.gif)
