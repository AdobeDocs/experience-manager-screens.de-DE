---
title: Temperaturaktivierung für ein Reiseangebot
description: Sehen Sie sich das folgende Nutzungsszenario an, das die Verwendung einer lokalen Temperaturaktivierung im Reisezentrum anhand der in Google-Tabellen eingegebenen Werte mithilfe von AEM Screens veranschaulicht.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 2ec2891f-0fbe-4812-b3c4-ff160ead36b8
TQID: https://experienceleague.adobe.com/C8FAKzAKUjdochkR96MShKiu2Ig-g-9BDnoX09g4xnM
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
  - id: eb3ad9f8-54a2-45f3-abb1-d3976415a718
subfeature_v2:
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
source-git-commit: d4664dd5678eaccabe656398c437dca264d4675e
workflow-type: tm+mt
source-wordcount: 500
ht-degree: 88%

---

# Temperaturaktivierung für ein Reiseangebot {#travel-center-temperature-activation}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Das folgende Anwendungsbeispiel veranschaulicht die Verwendung der Temperaturaktivierung für ein Reiseangebot anhand der in Google Tabellen angegebenen Werten.

## Beschreibung {#description}

Wenn der Wert in Google-Tabellen für diesen Anwendungsfall unter 50 liegt, wird ein Bild mit heißen Getränken angezeigt. Wenn der Wert größer oder gleich 50 ist, wird ein Bild mit kalten Getränken angezeigt. Wenn ein anderer Wert oder gar kein Wert vorhanden ist, zeigt der Player ein Standardbild an.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der lokalen Temperaturaktivierung im Reisezentrum beginnen, sollten Sie wissen, wie Sie ***Datenspeicher***, ***Zielgruppensegmentierung*** und ***Targeting für Kanäle aktivieren*** in einem AEM Screens-Projekt einrichten.

Genaue Informationen dazu finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md).

## Grundlegender Ablauf {#basic-flow}

Gehen Sie wie folgt vor, um das Anwendungsbeispiel für die temperaturgesteuerte Aktivierung eines Reiseangebots zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zur Google Tabelle „ContextHubDemo“.
   1. Fügen Sie eine Spalte mit **`Heading1`** mit dem entsprechenden Temperaturwert hinzu.

   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** auf der Seite **[Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)**, um mehr zu erfahren).

   1. Klicken Sie auf **Tabellen A1 1** und dann auf **Bearbeiten**.

   1. Klicken Sie auf die Vergleichseigenschaft und dann auf das Konfigurationssymbol.
   1. Klicken Sie auf **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname**.

   1. Wählen Sie für den **Operator** in der Dropdown-Liste **größer oder gleich** aus.

   1. Geben Sie den **Wert** als **50** ein

   1. Wählen Sie nun **Tabellen A1 2** aus und klicken Sie auf **Bearbeiten**.

   1. Klicken Sie auf die Option **Vergleichseigenschaft – Wert** und wählen Sie das Konfigurationssymbol aus.
   1. Klicken Sie auf **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname**.

   1. Wählen Sie für den **Operator** in der Dropdown-Liste **kleiner als** aus

   1. Geben Sie den **Wert** als **50** ein

1. Navigieren Sie zu Ihrem Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Im folgenden Beispiel wird ein sequenzieller Kanal **DataDrivenWeather** verwendet, um die Funktionalität zu demonstrieren.

   >[!NOTE]
   >
   >Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten vorkonfiguriert sein, wie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) beschrieben.

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >Ihre **ContextHub**-**Konfigurationen**, die den Kanal auf der Registerkarte **Eigenschaften** > **Personalisierung** verwenden, sollten bereits eingerichtet sein.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Klicken Sie im Editor auf **Targeting**, wählen Sie danach die **Marke** und die **Aktivität** aus dem Dropdown-Menü und klicken Sie auf **Targeting starten**.

   ![new_activity3](assets/new_activity3.gif)

1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau.** Öffnen Sie außerdem Ihre Google-Tabelle und aktualisieren Sie deren Wert.
   1. Ändern Sie den Wert in weniger als 50. Sie können das Bild eines kalten Getränks sehen. Wenn der Wert in Google Sheets 50 oder höher ist, sollten Sie ein Bild eines heißen Getränks sehen.

   ![result3](assets/result3.gif)
