---
title: Verwenden adaptiver Ausgabeformate in AEM Screens
description: Auf dieser Seite wird die Verwendung von adaptiven Ausgabeformaten in AEM Screens beschrieben.
index: false
source-git-commit: 97354c05f3b01dd76b6b8d4bdaf45c9be3ce4db2
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 1%

---

# Verwenden adaptiver Ausgabeformate in AEM Screens {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabeformate ermöglichen es den Geräten, basierend auf kundendefinierten Regeln automatisch das beste Ausgabeformat für ein Gerät auszuwählen. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich Kunden nur auf das Entwerfen des Erlebnisses *main* konzentrieren können.

## Ziele {#objective}

Als AEM Screens Content Author können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen.

Wenn Sie also eine Vielzahl von Geräten bereitgestellt haben, ermöglicht die Verwendung dieser Funktion dem Gerät das automatische Herunterladen und Wiedergeben der am besten geeigneten Wiedergabe eines Assets basierend auf den Regeln.

>[!IMPORTANT]
>Bevor Sie mit der Verwendung von adaptiven Ausgabeformaten beginnen, sollten Sie in einem AEM Screens-Kanal mehr über die Architekturübersicht und -konfiguration dieser Funktion erfahren. Siehe Adaptive Ausgabeformate: Architektonischer Überblick und Konfigurationen für weitere Details.

## Migrationsstrategie {#migration-strategy}

>[!IMPORTANT]
>Bei großen Netzwerken wird empfohlen, die Migration schrittweise durchzuführen, um die Risiken zu verringern, da die Funktion Änderungen am Manifest- und Dateispeicherformat einführt.

Das folgende Diagramm zeigt die Migrationsstrategie für große Netzwerke:

![Bild](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Um die Funktion zu aktivieren, fügen Sie mindestens eine Zuordnungsregel hinzu und stellen Sie sicher, dass die Konfiguration der Ausgabedarstellungszuordnung im Kontext von Anzeigen und Kanälen aufgelöst werden kann. Gehen Sie zur Migration wie folgt vor:

1. Fügen Sie [Rendition Mapping Rules](/help/user-guide/adaptive-renditions.md) hinzu.
1. Erstellen Sie einen Ordner für neue Kanäle und fügen Sie einen Verweis hinzu, der auf die Konfiguration der Ausgabedarstellungszuordnung verweist.
1. Erstellen Sie neue Kanäle, die die alten ersetzen, und laden Sie Ausgabedarstellungen hoch.
1. Weisen Sie den neuen Kanälen neue Anzeigen zu.
1. Fügen Sie einen Verweis zu den migrierten Anzeigen oder Positionen hinzu, die auf die Konfiguration der Ausgabedarstellungs-Zuordnung verweisen.
1. Wiederholen Sie die Schritte 3, 4 und 5 für alle verbleibenden Kanäle und Anzeigen.

   >[!NOTE]
   >Nachdem Sie die Migration abgeschlossen haben, stellen Sie sicher, dass Sie alle Konfigurationsverweise aus Kanälen, Anzeigen und Standorten entfernen und dem Projektinhaltsknoten eine einzelne hinzufügen.


## Hochladen von Ausgabedarstellungen und Verwenden adaptiver Ausgabedarstellungen in einem AEM Screens-Kanal {#upload-renditions}

1. Erstellen Sie eine Version des Assets, die der Signage-Anzeige besser entspricht, z. B. `portrait orientation`.

1. Wählen Sie das Benennungsmuster der Ausgabedarstellung aus, z. B.`portrait`.

1. Benennen Sie die Asset-Datei so um, dass sie das Muster enthält, z. B. `my_asset_portrait.png`.

1. Klicken Sie auf **Ausgabedarstellung hinzufügen** , um die Ausgabedarstellung hochzuladen, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-rendition.png)