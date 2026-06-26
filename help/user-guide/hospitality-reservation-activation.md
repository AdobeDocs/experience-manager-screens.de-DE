---
title: Aktivierung der Reservierung im Gastgewerbe
description: Sehen Sie sich das folgende Nutzungsszenario an, das die Aktivierung der Reservierung im Gastgewerbe auf anhand der in Google-Tabellen angegebenen Werte veranschaulicht.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: ae032042-fa2b-49cd-91fe-ce50f3ce9867
TQID: https://experienceleague.adobe.com/WwFvV7ZVDRUPpsXWQUKYkz6-gmEjBcpkApcHxzx5vII
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
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 499
ht-degree: 88%

---

# Aktivierung der Reservierung im Gastgewerbe {#hospitality-reservation-activation}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Das folgende Nutzungsszenario veranschaulicht die Verwendung der Aktivierung von Reservierungen im Gastgewerbe anhand der in Google Tabellen angegebenen Werten.

## Beschreibung {#description}

Für diesen Anwendungsfall wird die Google-Tabelle mit dem Prozentsatz der Reservierungen für zwei Restaurants **`Restaurant1`** und **`Restaurant2`** befüllt. Auf der Grundlage der Werte von `Restaurant1` und `Restaurant2` wird eine Formel angewendet und auf der Grundlage der Formel wird der Spalte **AdTarget** der Wert „1“ oder „2“ zugewiesen.

Wenn der Wert von **`Restaurant1`** > **`Restaurant2`** ist, dann wird **AdTarget** der Wert **1** zugewiesen, andernfalls wird **AdTarget** der Wert **2** zugewiesen. Der Wert „1“ generiert die Option *Steak-Gerichte* und der Wert „2“ zeigt die Option *Thailändisches Essen* auf Ihrem Bildschirm an.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der Reservierungsaktivierung beginnen, müssen Sie lernen, wie Sie in einem AEM Screens-Projekt ***Datenspeicher*** und ***Zielgruppensegmentierung*** einrichten und ***Targeting für Kanäle aktivieren***.

Genaue Informationen dazu finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md).

## Grundlegender Ablauf {#basic-flow}

Gehen Sie wie folgt vor, um den Anwendungsfall für die reservierungsgesteuerte Aktivierung der Reservierung im Gastgewerbe für Ihr AEM Screens-Projekt zu implementieren:

1. **Füllen der Google-Tabellen und Hinzufügen der Formel**.

   Wenden Sie beispielsweise die Formel auf die dritte Spalte **AdTarget** an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** auf der Seite **[Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)**, um mehr zu erfahren).
   1. Klicken Sie auf **Tabellen A1 1** und dann auf **Bearbeiten**.
   1. Klicken Sie auf die Vergleichseigenschaften und dann auf das Symbol **Konfiguration**.
   1. Klicken Sie auf **googlesheets/value/1/2** aus der Dropdown-Liste in **Eigenschaftsname**.
   1. Wählen Sie für den **Operator** in der Dropdown-Liste **Gleich** aus.
   1. Geben Sie den **Wert** als **1** ein.
   1. Klicken Sie auf die gleiche Weise auf **Tabellen A1 2** und dann auf **Bearbeiten**.
   1. Klicken Sie auf die Vergleichseigenschaften und dann auf das Symbol **Konfiguration**.
   1. Klicken Sie auf **googlesheets/value/1/2** aus der Dropdown-Liste in **Eigenschaftsname**.
   1. Wählen Sie für den **Operator** den Wert **2**.

1. Navigieren Sie zu Ihrem Kanal (), wählen Sie ihn aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Im folgenden Beispiel wird ein sequenzieller Kanal **DataDrivenRestaurant** verwendet, um die Funktionalität zu demonstrieren.

   >[!NOTE]
   >
   >Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten vorkonfiguriert sein, wie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) beschrieben.

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   >
   >Ihre **ContextHub**-**Konfigurationen**, die den Kanal auf der Registerkarte **Eigenschaften** > **Personalisierung** verwenden, sollten zu diesem Zeitpunkt bereits eingerichtet sein.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Klicken Sie im Editor auf **Targeting**, wählen Sie danach die **Marke** und die **Aktivität** aus dem Dropdown-Menü und klicken Sie auf **Targeting starten**.
1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau.** Öffnen Sie außerdem Ihre Google-Arbeitsblätter und aktualisieren Sie deren Wert.
   1. Aktualisieren Sie den Wert in den Spalten **`Restaurant1`** und **`Restaurant2`**. Wenn **`Restaurant1`** > **`Restaurant2`ist,** sollten Sie ein Bild eines *Steak-Gerichts* sehen. Andernfalls wird ein Bild mit *thailändischem Essen* auf Ihrem Bildschirm angezeigt.

   ![result5](assets/result5.gif)

