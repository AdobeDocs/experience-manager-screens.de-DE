---
title: Verwenden adaptiver Ausgabeformate in AEM Screens
description: Auf dieser Seite wird die Verwendung von adaptiven Ausgabeformaten in AEM Screens beschrieben.
source-git-commit: 68e7a47d7a9b10d1d3fecb7a7f7d96bbbde1c48a
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 1%

---


# Verwenden adaptiver Ausgabeformate in AEM Screens {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabeformate ermöglichen es den Geräten, basierend auf kundendefinierten Regeln automatisch das beste Ausgabeformat für ein Gerät auszuwählen. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich Kunden nur auf das Entwerfen des Erlebnisses *main* konzentrieren können.

## Ziele {#objective}

Als AEM Screens Content Author können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen.
Sobald ein Entwickler die Eigenschaften und Regeln für die Ausgabedarstellungszuordnung hinzugefügt hat, können Sie die Ausgabedarstellungs-Zuordnung nun auf Assets anwenden und diese anschließend in einen AEM Screens-Kanal einschließen.

>[!IMPORTANT]
>Bevor Sie mit der Verwendung von adaptiven Ausgabeformaten beginnen, sollten Sie in einem AEM Screens-Kanal mehr über die Architekturübersicht und -konfiguration dieser Funktion erfahren. Siehe [Adaptive Ausgabeformate: Architektonischer Überblick und Konfigurationen](/help/user-guide/adaptive-renditions.md) für weitere Details.

## Verwenden adaptiver Ausgabeformate in Kanälen {#using-adaptive-renditions}

>[!NOTE]
>Nachdem Sie die Eigenschaft [Ausgabedarstellungs-Mapping zum Screens-Projekt](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) und den [Darstellungszuordnungsregeln](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) hinzugefügt haben, sind Sie als Inhaltsautor jetzt bereit, die Ausgabedarstellungen auf Ihre Assets anzuwenden.

### Anwenden von Ausgabeformaten auf Assets {#apply-renditions-assets}

Gehen Sie wie folgt vor, um Ausgabeformate auf die Assets anzuwenden, die Sie im Tour Screens-Kanal verwenden möchten:

1. Navigieren Sie zum Ordner **Assets** in Ihrer AEM-Instanz.

1. Erstellen Sie eine Version des Assets, die der Signage-Anzeige besser entspricht, z. B. `seahorse.jpg`.

1. Wählen Sie das Benennungsmuster für die Ausgabedarstellung aus, z. B.`landscape`, ähnlich dem, das in der Eigenschaft **pattern** in **CRXDE Lite** definiert wurde. Weitere Informationen finden Sie unter [Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) .

1. Benennen Sie die Asset-Datei so um, dass sie das Muster enthält (definiert in Schritt 3), z. B. `seahorse-landscape.png`.

1. Klicken Sie auf **Ausgabedarstellung hinzufügen** , um die Ausgabedarstellung hochzuladen, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/add-rendition.png)

1. Nachdem Sie das Asset hinzugefügt haben, wählen Sie das Asset aus und klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten** , um das Asset zu veröffentlichen.

   ![Bild](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Weitere Informationen zum Verwalten von Veröffentlichungen und Bereitstellen von Inhaltsaktualisierungen von der Autoren- zur Veröffentlichungsinstanz auf dem Gerät finden Sie unter [On-Demand-Inhaltsaktualisierung](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content.html?lang=en) .


## Migrationsstrategie {#migration-strategy}

>[!IMPORTANT]
>Bei großen Netzwerken wird empfohlen, die Migration schrittweise durchzuführen, um die Risiken zu verringern, da die Funktion Änderungen am Manifest- und Dateispeicherformat einführt. Wenn Sie das `sling:configRef` zum gesamten Projekt hinzufügen, müssen alle Player auf Feature Pack 6.5.9 aktualisiert werden. Falls Sie einige Player aktualisiert haben, müssen Sie das `sling:configRef` nur zu den Anzeigen, Speicherorten oder Kanalordnern hinzufügen, in denen alle Player auf Feature Pack 6.5.9 aktualisiert wurden.

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

