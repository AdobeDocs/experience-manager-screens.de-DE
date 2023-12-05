---
title: Konfigurieren von ContextHub in AEM Screens
seo-title: Configuring ContextHub in AEM Screens
description: Auf dieser Seite erfahren Sie mehr über ContextHub in der Targeting-Engine, um den Datenspeicher für die Zwecke datenbasierter Inhaltsänderungen zu definieren.
seo-description: Follow this page to learn about ContextHub in the targeting engine to define data store for the purpose of data trigger content change.
uuid: be06bda8-7de9-40d6-a84b-5ed8d8b3d180
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
discoiquuid: 9a26b5cd-b957-4df7-9b5b-f57e32b4196a
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 04072107-d6be-4030-bb79-1f1a7609f37e
source-git-commit: 93e9514ebd25a4d84076174c4d90a0325b167393
workflow-type: ht
source-wordcount: '1513'
ht-degree: 100%

---

# Konfigurieren von ContextHub in AEM Screens {#configuring-contexthub-in-aem-screens}

Dieser Abschnitt konzentriert sich auf das Erstellen und Verwalten von datengesteuerten Asset-Änderungen mithilfe eines Datenspeichers.

## Schlüsselbegriffe {#key-terms}

Bevor wir uns mit der Erstellung und Verwaltung von bestandsgesteuerten Kanälen in Ihrem AEM Screens-Projekt beschäftigen, müssen Sie sich mit einigen der Schlüsselbegriffe vertraut machen, die für die verschiedenen Szenarien wichtig und relevant sind.

**Marke** bezieht sich auf Ihre allgemeine Projektbeschreibung.

**Bereich** bezieht sich auf den Namen Ihres AEM Screens-Projekts, z. B. „Digitale Werbebeschilderung“

**Aktivität** definiert die Regelkategorie wie „bestandsgesteuert“, „wettergesteuert“, „gesteuert durch Abteilungsverfügbarkeit“ usw.

**Zielgruppe** definiert die Regel.

**Segment** bezieht sich auf die Version des Assets, die für die jeweilige Regel abgespielt werden soll, z. B. wenn die Temperatur unter 10 Grad Celsius liegt, zeigt der Bildschirm ein Bild eines heißen Kaffees an, andernfalls ein kaltes Getränk.

