---
title: Adaptive Ausgabeformate in AEM Screens
description: Auf dieser Seite wird die Verwendung von adaptiven Ausgabeformaten in AEM Screens beschrieben.
index: false
source-git-commit: e56b14639370b9ecd8924270e827dbd70112581b
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 1%

---

# Adaptive Ausgabeformate {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabeformate ermöglichen es den Geräten, basierend auf kundendefinierten Regeln automatisch das beste Ausgabeformat für ein Gerät auszuwählen. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich Kunden nur auf das Entwerfen des Erlebnisses *main* konzentrieren können.

## Ziele {#objective}

Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Sie müssen die adaptiven Ausgabedarstellungen konfigurieren, bevor ein Inhaltsautor diese Funktion in einem AEM Screens-Kanal verwenden kann.

Wenn Sie also eine Vielzahl von Geräten bereitgestellt haben, ermöglicht die Verwendung dieser Funktion dem Gerät das automatische Herunterladen und Wiedergeben der am besten geeigneten Wiedergabe eines Assets basierend auf den Regeln.

## Architektonischer Überblick {#architectural-overview}

Adaptive Ausgabeformate basieren auf der Idee, dass mehrere Asset-Ausgabeformate nach einer bestimmten Benennungskonvention benannt sind. Die Entscheidung, eine bestimmte Ausgabedarstellung abzuspielen, wird getroffen, indem Medienabfrageausdrücke ausgewertet werden, die nur auf Geräten mit erwarteten Funktionen aufgelöst werden können. Die Möglichkeit, über ein verknüpftes Ausgabedarstellungs-Namensmuster zu verfügen, definiert eine Ausgabedarstellungs-Zuordnungsregel. Nach der Berechnung aller verfügbaren Ausdrücke erfasst der Screens-Player die Namensmuster, die den entsprechenden Regeln entsprechen. Die Muster werden verwendet, um die richtigen Ausgabeformate während der Sequenzwiedergabe zu finden, indem nach den Mustern in den Ausgabedarstellungsnamen gesucht wird.


## Konfigurieren der Einrichtung für die Verwendung adaptiver Ausgabeformate {#setup-adaptive-renditions}

Um die Funktion Adaptive Ausgabeformate zu aktivieren, sollten die Zuordnungsregeln vorhanden sein und die CA-Konfiguration für Kanäle und Anzeigen aufgelöst werden können:

1. Überprüfen Sie, ob die Konfiguration der Ausgabedarstellungs-Zuordnung in `JCR` vorhanden ist. Diese Knotenstruktur ist für alle aktuellen Feature Packs vorausgefüllt.

   >[!NOTE]
   >Diese Knotenstruktur ist für alle aktuellen Feature Packs vorausgefüllt.


1. Stellen Sie sicher, dass dem Screens-Projekt die Konfiguration der Ausgabedarstellungs-Zuordnung zugeordnet ist.

   * Jedes neue Projekt, das mit dem Screens-Projekt-Assistenten erstellt wurde, enthält einen Verweis auf die Konfiguration der Ausgabedarstellungszuordnung.

   * In einer älteren Version von Screens-Projekten muss die Verknüpfung explizit definiert werden, indem die Eigenschaft `sling:configRef` hinzugefügt wird, die auf `/conf/screens` verweist.

## Migrationsstrategie {#migration-strategy}

>[!IMPORTANT]
>Bei großen Netzwerken wird empfohlen, die Migration schrittweise durchzuführen, um die Risiken zu verringern, da die Funktion Änderungen am Manifest- und Dateispeicherformat einführt.

Um die Funktion zu aktivieren, fügen Sie mindestens eine Zuordnungsregel hinzu und stellen Sie sicher, dass die Konfiguration der Ausgabedarstellungszuordnung im Kontext von Anzeigen und Kanälen aufgelöst werden kann:

1. Fügen Sie Regeln für die Ausgabedarstellungszuordnung hinzu.
1. Erstellen Sie einen Ordner für neue Kanäle und fügen Sie einen Verweis hinzu, der auf die Konfiguration der Ausgabedarstellungszuordnung verweist.
1. Erstellen Sie neue Kanäle, die die alten ersetzen, und laden Sie Ausgabedarstellungen hoch.
1. Weisen Sie den neuen Kanälen neue Anzeigen zu.
1. Fügen Sie den migrierten Anzeigen/Speicherorten einen Verweis hinzu, der auf die Konfiguration der Ausgabedarstellungs-Zuordnung verweist.
1. Wiederholen Sie die Schritte 3, 4 und 5 für alle verbleibenden Kanäle und Anzeigen.
1. Nachdem Sie mit der Migration fertig sind, entfernen Sie alle Konfigurationsverweise aus Kanälen/Anzeigen/Standorten und fügen Sie dem Projektinhaltsknoten eine einzelne hinzu.

## Einrichten von Autoren- und Veröffentlichungsinstanz {#setup-author-publish}

Gehen Sie wie folgt vor, um Autor und Veröffentlichung einzurichten:

* Das Mapping von Ausgabedarstellungen muss manuell repliziert werden.

* Asset-Ausgabedarstellungen werden nicht standardmäßig repliziert. Alle relevanten Assets müssen manuell repliziert werden.


## Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen {#adding-rendition-mapping-rules}

1. Um eine Zuordnungsregel hinzuzufügen, müssen Sie einen Knoten des Typs `nt:unstructured` unter dem Knoten rendition-mapping erstellen.

1. Fügen Sie die Eigenschaft expression mit dem Wert hinzu, der den Abfrageausdruck enthält.

   >[!NOTE]
   >Weitere Informationen finden Sie unter [Verwenden der Syntax von Medienabfragen](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) .

1. Fügen Sie die pattern-Eigenschaft mit dem Wert hinzu, der das ausgewählte Ausgabedarstellungs-Benennungsmuster enthält, wenn der Ausdruck als &quot;true&quot;ausgewertet wird.

## Hochladen von Ausgabeformaten {#upload-renditions}

1. Erstellen Sie eine Version des Assets, die der Signage-Anzeige besser entspricht, z. B. `portrait orientation`.

1. Wählen Sie das Benennungsmuster der Ausgabedarstellung aus, z. B.`portrait`.

1. Benennen Sie die Asset-Datei so um, dass sie das Muster enthält, z. B. `my_asset_portrait.png`.

1. Laden Sie die Ausgabedarstellung hoch, indem Sie in der Symbolleiste auf die Schaltfläche Ausgabedarstellung hinzufügen klicken.


## Die nächsten Schritte {#next-steps}

Nachdem Sie die Ausgabedarstellungen hochgeladen haben, können Sie jetzt adaptive Ausgabedarstellungen in Ihren AEM Screens-Kanälen verwenden.
