---
title: Temperaturaktivierung für ein Reiseangebot
seo-title: Temperaturaktivierung für ein Reiseangebot
description: Das folgende Anwendungsbeispiel veranschaulicht die Verwendung der Temperaturaktivierung für ein Reiseangebot anhand der in Google Tabellen angegebenen Werten.
seo-description: Das folgende Anwendungsbeispiel veranschaulicht die Verwendung der Temperaturaktivierung für ein Reiseangebot anhand der in Google Tabellen angegebenen Werten.
uuid: b35286d2-79be-4c36-b72e-c40ffc1a0ca0
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 9d58b971-4540-4007-968d-2a1d94d1fd38
docset: aem65
feature: Inhaltserstellung in Screens
role: Administrator, Entwickler
level: Fortgeschrittene
translation-type: ht
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: ht
source-wordcount: '481'
ht-degree: 100%

---


# Temperaturaktivierung für ein Reiseangebot {#travel-center-temperature-activation}

Das folgende Anwendungsbeispiel veranschaulicht die Verwendung der Temperaturaktivierung für ein Reiseangebot anhand der in Google Tabellen angegebenen Werten.

## Beschreibung {#description}

Wenn Ihre Google Tabelle einen Wert unter 10 hat, wird in diesem Nutzungsszenario ein Bild mit heißen Getränken angezeigt, und wenn der Wert größer oder gleich 10 ist, wird das Bild mit kalten Getränken angezeigt. Bei einem anderen oder keinem Wert zeigt der Player ein Standardbild an.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der temperaturgesteuerten Aktivierung eines Reiseangebots beginnen, müssen Sie lernen, wie Sie in einem AEM Screens-Projekt ***Datenspeicher***, ***Zielgruppensegmentierung*** und ***Targeting für Kanäle aktivieren*** einrichten.

Genaue Informationen dazu finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md).

## Grundlegender Ablauf {#basic-flow}

Gehen Sie wie folgt vor, um das Anwendungsbeispiel für die temperaturgesteuerte Aktivierung eines Reiseangebots zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zur Google Tabelle „ContextHubDemo“.
   1. Fügen Sie eine Spalte mit **Überschrift1** mit dem entsprechenden Temperaturwert hinzu.

   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** auf der Seite **[Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)**, um mehr zu erfahren).

   1. Wählen Sie **Tabellen A1 1** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Eigenschaft zum Vergleichen aus und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus

   1. Wählen Sie als **Operator** den Wert **größer oder gleich** aus dem Dropdown-Menü aus

   1. Geben Sie den **Wert** als **50** ein

   1. Wählen Sie nun **Tabellen A1 2** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie **Vergleich: Eigenschaft - Wert** aus und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus

   1. Wählen Sie unter **Operator** den Wert **kleiner als** aus dem Dropdown-Menü aus

   1. Geben Sie den **Wert** als **50** ein

1. Navigieren Sie zu Ihrem Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Im folgenden Beispiel wird ein sequenzieller Kanal **DataDrivenWeather** verwendet, um die Funktionalität zu demonstrieren.

   >[!NOTE]
   >
   >Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten vorkonfiguriert sein, wie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) beschrieben.

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >Sie sollten Ihre **ContextHub**-**Konfigurationen** auf der Registerkarte **Eigenschaften** für Kanäle > **Personalisierung** eingerichtet haben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Wählen Sie **Targeting** aus dem Editor aus. Wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü aus und klicken Sie auf **Targeting starten**.

   ![new_activity3](assets/new_activity3.gif)

1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau**. Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Wenn Sie den Wert auf weniger als 10 ändern, sollte ein Bild mit Sommergetränken angezeigt werden. Wenn der Wert in der Google Tabelle 10 oder größer ist, sollte ein Bild mit heißen Getränken angezeigt werden.

   ![result3](assets/result3.gif)

