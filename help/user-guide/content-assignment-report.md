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

Die Funktion &quot;Inhaltszuweisungsbericht&quot;ermöglicht es einem AEM Screens-Administrator oder einem Autor, einen *Inhaltszuweisungsbericht* in ein Tabellenformat zu exportieren.

## Verwenden des Inhaltszuweisungsberichts {#using-content-assignment-report}

Der Bericht &quot;Inhaltszuweisung&quot;ermöglicht es einem AEM Screens-Autor oder einem Administrator, den Bericht herunterzuladen, der alle Assets wie Bilder oder Videos in allen Kanälen enthält, die in einem AEM Screens-Projekt erstellt wurden. Darüber hinaus enthält es die Informationen zu allen Kanälen, die allen angegebenen Anzeigen zugewiesen sind, und ab sofort alle Geräte, die ihren jeweiligen Displays zugeordnet sind.

Der Bericht &quot;Inhaltszuweisung&quot;ermöglicht nicht nur eine Vorschau aller Kanal, Assets, Anzeigen und Geräte im ausgewählten AEM Screens-Projekt, sondern stellt auch eine hohe Projektstruktur bereit.

### Verwenden des Inhaltszuweisungsberichts {#downloading-content-assignment-report-fp}

#### Einrichten des Projekts {#setting-up-project}

Gehen Sie wie folgt vor, um den Bericht &quot;Inhaltszuweisung&quot;aus einem AEM Screens-Projekt herunterzuladen:

1. Erstellen Sie ein AEM Screens mit dem Titel **DemoScreens**.

   ![image](/help/user-guide/assets/content-assignment-report/car-1.png)

1. Erstellen Sie in **DemoScreens** zwei Sequenz-Kanal, wie **ChannelOne** und **ChannelTwo**.

   ![image](/help/user-guide/assets/content-assignment-report/car-2.png)

1. Wählen Sie **ChannelOne** und klicken Sie in der Aktionsleiste auf **Bearbeiten**. hinzufügen einige Assets (Bilder/Videos) zu diesem Kanal. Fügen Sie entsprechend Assets zu **ChannelTwo** hinzu.

1. Navigieren Sie zum Ordner Speicherorte von **DemoScreens** —> **Speicherorte** und erstellen Sie drei verschiedene Speicherorte mit dem Titel **SanJose**, **Dublin** und **SanFrancisco**.

   ![image](/help/user-guide/assets/content-assignment-report/car-3.png)

1. Navigieren Sie zu den einzelnen Speicherorten und erstellen Sie eine Anzeige für jeden Standort, z. B. **SanJoseMain** unter **SanJose**, **DublinMain** unter **Dublin** und **SanFranciscoMain** unter **SanFrancisco**-Speicherort.

1. Weisen Sie jedem Display ein Gerät zu.

   >[!NOTE]
   >Weitere Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Zuweisen eines Kanals](/help/user-guide/channel-assignment.md).

#### Herunterladen des Inhaltszuweisungsberichts {#downloading-content-assignment-report}

Nachdem Sie Ihr AEM Screens-Projekt eingerichtet haben und den einzelnen Orten, wie in den vorherigen Schritten gezeigt, Anzeigen zugewiesen haben, können Sie den Bericht &quot;Inhaltszuweisung&quot;herunterladen.

>[!NOTE]
>Die Funktion &quot;Inhaltszuweisungsbericht&quot;kann nur auf Projektebene aufgerufen werden.

Befolgen Sie die unten stehenden Anweisungen, um den Bericht &quot;Inhaltszuweisung&quot;herunterzuladen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt und wählen Sie das Projekt **DemoScreens** aus.

1. Klicken Sie in der Aktionsleiste auf **Inhaltszuweisungsbericht**. Ein Excel-Blatt sollte auf Ihren lokalen Computer heruntergeladen werden.

   ![image](/help/user-guide/assets/content-assignment-report/can-download.png)

   >[!NOTE]
   >Die heruntergeladene Tabelle besteht aus vier Spalten, wie **Kanal**, **Elemente**, **Anzeigen** und **Geräte**, die zur weiteren Untersuchung dieser vier Entitäten für Ihr AEM Screens-Projekt verwendet werden können.





