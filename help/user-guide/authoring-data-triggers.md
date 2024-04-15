---
title: Inhaltserstellung mit Datenauslösern
description: Erfahren Sie mehr darüber, wie Sie mit Daten-Triggern in einem AEM Screens-Kanal erstellen können.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: c95da2e9-a216-4d0a-85d0-a0fb895a8d8a
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 52%

---

# Inhaltserstellung mit Datenauslösern {#authoring-with-data-triggers}

In diesem Abschnitt wird erläutert, wie Sie Targeting in Ihren Kanälen aktivieren.

>[!IMPORTANT]
>
>Die Mindestversion, die Datenauslöser in einem AEM Screens-Kanal unterstützt, ist AEM 6.5.3 Feature Pack 3.

## Voraussetzungen {#prereqs}

Bevor Sie die folgenden Schritte ausführen, um Targeting in Kanälen zu aktivieren, sollten Sie die [Schlüsselbegriffe beim Konfigurieren in AEM Screens](configuring-context-hub.md) erforderlich, um ContextHub und Targeting in AEM Screens zu verstehen.

>[!IMPORTANT]
>
>Sie sollten ContextHub-Konfigurationen verstehen und einzurichten können, bevor Sie das Targeting in einem AEM Screens-Kanal aktivieren.

Weitere Informationen finden Sie unter den folgenden Links:

1. **[Einrichten eines Datenspeichers](configuring-context-hub.md)**
1. **[Einrichten der Zielgruppensegmentierung](configuring-context-hub.md)**

Wenn Sie die vorherigen Schritte ausgeführt haben, können Sie das Targeting in Ihren Kanälen aktivieren.

## Überblick über die Inhaltserstellung mit Datenauslösern {#author-targeting}

>[!VIDEO](https://video.tv.adobe.com/v/31921)

## Aktivieren von Targeting in einem AEM Screens-Kanal {#enabling-targeting}

Gehen Sie wie folgt vor, um Targeting in Ihren Kanälen zu aktivieren.

1. Navigieren Sie zu einem der AEM Screens-Kanäle. Die folgenden Schritte zeigen, wie Sie das Targeting mit **DataDrivenRetail** *(Sequenzkanal)* aktivieren, das in einem AEM Screens-Kanal erstellt wurde.

1. Kanal auswählen **DataDrivenRetail** und wählen **Eigenschaften** in der Aktionsleiste aus.

   ![screen_shot_2019-05-01at43332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Wählen Sie die **Personalisierung** -Registerkarte, damit Sie die ContextHub-Konfigurationen einrichten und den Pfad ContextHub und Segmente auswählen können.

   1. Wählen Sie die **ContextHub-Pfad** as **libs** > **settings** > **cloudsettings** > **default** > **ContextHub-Konfigurationen** und wählen **Auswählen**.

   1. Wählen Sie die **Segmentpfad** as **conf** > **`We.Retail`** > **settings** > **wcm** > **Segmente** und wählen **Auswählen**.

   1. Klicken Sie auf **Speichern und schließen**.

   >[!NOTE]
   >
   >Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie Ihre Kontexthub-Konfigurationen und -Segmente anfänglich gespeichert haben.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigieren Sie zu und wählen Sie die **DataDrivenRetail** von **DataDrivenAssets** > **Kanäle** und wählen **Bearbeiten** in der Aktionsleiste aus. Ziehen Sie die Assets in Ihren Kanal-Editor.

   >[!NOTE]
   >
   >Wenn Sie alles korrekt eingerichtet haben, sehen Sie **Targeting** in der Dropdown-Liste des Editors, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

1. Auswählen **Targeting**.

1. Auswählen **Marke** und **Aktivität** aus dem Dropdown-Menü und wählen Sie **Targeting starten**.

### Weitere Informationen: Anwendungsbeispiele {#learn-more-example-use-cases}

Nachdem Sie ContextHub für Ihr AEM Screens-Projekt konfiguriert haben, können Sie die verschiedenen Nutzungsszenarios durchgehen, um zu verstehen, wie datengesteuerte Assets in verschiedenen Branchen eine wichtige Rolle spielen:

1. **[Zielgerichtete Aktivierung des Einzelhandelsinventars](retail-inventory-activation.md)**
1. **[Temperaturaktivierung für ein Reiseangebot](local-temperature-activation.md)**
1. **[Aktivierung der Gastgewerbereservierung](hospitality-reservation-activation.md)**
