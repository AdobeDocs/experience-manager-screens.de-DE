---
title: Adaptive Ausgabeformate in AEM Screens
description: Auf dieser Seite werden Architekturübersicht und Konfigurationen für adaptive Ausgabedarstellungen in AEM Screens beschrieben.
index: false
source-git-commit: 951fd38d5f69cdab1bf9b23f07b4e92075e87baf
workflow-type: tm+mt
source-wordcount: '552'
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


## Einrichten von Autoren- und Veröffentlichungsinstanz {#setup-author-publish}

Beachten Sie die folgenden Empfehlungen in der Autoren- und Veröffentlichungsinstanz, bevor Sie adaptive Ausgabedarstellungen verwenden:

* Das Mapping von Ausgabedarstellungen muss manuell repliziert werden.

* Asset-Ausgabedarstellungen werden nicht standardmäßig repliziert. Alle relevanten Assets müssen manuell repliziert werden.

## Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen {#add-rendition-mapping-rules}

1. Um eine Zuordnungsregel hinzuzufügen, müssen Sie einen Knoten des Typs `nt:unstructured` unter dem Knoten **rendition-mapping** erstellen.

1. Fügen Sie die Eigenschaft expression mit dem Wert hinzu, der den Abfrageausdruck enthält.

   >[!NOTE]
   >Weitere Informationen finden Sie unter [Verwenden der Syntax von Medienabfragen](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) .

1. Fügen Sie die pattern-Eigenschaft mit dem Wert hinzu, der das ausgewählte Ausgabedarstellungs-Benennungsmuster enthält, wenn der Ausdruck als &quot;true&quot;ausgewertet wird.

   ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules4.png)


## Die nächsten Schritte {#next-steps}

Nachdem Sie die Ausgabedarstellungen als Inhaltsautor konfiguriert und hochgeladen haben, können Sie jetzt adaptive Ausgabedarstellungen verwenden und Ihre Geräte für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu nutzen. Weitere Informationen finden Sie unter [Verwenden adaptiver Ausgabeformate](/help/user-guide/using-adaptive-renditions.md) .
