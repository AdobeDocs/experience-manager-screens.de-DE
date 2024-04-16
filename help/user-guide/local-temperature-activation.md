---
title: Temperaturaktivierung für ein Reiseangebot
description: Erfahren Sie, wie Sie mit AEM Screens anhand dieses Anwendungsbeispiels die Verwendung der Temperaturaktivierung für ein Reiseangebot anhand der in Google Tabellen angegebenen Werte veranschaulichen.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 2ec2891f-0fbe-4812-b3c4-ff160ead36b8
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 33%

---

# Temperaturaktivierung für ein Reiseangebot {#travel-center-temperature-activation}

Das folgende Anwendungsbeispiel veranschaulicht die Verwendung der Temperaturaktivierung für ein Reiseangebot anhand der in Google Tabellen angegebenen Werten.

## Beschreibung {#description}

Wenn der Wert in Google Tabellen unter 50 liegt, wird für dieses Anwendungsbeispiel ein Bild mit heißen Getränken angezeigt. Wenn der Wert größer oder gleich 50 ist, wird ein Bild mit kalten Getränken angezeigt. Wenn ein anderer Wert oder gar kein Wert vorhanden ist, zeigt der Player ein Standardbild an.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der temperaturgesteuerten Aktivierung eines Reiseangebots beginnen, erfahren Sie, wie Sie ***Datenspeicher***, ***Zielgruppensegmentierung*** und ***Targeting für Kanäle aktivieren*** in einem AEM Screens-Projekt.

Siehe [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) für detaillierte Informationen.

## Grundlegender Ablauf {#basic-flow}

Gehen Sie wie folgt vor, um das Anwendungsbeispiel für die temperaturgesteuerte Aktivierung eines Reiseangebots zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zur Google Tabelle „ContextHubDemo“.
   1. Hinzufügen einer Spalte mit **`Heading1`** mit dem entsprechenden Temperaturwert.

   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** in **[Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)** Seite für weitere Details).

   1. Klicken Sie auf **Blätter A1 1** und klicken **Bearbeiten**.

   1. Klicken Sie auf die Vergleichseigenschaft und dann auf das Konfigurationssymbol.
   1. Klicks **googlesheets/value/1/0** aus der Dropdown-Liste **Eigenschaftsname**

   1. Klicken Sie auf **Operator** as **greater-than-or-equal** aus dem Dropdownmenü

   1. Geben Sie den **Wert** als **50** ein

   1. Wählen Sie auf ähnliche Weise die **Blätter A1 2** und klicken **Bearbeiten**.

   1. Klicken Sie auf **Vergleichseigenschaft - Wert** und wählen Sie das Konfigurationssymbol aus.
   1. Klicks **googlesheets/value/1/0** aus der Dropdown-Liste **Eigenschaftsname**

   1. Klicken Sie auf **Operator** as **kleiner als** aus dem Dropdownmenü

   1. Geben Sie den **Wert** als **50** ein

1. Navigieren Sie zu Ihrem Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Im folgenden Beispiel wird ein sequenzieller Kanal **DataDrivenWeather** verwendet, um die Funktionalität zu demonstrieren.

   >[!NOTE]
   >
   >Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten vorkonfiguriert sein, wie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) beschrieben.

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >Sie sollten Ihre **ContextHub** **Konfigurationen** über den Kanal **Eigenschaften** > **Personalisierung** Registerkarte.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Klicks **Targeting** Klicken Sie im Editor auf **Marke** und **Aktivität** aus dem Dropdown-Menü aus und klicken Sie auf **Targeting starten**.

   ![new_activity3](assets/new_activity3.gif)

1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau**. Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Ändern Sie den Wert in weniger als 50. Sie sollten ein Bild eines kalten Getränks sehen können. Wenn der Wert in Google Tabellen 50 oder höher ist, sollte ein Bild eines heißen Getränks angezeigt werden.

   ![result3](assets/result3.gif)
