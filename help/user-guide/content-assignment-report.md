---
title: Inhaltszuweisungsbericht
description: Diese Seite beschreibt das Herunterladen und Verwenden des Inhaltszuweisungsberichts.
translation-type: tm+mt
source-git-commit: b9091708221f92b11e859f0da8a7080b31b0af77
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---


# Inhaltszuweisungsbericht {#content-assignment-report}

Die Funktion &quot;Bericht zur Inhaltszuweisung&quot;ermöglicht es einem AEM Screens-Administrator oder einem Autor, einen *Inhaltszuweisungsbericht* im Tabellenformat zu exportieren.

## Verwenden des Inhaltszuweisungsberichts {#using-content-assignment-report}

Der Bericht &quot;Inhaltszuweisung&quot;ermöglicht es einem AEM Screens-Autor oder einem Administrator, den Bericht herunterzuladen, der alle Assets wie Bilder oder Videos in allen Kanälen enthält, die in einem AEM Screens-Projekt erstellt wurden. Darüber hinaus enthält es die Informationen zu allen Kanälen, die allen angegebenen Anzeigen zugewiesen sind, und ab sofort alle Geräte, die ihren jeweiligen Displays zugeordnet sind.

### Verwenden der Berichtsfunktion &quot;Inhaltszuweisung&quot;{#downloading-content-assignment-report-fp}

#### Einrichten des Projekts {#setting-up-project}

Gehen Sie wie folgt vor, um den Bericht &quot;Inhaltszuweisung&quot;aus einem AEM Screens-Projekt herunterzuladen:

1. Create an AEM Screens titled as **DemoScreens**.

1. Erstellen Sie zwei Sequenz-Kanal in **DemoScreens** , z. B. **ChannelOne** und **ChannelTwo**.

1. Select **ChannelOne** and click **Edit** from the action bar. hinzufügen einige Assets (Bilder/Videos) zu diesem Kanal. Fügen Sie auf ähnliche Weise Assets zu **ChannelTwo** hinzu.

1. Navigieren Sie zum Ordner Speicherorte von **DemoScreens** —> **Speicherorte** und erstellen Sie drei verschiedene Speicherorte mit dem Titel **SanJose**, **Dublin** und **SanFrancisco**.

1. Navigieren Sie zu den einzelnen Orten und erstellen Sie eine Anzeige für jeden Ort, z. B. **SanJoseMain** unter **SanJose** -Standort, **DublinMain** unter **Dublin** -Standort und **SanFranciscoMain** **** unterSanFrancisco-Standort.

1. Weisen Sie jedem Display ein Gerät zu.

#### Herunterladen des Berichts &quot;Inhaltszuweisung&quot; {#downloading-content-assignment-report}

Nachdem Sie Ihr AEM Screens-Projekt eingerichtet und den einzelnen Orten Bildschirme zugewiesen haben, wie in den vorherigen Schritten gezeigt.

>[!NOTE]
>Die Funktion &quot;Inhaltszuweisungsbericht&quot;kann nur auf Projektebene aufgerufen werden.

Befolgen Sie die unten stehenden Anweisungen, um den Bericht &quot;Inhaltszuweisung&quot;herunterzuladen:

1. Navigate to your AEM Screens project and select the project **DemoScreens**.

1. Klicken Sie in der Aktionsleiste auf &quot;Inhaltszuweisungsbericht&quot;. Ein Excel-Blatt sollte auf Ihren lokalen Computer heruntergeladen werden.

   >[!NOTE]
   >Das heruntergeladene Excel-Blatt besteht aus vier Spalten wie **Kanal**, **Assets**, **Displays** und **Geräte** , die zur weiteren Untersuchung aller dieser vier Entitäten verwendet werden können.




