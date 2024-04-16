---
title: Aktivierung der Gastgewerbereservierung
description: Erfahren Sie, wie dieser Anwendungsfall die Verwendung der Aktivierung der Gastgewerbereservierung anhand der in Google Tabellen angegebenen Werte veranschaulicht.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: ae032042-fa2b-49cd-91fe-ce50f3ce9867
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 26%

---

# Aktivierung der Gastgewerbereservierung {#hospitality-reservation-activation}

Das folgende Nutzungsszenario veranschaulicht die Verwendung der Aktivierung von Reservierungen im Gastgewerbe anhand der in Google Tabellen angegebenen Werten.

## Beschreibung {#description}

Für dieses Anwendungsbeispiel wird die Google Tabelle mit dem Prozentsatz der Reservierungen in zwei Restaurants gefüllt. **`Restaurant1`** und **`Restaurant2`**. Eine Formel wird anhand der Werte von `Restaurant1` und `Restaurant2` und basierend auf der Formel wird der Wert 1 oder 2 dem **AdTarget** Spalte.

Wenn der Wert von **`Restaurant1`** > **`Restaurant2`**, dann **AdTarget** zugewiesener Wert **1** else **AdTarget** zugewiesener Wert **2**. Wert 1 generiert *Stechnahrung* -Option und -Wert: Ergebnisse der Anzeige von *Thailändische Küche* auf Ihrem Bildschirm angezeigt.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der Reservierungsaktivierung beginnen, erfahren Sie, wie Sie ***Datenspeicher***, ***Zielgruppensegmentierung*** und ***Targeting für Kanäle aktivieren*** in einem AEM Screens-Projekt.

Siehe [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) für detaillierte Informationen.

## Grundlegender Ablauf {#basic-flow}

Gehen Sie wie folgt vor, um die Aktivierung der Reservierung für Gastgewerbe für Ihr AEM Screens-Projekt zu implementieren:

1. **Befüllen der Google Tabellen und Hinzufügen der Formel**.

   Wenden Sie beispielsweise die Formel auf die dritte Spalte **AdTarget** an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** in **[Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)** Seite für weitere Details).
   1. Klicken Sie auf **Blätter A1 1** und klicken **Bearbeiten**.
   1. Klicken Sie auf die Vergleichseigenschaft und klicken Sie auf die **Konfiguration** Symbol.
   1. Klicks **googlesheets/value/1/2** aus der Dropdown-Liste **Eigenschaftsname**.
   1. Klicken Sie auf **Operator** as **equal** aus dem Dropdown-Menü.
   1. Geben Sie den **Wert** als **1** ein.
   1. Klicken Sie auf die **Blätter A1 2** und klicken **Bearbeiten**.
   1. Klicken Sie auf die Vergleichseigenschaft und klicken Sie auf die **Konfiguration** Symbol.
   1. Klicks **googlesheets/value/1/2** aus der Dropdown-Liste **Eigenschaftsname**.
   1. Klicken Sie auf **Operator** as **2**.

1. Navigieren Sie zu Ihrem Kanal () und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus. Im folgenden Beispiel wird ein sequenzieller Kanal **DataDrivenRestaurant** verwendet, um die Funktionalität zu demonstrieren.

   >[!NOTE]
   >
   >Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten vorkonfiguriert sein, wie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) beschrieben.

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   >
   >Sie sollten Ihre **ContextHub** **Konfigurationen** über den Kanal **Eigenschaften** > **Personalisierung** Registerkarte.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Klicks **Targeting** Klicken Sie im Editor auf **Marke** und **Aktivität** aus dem Dropdown-Menü aus und klicken Sie auf **Targeting starten**.
1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau.** Öffnen Sie außerdem Google Tabellen und aktualisieren Sie den Wert.
   1. Aktualisieren Sie den Wert in **`Restaurant1`** und **`Restaurant2`** Spalten. Wenn **`Restaurant1`** > **`Restaurant2`,** Sie sollten ein Bild von *Steak* andernfalls *Thailändisch* Auf dem Bildschirm wird ein Bild mit Lebensmitteln angezeigt.

   ![result5](assets/result5.gif)
