---
title: Anwenden von Übergängen
seo-title: Anwenden von Übergängen
description: Auf dieser Seite erfahren Sie, wie Sie auf Ihre Screens-Projekte Übergänge anwenden können.
seo-description: Auf dieser Seite erfahren Sie, wie Sie auf Ihre Screens-Projekte Übergänge anwenden können.
uuid: b79d521b-19d4-47c8-a41a-148d7bbf6ac9
contentOwner: jsyal
feature: Authoring Screens
role: Administrator, Developer
level: Intermediate
translation-type: ht
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: ht
source-wordcount: '292'
ht-degree: 100%

---


# Anwenden von Übergängen {#applying-transitions}

In diesem Abschnitt wird beschrieben, wie Sie die **Übergangskomponente** zwischen verschiedenen Assets (Bilder und Videos) und eingebetteten Sequenzen in einem Kanal anwenden können.


>[!CAUTION]
>
>Weitere Informationen zu den Eigenschaften der **Übergangskomponente** finden Sie unter [Übergänge](adding-components-to-a-channel.md#transition).

## Hinzufügen der Übergangskomponente zu Assets in einem Kanal {#adding-transition}

Gehen Sie wie folgt vor, um Ihrem AEM Screens-Projekt eine Übergangskomponente hinzuzufügen:

>[!NOTE]
>
>**Voraussetzungen**
>
>Erstellen Sie ein AEM Screens-Projekt namens **Testprojekt** mit einem Kanal namens **Testübergang**. Richten Sie außerdem einen Standort und eine Anzeige ein, um die Ausgabe anzuzeigen.

1. Navigieren Sie zum Kanal **Testübergang** und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >Der Kanal **Testübergang** enthält bereits einige Assets (Bilder und Videos). Beispielsweise enthält der Kanal **Testübergang** drei Bilder und zwei Videos, wie unten dargestellt:

   ![image2](assets/transitions2.png)


1. Ziehen Sie die **Übergangskomponente** per Drag-and-Drop in Ihren Editor.
   >[!CAUTION]
   >
   >Bevor Sie den Übergang zu den Assets in Ihrem Kanal hinzufügen, stellen Sie sicher, dass Sie keinen Übergang vor dem ersten Asset im Sequenzkanal hinzufügen. Das erste Element im Kanal muss ein Asset und darf kein Übergang sein.

   ![image3](assets/transitions3.png)

   >[!NOTE]
   >
   >Standardmäßig sind die Eigenschaften der Übergangskomponente wie **Typ** auf **Ausblenden** und die **Dauer** auf *1600 ms* eingestellt.  Darüber hinaus ist es nicht ratsam, eine Übergangszeit festzulegen, die länger ist als die Dauer des Assets, auf das sie angewendet wird.

1. Wenn Sie diesem Kanaleditor außerdem eine **eingebettete Sequenzkomponente** hinzufügen (die einen Sequenzkanal enthält), können Sie am Ende eine Übergangskomponente hinzufügen, damit der Inhalt in der angegebenen Reihenfolge wiedergegeben wird, wie in der folgenden Abbildung dargestellt:

   ![image3](assets/transitions5.png)

