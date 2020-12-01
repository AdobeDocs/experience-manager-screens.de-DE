---
title: Inhaltszuweisungsbericht
description: Diese Seite beschreibt das Herunterladen und Verwenden des Inhaltszuweisungsberichts.
translation-type: tm+mt
source-git-commit: b93baeeb26e48b906ee1ddfc034112f8b73615af
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 3%

---


# Inhaltszuweisungsbericht {#content-assignment-report}

Die Funktion &quot;Bericht zur Inhaltszuweisung&quot;ermöglicht es einem AEM Screens-Administrator oder einem Autor, einen *Inhaltszuweisungsbericht* in ein Tabellenformat zu exportieren.

## Verwenden des Inhaltszuweisungsberichts {#using-content-assignment-report}

Der Bericht &quot;Inhaltszuweisung&quot;ermöglicht es einem AEM Screens-Autor oder einem Administrator, den Bericht herunterzuladen, der alle Assets wie Bilder oder Videos in allen Kanälen enthält, die in einem AEM Screens-Projekt erstellt wurden. Darüber hinaus enthält es die Informationen zu allen Kanälen, die allen angegebenen Anzeigen zugewiesen sind, und ab sofort alle Geräte, die ihren jeweiligen Displays zugeordnet sind.

Der Bericht &quot;Inhaltszuweisung&quot;ermöglicht nicht nur eine Vorschau aller Kanal, Assets, Anzeigen und Geräte im ausgewählten AEM Screens-Projekt, sondern stellt auch eine hohe Projektstruktur bereit.

### Verwenden des Berichts &quot;Inhaltszuweisung&quot; {#downloading-content-assignment-report-fp}

#### Einrichten des Projekts {#setting-up-project}

Gehen Sie wie folgt vor, um den Bericht &quot;Inhaltszuweisung&quot;aus einem AEM Screens-Projekt herunterzuladen:

1. Create an AEM Screens titled as **DemoScreens**.

   ![image](/help/user-guide/assets/content-assignment-report/car-1.png)

1. Erstellen Sie zwei Sequenz-Kanal in **DemoScreens** , z. B. **ChannelOne** und **ChannelTwo**.

   ![image](/help/user-guide/assets/content-assignment-report/car-2.png)

1. Select **ChannelOne** and click **Edit** from the action bar. hinzufügen einige Assets (Bilder/Videos) zu diesem Kanal. Fügen Sie auf ähnliche Weise Assets zu **ChannelTwo** hinzu.

1. Navigieren Sie zum Ordner Speicherorte von **DemoScreens** —> **Speicherorte** und erstellen Sie drei verschiedene Speicherorte mit dem Titel **SanJose**, **Dublin** und **SanFrancisco**.

   ![image](/help/user-guide/assets/content-assignment-report/car-3.png)

1. Navigieren Sie zu den einzelnen Orten und erstellen Sie eine Anzeige für jeden Ort, z. B. **SanJoseMain** unter **SanJose** -Standort, **DublinMain** unter **Dublin** -Standort und **SanFranciscoMain** **** unterSanFrancisco-Standort.

1. Weisen Sie jedem Display ein Gerät zu.

   >[!NOTE]
   >To learn about assigning a channel to a display, refer to [Channel Assignment](/help/user-guide/channel-assignment.md).

#### Herunterladen des Berichts &quot;Inhaltszuweisung&quot; {#downloading-content-assignment-report}

Nachdem Sie Ihr AEM Screens-Projekt eingerichtet haben und den einzelnen Orten, wie in den vorherigen Schritten gezeigt, Anzeigen zugewiesen haben, können Sie den Bericht &quot;Inhaltszuweisung&quot;herunterladen.

>[!NOTE]
>Die Funktion &quot;Inhaltszuweisungsbericht&quot;kann nur auf Projektebene aufgerufen werden.

Befolgen Sie die unten stehenden Anweisungen, um den Bericht &quot;Inhaltszuweisung&quot;herunterzuladen:

1. Navigate to your AEM Screens project and select the project **DemoScreens**.

1. Klicken Sie in der Aktionsleiste auf **Inhaltszuweisungsbericht** . Ein Excel-Blatt sollte auf Ihren lokalen Computer heruntergeladen werden.

   ![image](/help/user-guide/assets/content-assignment-report/can-download.png)

   >[!NOTE]
   >Die heruntergeladene Tabelle besteht aus vier Spalten wie **Kanal**, **Assets**, **Displays** und **Devices** , die zur weiteren Untersuchung dieser vier Entitäten für Ihr AEM Screens-Projekt verwendet werden können.





