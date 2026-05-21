---
title: Anwenden von Übergängen
description: Erfahren Sie, wie Sie Übergänge auf Ihre AEM Screens-Projekte anwenden.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 757e6751-8008-487f-be89-9f53ac898928
TQID: https://experienceleague.adobe.com/t4JTCyQhe7kb5v-dveK4Np9dAAGLBeatCN2kyTM6ELc
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2:
  - id: e8696a6a-4caa-4059-b0b2-3fbb66f5ab7e
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 0b0bfcd803c3da9298122200a0a1715fc2d5e49c
workflow-type: tm+mt
source-wordcount: 276
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
>Erstellen Sie ein AEM Screens-Projekt namens **Testprojekt** mit einem Kanal namens **Testübergang**. Richten Sie zudem einen Standort und eine Anzeige ein, um die Ausgabe anzuzeigen.

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
   >Standardmäßig sind die Eigenschaften der Übergangskomponente wie **Typ** auf **Überblendung** und die **Dauer** auf *1600 Millisekunden* eingestellt. Außerdem ist es nicht ratsam, eine Übergangsdauer festzulegen, die länger ist als die Dauer des Assets, auf das sie angewendet wird.

1. Wenn Sie diesem Kanaleditor eine Komponente **Eingebettete Sequenz** (die einen Sequenzkanal enthält) hinzufügen, können Sie außerdem am Ende eine Übergangskomponente hinzufügen. Dadurch wird sichergestellt, dass der Inhalt in der richtigen Reihenfolge wiedergegeben wird, wie in der folgenden Abbildung dargestellt:

   ![image3](assets/transitions5.png)
