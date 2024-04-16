---
title: Konfigurieren von ContextHub in AEM Screens
description: Erfahren Sie mehr über ContextHub in der Targeting-Engine, damit Sie einen Datenspeicher für die Inhaltsänderung von Daten-Triggern definieren können.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 04072107-d6be-4030-bb79-1f1a7609f37e
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 40%

---

# Konfigurieren von ContextHub in AEM Screens {#configuring-contexthub-in-aem-screens}

Dieser Abschnitt konzentriert sich auf die Erstellung und Verwaltung datengesteuerter Asset-Änderungen mithilfe eines Datenspeichers.

## Schlüsselbegriffe {#key-terms}

Bevor Sie sich mit der Erstellung und Verwaltung von bestandsgesteuerten Kanälen in Ihrem AEM Screens-Projekt befassen, sollten Sie sich mit einigen Schlüsselbegriffen für die verschiedenen Szenarien vertraut machen.

**Marke** - Ihre allgemeine Projektbeschreibung.

**Bereich** - Ihr AEM Screens-Projektname, z. B. Digital Ad Signage

**Aktivität** - Definiert die Kategorieregeln wie &quot;bestandsgesteuert&quot;, &quot;wettergesteuert&quot;oder &quot;Abteilungsverfügbarkeit gesteuert&quot;.

**Zielgruppe** - Definiert die Regel.

**Segment** - Die Version des Assets, das für die jeweilige Regel wiedergegeben werden soll. Wenn die Temperatur beispielsweise unter 50 Grad Fahrenheit liegt, zeigt der Bildschirm ein Bild eines heißen Getränks an, ansonsten ein kaltes Getränk.

