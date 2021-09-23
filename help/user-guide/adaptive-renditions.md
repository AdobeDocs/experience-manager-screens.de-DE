---
title: Architektonischer Überblick und Konfigurationen für adaptive Ausgabedarstellungen
description: Auf dieser Seite werden Architekturübersicht und Konfigurationen in CRXDE Lite für adaptive Ausgabedarstellungen in AEM Screens beschrieben.
source-git-commit: d30426f871d319bcfacb7a832479b87400e18fc2
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---


# Adaptive Ausgabeformate: Architektonischer Überblick und Konfigurationen {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabeformate ermöglichen es den Geräten, basierend auf kundendefinierten Regeln automatisch das beste Ausgabeformat für ein Gerät auszuwählen. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich Kunden nur auf das Entwerfen des Erlebnisses *main* konzentrieren können.

## Ziele {#objective}

Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Sie müssen die adaptiven Ausgabedarstellungen konfigurieren, bevor ein Inhaltsautor diese Funktion in einem AEM Screens-Kanal verwenden kann.

## Architektonischer Überblick {#architectural-overview}

Adaptive Ausgabeformate basieren auf der Idee, dass mehrere Asset-Ausgabeformate nach einer bestimmten Benennungskonvention benannt sind. Die Entscheidung, eine bestimmte Ausgabedarstellung abzuspielen, wird getroffen, indem Medienabfrageausdrücke ausgewertet werden, die nur auf Geräten mit erwarteten Funktionen aufgelöst werden können.

Die Möglichkeit, über ein verknüpftes Ausgabedarstellungs-Benennungsmuster zu verfügen, definiert eine Ausgabedarstellungs-Zuordnungsregel wie Hochformat oder Querformat, wie in der folgenden Abbildung dargestellt. Nach der Berechnung aller verfügbaren Ausdrücke erfasst der Screens-Player die Namensmuster, die den entsprechenden Regeln entsprechen. Die Muster werden verwendet, um die richtigen Ausgabeformate während der Sequenzwiedergabe zu finden, indem nach den Mustern in den Ausgabedarstellungsnamen gesucht wird.

![Bild](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Hinzufügen der Eigenschaft für die Ausgabenzuordnung zum Screens-Projekt {#rendition-mapping-new}

Um die Funktion Adaptive Ausgabeformate zu aktivieren, sollten die folgenden Zuordnungsregeln vorhanden sein und die kontextabhängige Konfiguration (Context-Aware, CA) sollte für Kanäle und Anzeigen aufgelöst werden können.

>[!NOTE]
>Weitere Informationen zu inhaltsbasierten Konfigurationen finden Sie unter [hier](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Gehen Sie wie folgt vor, um das Setup zu konfigurieren:

1. Navigieren Sie zu **CRXDE Lite**. Überprüfen Sie, ob die **rendition-mapping**-Konfiguration in `/conf/screens/sling:configs/rendition-mapping` vorhanden ist, wie in der folgenden Abbildung dargestellt.

   >![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >Wenn Sie das neueste Feature Pack 202109 installiert haben, sehen Sie in CRXDE Lite die Knotenstruktur **rendition-mapping**, die bereits in `/conf/screens/sling:configs/rendition-mapping` vorausgefüllt ist. Weitere Informationen zum neuesten Feature Pack finden Sie unter [Versionshinweise für Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md) .
   >Stellen Sie bei vorhandenen Projekten sicher, dass dem Screens-Projekt die Konfiguration **rendition-mapping** zugeordnet ist. Weitere Informationen finden Sie unter [Hinzufügen der Ausgabedarstellungs-Zuordnung zu einem vorhandenen Projekt](#rendition-mapping-existing) .

### Hinzufügen der Ausgabezuordnungseigenschaft zu einem vorhandenen Projekt {#rendition-mapping-existing}

1. Navigieren Sie zu **CRXDE Lite**.

1. Definieren Sie explizit die Zuordnung der Ausgabedarstellungs-Zuordnung, indem Sie die Eigenschaft `sling:configRef` hinzufügen, die auf `/conf/screens` verweist, wie in der folgenden Abbildung gezeigt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen {#add-rendition-mapping-rules}

Gehen Sie wie folgt vor, um einen Knoten unter Ausgabedarstellungszuordnung hinzuzufügen:

1. Navigieren Sie von **CRXDE Lite** zu diesem Pfad `/conf/screens/sling:configs/rendition-mapping`.

1. Erstellen Sie einen Knoten unter **rendition-mapping**. Klicken Sie mit der rechten Maustaste auf **rendition-mapping** und klicken Sie auf **Erstellen** —> **Knoten erstellen**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Geben Sie den **Namen** für Ihre Zuordnungsregel wie **Regel1** und den Knoten **Typ** als **nt:unstructured** im Dialogfeld **Knoten erstellen** ein. Klicken Sie auf **OK**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. Fügen Sie die Ausdruckseigenschaft mit dem Wert hinzu, der den Abfrageausdruck enthält.

   >[!NOTE]
   >Weitere Informationen finden Sie unter [Verwenden der Syntax von Medienabfragen](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) .

   Klicken Sie auf **rule1**, die Sie erstellt haben, und geben Sie **expression** in **Name** und **(orientation:landscape)** in **Wert** ein, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Fügen Sie die pattern-Eigenschaft mit dem Wert hinzu, der das Ausgabedarstellungsbenennungsmuster enthält.

   >[!NOTE]
   >Der in der pattern-Eigenschaft definierte Wert wird mit der neuen Asset-Ausgabedarstellung abgeglichen und ausgewählt, wenn der Ausdruck als &quot;true&quot;ausgewertet wird.

   Um die Eigenschaft pattern hinzuzufügen, klicken Sie auf **rule1**, die Sie erstellt haben, und geben Sie **pattern** in **Name** und **landscape** in **Wert** ein, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klicken Sie auf **Alle speichern** und Sie sehen die Eigenschaften unter dem Knoten, den Sie unter **rendition-mapping** erstellt haben.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node5.png)


## Die nächsten Schritte {#next-steps}

Nachdem Sie Eigenschaften und Regeln für die Ausgabedarstellungszuordnung hinzugefügt haben, können Sie jetzt als Inhaltsautor Ihre Assets so konfigurieren, dass adaptive Ausgabedarstellungen verwendet werden, und Ihre Geräte für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu nutzen.
