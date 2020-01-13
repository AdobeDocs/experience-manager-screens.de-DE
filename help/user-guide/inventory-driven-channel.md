---
title: Bestandsgesteuerter Kanal
seo-title: Bestandsgesteuerter Kanal
description: 'null'
seo-description: 'null'
page-status-flag: never-activated
uuid: a7e7aa08-8f9e-4458-bdce-225cf29a6da4
contentOwner: jsyal
discoiquuid: 9989ef4c-9fdd-4bf2-9f7c-0c74a9cc4e7f
docset: aem65
translation-type: ht
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Bestandsgesteuerter Kanal{#inventory-driven-channel}

## Erste Schritte mit bestandsgesteuerten Kanälen {#getting-started-with-inventory-driven-channels}

In diesem Abschnitt wird ein Nutzungsszenario beschrieben, das sich mit der Erstellung und Verwaltung einer datengesteuerten Asset-Änderung mithilfe von Google Tabellen befasst.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Nutzungsszenario beginnen, sollten Sie sich mit den folgenden Themen vertraut machen:

* **[Erstellen und Verwalten von Kanälen](managing-channels.md)**
* **[Erstellen und Verwalten von Standorten](managing-locations.md)**
* **[Erstellen und Verwalten von Zeitplänen](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Autoren von Inhalten

### Begriffe {#terminolgies}

Befolgen Sie die nachstehenden Begriffe, die für das Verständnis und die Einrichtung des Projekts in den verschiedenen Nutzungsszenarien von entscheidender Bedeutung sind:

**Aktivität** Aktivität bezieht sich auf die Kategorie.

**Bereich** Hauptbereich des Projekts

**Zielgruppe** Standort der Daten

**Marke** Marke bezieht sich auf

**Segment** Segment bezieht sich auf einen Container mit Assets, die Sie für das Targeting verwenden möchten.

### Grundlegender Ablauf: Einrichten des Projekts {#basic-flow-setting-up-the-project}

>[!NOTE]
>
>**Voraussetzung:**
>
>Bevor Sie sich näher mit den Details zur Einrichtung und Verwendung datengesteuerter Asset-Änderungen in Ihrem Projekt befassen, stellen Sie sicher, dass Sie ein AEM Screens-Projekt mit einem Sequenzkanal erstellen. Zu Demozwecken werden dem Projekt **DataDrivenAsset** die Sequenzkanäle **DataDrivenRestaurant**, **DataDrivenTextOverlay**, **DataDrivenWeather** und **DataDrivenRetail** hinzugefügt (siehe folgende Abbildung).
>
>Die Erstellung von vier verschiedenen Kanälen dient nur zu Demonstrationszwecken und zur Präsentation von vier verschiedenen Nutzungsszenarios in verschiedenen Kanälen. Wenn Sie nur ein Nutzungsszenario als Ihre Anforderung verfolgen möchten, können Sie auch nur einen Sequenzkanal erstellen.

![screen_shot_2019-05-01at42043pm](assets/screen_shot_2019-05-01at42043pm.png)

Befolgen Sie die folgenden Abschnitte, um ein Beispielprojekt zum Erstellen und Verwalten einer datengesteuerten Asset-Änderung mit Google Tabellen in einem AEM Screens-Projekt zu erstellen:

## Schritt 1: Einrichten der Datenbank {#step-setting-up-database}

>[!CAUTION]
>
>Google Tabellen wird im folgenden Beispiel als Beispieldatenbanksystem verwendet, von dem die Werte abgerufen werden. Dies dient ausschließlich zu Forbildungszwecken. Adobe unterstützt die Verwendung von Google Tabellen in Produktionsumgebungen nicht.
>
>Weitere Informationen finden Sie in der Google-Dokumentation unter [Abrufen eines API-Schlüssels](https://developers.google.com/maps/documentation/javascript/get-api-key).

1. Melden Sie sich bei Google Docs an.

   >[!NOTE]
   >
   >Sie müssen über ein Konto bei Google Drive verfügen, damit Sie eine neue Google Tabelle erstellen können.

1. Starten Sie eine neue leere Tabelle. Fügen Sie Ihrer Google Tabelle Inhalt hinzu und speichern Sie sie. Zu Demozwecken wird die Google Tabelle als **ContextHubDemo** bezeichnet.
1. Klicken Sie in der oberen rechten Ecke der Google Tabelle auf **Freigeben**, um das Dialogfeld **Für andere freigeben** zu öffnen. Klicken Sie auf die Option **Erweitert** und ändern Sie die Einstellungen in **Ein - Jeder, der über den Link verfügt**, wie in der Abbildung unten dargestellt.

   Mit diesem Schritt können Sie auf Werte in der Google Tabelle zugreifen.

   ![screen_shot_2019-04-22at115829am](assets/screen_shot_2019-04-22at115829am.png)

1. Wenn Sie im vorherigen Schritt auf **Speichern** klicken, erhalten Sie den Link für die Google Tabelle. Speichern Sie den Link zur späteren Verwendung und klicken Sie auf **Fertig**.

   ![screen_shot_2019-04-22at120242pm](assets/screen_shot_2019-04-22at120242pm.png)

>[!CAUTION]
>
>Google Tabellen wird im folgenden Beispiel für Fortbildungszwecke verwendet. Adobe unterstützt die Verwendung von Google Tabellen in Produktionsumgebungen nicht.

## Schritt 2: Aktivieren der Google Tabellen-REST-APIs {#step-enabling-the-google-sheets-rest-apis}

Nachdem Sie Ihre Google Tabelle eingerichtet haben, müssen Sie die Google Tabellen-REST-API aktivieren, um auf die Werte zuzugreifen.

Informationen zum Aktivieren der REST-APIs für Google Tabellen finden Sie in der Dokumentation zu den Google-APIs.

1. Navigieren Sie zur [Google API Console](https://console.developers.google.com/apis/credentials). Klicken Sie auf **ERSTELLEN**, um ein neues Projekt zu erstellen.

   ![screen_shot_2019-04-22at125028pm](assets/screen_shot_2019-04-22at125028pm.png)

1. Geben Sie unter **Projektnamen** den Wert **AssetChange** ein und klicken Sie auf **ERSTELLEN**.
1. Nachdem Sie das Projekt erstellt haben, müssen Sie den API-Schlüssel einrichten. Klicken Sie auf **Anmeldeinformationen erstellen** und wählen Sie „API-Schlüssel“ aus, um den API-Schlüssel für Ihr Projekt zu generieren. Speichern Sie den API-Schlüssel zur späteren Verwendung.

   >[!NOTE]
   >
   >Dieses Demoprojekt verwendet den kostenlosen Google-API-Schlüssel. Weitere Informationen (hinsichtlich Preisen und Einschränkungen) finden Sie auf der Website von Google **API-Schlüssel abrufen**.

### Überprüfen der Einrichtung von Google Tabellen {#verifying-the-setup-of-google-sheets}

```
Verify the data in your Google Sheets using the steps below
```

[https://sheets.googleapis.com/v4/spreadsheets/](https://sheets.googleapis.com/v4/spreadsheets/)&lt;Ihre Tabellenblatt-ID&gt;/values/Sheet1?key=&lt;Ihr API-Schlüssel&gt;

Beispiel:

Wenn der Link „Google Tabellen“ *wie folgt lautet:*

`https://docs.google.com/spreadsheets/d/1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M/edit?usp=sharing`, ist die

**Tabellen-ID**: `1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M`

Der **API-Schlüssel** ist: `AIzaSyAfoANOeLkFCCyohjL8cOdJLhrhGefqEy8`

Fügen Sie beide Werte in der obigen Syntax hinzu:

`https://sheets.googleapis.com/v4/spreadsheets/1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M/values/Sheet1?key=AIzaSyAfoANOeLkFCCyohjL8cOdJLhrhGefqEy8`

Sie sollten jetzt in der Lage sein, Ihre Daten im Arbeitsblatt anzuzeigen.

## Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google Tabellen {#step-configuring-aem-to-fetch-the-content-of-the-google-sheets}

Im folgenden Abschnitt wird beschrieben, wie Sie Adobe Experience Manager (AEM) so konfigurieren, dass Inhalte aus den Google Tabellen abgerufen werden.

1. Navigieren Sie zu Ihrer AEM-Instanz und klicken Sie in der linken Seitenleiste auf das Symbol „Tools“. Klicken Sie auf **Sites** &gt; **ContextHub**, wie in der Abbildung unten gezeigt.

   ![screen_shot_2019-04-22at53222pm](assets/screen_shot_2019-04-22at53222pm.png)

1. **Erstellen einer neuen ContextHub Store-Konfiguration**

   1. Navigieren Sie zu **global** &gt; **default** &gt; **ContextHub-Konfiguration**.

   1. Klicken Sie auf „Erstellen“ &gt; „Konfigurations-Container“ **und geben Sie als Titel**„ContextHubDemo“ ein.

   1. **Navigieren** Sie zu **ContextHubDemo** &gt; **ContentHub Store-Konfiguration...**, um den **Konfigurationsassistenten** zu öffnen
   1. Geben Sie unter **Titel** den Wert **Google Tabellen**, unter **Store-Name** den Wert **googlesheets** und unter **Store-Typ** den Wert **contexthub.generic-jsonp** ein.
   1. Klicken Sie auf **Weiter**
   1. Geben Sie Ihre spezifische json-Konfiguration ein. Beispielsweise können Sie die folgende json für Demozwecke verwenden.
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
   >Im obigen Beispiel-Code definiert **pollInterval** die Häufigkeit, mit der die Werte aktualisiert werden (in ms).
   >
   >
   >Ersetzen Sie den Code durch Ihre *&lt;Tabellenblatt-ID&gt;* und Ihren *&lt;API-Schlüssel&gt;*, den Sie aus **Schritt 1: Einrichten der Datenbank** abgerufen haben.

   >[!CAUTION]
   Wenn Sie Google Tabellen-Store-Konfigurationen außerhalb des bestehenden Ordners erstellen (z. B. in Ihrem eigenen Projektordner), funktioniert das Targeting nicht standardmäßig.
   Wenn Sie die Google Tabellen-Store-Konfigurationen außerhalb des bestehenden globalen Ordners konfigurieren möchten, müssen Sie den **Store-Namen** als **segmentation** und den **Store-Typ** als **aem.segmentation** festlegen. Außerdem müssen Sie den Prozess der Definition des json wie oben definiert überspringen.

1. **Erstellen einer Marke in „Aktivitäten“**

   1. Navigieren Sie von Ihrer AEM-Instanz aus zu **Personalisierung** &gt; **Aktivitäten**

   1. Klicken Sie auf „Erstellen“ &gt; **Marke erstellen**

   1. Wählen Sie im Assistenten **Seite erstellen** die Option **Marke** aus und klicken Sie auf **Weiter**.

   1. Geben Sie unter **Titel** den Wert **ContextHubDemo** ein und klicken Sie auf **Erstellen**. Ihre Marke wird jetzt wie unten dargestellt erstellt.
   ![screen_shot_2019-05-05at44305pm](assets/screen_shot_2019-05-05at44305pm.png)

1. 

>[!CAUTION]
Bekanntes Problem:
Um einen Bereich hinzuzufügen, entfernen Sie den Master aus der URL, z. B.
[https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master](https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master)

1. Erstellen eines Bereichs in Ihrer Marke

   1. Klicken Sie auf **Erstellen** &gt; **Bereich erstellen**

   1. Wählen Sie im Assistenten „Seite erstellen“ die Option **Bereich** aus und klicken Sie auf „Weiter“

   1. Geben Sie unter **Titel** den Wert **GoogleTabellen** ein und klicken Sie auf **Erstellen**. Ihr Bereich wird in Ihrer Aktivität erstellt.

1. **Erstellen von Segmenten in Zielgruppen**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** &gt; **Zielgruppen** &gt; **We.Retail**.
   1. Klicken Sie auf **Erstellen** &gt; **ContextHub-Segment erstellen**. Das Dialogfeld „Neues ContextHub-Segment“ wird geöffnet.
   1. Geben Sie unter **Titel** den Wert **TabellenblattA1 1** ein und klicken Sie auf **Erstellen**. Erstellen Sie auf ähnliche Weise ein weiteres Segment mit der Bezeichnung **TabellenblattA2 2**.

1. **Bearbeiten der Segmente**

   1. Wählen Sie das Segment **Tabellenblatt A1 1** (erstellt in Schritt 5) aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   1. Ziehen Sie die Komponente **Vergleich: Eigenschaft - Wert** in den Editor.
   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich von Eigenschaft und Wert** zu öffnen.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus.

   1. Wählen Sie unter **Operator** den Wert „Gleich“ aus dem Dropdown-Menü aus.

   1. Geben Sie den **Wert** als **1** ein.
   >[!NOTE]
   AEM validiert Ihre Daten aus dem Google-Tabellenblatt, indem Ihr Segment grün anzeigt wird.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Bearbeiten Sie die Eigenschaftswerte entsprechend in **Tabellen A1 2**.

   1. Ziehen Sie die Komponente **Vergleich: Eigenschaft - Wert** in den Editor.
   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich von Eigenschaft und Wert** zu öffnen.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus.

   1. Wählen Sie unter **Operator** den Wert „Gleich“ aus dem Dropdown-Menü aus.

   1. Geben Sie den **Wert** als **2** ein.
   >[!NOTE]
   Die in den vorherigen Schritten angewendeten Regeln sind nur ein Beispiel dafür, wie Sie Segmente für die Implementierung der folgenden Anwendungsfälle einrichten.

## Schritt 3: Einrichten von Context Hub-Konfigurationen im AEM Screens-Kanal {#step-setting-up-context-hub-configurations-in-aem-screens-channel}

Gehen Sie wie unten beschrieben vor, um ContextHub-Konfigurationen und Segmentpfade zum AEM Screens-Kanal einzurichten.

1. Navigieren Sie zuerst zu einem der von Ihnen erstellten AEM Screens-Kanäle (**DataDrivenRetail**).
1. Wählen Sie den Kanal (**DataDrivenRetail**) aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   ![screen_shot_2019-05-01at43332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Wählen Sie die Registerkarte **Personalisierung**, um die ContextHub-Konfigurationen einzurichten.

   1. Wählen Sie unter **ContextHub-Pfad** den Wert **libs** &gt; **settings** &gt; **cloudsettings** &gt; **default** &gt; **ContextHub Konfigurationen** aus und klicken Sie auf **Auswählen**.

   1. Wählen Sie unter **Segmentpfad** den Wert **conf** &gt; „We.Retail“ &gt; **settings** &gt; **wcm** &gt; **segments** aus und klicken Sie auf **Auswählen**.

   1. Klicken Sie auf **Speichern und schließen**.
   >[!NOTE]
   Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie Ihre Kontexthub-Konfigurationen und -Segmente anfänglich gespeichert haben.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht im obigen Dialogfeld unter **Targeting-Konfiguration** auswählen, müssen Sie die Marke und Aktivität auswählen, wenn Sie den Targeting-Prozess starten.

1. Navigieren Sie zu und wählen Sie **DataDrivenRetail** aus **DataDrivenAssets** &gt; „Kanäle“ aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   >[!NOTE]
   Wenn Sie alles korrekt eingerichtet haben, sehen Sie die Option **Targeting** in der Dropdown-Liste des Editors, wie in der Abbildung unten gezeigt.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

   >[!NOTE]
   Nachdem Sie die ContextHub-Konfigurationen für Ihren Kanal konfiguriert haben, stellen Sie sicher, dass Sie die vorhergehenden Schritte 1 bis 4 auch für die anderen drei Sequenzkanäle befolgen, wenn Sie alle unten aufgeführten Anwendungsfälle nutzen möchten.

## Anwendungsbeispiel 1: Aktivierung des Einzelhandelinventars {#use-case-retail-inventory-activation}

Im folgenden Anwendungsbeispiel werden je nach den Werten in Ihrer Google Tabelle drei verschiedene Bilder dargestellt.

### Beschreibung {#description}

In diesem Anwendungsbeispiel wird der Lagerbestand für drei verschiedenfarbige Pullover veranschaulicht. Je nachdem, wie viele Pullover auf Lager vorhanden sind (erfasst in Google Tabellen), wird das Bild (roter, grüner oder blauer Pullover) mit der höchsten Zahl auf dem Bildschirm angezeigt.

Für dieses Anwendungsbeispiel wird je nach der höchsten verfügbaren Anzahl an Pullovern der rote, grüne oder blaue Pullover auf dem Bildschirm angezeigt.

### Verfahrensweise {#procedure}

Gehen Sie wie folgt vor, um das Anwendungsbeispiel zur Aktivierung des Einzelhandelsinventars zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zur Google Tabelle „ContextHubDemo“.
   1. Fügen Sie drei Spalten (Rot, Grün und Blau) mit entsprechenden Werten für drei verschiedene Pullover hinzu.
   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Konfigurieren der Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (erstellt in Schritt (5) im Abschnitt ***Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google Tabellen***).
   1. Fügen Sie drei neue Segmente **Für_Rot**, **Für_Grün** und **Für_Blau** hinzu.

   1. Wählen Sie **Für_Rot** und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   1. Ziehen Sie den **Vergleich: Eigenschaft - Eigenschaft** per Drag-and-Drop in den Editor und klicken Sie auf das Konfigurationssymbol, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdown-Liste in **Name der ersten Eigenschaft** aus.

   1. Wählen Sie unter **Operator** den Wert „größer als“ aus dem Dropdown-Menü aus

   1. Wählen Sie als **Datentyp** die Option **Zahl**.

   1. Wählen Sie **googlesheets/value/1/1** aus der Dropdown-Liste in **Name der zweiten Eigenschaft**.

   1. Ziehen Sie „Weiterer Vergleich: Eigenschaft - Eigenschaft“ per Drag-and-Drop in den Editor und klicken Sie auf das Konfigurationssymbol, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdown-Liste in **Name der ersten Eigenschaft** aus.

   1. Wählen Sie unter **Operator** den Wert „größer als“ aus dem Dropdown-Menü aus

   1. Wählen Sie als **Datentyp** die Option **Zahl**.

   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Name der zweiten Eigenschaft**.
   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Bearbeiten und fügen Sie auf gleiche Weise Vergleichseigenschaftsregeln zum Segment **Für_Blau** hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Bearbeiten und fügen Sie auf gleiche Weise Vergleichseigenschaftsregeln zum Segment „Für_Grün“ hinzu, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   Sie werden feststellen, dass sich Daten für die Segmente **Für_Grün** und **Für_Grün** im Editor nicht laden lassen, da gemäß den Werten in der Google Tabelle nur der erste Vergleich gültig ist.

1. Navigieren Sie zu Ihrem Kanal „DataDrivenRetail“ (einem Sequenzkanal) und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   Sie sollten Ihre **ContextHub**-**Konfigurationen** auf der Registerkarte **Eigenschaften** für Kanäle &gt; **Personalisierung** eingerichtet haben.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht wie in der Abbildung oben gezeigt unter **Targeting-Konfigurationen** hinzufügen, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie die **Marke** und **Aktivität** beim Starten des Targetings im nächsten Schritt auswählen.

1. **Hinzufügen eines Standardbilds**

   1. Fügen Sie Ihrem Kanal ein Standardbild hinzu und klicken Sie auf **Targeting**.
   1. Wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü und klicken Sie auf **Targeting starten**.

   1. Klicken Sie auf **Targeting starten**.
   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   Bevor Sie mit dem Targeting beginnen, müssen Sie die Segmente (**Für_Grün**, **Für_Rot** und **Für_Blau**) hinzufügen, indem Sie auf **+ Erlebnis-Targeting hinzufügen** klicken (wie in der folgenden Abbildung dargestellt).

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Fügen Sie die Bilder den drei verschiedenen Szenarien hinzu, wie unten dargestellt.

   ![retail_targeting](assets/retail_targeting.gif)

1. **Überprüfen der Vorschau**

   1. Klicken Sie auf **Vorschau.**. Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Ändern Sie den Wert für die drei verschiedenen Spalten und Sie werden sehen, dass das Anzeigebild entsprechend dem höchsten Wert im Bestand aktualisiert wird.
   ![retail_result](assets/retail_result.gif)

## Anwendungsbeispiel 2: Temperaturaktivierung für ein Reiseangebot {#use-case-travel-center-weather-activation}

Im folgenden Anwendungsbeispiel werden je nach den Werten in Ihrer Google Tabelle zwei verschiedene Bilder dargestellt.

### Beschreibung {#description-1}

Wenn Ihre Google Tabelle einen Wert unter 10 hat, wird in diesem Nutzungsszenario ein Bild mit heißen Getränken angezeigt, und wenn der Wert größer oder gleich 10 ist, wird das Bild mit kalten Getränken angezeigt. Bei einem anderen oder keinem Wert zeigt der Player ein Standardbild an.

### Verfahrensweise {#procedure-1}

Gehen Sie wie folgt vor, um das Nutzungsszenario für die Temperaturaktivierung für ein Reiseangebot für Ihr AEM Screens-Projekt zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zur Google Tabelle „ContextHubDemo“.
   1. Fügen Sie eine Spalte mit **Überschrift1** mit dem entsprechenden Temperaturwert hinzu.
   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (erstellt in Schritt (5) im Abschnitt ***Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google Tabellen***).
   1. Wählen Sie **Tabellen A1 1** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Eigenschaft zum Vergleichen aus und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus

   1. Wählen Sie unter **Operator** den Wert „größer oder gleich“ aus dem Dropdown-Menü aus

   1. Geben Sie den **Wert** als **50** ein

   1. Wählen Sie nun „Tabellen A1 2“ aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Eigenschaft zum Vergleichen aus und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus

   1. Wählen Sie unter **Operator** den Wert „kleiner als“ aus dem Dropdown-Menü aus

   1. Geben Sie den **Wert** als **50** ein

1. Navigieren Sie zu Ihrem Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Im folgenden Beispiel wird ein sequenzieller Kanal **DataDrivenWeather** verwendet, um die Funktionalität zu demonstrieren.

   >[!NOTE]
   Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten – wie in Schritt (3) beschrieben – vorkonfiguriert sein

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   Sie sollten Ihre **ContextHub**-**Konfigurationen** auf der Registerkarte **Eigenschaften** für Kanäle &gt; **Personalisierung** eingerichtet haben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht wie in der Abbildung oben gezeigt unter **Targeting-Konfigurationen** hinzufügen, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie die **Marke** und **Aktivität** beim Starten des Targetings im nächsten Schritt auswählen.

1. Wählen Sie **Targeting** aus dem Editor aus. Wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü aus und klicken Sie auf **Targeting starten**.

   >[!NOTE]
   Wenn Sie die **Marke** unter **Targeting-Konfigurationen** hinzugefügt haben, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie in diesem Schritt nicht die **Marke** und **Aktivität** auswählen.

   ![new_activity3](assets/new_activity3.gif)

1. Überprüfen der Vorschau

   1. Klicken Sie auf **Vorschau.**. Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Wenn Sie den Wert auf weniger als 10 ändern, sollte ein Bild mit Sommergetränken angezeigt werden. Wenn der Wert in der Google Tabelle 10 oder größer ist, sollte ein Bild mit heißen Getränken angezeigt werden.
   ![result3](assets/result3.gif)

## Anwendungsbeispiel 3: Aktivierung der Gastgewerbereservierung {#use-case-hospitality-reservation-activation}

Im folgenden Anwendungsbeispiel werden zwei verschiedene Bilder basierend auf den Werten und der angewandten Formel in Ihrer Google Tabelle dargestellt.

### Beschreibung {#description-2}

Für dieses Nutzungsszenario wird die Google Tabelle mit dem Reservierungsprozentsatz für zwei Restaurants **Restaurant1** und **Restaurant2** gefüllt. Eine Formel wird anhand der Werte von Restaurant1 und Restaurant2 angewendet und anhand der Formel wird der Spalte **AdTarget** der Wert „1“ oder „2“ zugewiesen.

Wenn **Restaurant1** &gt; **Restaurant2**, dann ist der Wert von **AdTarget** „1“. Anderenfalls wird **AdTarget** der Wert „2“ zugewiesen. Der Wert „1“ generiert die Option *Steak-Gerichte* und der Wert „2“ zeigt die Option *Thailändisches Essen* auf Ihrem Bildschirm an.

### Vorgehensweise {#procedural-approach}

Gehen Sie wie folgt vor, um das Nutzungsszenario für die reservierungsgesteuerte Aktivierung im Gastgewerbe für Ihr AEM Screens-Projekt zu implementieren:

1. Füllen der Google Tabellen und Hinzufügen der Formel.

   Wenden Sie beispielsweise die Formel auf die dritte Spalte **AdTarget** an, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **Konfigurieren der Segmente in Zielgruppen gemäß den Anforderungen**

   1. Navigieren Sie zu den Segmenten in Ihrer Zielgruppe (erstellt in Schritt (5) im Abschnitt ***Schritt 2: Konfigurieren von AEM zum Abrufen des Inhalts der Google Tabellen***).
   1. Wählen Sie **Tabellen A1 1** aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Eigenschaft zum Vergleichen aus und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdown-Liste in **Eigenschaftsname** aus

   1. Wählen Sie unter **Operator** den Wert „Gleich“ aus dem Dropdown-Menü aus

   1. Geben Sie den **Wert** als **1** ein

   1. Wählen Sie nun „Tabellen A1 2“ aus und klicken Sie auf **Bearbeiten**.

   1. Wählen Sie die Eigenschaft zum Vergleichen aus und klicken Sie auf das Symbol zum Konfigurieren, um die Eigenschaften zu bearbeiten.
   1. Wählen Sie **googlesheets/value/1/2** aus der Dropdown-Liste in **Eigenschaftsname** aus

   1. Wählen Sie den **Operator** als **2** aus

1. Navigieren Sie zu Ihrem Kanal () und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Im folgenden Beispiel wird ein sequenzieller Kanal **DataDrivenRestaurant** verwendet, um die Funktionalität zu demonstrieren.

   >[!NOTE]
   Ihr Kanal sollte bereits über ein Standardbild verfügen und die Zielgruppen sollten – wie in Schritt (3) beschrieben – vorkonfiguriert sein.

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   Sie sollten Ihre **ContextHub**-**Konfigurationen** auf der Registerkarte **Eigenschaften** für Kanäle &gt; **Personalisierung** eingerichtet haben.

   ![screen_shot_2019-05-08at14903pm](assets/screen_shot_2019-05-08at14903pm.png)

   >[!NOTE]
   Wenn Sie die **Marke** nicht wie in der Abbildung oben gezeigt unter **Targeting-Konfigurationen** hinzufügen, während Sie **ContextHub-Konfigurationen** für Ihr Projekt einrichten, müssen Sie die **Marke** und **Aktivität** beim Starten des Targetings im nächsten Schritt auswählen.

1. Wählen Sie **Targeting** aus dem Editor aus. Wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü aus und klicken Sie auf **Targeting starten**.
1. Überprüfen der Vorschau

   1. Klicken Sie auf **Vorschau.**. Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Wenn Sie den Wert in „Restaurant1“ &gt; „Restaurant2“ ändern, sollte ein Bild eines Steak-Gerichts angezeigt werden. Wenn „Restaurant1“ &lt; „Restaurant2“, sollte ein Bild mit thailändischem Essen auf Ihrem Bildschirm angezeigt werden.
   ![result5](assets/result5.gif)

## Anwendungsbeispiel 4: Textüberlagerung für digitale Speisekarten {#use-case-digital-menu-board-text-overlay}

Im folgenden Anwendungsbeispiel wird eine digitale Speisekarte vorgestellt, die in Restaurants und Schnellimbisslokalen häufig vorkommt.

### Beschreibung {#description-3}

Im folgenden Anwendungsbeispiel wird beschrieben, wie Textüberlagerungen in einem sequenziellen Kanal verwendet werden und wie die Aktualisierung eines Preises in den Google Tabellen eine Aktualisierung der Textüberlagerungskomponente auslöst.

### Vorgehensweise {#procedural-approach-1}

Gehen Sie wie folgt vor, um das Anwendungsbeispiel für eine digitale Speisekarte mit Textüberlagerung für Ihr AEM Screens-Projekt zu implementieren:

1. **Ausfüllen der Google Tabellen**

   1. Navigieren Sie zu Ihren Google Tabellen.
   1. Fügen Sie eine Spalte mit dem Preiswert für das Anwendungsbeispiel hinzu, wie in der folgenden Abbildung dargestellt.
   ![screen_shot_2019-05-05at111344am](assets/screen_shot_2019-05-05at111344am.png)

1. **Hinzufügen eines Bildes zum Sequenzkanal**

   1. Navigieren Sie zu Ihrem Kanal (**DataDrivenAssets** &gt; **Kanäle** &gt; **DataDrivenTextOverlay**) und wählen Sie ihn aus.

   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
   1. Ziehen Sie ein Bild mit Apfelkuchen in den Editor.
   ![screen_shot_2019-05-05at112933am](assets/screen_shot_2019-05-05at112933am.png)

1. **Hinzufügen von Textüberlagerung zum Bild**

   1. Wählen Sie das Bild im Editor aus und klicken Sie auf „Konfigurieren“.
   1. Navigieren Sie zur Registerkarte **Textüberlagerung** und fügen Sie dem Bild die Textüberlagerung hinzu. Um den Wert aus Ihren Google Tabellen abzurufen, stellen Sie sicher, dass der Wert in den geschweiften Klammern eingeschlossen ist. Beispielsweise wird der Preis aus den Google Tabellen abgerufen und bei der Definition der Textüberlagerung als **{Preis}** angegeben.

   1. Navigieren Sie zur Registerkarte **ContextHub** und konfigurieren Sie den Wert, der aus den Google Tabellen abgerufen werden soll, wie in der folgenden Abbildung dargestellt.
   ![textoverlay_result](assets/textoverlay_result.gif)

1. **Überprüfen der Vorschau**

   <!-- Edit text in steps below. wonky-->

   1. Klicken Sie auf **Vorschau**.  Öffnen Sie außerdem Ihre Google Tabelle und aktualisieren Sie den Wert.
   1. Wenn Sie den Wert unter **Preis** ändern, wird der in der Textüberlagerung angezeigte Wert entsprechend aktualisiert (siehe Abbildung unten).
   ![textoverlay_result-1](assets/textoverlay_result-1.gif)
