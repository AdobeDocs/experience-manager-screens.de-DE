---
title: Gastgewerbereservierung Aktivierung
seo-title: Gastgewerbereservierung Aktivierung
description: Der folgende Anwendungsfall zeigt die Nutzung der Aktivierung der Krankenhausreservierung anhand der in Google Sheets ausgefüllten Werte.
seo-description: Der folgende Anwendungsfall zeigt die Nutzung der Aktivierung der Krankenhausreservierung anhand der in Google Sheets ausgefüllten Werte.
uuid: 7692d616-2b00-4d9a-9d3f-211c089b29af
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: ef3e5dce-e36a-45d3-ad5e-db01430477c6
docset: aem65
translation-type: tm+mt
source-git-commit: 209a9a833957d9a8bb7c7ec70ff421514f5b974c

---


#  Gastgewerbereservierung Aktivierung {#hospitality-reservation-activation}

Der folgende Anwendungsfall zeigt die Nutzung der Aktivierung der Krankenhausreservierung anhand der in Google Sheets ausgefüllten Werte.

## Beschreibung {#description}

Für diesen Verwendungsfall wird das Google Sheet mit einem Prozentsatz der Reservierung in zwei Restaurants **Restaurant1** und **Restaurant2** gefüllt. Eine Formel wird basierend auf den Werten von Restaurant1 und Restaurant2 angewendet und basierend auf der Formel wird der Spalte **AdTarget** der Wert 1 oder 2 zugewiesen.

Wenn der Wert von **Restaurant1** &gt; **Restaurant2**, dann wird **AdTarget** der Wert **1** zugewiesen. Andernfalls wird **AdTarget** **** der Wert2zugewiesen. Der Wert 1 generiert die Option *Steak food* und der Wert 2 zeigt die Option *Thai food* an.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der Reservierungsaktivierung beginnen, müssen Sie lernen, wie Sie ***Data Store***, ***Zielgruppensegmentierung*** und Targeting für Kanäle ***in einem AEM Screens-Projekt*** aktivieren.

Detaillierte Informationen finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) .

## Grundfluss {#basic-flow}

Gehen Sie wie folgt vor, um den Anwendungsfall für die Aktivierung der Gastfreundschaftsreservierung für Ihr AEM Screens-Projekt zu implementieren:

1. **Füllen der Google-Blätter und Hinzufügen der Formel.**

   Wenden Sie beispielsweise die Formel auf die dritte Spalte **AdTarget** an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** unter **[Konfigurieren von ContextHub auf der Seite "AEM Screens](configuring-context-hub.md)** ".

   1. Wählen Sie die **Blätter A1 1** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Vergleichseigenschaft und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** aus dem Dropdownmenü als **gleich** aus

   1. Geben Sie den **Wert** als **1 ein**

   1. Gleichermaßen wählen Sie die **Blätter A1 2** und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Vergleichseigenschaft und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** als **2**

1. Navigieren Sie zum gewünschten Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten** . Im folgenden Beispiel, **DataDrivenRestaurant**, wird ein sequenzieller Kanal verwendet, um die Funktionalität zu präsentieren.

   >[!NOTE]
   >
   >Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten wie unter Konfigurieren von ContextHub in AEM Screens beschrieben vorkonfiguriert werden[](configuring-context-hub.md).

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   >
   >Sie sollten Ihre **ContextHub** - **Konfigurationen** auf der Registerkarte "Kanaleigenschaften **"&gt; "** Personalisierung ****"eingerichtet haben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Wählen Sie **Targeting** aus dem Editor, wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü und klicken Sie auf Targeting **starten**.
1. **Überprüfen der Vorschau**

   1. Click **Preview.** Öffnen Sie außerdem Ihre Google-Blätter und aktualisieren Sie deren Wert.
   1. Aktualisieren Sie den Wert in den Spalten **Restaurant1** und **Restaurant2** . Wenn **Restaurant1** &gt; **Restaurant2,** sollten Sie in der Lage sein, ein Bild von *Steak* Essen ansonsten, *Thai* Essen Image auf Ihrem Bildschirm angezeigt.
   ![result5](assets/result5.gif)