Das folgende Diagramm zeigt visuell, wie ContextHub-Konfigurationen mit Aktivität, Zielgruppe und Kanälen zusammenfallen.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Voraussetzungen {#preconditions}

Bevor Sie mit der Konfiguration von Context-Hub-Konfigurationen für ein AEM Screens-Projekt beginnen, müssen Sie Google Tabellen (für Demonstrationszwecke) einrichten.

>[!IMPORTANT]
>
>Google Tabellen wird im folgenden Beispiel als Beispieldatenbanksystem verwendet, von dem die Werte abgerufen werden und das ausschließlich zu Fortbildungszwecken dient. Adobe unterstützt die Verwendung von Google Tabellen in Produktionsumgebungen nicht.
>
>Weitere Informationen finden Sie in der Google-Dokumentation unter [Abrufen eines API-Schlüssels](https://developers.google.com/maps/documentation/javascript/get-api-key).

## Schritt 1: Einrichten eines Datenspeichers {#step-setting-up-a-data-store}

Sie können den Datenspeicher als lokales E/A-Ereignis oder als lokales Datenbankereignis einrichten.

Im folgenden Beispiel für Datenauslöser auf Asset-Ebene wird ein lokales Datenbankereignis gezeigt, das einen Datenspeicher wie beispielsweise ein Excel-Blatt einrichtet, das die Verwendung von ContextHub-Konfigurationen und Segmentpfaden zum AEM Screens-Kanal ermöglicht.

Unten sehen Sie ein Beispiel für ein korrekt eingerichtetes Google-Tabellenblatt:

![image](/help/user-guide/assets/context-hub/context-hub1.png)

Die folgende Validierung wird angezeigt, wenn Sie Ihre Verbindung prüfen, indem Sie die beiden Werte *Google-Tabellenblatt-ID* und *API-Schlüssel* im folgenden Format eingeben:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![image](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
>
>Im folgenden Beispiel werden Google-Tabellenblätter als Datenspeicher gezeigt, der eine Asset-Änderung auslöst, wenn der Wert größer als 100 oder kleiner als 50 ist.

## Schritt 2: Einrichten von Speicherkonfigurationen {#step-setting-store-configurations}

1. **Navigieren zu ContextHub**

   Navigieren Sie zu Ihrer AEM-Instanz und klicken Sie in der linken Seitenleiste auf das Symbol „Tools“. Klicken Sie auf **Sites** > **ContextHub**, wie in der Abbildung unten gezeigt.

   ![image](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Erstellen einer neuen ContextHub-Speicherkonfiguration**

   1. Navigieren Sie zum Konfigurations-Containers mit dem Namen **screens**.

   1. Klicken Sie auf **Erstellen** > **Konfigurations-Container erstellen** und geben Sie als Titel **ContextHubDemo** ein.

      ![image](/help/user-guide/assets/context-hub/context-hub4.png)

   1. **Navigieren** Sie zu **ContextHubDemo** > **Erstellen** **ContextHub-Konfiguration** und klicken Sie auf **Speichern**.

      >[!NOTE]
      > Nachdem Sie auf **Speichern** geklickt haben, befinden Sie sich auf dem Bildschirm **ContextHub-Konfiguration**.

   1. Klicken Sie im Bildschirm **ContextHub-Konfiguration** auf **Erstellen** > **ContentHub-Speicherkonfiguration**.

      ![image](/help/user-guide/assets/context-hub/context-hub5.png)

      >[!CAUTION]
      >
      >Als Teil von AEM 6.5 Feature Pack 4 oder AEM 6.4 Feature Pack 8 sollten Kunden `/conf/screens/settings/cloudsettings` in `sling:Folder` ändern.
      >
      >Führen Sie dazu folgende Schritte durch:
      >
      >1. Navigieren Sie zu CRXDE Lite und dann zu `/conf/screens/settings/cloudsettings`.
      >1. Überprüfen Sie, ob `cloudsettings jcr:primaryType` sich in `sling:Folder` befindet. Wenn die Variable `jcr:primaryType` sich nicht in `sling:folder` befindet, fahren Sie mit den nächsten Schritten fort.
      >1. Klicken Sie mit der rechten Maustaste auf `/conf/screens/settings`, erstellen Sie einen neuen Knoten, für den Sie unter *Name* den Wert **cloudsettings1** und unter *Typ* den Wert **sling:Folder** eingeben, und speichern Sie die Änderungen.
      >1. Verschieben Sie alle Knoten unter `/conf/screens/settings/cloudsettings` nach `cloudsettings1`.
      >1. Löschen Sie `cloudsettings` und speichern Sie.
      >1. Benennen Sie `cloudsettings1` in `cloudsettings` um und speichern Sie sie.
      >1. Beachten Sie, dass /conf/screens/settings/cloudsettings jetzt `jcr:primaryType` als `sling:Folder` hat.
      >
      >Führen Sie diese Schritte vor oder nach dem Upgrade im Autorenmodus und im Veröffentlichungsmodus aus.

   1. Geben Sie unter **Titel** den Wert **Google Tabellen**, unter **Speichername** den Wert **googlesheets** und unter **Speichertyp** den Wert **contexthub.generic-jsonp** ein und klicken Sie auf **Weiter**.

      >[!CAUTION]
      >Wenn Sie Adobe Experience Manager (AEM) 6.4 verwenden, geben Sie den **Konfigurationstitel** als **googlesheets** und den **Store-Typ** als **contexthub.generic-jsonp** ein.

      ![image](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Geben Sie Ihre spezifische json-Konfiguration ein. Sie können beispielsweise die folgende JSON-Datei für Demozwecke verwenden und auf **Speichern** klicken. Die Speicherkonfiguration wird dann in der ContextHub-Konfiguration als **Google Tabellen** angegeben.

      >[!IMPORTANT]
      >Stellen Sie sicher, dass Sie den Code durch Ihre *&lt;Tabellenblatt-ID>* und Ihren *&lt;API-Schlüssel>* ersetzen, den Sie beim Einrichten von Google Tabellen abgerufen haben.

      ```
       {
        "service": {
        "host": "sheets.googleapis.com",
        "port": 80,
        "path": "/v4/spreadsheets/<your google sheets id>/values/Sheet1",
        "jsonp": false,
        "secure": true,
        "params": {
        "key": "<your Google API key>"
       }
      },
      "pollInterval": 10000
      }
      ```

      >[!NOTE]
      >
      Im obigen Beispiel-Code definiert **pollInterval** die Häufigkeit, mit der die Werte aktualisiert werden (in ms).
      >
      Ersetzen Sie den Code durch Ihre *&lt;Tabellenblatt-ID>* und Ihren *&lt;API-Schlüssel>*, den Sie beim Einrichten von Google Tabellen abgerufen haben.

      >[!CAUTION]
      >
      Wenn Sie Google Tabellen-Speicherkonfigurationen außerhalb des globalen Ordners erstellen (z. B. in Ihrem eigenen Projektordner), funktioniert das Targeting nicht standardmäßig.

1. **Einrichten der Speichersegmentierung**

   1. Navigieren Sie zu **ContextHub-Speicherkonfiguration …** und erstellen Sie eine weitere Speicherkonfiguration im Screens-Konfigurations-Container und legen Sie den **Titel** als **segmentation-contexthub**, den **Speichernamen** als **Segmentierung** und den **Speichertyp** als **alsaem.segmentation** fest.

      ![image](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Klicken Sie auf **Weiter** und dann auf **Speichern**.

      >[!NOTE]
Sie müssen die Definition der JSON-Datei überspringen und diese leer lassen.


## Schritt 3: Einrichten von Segmenten in der Zielgruppe {#setting-up-audience}

1. **Erstellen von Segmenten in Zielgruppen**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** > **Zielgruppen** > **Screens**.

   1. Klicken Sie auf **Erstellen** > **ContextHub-Segment erstellen.** Das Dialogfeld **Neues ContextHub-Segment** wird geöffnet.

   1. Geben Sie unter **Titel** den Wert **Higherthan50** ein und klicken Sie auf **Erstellen**. Erstellen Sie auf ähnliche Weise ein weiteres Segment mit der Bezeichnung **Lowerthan50**.

      ![image](/help/user-guide/assets/context-hub/context-hub11.png)

   1. Wählen Sie das Segment **Higherthan50** aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.
      ![image](/help/user-guide/assets/context-hub/context-hub12.png)

   1. Wählen Sie die Registerkarte **Personalisierung** aus den **Segmenteigenschaften** aus. Stellen Sie den **ContextHub-Pfad** auf `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` und den **Segmentpfad** auf `/conf/screens/settings/wcm/segments` ein und klicken Sie auf **Speichern**, wie in der folgenden Abbildung dargestellt.

      ![image](/help/user-guide/assets/context-hub/context-hub13.png)

   1. Stellen Sie auf ähnliche Weise auch den **ContextHub-Pfad** und den **Segmentpfad** für das Segment **Lowerthan50** ein.

## Schritt 4: Einrichten von Marke und Bereich {#setting-brand-area}

Gehen Sie wie folgt vor, um eine Marke in Ihren Aktivitäten und einen Bereich unter der Marke zu erstellen:

1. **Erstellen einer Marke in „Aktivitäten“**

   1. Navigieren Sie von Ihrer AEM-Instanz aus zu **Personalisierung** > **Aktivitäten**.

   1. Klicken Sie auf **Erstellen** > **Marke erstellen**.

   1. Wählen Sie im Assistenten **Seite erstellen** die Option **Marke** aus und klicken Sie auf **Weiter**.

   1. Geben Sie unter **Titel** den Wert **ScreensBrand** ein und klicken Sie auf **Erstellen**. Ihre Marke wird jetzt wie unten dargestellt erstellt.

      ![image](/help/user-guide/assets/context-hub/context-hub8.png)


      >[!CAUTION]
      >
      Bekanntes Problem:
Um einen Bereich hinzuzufügen, entfernen Sie den Master aus der URL, z. B.
      `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Erstellen eines Bereichs in Ihrer Marke**

   Gehen Sie wie folgt vor, um einen Bereich in der Marke zu erstellen:

   1. Klicken Sie auf **Erstellen** und dann auf **Bereich erstellen**.

      ![image](/help/user-guide/assets/context-hub/context-hub9.png)

   1. Wählen Sie im Assistenten **Seite erstellen** die Option **Bereich** aus und klicken Sie auf **Weiter**.

   1. Geben Sie unter **Titel** den Wert **ScreensValue** ein und klicken Sie auf **Erstellen**.
Es wird ein Bereich in Ihrer Marke erstellt.

## Schritt 5: Erstellen der Segmente in einer Aktivität {#step-setting-up-audience-segmentation}

Nachdem Sie einen Datenspeicher eingerichtet und Ihre Aktivität (Marke und Bereich) definiert haben, führen Sie die folgenden Schritte aus, um Segmente in Ihrer Aktivität zu erstellen.

1. **Erstellen von Segmenten in Aktivitäten**

   1. Navigieren Sie von Ihrer AEM-Instanz aus zu **Personalisierung** > **Aktivitäten** > **ScreensBrand** > **ScreensValue**.

   1. Klicken Sie auf **Erstellen** > **Aktivität erstellen.** Der **Assistent zum Konfigurieren der Aktivität** wird geöffnet.

   1. Geben Sie den **Titel** als **ValueCheck50** und den **Namen** als **valuecheck50** ein. Wählen Sie die **Targeting-Engine** als **ContextHub (AEM)** aus der Dropdown-Liste aus und klicken Sie auf **Weiter**.

      ![image](/help/user-guide/assets/context-hub/context-hub14.png)

   1. Klicken Sie im **Assistent zum Konfigurieren der Aktivität** auf **Erlebnis hinzufügen**.

   1. Wählen Sie **Higherthan50** aus den **Zielgruppen** aus. Klicken Sie auf **Erlebnis hinzufügen** und geben Sie den **Titel** als **higherthan50** und den **Namen** als **higherthan50** ein. Klicken Sie auf **OK**.

   1. Wählen Sie **Lowerthan50** aus den **Zielgruppen** aus. Klicken Sie auf **Erlebnis hinzufügen** und geben Sie den **Titel** als **lowerthan50** und den **Namen** als **lowerthan50** ein. Klicken Sie auf **OK**.

      ![image](/help/user-guide/assets/context-hub/context-hub15.png)

   1. Klicken Sie auf **Weiter** und dann auf **Speichern**. Die Aktivität **ValueCheck50** wird jetzt erstellt und konfiguriert.

      ![image](/help/user-guide/assets/context-hub/context-hub16.png)

## Schritt 5: Bearbeiten der Segmente in Zielgruppen{#editing-audience-segmentation}

1. **Bearbeiten der Segmente**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** > **Zielgruppen** > **Screens**.

   1. Wählen Sie das Segment **Higherthan50** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   1. Ziehen Sie die Komponente **Vergleich: Eigenschaft - Wert** in den Editor.

   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich von Eigenschaft und Wert** zu öffnen.

   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus.

      >[!NOTE]
**googlesheets/Wert/1/0** bezieht sich auf die Zeile 2 und die Spalte, wie in den Google-Tabellenblättern in der folgenden Abbildung angegeben:

      ![image](/help/user-guide/assets/context-hub/context-hub17.png)

   1. Wählen Sie unter **Operator** den Wert **größer als** aus dem Dropdown-Menü aus.

   1. Geben Sie den **Wert** als **70** ein.

      >[!NOTE]
      >
      AEM validiert Ihre Daten aus dem Google-Tabellenblatt, indem Ihr Segment grün anzeigt wird.

      ![image](/help/user-guide/assets/context-hub/context-hub18.png)

   Geben Sie die Eigenschaftswerte als **Lowerthan50** an.

   1. Ziehen Sie die Komponente **Vergleich: Eigenschaft - Wert** in den Editor.

   1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Vergleich von Eigenschaft und Wert** zu öffnen.

   1. Wählen Sie **googlesheets/value/1/0** aus der Dropdown-Liste in **Eigenschaftsname** aus.

   1. Wählen Sie unter **Operator** den Wert **kleiner als** aus dem Dropdown-Menü aus.

   1. Geben Sie den **Wert** als **50** ein.


## Aktivieren von Targeting in Kanälen {#step-enabling-targeting-in-channels}

Gehen Sie wie folgt vor, um Targeting in Ihren Kanälen zu aktivieren.

1. Navigieren Sie zu einem der AEM Screens-Kanäle. Die folgenden Schritte zeigen, wie Sie das Targeting mit **DataDrivenChannel** aktivieren, das in einem AEM Screens-Kanal erstellt wurde.

1. Wählen Sie den Kanal **TargetChannel** aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   ![image](/help/user-guide/assets/context-hub/context-hub19.png)

1. Wählen Sie die Registerkarte **Personalisierung**, um die ContextHub-Konfigurationen einzurichten.

   1. Stellen Sie den **ContextHub-Pfad** auf `/conf/screens/settings/wcm/segments` und den **Segmentpfad** auf `/conf/screens/settings/wcm/segments` ein.
   1. Setzen Sie die Marke im Dropdown-Menü auf **ScreensBrand** und setzen Sie **Gebietsverweis festlegen** auf **ScreensValue**.

   1. Klicken Sie auf **Speichern und schließen**.

      >[!NOTE]
      >
      Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie Ihre Kontexthub-Konfigurationen und -Segmente anfänglich gespeichert haben.

      ![image](/help/user-guide/assets/context-hub/context-hub20New.png)

   1. Navigieren Sie zu und wählen Sie **TargetChannel** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

      >[!NOTE]
      >
      Wenn Sie alles korrekt eingerichtet haben, sehen Sie die Option **Targeting** in der Dropdown-Liste des Editors, wie in der Abbildung unten gezeigt.

      ![image](/help/user-guide/assets/context-hub/context-hub21.png)

## Weitere Informationen: Anwendungsbeispiele {#learn-more-example-use-cases}

Nachdem Sie ContextHub für Ihr AEM Screens-Projekt konfiguriert haben, können Sie die verschiedenen Nutzungsszenarios durchgehen, um zu verstehen, wie datengesteuerte Assets in verschiedenen Branchen eine wichtige Rolle spielen:

1. **[Zielgerichtete Aktivierung des Einzelhandelsinventars](retail-inventory-activation.md)**
1. **[Temperaturaktivierung für ein Reiseangebot](local-temperature-activation.md)**
1. **[Aktivierung der Gastgewerbereservierung](hospitality-reservation-activation.md)**
