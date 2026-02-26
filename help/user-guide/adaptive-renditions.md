---
title: Überblick über die Architektur und Konfigurationen für adaptive Ausgabedarstellungen
description: Erfahren Sie mehr über den Überblick über die Architektur und Konfigurationen in CRXDE Lite für adaptive Ausgabedarstellungen in AEM Screens.
exl-id: 0419b9c6-3c27-4a61-84ff-a6fe697e773f
source-git-commit: 053df80bfd6fe39be93c0fe4c800fe775740dc7e
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 94%

---

# Adaptive Ausgabedarstellungen: Überblick über die Architektur und Konfigurationen {#adaptive-renditions}

## Einführung {#introduction}

>[!CAUTION]
>Diese Funktion wird nur On-Premise-AEM (AEM 6.5) unterstützt. Dies wird in AEM as a Cloud Service nicht unterstützt.

Mit adaptiven Ausgabedarstellungen können Geräte anhand von kundendefinierten Regeln automatisch auf die beste Ausgabedarstellung für ein Gerät klicken. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich die Kundinnen und Kunden nur auf die Gestaltung des *eigentlichen* Erlebnisses konzentrieren müssen.

## Ziel {#objective}

Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Konfigurieren Sie die adaptiven Ausgabedarstellungen, bevor eine Inhaltsautorin oder ein Inhaltsautor diese Funktion in einem AEM Screens-Kanal verwenden kann.

## Architektonische Übersicht {#architectural-overview}

Adaptive Ausgabedarstellungen basieren auf der Idee, dass mehrere Asset-Ausgabedarstellungen nach einer bestimmten Namenskonvention benannt sind. Die Entscheidung, eine bestimmte Ausgabedarstellung abzuspielen, wird getroffen, indem Medienabfrageausdrücke ausgewertet werden, die nur auf Geräten mit erwarteten Funktionen aufgelöst werden können.

Die Möglichkeit, über ein verknüpftes Ausgabedarstellungs-Namensmuster zu verfügen, definiert eine Ausgabedarstellungs-Zuordnungsregel wie Hochformat oder Querformat, wie in der folgenden Abbildung dargestellt. Nach der Berechnung aller verfügbaren Ausdrücke erfasst der Screens-Player die Namensmuster, die den entsprechenden Regeln entsprechen. Die Muster werden verwendet, um die richtigen Ausgabedarstellungen während der Sequenzwiedergabe zu finden, indem nach den Mustern in den Ausgabedarstellungsnamen gesucht wird.

![Bild](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Hinzufügen der Eigenschaft für die Ausgabedarstellungszuordnung zum Screens-Projekt {#rendition-mapping-new}

Um die Funktion „Adaptive Ausgabedarstellungen“ zu aktivieren, sollten die folgenden Zuordnungsregeln vorhanden sein und die kontextabhängige Konfiguration (Context-Aware, CA) sollte für Kanäle und Anzeigen aufgelöst werden können.

>[!NOTE]
>Weitere Informationen zu kontextabhängigen Konfigurationen finden Sie [hier](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Gehen Sie wie folgt vor, um die Einrichtung zu konfigurieren:

1. Gehen Sie zu **CRXDE Lite**. Überprüfen Sie, ob die **Ausgabedarstellungszuordnungs**-Konfiguration in `/conf/screens/sling:configs/rendition-mapping` vorhanden ist, wie in der folgenden Abbildung dargestellt.

   >![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >Wenn Sie das neueste Feature Pack 202109 installiert haben, sehen Sie in CRXDE Lite die Knotenstruktur **rendition-mapping**, die in `/conf/screens/sling:configs/rendition-mapping` bereits vorausgefüllt ist. Weitere Informationen zum neuesten Feature Pack finden Sie unter [Versionshinweise für Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md).
   >Stellen Sie bei vorhandenen Projekten sicher, dass dem Screens-Projekt die Konfiguration **rendition-mapping** zugeordnet ist. Weitere Informationen finden Sie unter [Hinzufügen der Ausgabedarstellungszuordnung zu einem vorhandenen Projekt](#rendition-mapping-existing).

### Hinzufügen der Ausgabedarstellungszuordnungs-Eigenschaft zu einem vorhandenen Projekt {#rendition-mapping-existing}

1. Gehen Sie zu **CRXDE Lite**.

1. Definieren Sie die Zuweisung der Ausgabedarstellungszuordnung explizit, indem Sie die Eigenschaft `sling:configRef`, die auf `/conf/screens` verweist, zum Projektinhaltsknoten hinzufügen, wie in der folgenden Abbildung gezeigt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen {#add-rendition-mapping-rules}

Gehen Sie wie folgt vor, um einen Knoten unter „Ausgabedarstellungszuordnung“ hinzuzufügen:

1. Gehen Sie von **CRXDE Lite** zum Pfad `/conf/screens/sling:configs/rendition-mapping`.
1. Erstellen Sie einen Knoten unter **Ausgabedarstellungszuordnung**. Klicken Sie mit der rechten Maustaste auf **Ausgabedarstellungszuordnung** und klicken Sie auf **Erstellen** > **Knoten erstellen**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Geben Sie den **Namen** für Ihre Zuordnungsregel wie z. B. **Regel1** und den **Knotentyp** im Dialogfeld **Knoten erstellen** als **`nt:unstructured`** ein. Klicken Sie auf **OK**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. Fügen Sie die Ausdruckseigenschaft mit dem Wert hinzu, der den Abfrageausdruck enthält.

   >[!NOTE]
   >Weitere Informationen finden Sie unter [Verwenden der Syntax von Medienabfragen](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries).

   Klicken Sie auf **Regel1**, die Sie erstellt haben, und geben Sie den **Ausdruck** in **Name** und **(Ausrichtung:landscape)** in **Wert** ein, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Fügen Sie die Eigenschaft „Muster“ mit dem Wert hinzu, der das Ausgabedarstellungs-Namensmuster enthält.

   >[!NOTE]
   >Der in der Eigenschaft „Muster“ definierte Wert wird mit der neuen Asset-Ausgabedarstellung abgeglichen und ausgewählt, wenn der Ausdruck als „true“ ausgewertet wird.

   Um die Eigenschaft „Muster“ hinzuzufügen, klicken Sie auf **Regel1**, die Sie erstellt haben, und geben Sie **Muster** in **Name** und **Querformat** in **Wert** ein, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klicken Sie auf **Alle speichern** und beachten Sie die Eigenschaften unter dem Knoten, den Sie unter **rendition-mapping** erstellt haben.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node5.png)

## Die nächsten Schritte {#next-steps}

Nachdem Sie Eigenschaften und Regeln für die Ausgabedarstellungszuordnung hinzugefügt haben, können Sie als Inhaltsautorin bzw. Inhaltsautor Ihre Assets konfigurieren. Sie können adaptive Ausgabedarstellungen nutzen und außerdem Ihre Geräte auch für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu verwenden. Weitere Informationen finden Sie unter [Verwenden adaptiver Ausgabedarstellungen in AEM Screens](/help/user-guide/using-adaptive-renditions.md).
