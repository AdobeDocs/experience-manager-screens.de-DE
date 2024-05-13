---
title: Überblick über die Architektur und Konfigurationen für adaptive Ausgabedarstellungen
description: Erfahren Sie mehr über die Architekturübersicht und -konfigurationen unter CRXDE Lite für adaptive Ausgabedarstellungen in AEM Screens.
exl-id: 0419b9c6-3c27-4a61-84ff-a6fe697e773f
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 39%

---

# Adaptive Ausgabedarstellungen: Überblick über die Architektur und Konfigurationen {#adaptive-renditions}

## Einführung {#introduction}

Mit adaptiven Ausgabeformaten können Geräte anhand von kundendefinierten Regeln automatisch auf die beste Ausgabedarstellung für ein Gerät klicken. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese basierend auf diesen Regeln wieder, sodass sich Kunden auf das Entwerfen der *main* Erlebnis.

## Ziel {#objective}

Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Konfigurieren Sie die adaptiven Ausgabeformate, bevor ein Inhaltsautor diese Funktion in einem AEM Screens-Kanal verwenden kann.

## Architektonischer Übersicht {#architectural-overview}

Adaptive Ausgabeformate basieren auf der Idee, dass mehrere Ausgabeformate eines Assets namens nach einer bestimmten Benennungskonvention vorliegen. Die Entscheidung, eine bestimmte Ausgabedarstellung abzuspielen, wird getroffen, indem Medienabfrageausdrücke ausgewertet werden, die nur auf Geräten mit erwarteten Funktionen aufgelöst werden können.

Durch die Möglichkeit, über ein verknüpftes Ausgabedarstellungs-Benennungsmuster zu verfügen, wird eine Regel für die Ausgabedarstellungszuordnung wie Hochformat oder Querformat definiert, wie in der folgenden Abbildung dargestellt. Nach der Berechnung aller verfügbaren Ausdrücke erfasst der Screens-Player die Namensmuster, die den entsprechenden Regeln entsprechen. Die Muster werden verwendet, um die richtigen Ausgabedarstellungen während der Sequenzwiedergabe zu finden, indem nach den Mustern in den Ausgabedarstellungsnamen gesucht wird.

![Bild](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Hinzufügen der Eigenschaft für die Ausgabedarstellungszuordnung zum Screens-Projekt {#rendition-mapping-new}

Um die Funktion „Adaptive Ausgabedarstellungen“ zu aktivieren, sollten die folgenden Zuordnungsregeln vorhanden sein und die kontextabhängige Konfiguration (Context-Aware, CA) sollte für Kanäle und Anzeigen aufgelöst werden können.

>[!NOTE]
>Weitere Informationen zu kontextabhängigen Konfigurationen finden Sie [hier](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Gehen Sie wie folgt vor, um die Einrichtung zu konfigurieren:

1. Gehen Sie zu **CRXDE Lite**. Überprüfen Sie, ob die **Ausgabedarstellungszuordnungs**-Konfiguration in `/conf/screens/sling:configs/rendition-mapping` vorhanden ist, wie in der folgenden Abbildung dargestellt.

   >![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >Wenn Sie das neueste Feature Pack 202109 installiert haben, sehen Sie die **rendition-mapping** Knotenstruktur, vorausgefüllt in `/conf/screens/sling:configs/rendition-mapping` in CRXDE Lite. Siehe [Versionshinweise für Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md) um Details zum neuesten Feature Pack zu erhalten.
   >Stellen Sie bei vorhandenen Projekten sicher, dass dem Screens-Projekt die Konfiguration **Ausgabedarstellungszuordnung** zugeordnet ist. Siehe [Hinzufügen der Ausgabedarstellungszuordnung zu einem vorhandenen Projekt](#rendition-mapping-existing) für weitere Informationen.

### Hinzufügen der Ausgabedarstellungszuordnungs-Eigenschaft zu einem vorhandenen Projekt {#rendition-mapping-existing}

1. Gehen Sie zu **CRXDE Lite**.

1. Definieren Sie explizit die Zuordnung der Ausgabedarstellung durch Hinzufügen von `sling:configRef` -Eigenschaft, die auf `/conf/screens` zum Projektinhalt-Knoten hinzu, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen {#add-rendition-mapping-rules}

Gehen Sie wie folgt vor, um einen Knoten unter „Ausgabedarstellungszuordnung“ hinzuzufügen:

1. Gehen Sie von **CRXDE Lite** zum Pfad `/conf/screens/sling:configs/rendition-mapping`.
1. Erstellen Sie einen Knoten unter **Ausgabedarstellungszuordnung**. Rechtsklick **rendition-mapping** und klicken **Erstellen** > **Knoten erstellen**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Geben Sie die **Name** für Ihre Zuordnungsregel wie **rule1** und dem Knoten **Typ** as **`nt:unstructured`** in **Knoten erstellen** Dialogfeld. Klicken Sie auf **OK**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. Fügen Sie die Eigenschaft expression mit dem Wert hinzu, der den Abfrageausdruck enthält.

   >[!NOTE]
   >Weitere Informationen finden Sie unter [Verwenden der Syntax von Medienabfragen](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries).

   Klicks **rule1** die Sie erstellt haben, und geben Sie die **Ausdruck** in **Name** und **(Ausrichtung:Querformat)** in **Wert**, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Fügen Sie die Eigenschaft „Muster“ mit dem Wert hinzu, der das Ausgabedarstellungs-Namensmuster enthält.

   >[!NOTE]
   >Der in der pattern-Eigenschaft definierte Wert wird mit der neuen Asset-Ausgabedarstellung abgeglichen und ausgewählt, wenn der Ausdruck als &quot;true&quot;ausgewertet wird.

   Um die pattern-Eigenschaft hinzuzufügen, klicken Sie auf **rule1** die Sie erstellt haben, und geben Sie die **pattern** in **Name** und **landscape** in **Wert**, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klicks **Alle speichern** und beachten Sie die Eigenschaften unter dem Knoten, den Sie unter erstellt haben **rendition-mapping**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node5.png)

## Die nächsten Schritte {#next-steps}

Nachdem Sie Eigenschaften und Regeln für die Ausgabedarstellungszuordnung hinzugefügt haben, können Sie als Inhaltsautor Ihre Assets konfigurieren. Sie können adaptive Ausgabeformate verwenden und Ihre Geräte für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu verwenden. Siehe [Verwenden adaptiver Ausgabeformate in AEM Screens](/help/user-guide/using-adaptive-renditions.md) für weitere Informationen.
