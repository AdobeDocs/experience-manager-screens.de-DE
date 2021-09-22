---
title: Adaptive Ausgabeformate in AEM Screens
description: Auf dieser Seite werden Architekturübersicht und Konfigurationen für adaptive Ausgabedarstellungen in AEM Screens beschrieben.
index: false
source-git-commit: fcc7126ac545c80004d718888b39c6477624cd33
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# Adaptive Ausgabeformate: Architektonischer Überblick und Konfigurationen {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabeformate ermöglichen es den Geräten, basierend auf kundendefinierten Regeln automatisch das beste Ausgabeformat für ein Gerät auszuwählen. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich Kunden nur auf das Entwerfen des Erlebnisses *main* konzentrieren können.

## Ziele {#objective}

Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Sie müssen die adaptiven Ausgabedarstellungen konfigurieren, bevor ein Inhaltsautor diese Funktion in einem AEM Screens-Kanal verwenden kann.

Wenn Sie also eine Vielzahl von Geräten bereitgestellt haben, ermöglicht die Verwendung dieser Funktion dem Gerät das automatische Herunterladen und Wiedergeben der am besten geeigneten Wiedergabe eines Assets basierend auf den Regeln.

## Architektonischer Überblick {#architectural-overview}

Adaptive Ausgabeformate basieren auf der Idee, dass mehrere Asset-Ausgabeformate nach einer bestimmten Benennungskonvention benannt sind. Die Entscheidung, eine bestimmte Ausgabedarstellung abzuspielen, wird getroffen, indem Medienabfrageausdrücke ausgewertet werden, die nur auf Geräten mit erwarteten Funktionen aufgelöst werden können. Die Möglichkeit, über ein verknüpftes Ausgabedarstellungs-Namensmuster zu verfügen, definiert eine Ausgabedarstellungs-Zuordnungsregel. Nach der Berechnung aller verfügbaren Ausdrücke erfasst der Screens-Player die Namensmuster, die den entsprechenden Regeln entsprechen. Die Muster werden verwendet, um die richtigen Ausgabeformate während der Sequenzwiedergabe zu finden, indem nach den Mustern in den Ausgabedarstellungsnamen gesucht wird.

![Bild](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Konfigurieren der Einrichtung für die Verwendung adaptiver Ausgabeformate {#setup-adaptive-renditions}

Um die Funktion Adaptive Ausgabeformate zu aktivieren, sollten die Zuordnungsregeln vorhanden und die kontextabhängige Konfiguration für Kanäle und Anzeigen auflösbar sein:

1. Überprüfen Sie, ob die Konfiguration der Ausgabedarstellungs-Zuordnung in `JCR` vorhanden ist. Diese Knotenstruktur ist für alle aktuellen Feature Packs vorausgefüllt.

   >[!NOTE]
   >Diese Knotenstruktur ist für alle aktuellen Feature Packs vorausgefüllt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

1. Stellen Sie sicher, dass dem Screens-Projekt die Konfiguration der Ausgabedarstellungs-Zuordnung zugeordnet ist.

   * Jedes neue Projekt, das mit dem Screens-Projekt-Assistenten erstellt wurde, enthält einen Verweis auf die Konfiguration der Ausgabedarstellungszuordnung.

      ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules2.png)

   * In einer älteren Version von Screens-Projekten muss die Verknüpfung explizit definiert werden, indem die Eigenschaft `sling:configRef` hinzugefügt wird, die auf `/conf/screens` verweist.

      ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules3.png)



## Einrichten von Autoren- und Veröffentlichungsinstanz {#setup-author-publish}

Beachten Sie die folgenden Empfehlungen in der Autoren- und Veröffentlichungsinstanz, bevor Sie adaptive Ausgabedarstellungen verwenden:

* Das Mapping von Ausgabedarstellungen muss manuell repliziert werden.

* Asset-Ausgabedarstellungen werden nicht standardmäßig repliziert. Alle relevanten Assets müssen manuell repliziert werden.

## Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen {#add-rendition-mapping-rules}

1. Um eine Zuordnungsregel hinzuzufügen, müssen Sie einen Knoten des Typs `nt:unstructured` unter dem Knoten rendition-mapping erstellen.

1. Fügen Sie die Eigenschaft expression mit dem Wert hinzu, der den Abfrageausdruck enthält.

   >[!NOTE]
   >Weitere Informationen finden Sie unter [Verwenden der Syntax von Medienabfragen](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) .

1. Fügen Sie die pattern-Eigenschaft mit dem Wert hinzu, der das ausgewählte Ausgabedarstellungs-Benennungsmuster enthält, wenn der Ausdruck als &quot;true&quot;ausgewertet wird.

   ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules4.png)



## Die nächsten Schritte {#next-steps}

Nachdem Sie die Ausgabedarstellungen konfiguriert und hochgeladen haben, können Sie jetzt adaptive Ausgabedarstellungen in Ihren AEM Screens-Kanälen verwenden. Weitere Informationen finden Sie unter Verwenden adaptiver Ausgabeformate .
