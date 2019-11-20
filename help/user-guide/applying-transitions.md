---
title: Anwenden von Übergängen
seo-title: Anwenden von Übergängen
description: Auf dieser Seite erfahren Sie, wie Sie Übergänge auf Ihre Screens-Projekte anwenden.
seo-description: Auf dieser Seite erfahren Sie, wie Sie Übergänge auf Ihre Screens-Projekte anwenden.
uuid: b79d521b-19d4-47c8-a41a-148d7bbf6ac9
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: 02acf7ffc447c92efb75d756071d2cd5f4aaf104

---


# Anwenden von Übergängen {#applying-transitions}

In diesem Abschnitt wird beschrieben, wie Sie mit einer **Übergangskomponente** einen Übergang zu Ihrem Screens-Projekt hinzufügen können.


>[!CAUTION]
>
>Weitere Informationen zu den Eigenschaften der Übergangskomponente finden Sie unter [Übergänge](adding-components-to-a-channel.md#transition)

## Hinzufügen einer Übergangskomponente {#adding-transition}

Gehen Sie wie folgt vor, um Ihrem AEM Screens-Projekt eine Übergangskomponente hinzuzufügen:

>[!NOTE]
>
>**Voraussetzungen**
> Erstellen Sie ein AEM Screens-Projekt **TestProject** mit einem Kanal **TestTransition**. Richten Sie außerdem einen Speicherort und eine Anzeige ein, um die Ausgabe anzuzeigen.

1. Navigieren Sie zum Kanal- **TestTransition** und klicken Sie in der Aktionsleiste auf **Bearbeiten** .



   >[!NOTE]
   >
   >Der **TestTransition** -Kanal enthält bereits wenige Assets (Bilder und Videos). Der **TestTransition** -Kanal enthält beispielsweise fünf Bilder und ein Video, wie unten dargestellt:



1. Ziehen Sie die **Übergangskomponente** per Drag &amp; Drop in Ihren Editor.

   > [!NOTE]
   >
   >Standardmäßig ist die Übergangskomponente auf "Typ"als " **Normal** "eingestellt, wobei die **Dauer** auf *600 ms* eingestellt ist.


   >[!CAUTION]
   >
   >Bevor Sie den Übergang zu Ihren Assets in Ihrem Kanal hinzufügen, stellen Sie Folgendes sicher:
Sie fügen keinen Übergang vor dem ersten Asset im sequenziellen Kanal hinzu. Das erste Element im Kanal muss ein Asset und kein Übergang sein.