Das folgende Diagramm zeigt visuell, wie ContextHub-Konfigurationen mit Aktivität, Zielgruppe und Kanälen zusammenfallen.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Voraussetzungen {#preconditions}

Bevor Sie mit der Konfiguration von ContextHub-Konfigurationen für ein AEM Screens-Projekt beginnen, richten Sie Google Tabellen ein (zu Demonstrationszwecken).

>[!IMPORTANT]
>
>Google Tabellen wird im folgenden Beispiel als Beispieldatenbanksystem verwendet, von dem die Werte abgerufen werden und das ausschließlich zu Fortbildungszwecken dient. Adobe unterstützt die Verwendung von Google Tabellen in Produktionsumgebungen nicht.
>
>Weitere Informationen finden Sie unter [API-Schlüssel abrufen](https://developers.google.com/maps/documentation/javascript/get-api-key) in der Google-Dokumentation.

## Schritt 1: Einrichten eines Datenspeichers {#step-setting-up-a-data-store}

Sie können den Datenspeicher als lokales E/A-Ereignis oder als lokales Datenbankereignis einrichten.

Im folgenden Trigger zu Datenprofilen auf Asset-Ebene wird ein lokales Datenbankereignis veranschaulicht, das einen Datenspeicher wie ein Excel-Blatt einrichtet, mit dem Sie ContextHub-Konfigurationen und Segmentpfade zum AEM Screens- verwenden können.

Nachdem Sie die `google` korrekt angezeigt werden, wie im folgenden Beispiel gezeigt:

![Bild](/help/user-guide/assets/context-hub/context-hub1.png)

Die folgende Validierung wird angezeigt, wenn Sie die Verbindung durch Eingabe der beiden Werte überprüfen. `*google sheet ID*` und `*API key*` im folgenden Format:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![Bild](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
>
>Im folgenden Beispiel werden die Google Tabellen als Datenspeicher dargestellt, in dem eine Asset-Änderung Trigger wird, wenn der Wert größer als 100 oder kleiner als 50 ist.

## Schritt 2: Einrichten von Speicherkonfigurationen {#step-setting-store-configurations}

1. **Navigieren zu ContextHub**

   Navigieren Sie zu Ihrer AEM-Instanz und klicken Sie in der linken Seitenleiste auf das Symbol „Tools“. Klicks **Sites** > **ContextHub**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Erstellen einer ContextHub-Speicherkonfiguration**

   1. Navigieren Sie zum Konfigurations-Containers mit dem Namen **screens**.

   1. Klicken Sie auf **Erstellen** > **Konfigurations-Container erstellen** und geben Sie als Titel **ContextHubDemo** ein.

      ![image](/help/user-guide/assets/context-hub/context-hub4.png)

   1. **Navigieren** Sie zu **ContextHubDemo** > **Erstellen** **ContextHub-Konfiguration** und klicken Sie auf **Speichern**.

      >[!NOTE]
      > Nachdem Sie auf **Speichern**, befinden Sie sich im **ContextHub-Konfiguration** angezeigt.

   1. Aus dem **ContextHub-Konfiguration** Bildschirm, klicken Sie **Erstellen** > **ContentHub-Speicherkonfiguration**

   ![Bild](/help/user-guide/assets/context-hub/context-hub5.png)

   >[!CAUTION]
   >
   >Als Teil von AEM 6.5 Feature Pack 4 oder AEM 6.4 Feature Pack 8 sollten Kunden `/conf/screens/settings/cloudsettings` in `sling:Folder` ändern.
   >
   >Führen Sie dazu folgende Schritte durch:
   >
   >1. Navigieren Sie zu CRXDE Lite und dann zu `/conf/screens/settings/cloudsettings`.
   >1. Überprüfen Sie, ob `cloudsettings jcr:primaryType` sich in `sling:Folder` befindet. Wenn die Variable `jcr:primaryType` sich nicht in `sling:folder` befindet, fahren Sie mit den nächsten Schritten fort.
   >1. Rechtsklick `/conf/screens/settings` und erstellen Sie einen Knoten mit *name* as **`cloudsettings1`** und *Typ* as **`sling:Folder`** und speichern Sie die Änderungen.
   >1. Verschieben Sie alle Knoten unter `/conf/screens/settings/cloudsettings` nach `cloudsettings1`.
   >1. Löschen Sie `cloudsettings` und speichern Sie.
   >1. Benennen Sie `cloudsettings1` in `cloudsettings` um und speichern Sie sie.
   >1. Beachten Sie, dass `/conf/screens/settings/cloudsettings` has `jcr:primaryType` as `sling:Folder`.
   >
   >Führen Sie die folgenden Schritte in Author and Publish vor oder nach dem Upgrade aus.

   1. Geben Sie die **Titel** as **Google Tabellen**, **Speichername** as **`googlesheets`**, und **Store Type** as **c`ontexthub.generic-jsonp`** und klicken **Nächste**.

      >[!CAUTION]
      >Wenn Sie Adobe Experience Manager (AEM) 6.4 verwenden, geben Sie die **Konfigurationstitel** as **`googlesheets`** und **Store Type** as **c`ontexthub.generic-jsonp`**.

      ![image](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Geben Sie Ihre spezifische json-Konfiguration ein. Sie können beispielsweise die folgende JSON-Datei für Demozwecke verwenden und auf **Speichern**. Sie sehen die Store-Konfiguration mit dem Titel **Google Tabellen** in der ContextHub-Konfiguration.

      >[!IMPORTANT]
      >Stellen Sie sicher, dass Sie den Code durch Ihre `*<Sheet ID>*` und `*<API Key>*`, die Sie beim Einrichten der Google Tabellen abgerufen haben.

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
      >Im obigen Beispielcode: **pollInterval** definiert die Häufigkeit, mit der die Werte aktualisiert werden (in Millisekunden).
      >
      >Ersetzen Sie den Code durch Ihre `*<Sheet ID>*` und `*<API Key>*`, die Sie beim Einrichten der Google Tabellen abgerufen haben.

      >[!CAUTION]
      >
      >Wenn Sie Ihre Google Tabellen-Speicherkonfigurationen außerhalb des globalen Ordners erstellen (z. B. in Ihrem eigenen Projektordner), funktioniert das Targeting nicht standardmäßig.

1. **Einrichten der Speichersegmentierung**

   1. Navigieren Sie zu **ContentHub-Speicherkonfiguration** und erstellen Sie eine weitere Speicherkonfiguration im AEM Screens-Konfigurationscontainer und legen Sie die **Titel** as **segmentation-contexthub**, **Speichername** as **Segmentierung** und **Store Type** as **aem.segmentation**.

      ![image](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Klicken Sie auf **Weiter** und dann auf **Speichern**.

      >[!NOTE]
      >Überspringen Sie die Definition der JSON-Datei und lassen Sie sie leer.


## Schritt 3: Einrichten von Segmenten in der Zielgruppe {#setting-up-audience}

1. **Erstellen von Segmenten in Zielgruppen**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** > **Zielgruppen** > **Screens**.

   1. Klicken Sie auf **Erstellen** > **ContextHub-Segment erstellen.** Das Dialogfeld **Neues ContextHub-Segment** wird geöffnet.

   1. Geben Sie die **Titel** as `**Higherthan50**` und klicken **Erstellen**. Erstellen Sie auf ähnliche Weise ein weiteres Segment mit dem Titel `**Lowerthan50**`.

      ![Bild](/help/user-guide/assets/context-hub/context-hub11.png)

   1. Klicken Sie auf das Segment `**Higherthan50**` und klicken **Eigenschaften** in der Aktionsleiste aus.
      ![Bild](/help/user-guide/assets/context-hub/context-hub12.png)

   1. Klicken Sie auf **Personalisierung** Registerkarte aus **Segmenteigenschaften**. Stellen Sie den **ContextHub-Pfad** auf `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` und den **Segmentpfad** auf `/conf/screens/settings/wcm/segments` ein und klicken Sie auf **Speichern**, wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/context-hub/context-hub13.png)

   1. Setzen Sie auf ähnliche Weise die **ContextHub-Pfad** und **Segmentpfad** für `**Lowerthan50**` -Segment.

## Schritt 4: Einrichten von Marke und Bereich {#setting-brand-area}

Gehen Sie wie folgt vor, um eine Marke in Ihren Aktivitäten und Bereichen unter der Marke zu erstellen:

1. **Erstellen einer Marke in „Aktivitäten“**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** > **Tätigkeiten**.

   1. Klicken Sie auf **Erstellen** > **Marke erstellen**.

   1. Klicks **Marke** aus dem **Seite erstellen** Assistent und klicken Sie auf **Nächste**.

   1. Geben Sie unter **Titel** den Wert **ScreensBrand** ein und klicken Sie auf **Erstellen**. Ihre Marke wird jetzt wie unten dargestellt erstellt.

      ![image](/help/user-guide/assets/context-hub/context-hub8.png)


      >[!CAUTION]
      >
      >Bekanntes Problem:
      >Um einen Bereich hinzuzufügen, entfernen Sie die primäre URL aus der URL, z. B.
      >`http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Erstellen eines Bereichs in Ihrer Marke**

   Gehen Sie wie folgt vor, um einen Bereich in der Marke zu erstellen:

   1. Klicks **Erstellen** und dann **Bereich erstellen**.

      ![Bild](/help/user-guide/assets/context-hub/context-hub9.png)

   1. Klicks **Bereich** aus dem **Seite erstellen** Assistent und klicken Sie auf **Nächste**.

   1. Geben Sie unter **Titel** den Wert **ScreensValue** ein und klicken Sie auf **Erstellen**.
Ein Gebiet wird in Ihrer Marke erstellt.

## Schritt 5: Erstellen der Segmente in einer Aktivität {#step-setting-up-audience-segmentation}

Nachdem Sie einen Datenspeicher eingerichtet und Ihre Aktivität (Marke und Bereich) definiert haben, führen Sie die folgenden Schritte aus, um Segmente in Ihrer Aktivität zu erstellen.

1. **Erstellen von Segmenten in Aktivitäten**

   1. Navigieren Sie von Ihrer AEM-Instanz aus zu **Personalisierung** > **Aktivitäten** > **ScreensBrand** > **ScreensValue**.

   1. Klicken Sie auf **Erstellen** > **Aktivität erstellen.** Der **Assistent zum Konfigurieren der Aktivität** wird geöffnet.

   1. Geben Sie den **Titel** als **ValueCheck50** und den **Namen** als **valuecheck50** ein. Klicken Sie auf **Targeting-Engine** as **ContextHub (AEM)** aus der Dropdown-Liste aus und klicken Sie auf **Nächste**.

      ![Bild](/help/user-guide/assets/context-hub/context-hub14.png)

   1. Klicks **Erlebnis hinzufügen** aus dem `**Configure Activity**` Assistent.

   1. Aus dem **Zielgruppen**, klicken Sie auf die `**Higherthan50**` und klicken **Erlebnis hinzufügen** und geben Sie die **Titel** as `**higherthan50**` **Name** as `**higherthan50**`. Klicken Sie auf **OK**.

   1. Aus dem **Zielgruppen**, klicken Sie auf die `**Lowerthan50**` und klicken **Erlebnis hinzufügen** und geben Sie die **Titel** as `**lowerthan50**` **Name** as `**lowerthan50**`. Klicken Sie auf **OK**.

   ![image](/help/user-guide/assets/context-hub/context-hub15.png)

   1. Klicken Sie auf **Weiter** und dann auf **Speichern**. `**ValueCheck50**` -Aktivität erstellt und konfiguriert wurde.

      ![Bild](/help/user-guide/assets/context-hub/context-hub16.png)

## Schritt 5: Bearbeiten der Segmente in Zielgruppen{#editing-audience-segmentation}

1. **Bearbeiten der Segmente**

   1. Navigieren Sie von Ihrer AEM-Instanz zu **Personalisierung** > **Zielgruppen** > **Screens**.

   1. Klicken Sie auf das Segment `**Higherthan50**`und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus.

   1. Ziehen Sie die Komponente **Vergleich: Eigenschaft - Wert** in den Editor.

   1. Klicken Sie auf das Schraubenschlüsselsymbol, damit Sie die **Vergleich einer Eigenschaft mit einem Wert** Dialogfeld.

   1. Klicks **googlesheets/value/1/0** aus der Dropdown-Liste **Eigenschaftsname**.

      >[!NOTE]
      > Die **googlesheets/value/1/0** bezieht sich auf Zeile 2 und Spalte wie in `google` Blätter in der folgenden Abbildung:

      ![Bild](/help/user-guide/assets/context-hub/context-hub17.png)

   1. Klicken Sie auf **Operator** as **größer als** aus dem Dropdown-Menü.

   1. Geben Sie den **Wert** als **70** ein.

      >[!NOTE]
      >
      >AEM validiert Ihre Daten aus dem Google-Tabellenblatt, indem Ihr Segment grün anzeigt wird.

      ![image](/help/user-guide/assets/context-hub/context-hub18.png)

   Bearbeiten Sie auf ähnliche Weise die Eigenschaftswerte in `**Lowerthan50**`.

   1. Ziehen Sie die Komponente **Vergleich: Eigenschaft - Wert** in den Editor.

   1. Klicken Sie auf das Schraubenschlüsselsymbol.

   1. Im **Vergleich einer Eigenschaft mit einem Wert** Dialogfeld, klicken Sie auf **googlesheets/value/1/0** aus der Dropdown-Liste **Eigenschaftsname**.

   1. Klicken Sie auf **Operator** as **kleiner als** aus dem Dropdown-Menü.

   1. Geben Sie den **Wert** als **50** ein.


## Aktivieren von Targeting in Kanälen {#step-enabling-targeting-in-channels}

Gehen Sie wie folgt vor, um Targeting in Ihren Kanälen zu aktivieren.

1. Navigieren Sie zu einem der AEM Screens-Kanäle. Die folgenden Schritte zeigen, wie Sie das Targeting mit **DataDrivenChannel** aktivieren, das in einem AEM Screens-Kanal erstellt wurde.

1. Klicken Sie auf den Kanal **TargetChannel** und klicken **Eigenschaften** in der Aktionsleiste aus.

   ![Bild](/help/user-guide/assets/context-hub/context-hub19.png)

1. Klicken Sie auf **Personalisierung** -Registerkarte, damit Sie die ContextHub-Konfigurationen einrichten können.

   1. Stellen Sie den **ContextHub-Pfad** auf `/conf/screens/settings/wcm/segments` und den **Segmentpfad** auf `/conf/screens/settings/wcm/segments` ein.
   1. Setzen Sie die Marke im Dropdown-Menü auf **ScreensBrand** und setzen Sie **Gebietsverweis festlegen** auf **ScreensValue**.

   1. Klicken Sie auf **Speichern und schließen**.

      >[!NOTE]
      >
      >Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie Ihre Kontexthub-Konfigurationen und -Segmente anfänglich gespeichert haben.

      ![image](/help/user-guide/assets/context-hub/context-hub20New.png)

   1. Navigieren Sie zu und klicken Sie auf die **TargetChannel** channel und click **Bearbeiten** in der Aktionsleiste aus.

      >[!NOTE]
      >
      >Wenn Sie alles korrekt eingerichtet haben, sehen Sie **Targeting** in der Dropdown-Liste des Editors, wie in der folgenden Abbildung dargestellt.

      ![Bild](/help/user-guide/assets/context-hub/context-hub21.png)

## Weitere Informationen: Anwendungsbeispiele {#learn-more-example-use-cases}

Nachdem Sie ContextHub für Ihr AEM Screens-Projekt konfiguriert haben, können Sie die verschiedenen Nutzungsszenarios durchgehen, um zu verstehen, wie datengesteuerte Assets in verschiedenen Branchen eine wichtige Rolle spielen:

1. **[Zielgerichtete Aktivierung des Einzelhandelsinventars](retail-inventory-activation.md)**
1. **[Temperaturaktivierung für ein Reiseangebot](local-temperature-activation.md)**
1. **[Aktivierung der Gastgewerbereservierung](hospitality-reservation-activation.md)**
