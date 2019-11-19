---
title: ContextHub in AEM Screens konfigurieren
seo-title: ContextHub in AEM Screens konfigurieren
description: Auf dieser Seite erfahren Sie mehr über ContextHub in der Targeting-Engine, um den Datenspeicher zum Zweck der Datenauslöserinhaltsänderung zu definieren.
seo-description: Auf dieser Seite erfahren Sie mehr über ContextHub in der Targeting-Engine, um den Datenspeicher zum Zweck der Datenauslöserinhaltsänderung zu definieren.
uuid: be06bda8-7de9-40d6-a84b-5ed8d8b3d180
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
discoiquuid: 9a26b5cd-b957-4df7-9b5b-f57e32b4196a
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# ContextHub in AEM Screens konfigurieren {#configuring-contexthub-in-aem-screens}

Dieser Abschnitt hebt hervor, wie datengesteuerte Asset-Änderungen mithilfe eines Datenspeichers erstellt und verwaltet werden.

## Schlüsselbegriffe {#key-terms}

Bevor wir uns mit der Erstellung und Verwaltung von Bestandskanälen in Ihrem AEM Screens-Projekt beschäftigen, müssen Sie sich mit einigen der Schlüsselbegriffe vertraut machen, die für die verschiedenen Szenarien wichtig und relevant sind.

**Marke** bezieht sich auf Ihre allgemeine Projektbeschreibung.

**Bereich** bezieht sich auf den Namen Ihres AEM Screens-Projekts, z. B. Digital Ad Signage

**Aktivität** Definiert die Regelkategorie wie "Inventarorientiert", "Wettergesteuert", "Verfügbarkeitsorientiert in einer Abteilung"usw.

**Zielgruppe** Definiert die Regel.

**Segment** bezieht sich auf die Version des Assets, die für die jeweilige Regel abgespielt werden soll, z. B. wenn die Temperatur unter 50 Grad Fahrenheit liegt, dann zeigt der Bildschirm ein Bild eines heißen Kaffees an, andernfalls ein kaltes Getränk.

