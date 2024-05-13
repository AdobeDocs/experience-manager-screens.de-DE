---
title: Zielgerichtete Aktivierung des Einzelhandelsinventars
description: Erfahren Sie mehr über dieses AEM Screens-Anwendungsbeispiel, in dem der Lagerbestand für drei verschiedene Pullover dargestellt wird.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 926f529b-f3cf-471d-83b4-6ccb628cf160
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 30%

---

# Zielgerichtete Aktivierung des Einzelhandelsinventars {#retail-inventory-targeted-activation}

Im folgenden Anwendungsbeispiel werden je nach den Werten in Ihrer Google Tabelle drei verschiedene Bilder dargestellt.

## Beschreibung {#description}

In diesem Anwendungsbeispiel wird der Lagerbestand für drei verschiedene Pullover dargestellt. Je nachdem, wie viele Pullover auf Lager vorhanden sind, die in Google Tabellen aufgezeichnet sind, wird das Bild (rotes, grünes oder blaues Pullover) mit der höchsten Zahl angezeigt.

Der rote, grüne oder blaue Pullover wird basierend auf dem höchsten Wert der verfügbaren Pullover angezeigt.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der zielgerichteten Aktivierung des Einzelhandelsinventars beginnen, erfahren Sie, wie Sie ***Datenspeicher***, ***Zielgruppensegmentierung*** und ***Targeting für Kanäle aktivieren*** in einem AEM Screens-Projekt.

Genaue Informationen dazu finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md).

## Grundlegender Ablauf {#basic-flow}

Gehen Sie wie folgt vor, um das Anwendungsbeispiel zur Aktivierung des Einzelhandelsinventars zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zur Google Tabelle „ContextHubDemo“.
   1. Fügen Sie drei Spalten (Rot, Grün und Blau) mit entsprechenden Werten für drei verschiedene Pullover hinzu.

   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Konfigurieren der Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (weitere Informationen unter ***Schritt 2: Einrichten der Zielgruppensegmentierung*** auf der Seite **[Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)**).

   1. Fügen Sie drei neue Segmente **Für_Rot**, **Für_Grün** und **Für_Blau** hinzu.

   1. Klicks **For_Red** und klicken **Bearbeiten** in der Aktionsleiste aus.

   1. Ziehen Sie die **Vergleich: Eigenschaft - Eigenschaft** in den Editor.
   1. Klicken Sie auf **Konfiguration** Symbol.
   1. Klicks **googlesheets/value/1/2** aus der Dropdown-Liste **Vorname der Eigenschaft**.
   1. Klicken Sie auf **Operator** und als **größer als** aus dem Dropdown-Menü.
   1. Klicks **Datentyp** und als **number**.
   1. Klicks **googlesheets/value/1/1** aus der Dropdown-Liste **Zweiter Eigenschaftsname**.
   1. Drag &amp; Drop **Weiterer Vergleich: Eigenschaft - Eigenschaft** zum Editor hinzu und klicken Sie auf die Schaltfläche **Konfiguration** Symbol.
   1. Klicks **googlesheets/value/1/2** aus der Dropdown-Liste **Vorname der Eigenschaft**.
   1. Klicken Sie auf **Operator** und als **größer als** aus dem Dropdown-Menü.
   1. Klicks **Datentyp** und als **number**.
   1. Klicks **googlesheets/value/1/0** aus der Dropdown-Liste **Zweiter Eigenschaftsname**.

   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Bearbeiten und fügen Sie auf ähnliche Weise Vergleichseigenschaftsregeln zum **For_Blue** Segment wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Bearbeiten und fügen Sie auf ähnliche Weise Vergleichseigenschaftsregeln zum **Für_Grün** Segment wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   >
   >Beachten Sie Folgendes für Segmente **Für_Grün** und **Für_Grün** können Daten nicht im Editor aufgelöst werden, da gemäß den Werten in der Google Tabelle nur der erste Vergleich gültig ist.

1. Navigieren Sie zu und klicken Sie auf Ihre **DataDrivenRetail** channel (ein Sequenzkanal).
1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**. 

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   >
   >Sie hätten bereits die **ContextHub** **Konfigurationen** über den Kanal **Eigenschaften** > **Personalisierung** Registerkarte.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   >
   >Klicken Sie auf beide **Marke** und **Bereich** , damit die Aktivitäten beim Starten des Targeting-Prozesses korrekt aufgelistet werden.

1. **Hinzufügen eines Standardbilds**

   1. Fügen Sie Ihrem Kanal ein Standardbild hinzu und klicken Sie auf **Targeting**.
   1. Klicks **Marke** und **Aktivität** aus dem Dropdown-Menü aus und klicken Sie auf **Targeting starten**.
   1. Klicken Sie auf **Targeting starten**.

   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   >
   >Bevor Sie mit dem Targeting beginnen, fügen Sie die Segmente hinzu (**Für_Grün**, **For_Red**, und **For_Blue**) durch Auswahl **+ Erlebnis-Targeting hinzufügen** aus der Seitenleiste, wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Fügen Sie die Bilder zu allen drei verschiedenen Szenarien hinzu, wie unten dargestellt.

   ![retail_targeting](assets/retail_targeting.gif)

1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau**. Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Ändern Sie den Wert für alle drei verschiedenen Spalten. Beachten Sie, dass das Anzeigebild entsprechend dem höchsten Wert im Bestand aktualisiert wird.

   ![retail_result](assets/retail_result.gif)
