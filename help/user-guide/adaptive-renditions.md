---
title: Überblick über die Architektur und Konfigurationen für adaptive Ausgabedarstellungen
description: Auf dieser Seite werden der Überblick über die Architektur und Konfigurationen in CRXDE Lite für adaptive Ausgabedarstellungen in AEM Screens beschrieben.
exl-id: 0419b9c6-3c27-4a61-84ff-a6fe697e773f
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 96%

---

# Adaptive Ausgabedarstellungen: Überblick über die Architektur und Konfigurationen {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabedarstellungen ermöglichen es den Geräten, basierend auf vom Kunden definierten Regeln automatisch die beste Ausgabedarstellung für ein Gerät auszuwählen. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich die Kunden nur auf die Gestaltung des *eigentlichen* Erlebnisses konzentrieren müssen.

## Ziele {#objective}

Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Sie müssen die adaptiven Ausgabedarstellungen konfigurieren, bevor ein Inhaltsautor diese Funktion in einem AEM Screens-Kanal verwenden kann.

## Architektonischer Überblick {#architectural-overview}

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
   >Wenn Sie das neueste Feature Pack 202109 installiert haben, sehen Sie in CRXDE Lite die Knotenstruktur **Ausgabedarstellungszuordnung**, die in `/conf/screens/sling:configs/rendition-mapping` bereits vorausgefüllt ist. Weitere Informationen zum neuesten Feature Pack finden Sie unter [Versionshinweise für Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md).
   >Stellen Sie bei vorhandenen Projekten sicher, dass dem Screens-Projekt die Konfiguration **Ausgabedarstellungszuordnung** zugeordnet ist. Weitere Informationen finden Sie unter [Hinzufügen der Ausgabedarstellungszuordnung zu einem vorhandenen Projekt](#rendition-mapping-existing).

### Hinzufügen der Ausgabedarstellungszuordnungs-Eigenschaft zu einem vorhandenen Projekt {#rendition-mapping-existing}

1. Gehen Sie zu **CRXDE Lite**.

1. Definieren Sie die Zuweisung der Ausgabedarstellungszuordnung explizit, indem Sie die Eigenschaft `sling:configRef` hinzufügen, die auf `/conf/screens` verweist, wie in der folgenden Abbildung gezeigt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen {#add-rendition-mapping-rules}

Gehen Sie wie folgt vor, um einen Knoten unter „Ausgabedarstellungszuordnung“ hinzuzufügen:

1. Gehen Sie von **CRXDE Lite** zum Pfad `/conf/screens/sling:configs/rendition-mapping`.

1. Erstellen Sie einen Knoten unter **Ausgabedarstellungszuordnung**. Rechtsklick auf **rendition-mapping** und auf **Erstellen** > **Knoten erstellen**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Geben Sie den **Namen** für Ihre Zuordnungsregel wie z. B. **Regel1** und den Knoten-**Typ** als **nt:unstructured** im Dialogfeld **Knoten erstellen** ein. Klicken Sie auf **OK**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. Fügen Sie die Ausdruckseigenschaft mit dem Wert hinzu, der den Abfrageausdruck enthält.

   >[!NOTE]
   >Siehe [Syntax der Medienabfrage verwenden](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) , um mehr zu erfahren.

   Klicken Sie auf **Regel 1**, die Sie erstellt haben, und geben Sie **Ausdruck** in **Name** und **(Ausrichtung:Querformat)** in **Wert** ein, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Fügen Sie die Eigenschaft „Muster“ mit dem Wert hinzu, der das Ausgabedarstellungs-Namensmuster enthält.

   >[!NOTE]
   >Der in der Eigenschaft „Muster“ definierte Wert wird mit der neuen Asset-Ausgabedarstellung abgeglichen und ausgewählt, wenn der Ausdruck als „true“ ausgewertet wird.

   Um die Eigenschaft „Muster“ hinzuzufügen, klicken Sie auf **Regel1**, die Sie erstellt haben, und geben Sie **Muster** in **Name** und **Querformat** in **Wert** ein, wie unten dargestellt. Klicken Sie auf **Hinzufügen**.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klicken Sie auf **Alle speichern**. Sie sehen die Eigenschaften unter dem Knoten, den Sie unter **Ausgabedarstellungszuordnung** erstellt haben.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-node5.png)


## Die nächsten Schritte {#next-steps}

Nachdem Sie Eigenschaften und Regeln für die Ausgabedarstellungszuordnung hinzugefügt haben, können Sie als Inhaltsautor Ihre Assets jetzt so konfigurieren, dass adaptive Ausgabedarstellungen verwendet werden, und Ihre Geräte für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu nutzen. Weitere Informationen finden Sie unter [Verwenden adaptiver Ausgabedarstellungen in AEM Screens](/help/user-guide/using-adaptive-renditions.md).
