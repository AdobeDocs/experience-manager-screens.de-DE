---
title: Aktivierung der Travel Center-Temperatur
seo-title: Aktivierung der Travel Center-Temperatur
description: Der folgende Anwendungsfall zeigt die Verwendung der Aktivierung der lokalen Temperatur im Reisezentrum anhand der in Google Sheets ausgefüllten Werte.
seo-description: Der folgende Anwendungsfall zeigt die Verwendung der Aktivierung der lokalen Temperatur im Reisezentrum anhand der in Google Sheets ausgefüllten Werte.
uuid: b35286d2-79be-4c36-b72e-c40ffc1a0ca0
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 9d58b971-4540-4007-968d-2a1d94d1fd38
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Aktivierung der Travel Center-Temperatur {#travel-center-temperature-activation}

Der folgende Anwendungsfall zeigt die Verwendung der Aktivierung der lokalen Temperatur im Reisezentrum anhand der in Google Sheets ausgefüllten Werte.

## Beschreibung {#description}

Wenn Ihre Google-Blätter einen Wert unter 50 haben, wird in diesem Fall ein Bild mit heißen Getränken angezeigt, und wenn der Wert größer oder gleich 50 ist, wird das Bild mit kalten Getränken angezeigt. Bei einem anderen oder keinem Wert zeigt der Player ein Standardbild an.

## Voraussetzungen {#preconditions}

Bevor Sie mit der Implementierung der Aktivierung der lokalen Temperatur im Reisezentrum beginnen, müssen Sie lernen, wie Sie ***Data Store***, die ***Zielgruppensegmentierung*** und das Targeting für Kanäle ***in einem AEM Screens-Projekt*** aktivieren.

Detaillierte Informationen finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md) .

## Grundfluss {#basic-flow}

Gehen Sie wie folgt vor, um den Anwendungsfall für die Aktivierung lokaler Temperaturen im Reisezentrum zu implementieren:

1. **Füllen der Google-Blätter**

   1. Navigieren Sie zum Google-Sheet "ContextHubDemo".
   1. Fügen Sie eine Spalte mit **Überschrift1** mit dem entsprechenden Temperaturwert hinzu.
   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (siehe ***Schritt 2: Einrichten der Zielgruppensegmentierung*** unter **[Konfigurieren von ContextHub auf der Seite "AEM Screens](configuring-context-hub.md)** ".

   1. Wählen Sie die **Blätter A1 1** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Vergleichseigenschaft und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** als **größer oder gleich **aus dem Dropdown-Menü

   1. Geben Sie den **Wert** als **50 ein**

   1. Gleichermaßen wählen Sie die** Blätter A1 2 **und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die **Vergleichseigenschaft - Wert** aus und klicken Sie auf das Symbol Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** als **kleiner als **aus dem Dropdownmenü aus.

   1. Geben Sie den **Wert** als **50 ein**

1. Navigieren Sie zum gewünschten Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten** . Im folgenden Beispiel, **DataDrivenWeather**, wird ein sequenzieller Kanal verwendet, um die Funktionalität zu präsentieren.

   >[!NOTE]
   >
   >Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten wie unter Konfigurieren von ContextHub in AEM Screens beschrieben vorkonfiguriert werden[](configuring-context-hub.md).

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >Sie sollten Ihre **ContextHub** - **Konfigurationen** auf der Registerkarte "Kanaleigenschaften **"&gt; "** Personalisierung ****"eingerichtet haben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Wählen Sie **Targeting** aus dem Editor, wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü und klicken Sie auf Targeting **starten**.

   ![new_activity3](assets/new_activity3.gif)

1. **Überprüfen der Vorschau**

   1. Click **Preview.** Öffnen Sie außerdem Ihr Google-Blatt und aktualisieren Sie dessen Wert.
   1. Ändern Sie den Wert auf weniger als 50, sollten Sie in der Lage sein, das Bild der Sommergetränke. Wenn der Wert im Google-Blatt 50 oder größer ist, als sollte in der Lage sein, das Bild von heißem Getränk anzuzeigen.
   ![result3](assets/result3.gif)