Das folgende Diagramm zeigt visuell, wie ContextHub-Konfigurationen mit Aktivität, Zielgruppe und Kanälen zusammenfallen.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Voraussetzungen {#preconditions}

Bevor Sie mit der Einrichtung eines Datenspeichers für die Konfiguration von Context Hub-Konfigurationen für ein AEM Screens-Projekt beginnen, müssen Sie Google Sheets (für Demonstrationszwecke) einrichten.

>[!CAUTION]
>
>Google Sheets werden im folgenden Beispiel als Beispiel-Datenbanksystem verwendet, von dem die Werte abgerufen werden und ausschließlich zu Bildungszwecken dienen. Adobe unterstützt die Verwendung von Google-Blättern in Produktionsumgebungen nicht.
>
>Weitere Informationen finden Sie in der Google-Dokumentation unter API-Schlüssel [abrufen](https://developers.google.com/maps/documentation/javascript/get-api-key) .

## Schritt 1: Einrichten eines Datenspeichers {#step-setting-up-a-data-store}

Gehen Sie wie unten beschrieben vor, um einen Datenspeicher einzurichten, mit dem Sie ContextHub-Konfigurationen und Segmentpfad zum AEM Screens-Kanal verwenden können.

1. **Navigieren zu ContextHub**

   Navigieren Sie zu Ihrer AEM-Instanz und klicken Sie in der linken Seitenleiste auf das Symbol "Tools". Klicken Sie auf **Sites** —&gt; **ContextHub**, wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-04-22at53222pm](assets/screen_shot_2019-04-22at53222pm.png)

1. **Erstellen einer neuen ContextHub Store-Konfiguration**

   1. Navigieren Sie zu **global** &gt; **default** &gt; **ContextHub-Konfiguration**.

   1. Klicken Sie auf** Erstellen &gt; Configuration Container **und geben Sie den Titel als** ContextHubDemo** ein.

   1. **** Navigieren Sie **zu** ContextHubDemo **&gt; Konfiguration des** ContentHub-Speichers... , um den Assistenten zum **Konfigurieren zu öffnen**.

   1. Geben Sie den **Titel** als **Google-Blätter**, **Store-Name** als **Google-Heets** und **Store-Typ** alscontexthub.generic-jsonp ein **.**

   1. Klicken Sie auf **Weiter**
   1. Geben Sie Ihre spezifische JSON-Konfiguration ein**.** Beispielsweise können Sie die folgende JSON für Demozwecke verwenden.
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
   >Ersetzen Sie den Code durch Ihren *&lt;Sheet ID&gt;* - und *&lt;API-Schlüssel&gt;*, den Sie beim Einrichten der Google-Arbeitsblätter abgerufen haben.

   >[!CAUTION]
   Wenn Sie Google Sheets Store-Konfigurationen außerhalb des Legacy-Ordners erstellen (z. B. in Ihrem eigenen Projektordner), funktioniert das Targeting nicht standardmäßig.
   Wenn Sie die Google Sheets Store-Konfigurationen außerhalb des globalen Legacy-Ordners konfigurieren möchten, müssen Sie den **Store-Namen** als **Segmentierung** und **Store-Typ** als **aem.segmentation** festlegen. Außerdem müssen Sie den Prozess der Definition des JSON wie oben definiert überspringen.

1. **Erstellen einer Marke in Aktivitäten**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** &gt; **Aktivitäten**

   1. Klicken Sie auf **Erstellen** &gt; Marke **erstellen**

   1. Select **Brand** from the **Create Page** wizard and click **Next**

   1. Enter the **Title** as **ContextHubDemo** and click **Create**. Ihre Marke wird nun wie unten dargestellt erstellt.
   ![screen_shot_2019-05-05at44305pm](assets/screen_shot_2019-05-05at44305pm.png)


   >[!CAUTION]
   Bekanntes Problem:
   Um einen Bereich hinzuzufügen, entfernen Sie die Master aus der URL, z. B.
   `https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master`

1. **Erstellen eines Bereichs in Ihrer Marke**

   Gehen Sie wie folgt vor, um einen Bereich in der Marke zu erstellen:

   1. Klicken Sie auf **Erstellen** und dann auf Bereich **erstellen**

   1. Select **Area** from the **Create Page** wizard and click Next

   1. Enter the **Title** as **GoogleSheets** and click **Create**.
Ihr Bereich wird in Ihrer Aktivität erstellt.

## Schritt 2: Einrichten der Zielgruppensegmentierung {#step-setting-up-audience-segmentation}

Nachdem Sie einen Datenspeicher eingerichtet und Ihre Marke definiert haben, führen Sie die folgenden Schritte aus, um Zielgruppensegmente einzurichten.

1. **Erstellen von Segmenten in Zielgruppen**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** &gt; **Zielgruppen** &gt; **We.Retail**.

   1. Klicken Sie auf **Erstellen** &gt; Kontexthub-Segment **erstellen.** Das Dialogfeld **Neues ContextHub-Segment** wird geöffnet.

   1. Enter the **Title** as **SheetA1 1** and click **Create**. Erstellen Sie auf ähnliche Weise ein weiteres Segment mit der Bezeichnung **SheetA2 2**.

1. **Bearbeiten der Segmente**

   1. Wählen Sie die Segmentblätter **A1 1** (erstellt in Schritt 5) aus und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   1. Ziehen Sie den **Vergleich per Drag &amp; Drop: Eigenschaft - Komponente "Wert** "im Editor.
   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich einer Eigenschaft mit Wert** zu öffnen.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**.

   1. Wählen Sie den **Operator** aus dem Dropdown-Menü als **Equal** .

   1. Geben Sie den **Wert** als **1** ein.
   >[!NOTE]
   AEM validiert Ihre Daten aus dem Google-Blatt, indem Sie Ihr Segment grün anzeigen.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Bearbeiten Sie die Eigenschaftswerte entsprechend in **Blatt A1 2**.

   1. Ziehen Sie den **Vergleich per Drag &amp; Drop: Eigenschaft - Komponente "Wert** "im Editor.
   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich einer Eigenschaft mit Wert** zu öffnen.
   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdownliste im **Eigenschaftsnamen**.

   1. Wählen Sie den **Operator** aus dem Dropdown-Menü als **Equal** .

   1. Geben Sie den **Wert** als **2** ein.
   >[!NOTE]
   Die in den vorherigen Schritten angewendeten Regeln sind nur ein Beispiel dafür, wie Sie Segmente für die Implementierung der folgenden Anwendungsfälle einrichten.

## Schritt 3: Aktivieren des Targeting in Kanälen {#step-enabling-targeting-in-channels}

Gehen Sie wie folgt vor, um Targeting in Ihren Kanälen zu aktivieren.

1. Navigieren Sie zu einem der AEM-Bildschirme-Kanäle**. **Die folgenden Schritte zeigen, wie Sie das Targeting mithilfe von **DataDrivenRetail** aktivieren, die in einem AEM-Bildschirmkanal erstellt wurden.

1. Wählen Sie den Kanal **DataDrivenRetail** aus und klicken Sie in der Aktionsleiste auf **Eigenschaften** .

   ![screen_shot_2019-05-01at4332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Wählen Sie die Registerkarte **Personalisierung** , um die ContextHub-Konfigurationen einzurichten.

   1. Wählen Sie den **ContextHub-Pfad** als **libs** &gt; **Einstellungen** &gt; **Cloudsettings** &gt; **default** **** ****&gt; ContextHub-Konfigurationenaus und klicken Sie aufSelect.

   1. Wählen Sie den **Segmentpfad** als **conf** &gt; **We.Retail** &gt; **Einstellungen** &gt; **wcm** **** ****&gt;Segmentsaus und klicken Sie aufSelect.

   1. Klicken Sie auf **Speichern und schließen**.
   >[!NOTE]
   Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie zunächst Ihre Kontexthub-Konfigurationen und -Segmente gespeichert haben.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigieren Sie zum **DataDrivenRetail** unter **DataDrivenAssets** &gt; **Channels** und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   >[!NOTE]
   Wenn Sie alles korrekt eingerichtet haben, sehen Sie die Option **Targeting** in der Dropdown-Liste des Editors, wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

   >[!NOTE]
   Nachdem Sie die ContextHub-Konfigurationen für Ihren Kanal konfiguriert haben, stellen Sie sicher, dass Sie die vorhergehenden Schritte von 1 bis 4, auch für die anderen drei Sequenzkanäle, befolgen, wenn Sie alle unten aufgeführten Anwendungsfälle befolgen möchten.

## Weitere Informationen: Verwendungsbeispiele {#learn-more-example-use-cases}

Nachdem Sie ContextHub für Ihr AEM Screens-Projekt konfiguriert haben, können Sie die verschiedenen Anwendungsfälle befolgen, um zu verstehen, wie datenausgelöste Assets eine entscheidende Rolle in verschiedenen Branchen spielen:

1. **[Zielgerichtete Aktivierung des Einzelhandelsinventars](retail-inventory-activation.md)**
1. **[Aktivierung der Travel Center-Temperatur](local-temperature-activation.md)**
1. **[Gastgewerbereservierung Aktivierung](hospitality-reservation-activation.md)**
