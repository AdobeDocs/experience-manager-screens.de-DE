---
title: Lagerbestandsgesteuerter Kanal
seo-title: Lagerbestandsgesteuerter Kanal
description: 'null'
seo-description: 'null'
page-status-flag: never-activated
uuid: a7e7aa08-8f9e-4458-bdce-225cf29a6da4
contentOwner: jsyal
discoiquuid: 9989ef4c-9fdd-4bf2-9f7c-0c74a9cc4e7f
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Lagerbestandsgesteuerter Kanal{#inventory-driven-channel}

## Erste Schritte mit bestandsbasierten Kanälen {#getting-started-with-inventory-driven-channels}

In diesem Abschnitt wird ein Verwendungsfallbeispiel beschrieben, das sich mit der Erstellung und Verwaltung einer datengesteuerten Asset-Änderung mithilfe von Google-Sheets befasst.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Anwendungsfall beginnen, sollten Sie wissen, wie:

* **[Kanäle erstellen und verwalten](managing-channels.md)**
* **[Orte erstellen und verwalten](managing-locations.md)**
* **[Zeitpläne erstellen und verwalten](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Inhaltsersteller

### Terminologie {#terminolgies}

Befolgen Sie die folgenden Begriffe, die eine wichtige Rolle bei der Verständigung und Einrichtung des Projekts in den verschiedenen Anwendungsfällen spielen:

**Aktivität** bezieht sich auf die Kategorie.

**Bereich** Projekt Haupt

**Zielgruppenort** der Daten

**Markenbezeichnungen**

**Segmentsegment** bezieht sich auf einen Container mit Assets, die Sie als Ziel auswählen möchten.

### Grundlegender Fluss: Einrichten des Projekts {#basic-flow-setting-up-the-project}

>[!NOTE]
>
>**Voraussetzung:**
>
>Bevor Sie sich näher mit den Details zur Einrichtung und Verwendung datengesteuerter Asset-Änderungen in Ihrem Projekt befassen, stellen Sie sicher, dass Sie ein AEM Screens-Projekt mit einem Sequenzkanal erstellen. Zu Demozwecken werden dem Projekt **DataDrivenAsset** die Sequenzkanäle **DataDrivenRestaurant**, **DataDrivenTextOverlay**, **DataDrivenWeather** und **DataDrivenRetail** hinzugefügt (siehe folgende Abbildung).
>
>Die Erstellung von vier verschiedenen Kanälen dient nur zu Demonstrationszwecken und zur Präsentation von vier verschiedenen Anwendungsfällen in verschiedenen Kanälen. Wenn Sie nur einen Anwendungsfall als Ihren Bedarf verwenden möchten, können Sie nur einen Sequenzkanal erstellen.

![screen_shot_2019-05-01at42043pm](assets/screen_shot_2019-05-01at42043pm.png)

Führen Sie die folgenden Abschnitte aus, um ein Beispielprojekt zum Erstellen und Verwalten einer datengesteuerten Asset-Änderung mithilfe von Google Sheets in einem AEM Screens-Projekt zu erstellen:

## Schritt 1: Datenbank einrichten {#step-setting-up-database}

>[!CAUTION]
>
>Google Sheets werden im folgenden Beispieldatenbanksystem verwendet, aus dem die Werte abgerufen werden, und dienen ausschließlich Bildungszwecken. Adobe unterstützt die Verwendung von Google-Blättern in Produktionsumgebungen nicht.
>
>Weitere Informationen finden Sie in der Google-Dokumentation unter API-Schlüssel [abrufen](https://developers.google.com/maps/documentation/javascript/get-api-key) .

1. Melden Sie sich bei Google Docs an.

   >[!NOTE]
   >
   >Sie müssen über ein Konto in Google Drive verfügen, bevor Sie ein neues Google Sheet erstellen können.

1. Starten Sie eine neue leere Tabelle. Fügen Sie Ihrem Google-Blatt Inhalt hinzu und speichern Sie es. Zu Demozwecken wird das Google-Blatt als **ContextHubDemo** bezeichnet.
1. Klicken Sie in der oberen rechten Ecke des Google-Blatts auf **Freigeben** , um das Dialogfeld **Für andere** freigeben zu öffnen. Klicken Sie auf **Erweitert** und ändern Sie die Einstellungen in **Ein - Jeder mit dem Link**, wie in der Abbildung unten dargestellt.

   Mit diesem Schritt können Sie auf Werte im Google-Blatt zugreifen.

   ![screen_shot_2019-04-22at115829am](assets/screen_shot_2019-04-22at115829am.png)

1. Wenn Sie im vorherigen Schritt auf **Speichern** klicken, erhalten Sie den Link für das Google-Blatt. Speichern Sie den Klick für künftige Verweise und klicken Sie auf **Fertig**.

   ![screen_shot_2019-04-22at120242pm](assets/screen_shot_2019-04-22at120242pm.png)

>[!CAUTION]
>
>Google Sheets werden im folgenden Beispiel für Bildungszwecke verwendet. Adobe unterstützt die Verwendung von Google-Blättern in Produktionsumgebungen nicht.

## Schritt 2: Aktivieren der Google Sheets REST APIs {#step-enabling-the-google-sheets-rest-apis}

Nachdem Sie Ihr Google Sheet eingerichtet haben, müssen Sie die Google Sheet REST API aktivieren, um auf die Werte zuzugreifen.

Informationen zum Aktivieren der REST-APIs für Google-Blätter finden Sie in der Dokumentation zu Google-APIs.

1. Navigieren Sie zur [Google API-Konsole](https://console.developers.google.com/apis/credentials). Click **CREATE** to create a new project.

   ![screen_shot_2019-04-22at125028pm](assets/screen_shot_2019-04-22at125028pm.png)

1. Geben Sie den **Projektnamen** als **AssetChange** ein und klicken Sie auf **CREATE**.
1. Nachdem Sie das Projekt erstellt haben, müssen Sie den API-Schlüssel einrichten. Klicken Sie auf Anmeldeinformationen **erstellen** und wählen Sie **API-Schlüssel **aus, um den API-Schlüssel für Ihr Projekt zu generieren. Speichern Sie den API-Schlüssel für künftige Verweise.

   >[!NOTE]
   >
   >Dieses Demoprojekt verwendet den kostenlosen Google API-Schlüssel. Weitere Informationen finden Sie auf der Website von Google unter Preise und Einschränkungen **API-Schlüssel** abrufen.

### Überprüfen der Einrichtung von Google-Blättern {#verifying-the-setup-of-google-sheets}

```
Verify the data in your Google Sheets using the steps below
```

[https://sheets.googleapis.com/v4/spreadsheets/](https://sheets.googleapis.com/v4/spreadsheets/)&lt;Ihr Blatt-ID&gt;/values/Sheet1?key=&lt;Ihr API-Schlüssel&gt;

Beispiel:

Wenn der Link** Google Sheets** *wie folgt lautet:*

`https://docs.google.com/spreadsheets/d/1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M/edit?usp=sharing`, dann die

**Sheet-ID** : `1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M`

**API-Schlüssel** : `AIzaSyAfoANOeLkFCCyohjL8cOdJLhrhGefqEy8`

Fügen Sie beide Werte in der obigen Syntax hinzu:

`https://sheets.googleapis.com/v4/spreadsheets/1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M/values/Sheet1?key=AIzaSyAfoANOeLkFCCyohjL8cOdJLhrhGefqEy8`

Sie sollten jetzt in der Lage sein, Ihre Daten im Arbeitsblatt anzuzeigen.

## Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google-Blätter {#step-configuring-aem-to-fetch-the-content-of-the-google-sheets}

Im folgenden Abschnitt wird beschrieben, wie Sie Adobe Experience Manager (AEM) so konfigurieren, dass Inhalte aus den Google-Arbeitsblättern abgerufen werden.

1. Navigieren Sie zu Ihrer AEM-Instanz und klicken Sie in der linken Seitenleiste auf das Symbol "Tools". Klicken Sie auf **Sites** —&gt; **ContextHub**, wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-04-22at53222pm](assets/screen_shot_2019-04-22at53222pm.png)

1. **Neue ContextHub Store-Konfiguration erstellen**

   1. Navigieren Sie zu **global** &gt; **default** &gt; **ContextHub-Konfiguration**.

   1. Klicken Sie auf** Erstellen &gt; Konfigurationscontainer **und geben Sie den Titel als** ContextHubDemo** ein.

   1. **** Navigieren Sie **zu** ContextHubDemo **&gt; Konfiguration des** ContentHub-Speichers... zum Öffnen des Assistenten zum **Konfigurieren**
   1. Geben Sie den **Titel** als **Google-Blätter**, **Store-Name** als **Google-Heets** und **Store-Typ** alscontexthub.generic-jsonp ein **.**
   1. Klicken Sie auf **Weiter**
   1. Geben Sie Ihre spezifische JSON-Konfiguration ein. Beispielsweise können Sie die folgende JSON für Demozwecke verwenden.
   1. Klicken Sie auf **Speichern**.

   ```
   {
     "service": {
       "host": "sheets.googleapis.com",
       "port": 80,
       "path": "/v4/spreadsheets/<your sheet it>/values/Sheet1",
       "jsonp": false,
       "secure": true,
       "params": {
         "key": "<your API key>"
       }
     },
     "pollInterval": 3000
   }
   ```

   >[!NOTE]
   >
   >Im obigen Beispielcode definiert **pollInterval** die Häufigkeit, mit der die Werte aktualisiert werden (in ms).
   >
   >
   >Ersetzen Sie den aus *Schritt 1 abgerufenen Code durch Ihren*&lt;Sheet ID&gt;*- und*&lt;API-Schlüssel&gt;**: Einrichten der Datenbank.**

   >[!CAUTION]
   Wenn Sie Google Sheets Store-Konfigurationen außerhalb des Legacy-Ordners erstellen (z. B. in Ihrem eigenen Projektordner), funktioniert das Targeting nicht standardmäßig.
   Wenn Sie die Google Sheets Store-Konfigurationen außerhalb des globalen Legacy-Ordners konfigurieren möchten, müssen Sie den **Store-Namen** als **Segmentierung** und **Store-Typ** als **aem.segmentation** festlegen. Außerdem müssen Sie den Prozess der Definition des JSON wie oben definiert überspringen.

1. **Erstellen einer Marke in Aktivitäten**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** &gt; **Aktivitäten**

   1. Klicken Sie auf** Erstellen* &gt; Marke **erstellen**

   1. Select **Brand** from the **Create Page** wizard and click **Next**

   1. Enter the **Title** as **ContextHubDemo** and click **Create**. Ihre Marke wird nun wie unten dargestellt erstellt.
   ![screen_shot_2019-05-05at44305pm](assets/screen_shot_2019-05-05at44305pm.png)

1. 

>[!CAUTION]
Bekanntes Problem:
Um einen Bereich hinzuzufügen, entfernen Sie die Master aus der URL, z. B.
[https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master](https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master)

1. Erstellen eines Bereichs in Ihrer Marke**

   1. Klicken Sie auf **Erstellen** &gt; Bereich **erstellen**

   1. Select **Area** from the** Create Page** wizard and click Next

   1. Enter the **Title** as **GoogleSheets** and click **Create**. Ihr Bereich wird in Ihrer Aktivität erstellt.

1. **Erstellen von Segmenten in Zielgruppen**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** &gt; **Zielgruppen** &gt; **We.Retail**.
   1. Klicken Sie auf **Erstellen** &gt; Kontext-Hub-Segment **erstellen**. Das Dialogfeld "Neues ContextHub-Segment"wird angezeigt.
   1. Enter the **Title** as **SheetA1 1** and click **Create**. Erstellen Sie auf ähnliche Weise ein weiteres Segment mit der Bezeichnung **SheetA2 2**.

1. **Bearbeiten der Segmente**

   1. Wählen Sie die Segmentblätter **A1 1** (erstellt in Schritt 5) aus und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   1. Ziehen Sie den **Vergleich per Drag &amp; Drop: Eigenschaft - Komponente "Wert** "im Editor.
   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich einer Eigenschaft mit Wert** zu öffnen.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**.

   1. Wählen Sie den **Operator** als **Equal **aus dem Dropdownmenü.

   1. Geben Sie den **Wert** als **1** ein.
   >[!NOTE]
   AEM validiert Ihre Daten aus dem Google-Blatt, indem Sie Ihr Segment grün anzeigen.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Bearbeiten Sie die Eigenschaftswerte entsprechend in **Blatt A1 2**.

   1. Ziehen Sie den **Vergleich per Drag &amp; Drop: Eigenschaft - Komponente "Wert** "im Editor.
   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich einer Eigenschaft mit Wert** zu öffnen.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**.

   1. Wählen Sie den **Operator** als **Equal **aus dem Dropdownmenü.

   1. Geben Sie den **Wert** als **2** ein.
   >[!NOTE]
   Die in den vorherigen Schritten angewendeten Regeln sind nur ein Beispiel dafür, wie Sie Segmente für die Implementierung der folgenden Anwendungsfälle einrichten.

## Schritt 3: Einrichten von Context Hub-Konfigurationen im AEM-Bildschirmkanal {#step-setting-up-context-hub-configurations-in-aem-screens-channel}

Gehen Sie wie folgt vor, um ContextHub-Konfigurationen und Segmentpfade zum AEM-Bildschirmkanal einzurichten.

1. Navigieren Sie zu einem der von Ihnen erstellten AEM-Bildschirme-Kanäle (**DataDrivenRetail**) als Voraussetzung.
1. Wählen Sie den Kanal (**DataDrivenRetail**) und klicken Sie in der Aktionsleiste auf **Eigenschaften** .

   ![screen_shot_2019-05-01at4332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Wählen Sie die Registerkarte **Personalisierung** , um die ContextHub-Konfigurationen einzurichten.

   1. Wählen Sie den **ContextHub-Pfad** als **libs** &gt; **Einstellungen** &gt; **Cloudsettings** &gt; **default** **** ****&gt; ContextHub-Konfigurationenaus und klicken Sie aufSelect.

   1. Wählen Sie den **Segmentpfad** als **conf** &gt; **We.Retail **&gt; **Einstellungen** &gt; **wcm** &gt; **Segmente** **** aus und klicken Sie aufSelect.

   1. Klicken Sie auf **Speichern und schließen**.
   >[!NOTE]
   Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie zunächst Ihre Kontexthub-Konfigurationen und -Segmente gespeichert haben.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht im Dialogfeld oben unter **Targeting-Konfiguration** auswählen, müssen Sie die Marke und Aktivität auswählen, wenn Sie den Targeting-Prozess starten.

1. Navigieren Sie zum **DataDrivenRetail** unter **DataDrivenAssets** &gt; **Channels **und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   >[!NOTE]
   Wenn Sie alles korrekt eingerichtet haben, sehen Sie die Option **Targeting** in der Dropdown-Liste des Editors, wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

   >[!NOTE]
   Nachdem Sie die ContextHub-Konfigurationen für Ihren Kanal konfiguriert haben, stellen Sie sicher, dass Sie die vorhergehenden Schritte von 1 bis 4, auch für die anderen drei Sequenzkanäle, befolgen, wenn Sie alle unten aufgeführten Anwendungsfälle befolgen möchten.

## Verwendungsfall 1: Aktivierung des Einzelhandelsbestands {#use-case-retail-inventory-activation}

Im folgenden Anwendungsfall werden drei verschiedene Bilder basierend auf den Werten in Ihrem Google Sheet veranschaulicht.

### Beschreibung {#description}

Dieser Verwendungsfall zeigt den Lagerbestand für drei verschiedene farbige Pullover. Je nachdem, wie viele Sweatshirts auf Lager vorhanden sind, die in Google Sheets aufgezeichnet werden, wird das Bild (rot, grün oder blau) mit der höchsten Zahl auf dem Bildschirm angezeigt.

Für diesen Verwendungsfall wird der Pullover Rot, Grün oder Blau basierend auf der höchsten verfügbaren Anzahl an Pullovern auf Ihrem Bildschirm angezeigt.

### Verfahren {#procedure}

Gehen Sie wie folgt vor, um den Anwendungsfall für die Aktivierung des Einzelhandelsbestands zu implementieren:

1. **Füllen der Google-Blätter**

   1. Navigieren Sie zum Google-Sheet "ContextHubDemo".
   1. Fügen Sie drei Spalten (Rot, Grün und Blau) mit entsprechenden Werten für drei verschiedene Sweatshirts hinzu.
   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Konfigurieren der Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (erstellt in Schritt 5 von ***Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google-Blätter***).
   1. Fügen Sie drei neue Segmente **für_Rot**, **für_Grün** und **für_Blau** hinzu.

   1. Wählen Sie **For_Red** und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   1. Ziehen Sie den **Vergleich per Drag &amp; Drop: Eigenschaft - Eigenschaft** des Editors und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im Namen der **Voreigenschaft**

   1. Wählen Sie den **Operator** als **größer als **aus dem Dropdownmenü aus.

   1. Wählen Sie **Datentyp** als **Zahl**

   1. Wählen Sie **googlesheets/value/1/1** aus der Dropdownliste unter Name der **zweiten Eigenschaft**

   1. Drag &amp; Drop **weiterer Vergleich: Eigenschaft - Eigenschaft **im Editor und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im Namen der **Voreigenschaft**

   1. Wählen Sie den **Operator** als **größer als **aus dem Dropdownmenü aus.

   1. **Datentyp** als **Nummer auswählen**

   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste unter Name der **zweiten Eigenschaft**
   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Bearbeiten Sie ähnliche Regeln und fügen Sie sie dem Segment **For_Blue** hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Bearbeiten Sie ähnliche Regeln und fügen Sie Vergleichseigenschaftsregeln zum Segment** For_Green **hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   Beachten Sie, dass Daten für Segmente **For_Green** und **For_Green** nicht in den Editor geladen werden können, da nur der erste Vergleich gemäß den Werten im Google-Blatt gültig ist.

1. Navigieren Sie zu Ihrem **DataDrivenRetail **Kanal (einem sequenzelt-Kanal) und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   Sie sollten Ihre **ContextHub** - **Konfigurationen** auf der Registerkarte "Kanaleigenschaften **"&gt; "** Personalisierung ****"eingerichtet haben.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht wie in der Abbildung oben gezeigt unter **Targeting-Konfigurationen** hinzufügen, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie die **Marke** und **Aktivität** beim Starten des Targeting im nächsten Schritt auswählen.

1. **Hinzufügen eines Standardbilds**

   1. Fügen Sie Ihrem Kanal ein Standardbild hinzu und klicken Sie auf **Targeting**.
   1. Wählen Sie **Marke** und **Aktivität** aus dem Dropdownmenü und klicken Sie auf Targeting **starten**.

   1. Klicken Sie auf **Targeting starten**.
   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   Bevor Sie mit dem Targeting beginnen, müssen Sie die Segmente (**For_Green**, **For_Red** und **For_Blue**) hinzufügen, indem Sie auf **+ Erlebnis-Targeting** hinzufügen klicken, wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Fügen Sie die Bilder zu allen drei verschiedenen Szenarios hinzu, wie unten dargestellt.

   ![retail_targeting](assets/retail_targeting.gif)

1. **Überprüfen der Vorschau**

   1. Click **Preview.** Öffnen Sie außerdem Ihr Google-Blatt und aktualisieren Sie dessen Wert.
   1. Ändern Sie den Wert für alle drei verschiedenen Spalten und Sie werden feststellen, dass das Anzeigebild entsprechend dem höchsten Wert im Bestand aktualisiert wird.
   ![retail_result](assets/retail_result.gif)

## Anwendungsfall 2: Wetteraktivierung im Reisezentrum {#use-case-travel-center-weather-activation}

Im folgenden Anwendungsfall werden zwei verschiedene Bilder basierend auf den Werten in Ihrem Google Sheet veranschaulicht.

### Beschreibung {#description-1}

Wenn Ihre Google-Blätter einen Wert unter 50 haben, wird in diesem Fall ein Bild mit heißen Getränken angezeigt, und wenn der Wert größer oder gleich 50 ist, wird das Bild mit kalten Getränken angezeigt. Bei einem anderen oder keinem Wert zeigt der Player ein Standardbild an.

### Verfahren {#procedure-1}

Gehen Sie wie folgt vor, um den Anwendungsfall für die Wetteraktivierung im Reisezentrum für Ihr AEM Screens-Projekt zu implementieren:

1. **Füllen der Google-Blätter**

   1. Navigieren Sie zum Google-Sheet "ContextHubDemo".
   1. Fügen Sie eine Spalte mit **Überschrift1** mit dem entsprechenden Temperaturwert hinzu.
   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (erstellt in Schritt 5 von ***Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google-Blätter***).
   1. Wählen Sie die **Blätter A1 1** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Vergleichseigenschaft und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** als **größer oder gleich **aus dem Dropdown-Menü

   1. Geben Sie den **Wert** als **50 ein**

   1. Gleichermaßen wählen Sie die** Blätter A1 2 **und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Vergleichseigenschaft und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** als **kleiner als **aus dem Dropdownmenü aus.

   1. Geben Sie den **Wert** als **50 ein**

1. Navigieren Sie zum gewünschten Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten** . Im folgenden Beispiel, **DataDrivenWeather**, wird ein sequenzieller Kanal verwendet, um die Funktionalität zu präsentieren.

   >[!NOTE]
   Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten wie in Schritt 3 beschrieben vorkonfiguriert werden.

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   Sie sollten Ihre **ContextHub** - **Konfigurationen** auf der Registerkarte "Kanaleigenschaften **"&gt; "** Personalisierung ****"eingerichtet haben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht wie in der Abbildung oben gezeigt unter **Targeting-Konfigurationen** hinzufügen, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie die **Marke** und **Aktivität** beim Starten des Targeting im nächsten Schritt auswählen.

1. Wählen Sie **Targeting** aus dem Editor, wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü und klicken Sie auf Targeting **starten**.

   >[!NOTE]
   Wenn Sie die **Marke** unter **Targeting-Konfigurationen** hinzugefügt haben, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie in diesem Schritt nicht die **Marke** und **Aktivität** auswählen.

   ![new_activity3](assets/new_activity3.gif)

1. Überprüfen der Vorschau

   1. Click **Preview.** Öffnen Sie außerdem Ihr Google-Blatt und aktualisieren Sie dessen Wert.
   1. Ändern Sie den Wert auf weniger als 50, sollten Sie in der Lage sein, das Bild der Sommergetränke. Wenn der Wert im Google-Blatt 50 oder größer ist, als sollte in der Lage sein, das Bild von heißem Getränk anzuzeigen.
   ![result3](assets/result3.gif)

## Anwendungsfall 3:Gastgewerbereservierung Aktivierung {#use-case-hospitality-reservation-activation}

Im folgenden Anwendungsfall werden zwei verschiedene Bilder basierend auf den Werten und der Formel in Ihrem Google Sheet veranschaulicht.

### Beschreibung {#description-2}

Für diesen Verwendungsfall wird das Google Sheet mit einem Prozentsatz der Reservierung in zwei Restaurants **Restaurant1** und **Restaurant2** gefüllt. Eine Formel wird basierend auf den Werten von Restaurant1 und Restaurant2 angewendet und basierend auf der Formel wird der Spalte **AdTarget** der Wert 1 oder 2 zugewiesen.

Wenn **Restaurant1** &gt; **Restaurant2**, dann ist **AdTarget** der Wert 1, andernfalls wird **AdTarget** der Wert 2 zugewiesen. Der Wert 1 generiert die Option *Steak food* und der Wert 2 zeigt die Option *Thai food* an.

### Verfahrensansatz {#procedural-approach}

Gehen Sie wie folgt vor, um den Anwendungsfall für die Aktivierung der Gastfreundschaftsreservierung für Ihr AEM Screens-Projekt zu implementieren:

1. Füllen der Google-Blätter und Hinzufügen der Formel.

   Wenden Sie beispielsweise die Formel auf die dritte Spalte **AdTarget** an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (erstellt in Schritt 5 von ***Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google-Blätter***).
   1. Wählen Sie die **Blätter A1 1** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Vergleichseigenschaft und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** als **gleich **aus dem Dropdown-Menü

   1. Geben Sie den **Wert** als **1 ein**

   1. Gleichermaßen wählen Sie die** Blätter A1 2 **und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Vergleichseigenschaft und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdownliste im **Eigenschaftsnamen**

   1. Wählen Sie den **Operator** als **2**

1. Navigieren Sie zum gewünschten Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten** . Im folgenden Beispiel, **DataDrivenRestaurant**, wird ein sequenzieller Kanal verwendet, um die Funktionalität zu präsentieren.

   >[!NOTE]
   Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten vorkonfiguriert sein, wie in Schritt 3 beschrieben.

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   Sie sollten Ihre **ContextHub** - **Konfigurationen** auf der Registerkarte "Kanaleigenschaften **"&gt; "** Personalisierung ****"eingerichtet haben.

   ![screen_shot_2019-05-08at14903pm](assets/screen_shot_2019-05-08at14903pm.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht wie in der Abbildung oben gezeigt unter **Targeting-Konfigurationen** hinzufügen, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie die **Marke** und **Aktivität** beim Starten des Targeting im nächsten Schritt auswählen.

1. Wählen Sie **Targeting** aus dem Editor, wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü und klicken Sie auf Targeting **starten**.
1. Überprüfen der Vorschau

   1. Click **Preview.** Öffnen Sie außerdem Ihr Google-Blatt und aktualisieren Sie dessen Wert.
   1. Ändern Sie den Wert in Restaurant1 &gt; Restaurant2, sollten Sie in der Lage sein, das Bild von Steak Bild und Restaurant1 &lt; Restaurant12, sollten Sie in der Lage sein, Thai-Essen Bild auf Ihrem Bildschirm.
   ![result5](assets/result5.gif)

## Verwendungsfall 4: Textüberlagerung auf der Digital-Menü-Pinnwand {#use-case-digital-menu-board-text-overlay}

Im folgenden Anwendungsfall wird ein digitales Menü-Board-Anwendungsbeispiel veranschaulicht, das in Restaurants und Fast-Food-Gelenken häufig vorkommt.

### Beschreibung {#description-3}

Im folgenden Verwendungsfall wird beschrieben, wie Text-Überlagerungen in einem sequenziellen Kanal verwendet werden und wie die Wertaktualisierung des Preises in den Google-Blättern eine Aktualisierung der Komponente Text Overlay auslöst.

### Verfahrensansatz {#procedural-approach-1}

Führen Sie die folgenden Schritte aus, um die digitale Menükarte mit dem Anwendungsfall für die Textüberlagerung für Ihr AEM Screens-Projekt zu implementieren:

1. **Füllen der Google-Blätter**

   1. Navigieren Sie zu Ihren Google-Blättern.
   1. Fügen Sie eine Spalte mit Preiswert für den Anwendungsfall hinzu, wie in der folgenden Abbildung dargestellt.
   ![screen_shot_2019-05-05at11344am](assets/screen_shot_2019-05-05at111344am.png)

1. **Hinzufügen eines Bildes zum Sequenzkanal**

   1. Navigieren Sie zu Ihrem Kanal (**DataDrivenAssets** —&gt; **Channels** —&gt; **DataDrivenTextOverlay**) und wählen Sie ihn aus.

   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
   1. Ziehen Sie ein Apfelkuchenbild per Drag &amp; Drop in den Editor.
   ![screen_shot_2019-05-05at112933am](assets/screen_shot_2019-05-05at112933am.png)

1. **Hinzufügen von Textüberlagerung zum Bild**

   1. Wählen Sie das Bild im Editor aus und klicken Sie auf Konfigurieren.
   1. Navigieren Sie zur Registerkarte " **Textüberlagerung** "und fügen Sie dem Bild die Textüberlagerung hinzu. Um den Wert aus Ihren Google-Blättern abzurufen, stellen Sie sicher, dass der Wert in den geschweiften Verzweigungen eingeschlossen ist. Beispielsweise wird der Preis aus den Google-Blättern abgerufen und bei der Definition der Textüberlagerung als **{price}** angegeben.

   1. Navigieren Sie zur Registerkarte **ContextHub** und konfigurieren Sie den Wert, der aus den Google-Bogen abgerufen werden soll, wie in der folgenden Abbildung dargestellt.
   ![textoverlay_result](assets/textoverlay_result.gif)

1. **Überprüfen der Vorschau**

   <!-- Edit text in steps below. wonky-->

   1. Click **Preview**.  Öffnen Sie außerdem Ihr Google-Blatt und aktualisieren Sie dessen Wert.
   1. Ändern Sie den Wert unter **Preis** , und Sie werden den Wert, der in der Textüberlagerung verwendet wird, entsprechend aktualisieren, wie in der Abbildung unten dargestellt.
   ![textoverlay_result-1](assets/textoverlay_result-1.gif)
