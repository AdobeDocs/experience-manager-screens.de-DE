---
title: Inhaltserstellung mit Datenauslösern
seo-title: Inhaltserstellung mit Datenauslösern
description: Auf dieser Seite erfahren Sie, wie Sie mit Datenauslösern Inhalte erstellen.
translation-type: ht
source-git-commit: a7d3ec582dde83ed6efb08a6c3c6a75cc0820970

---


# Inhaltserstellung mit Datenauslösern {#authoring-with-data-triggers}

In diesem Abschnitt wird erläutert, wie Sie Targeting in Ihren Kanälen aktivieren.

>[!IMPORTANT]
> Die Mindestversion, die Datenauslöser in einem AEM Screens-Kanal unterstützt, ist AEM 6.5.3 Feature Pack 3.

## Voraussetzungen {#prereqs}

Bevor Sie die folgenden Schritte ausführen, um Targeting in Kanälen zu aktivieren, müssen Sie die [Schlüsselbegriffe für das Konfigurieren in AEM Screens](configuring-context-hub.md) kennen, die zum Verständnis von ContextHub und Targeting in AEM Screens erforderlich sind.

>[!IMPORTANT]
> Sie sollten ContextHub-Konfigurationen verstehen und einzurichten können, bevor Sie das Targeting in einem AEM Screens-Kanal aktivieren.

Weitere Informationen finden Sie unter den folgenden Links:

1. **[Einrichten eines Datenspeichers](configuring-context-hub.md)**
1. **[Einrichten der Zielgruppensegmentierung](configuring-context-hub.md)**

Nachdem Sie die vorherigen Schritte durchgeführt haben, können Sie Targeting in Ihren Kanälen aktivieren.

## Überblick über die Inhaltserstellung mit Datenauslösern {#author-targeting}

>[!VIDEO](https://video.tv.adobe.com/v/31921?captions=ger)

## Aktivieren von Targeting in einem AEM Screens-Kanal {#enabling-targeting}

Gehen Sie wie folgt vor, um Targeting in Ihren Kanälen zu aktivieren.

1. Navigieren Sie zu einem der AEM Screens-Kanäle. Die folgenden Schritte zeigen, wie Sie das Targeting mit **DataDrivenRetail** *(Sequenzkanal)* aktivieren, das in einem AEM Screens-Kanal erstellt wurde.

1. Wählen Sie den Kanal **DataDrivenRetail** aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   ![screen_shot_2019-05-01at43332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Wählen Sie die Registerkarte **Personalisierung**, um die ContextHub-Konfigurationen einzurichten.

   1. Wählen Sie unter **ContextHub-Pfad** den Wert **libs** > **settings** > **cloudsettings** > **default** > **ContextHub Konfigurationen** aus und klicken Sie auf **Auswählen**.

   1. Wählen Sie unter **Segmentpfad** den Wert **conf** > **We.Retail** > **settings** > **wcm** > **segments** aus und klicken Sie auf **Auswählen**.

   1. Klicken Sie auf **Speichern und schließen**.
   >[!NOTE]
   >
   >Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie Ihre Kontexthub-Konfigurationen und -Segmente anfänglich gespeichert haben.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigieren Sie zu und wählen Sie **DataDrivenRetail** aus **DataDrivenAssets** > **Kanäle** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Ziehen Sie die Assets in Ihren Kanal-Editor.

   >[!NOTE]
   >
   >Wenn Sie alles korrekt eingerichtet haben, sehen Sie die Option **Targeting** in der Dropdown-Liste des Editors, wie in der Abbildung unten gezeigt.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

1. Klicken Sie auf **Targeting**.

1. Wählen Sie **Marke** und **Aktivität** aus dem Dropdown-Menü und klicken Sie auf **Targeting starten**.

### Weitere Informationen: Anwendungsbeispiele {#learn-more-example-use-cases}

Nachdem Sie ContextHub für Ihr AEM Screens-Projekt konfiguriert haben, können Sie die verschiedenen Nutzungsszenarios durchgehen, um zu verstehen, wie datengesteuerte Assets in verschiedenen Branchen eine wichtige Rolle spielen:

1. **[Zielgerichtete Aktivierung des Einzelhandelsinventars](retail-inventory-activation.md)**
1. **[Temperaturaktivierung für ein Reiseangebot](local-temperature-activation.md)**
1. **[Aktivierung der Gastgewerbereservierung](hospitality-reservation-activation.md)**

