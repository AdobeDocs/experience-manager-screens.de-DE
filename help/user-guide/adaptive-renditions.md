---
title: Adaptive Ausgabeformate in AEM Screens
description: Auf dieser Seite werden Architekturübersicht und Konfigurationen für adaptive Ausgabedarstellungen in AEM Screens beschrieben.
index: false
source-git-commit: 75f7cf722880bb0a1f35ac663308cf049cd4fd20
workflow-type: tm+mt
source-wordcount: '710'
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

Um die Funktion Adaptive Ausgabeformate zu aktivieren, sollten die Zuordnungsregeln vorhanden sein und die CA-Konfiguration für Kanäle und Anzeigen aufgelöst werden können:

1. Überprüfen Sie, ob die Konfiguration der Ausgabedarstellungs-Zuordnung in `JCR` vorhanden ist. Diese Knotenstruktur ist für alle aktuellen Feature Packs vorausgefüllt.

   >[!NOTE]
   >Diese Knotenstruktur ist für alle aktuellen Feature Packs vorausgefüllt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

1. Stellen Sie sicher, dass dem Screens-Projekt die Konfiguration der Ausgabedarstellungs-Zuordnung zugeordnet ist.

   * Jedes neue Projekt, das mit dem Screens-Projekt-Assistenten erstellt wurde, enthält einen Verweis auf die Konfiguration der Ausgabedarstellungszuordnung.

      ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules2.png)

   * In einer älteren Version von Screens-Projekten muss die Verknüpfung explizit definiert werden, indem die Eigenschaft `sling:configRef` hinzugefügt wird, die auf `/conf/screens` verweist.

      ![Bild](/help/user-guide/assets/adaptive-renditions/mapping-rules3.png)

## Migrationsstrategie {#migration-strategy}

>[!IMPORTANT]
>Bei großen Netzwerken wird empfohlen, die Migration schrittweise durchzuführen, um die Risiken zu verringern, da die Funktion Änderungen am Manifest- und Dateispeicherformat einführt.

Das folgende Diagramm zeigt die Migrationsstrategie für große Netzwerke:

![Bild](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Um die Funktion zu aktivieren, fügen Sie mindestens eine Zuordnungsregel hinzu und stellen Sie sicher, dass die Konfiguration der Ausgabedarstellungszuordnung im Kontext von Anzeigen und Kanälen aufgelöst werden kann. Gehen Sie zur Migration wie folgt vor:

1. Fügen Sie [Rendition Mapping Rules](#adding-rendition-mapping-rules) hinzu.
1. Erstellen Sie einen Ordner für neue Kanäle und fügen Sie einen Verweis hinzu, der auf die Konfiguration der Ausgabedarstellungszuordnung verweist.
1. Erstellen Sie neue Kanäle, die die alten ersetzen, und laden Sie Ausgabedarstellungen hoch.
1. Weisen Sie den neuen Kanälen neue Anzeigen zu.
1. Fügen Sie einen Verweis zu den migrierten Anzeigen oder Positionen hinzu, die auf die Konfiguration der Ausgabedarstellungs-Zuordnung verweisen.
1. Wiederholen Sie die Schritte 3, 4 und 5 für alle verbleibenden Kanäle und Anzeigen.
1. Entfernen Sie nach Abschluss der Migration alle Konfigurationsverweise aus Kanälen, Anzeigen und Positionen und fügen Sie dem Projektinhaltsknoten eine einzelne hinzu.

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


## Hochladen von Ausgabeformaten {#upload-renditions}

1. Erstellen Sie eine Version des Assets, die der Signage-Anzeige besser entspricht, z. B. `portrait orientation`.

1. Wählen Sie das Benennungsmuster der Ausgabedarstellung aus, z. B.`portrait`.

1. Benennen Sie die Asset-Datei so um, dass sie das Muster enthält, z. B. `my_asset_portrait.png`.

1. Klicken Sie auf **Ausgabedarstellung hinzufügen** , um die Ausgabedarstellung hochzuladen, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-rendition.png)

## Die nächsten Schritte {#next-steps}

Nachdem Sie die Ausgabedarstellungen hochgeladen haben, können Sie jetzt adaptive Ausgabedarstellungen in Ihren AEM Screens-Kanälen verwenden. Weitere Informationen finden Sie unter Verwenden adaptiver Ausgabeformate .
