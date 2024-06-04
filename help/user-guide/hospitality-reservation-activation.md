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
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 85%

---

# Aktivierung der Reservierung im Gastgewerbe {#hospitality-reservation-activation}

Das folgende Nutzungsszenario veranschaulicht die Verwendung der Aktivierung von Reservierungen im Gastgewerbe anhand der in Google Tabellen angegebenen Werten.

## Beschreibung {#description}

Für diesen Anwendungsfall wird die Google-Tabelle mit dem Prozentsatz der Reservierungen für zwei Restaurants **`Restaurant1`** und **`Restaurant2`** befüllt. Eine Formel wird anhand der Werte von `Restaurant1` und `Restaurant2` und, basierend auf der Formel, dem Wert 1 oder 2 zugewiesen wird. **AdTarget** Spalte.

Wenn der Wert von **`Restaurant1`** > **`Restaurant2`** ist, dann wird **AdTarget** der Wert **1** zugewiesen, andernfalls wird **AdTarget** der Wert **2** zugewiesen. Wert 1 generiert eine *Stechnahrung* Option und Wert zwei führt zur Anzeige von *Thailändische Küche* auf Ihrem Bildschirm angezeigt.

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
   >Ihre **ContextHub** **Konfigurationen** über den Kanal **Eigenschaften** > **Personalisierung** -Tab hätte zu diesem Zeitpunkt bereits eingerichtet sein müssen.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Klicken Sie im Editor auf **Targeting**, danach auf **Marke** und die **Aktivität** aus dem Dropdown-Menü, und klicken Sie dann auf **Targeting starten**.
1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau.** Öffnen Sie außerdem Google Tabellen und aktualisieren Sie den Wert.
   1. Aktualisieren Sie den Wert in den Spalten **`Restaurant1`** und **`Restaurant2`**. Wenn **`Restaurant1`** > **`Restaurant2`ist,** sollten Sie ein Bild eines *Steak-Gerichts* sehen. Andernfalls wird ein Bild mit *thailändischem Essen* auf Ihrem Bildschirm angezeigt.

   ![result5](assets/result5.gif)
