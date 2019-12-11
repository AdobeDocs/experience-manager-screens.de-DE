---
title: Anwenden von Übergängen
seo-title: Anwenden von Übergängen
description: Auf dieser Seite erfahren Sie, wie Sie Übergänge auf Ihre Screens-Projekte anwenden.
seo-description: Auf dieser Seite erfahren Sie, wie Sie Übergänge auf Ihre Screens-Projekte anwenden.
uuid: b79d521b-19d4-47c8-a41a-148d7bbf6ac9
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: 4078050ada4c53c2a9de00928d2198279aaa1e34

---


# Anwenden von Übergängen {#applying-transitions}

In diesem Abschnitt wird beschrieben, wie Sie die **Übergangskomponente** zwischen verschiedenen Assets (Bilder und Videos) in einem Kanal anwenden können.


>[!CAUTION]
>
>Ausführliche Informationen zu den Eigenschaften der Übergangskomponente finden Sie unter [Übergänge](adding-components-to-a-channel.md#transition).

## Hinzufügen der Übergangskomponente zu Assets in einem Kanal {#adding-transition}

Gehen Sie wie folgt vor, um Ihrem AEM Screens-Projekt eine Übergangskomponente hinzuzufügen:

>[!NOTE]
>
>**Voraussetzungen**
> Erstellen Sie ein AEM Screens-Projekt **TestProject** mit einem Kanal **TestTransition**. Richten Sie außerdem einen Speicherort und eine Anzeige ein, um die Ausgabe anzuzeigen.

1. Navigieren Sie zum Kanal- **TestTransition** und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >Der **TestTransition** -Kanal enthält bereits wenige Assets (Bilder und Videos). Der **TestTransition** -Kanal enthält beispielsweise drei Bilder und zwei Videos, wie unten dargestellt:

   ![image2](assets/transitions2.png)


1. Ziehen Sie die **Übergangskomponente** per Drag &amp; Drop in Ihren Editor.
   >[!CAUTION]
   >
   >Bevor Sie den Übergang zu Ihren Assets in Ihrem Kanal hinzufügen, stellen Sie sicher, dass Sie keinen Übergang vor dem ersten Asset im sequenziellen Kanal hinzufügen. Das erste Element im Kanal muss ein Asset und kein Übergang sein.

   ![image3](assets/transitions3.png)

   > [!NOTE]
   >
   >Standardmäßig sind die Eigenschaften der Übergangskomponente wie **Typ** auf **Normal** eingestellt und die **Dauer** auf *600 ms* eingestellt.  Darüber hinaus ist es nicht ratsam, eine Übergangszeit festzulegen, die länger ist als das Asset, auf das sie angewendet wird.

## Hinzufügen der Übergangskomponente zu Videos in einem Kanal {#adding-transition-videos}

Wenn Sie eine Übergangskomponente zwischen Videos anwenden, stellen Sie den **Typ** immer auf **Fade** und die **Sequenzdauer** auf **1600 ms** ein.

![image3](assets/transitions4.png)