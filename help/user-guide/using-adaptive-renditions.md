---
title: Verwenden adaptiver Ausgabedarstellungen in AEM Screens
description: Erfahren Sie, wie Sie adaptive Ausgabeformate in AEM Screens verwenden.
exl-id: e7f68ed4-73c3-492a-b33a-dd915ef1f8be
source-git-commit: 2a51258ffe7b969962378dcd0558bd001b616ba1
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 21%

---

# Verwenden adaptiver Ausgabedarstellungen in AEM Screens {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabeformate ermöglichen es den Geräten, für ein Gerät basierend auf kundendefinierten Regeln automatisch auf die beste Ausgabedarstellung zu klicken. Die Geräte laden basierend auf diesen Regeln automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese wieder. Dadurch können Kunden sich auf die Gestaltung der *main* Erlebnis.

## Ziel {#objective}

Als AEM Screens Content Author können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen.
Nachdem ein Entwickler die Eigenschaften und Regeln für die Ausgabedarstellungszuordnung hinzugefügt hat, können Sie die Ausgabedarstellungs-Zuordnung auf Assets anwenden und sie dann in einen AEM Screens-Kanal einschließen.

>[!IMPORTANT]
>Bevor Sie mit der Verwendung von adaptiven Ausgabeformaten in einem AEM Screens-Kanal beginnen, empfiehlt Adobe, sich mit der Architekturübersicht und -konfiguration dieser Funktion vertraut zu machen. Siehe [Adaptive Ausgaben: Architektonischer Überblick und Konfigurationen](/help/user-guide/adaptive-renditions.md).

## Verwenden adaptiver Ausgabedarstellungen in Kanälen {#using-adaptive-renditions}

>[!NOTE]
>Nachdem Sie die [rendition-mapping-Eigenschaft zum Screens-Projekt](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) und [Regeln für Ausgabedarstellung-Zuordnung](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules)als Inhaltsautor können Sie jetzt die Ausgabedarstellungen auf Ihre Assets anwenden.

### Anwenden von Ausgabedarstellungen auf Assets {#apply-renditions-assets}

Gehen Sie wie folgt vor, um Ausgabeformate auf Assets anzuwenden, die Sie im Kanal &quot;Tour Screens&quot;verwenden möchten.

1. Gehen Sie zum Ordner **Assets** in Ihrer AEM-Instanz.
1. Erstellen Sie eine Version des Assets, die der Signage-Anzeige besser entspricht, z. B. `seahorse.jpg`.
1. Wählen Sie das Benennungsmuster für die Ausgabedarstellung aus, z. B.`landscape`, ähnlich dem, was unter **pattern** -Eigenschaft in **CRXDE Lite**. Siehe [Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) für weitere Details.
1. Klicks **Ausgabedarstellung hinzufügen** , um die Ausgabedarstellung hochzuladen, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/manage-pub-asset2.png)

1. Klicken Sie auf die umbenannte Asset-Datei. Die Ausgabedarstellung, die Sie hinzufügen, muss das Muster enthalten (definiert in Schritt 3), z. B. `seahorse-landscape.png`.
1. Wenn Sie das Asset hinzugefügt haben, klicken Sie auf das Asset und klicken Sie auf **Veröffentlichung verwalten** in der Aktionsleiste, um das Asset zu veröffentlichen.

   ![Bild](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Siehe [On-Demand-Inhaltsaktualisierung](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content) , um mehr über die Verwaltung von Veröffentlichungen und die Bereitstellung von Inhaltsaktualisierungen vom Autor zur Veröffentlichung auf dem Gerät zu erfahren.

## Migrationsstrategie {#migration-strategy}

>[!IMPORTANT]
>Für große Netze empfiehlt Adobe, die Migration schrittweise durchzuführen, um die Risiken zu mindern. Der Grund dafür ist, dass die Funktion Änderungen am Manifest- und Dateispeicherformat einführen kann. Hinzufügen der `sling:configRef` zum gesamten Projekt hinzugefügt werden, müssen alle Player auf Feature Pack 6.5.9 aktualisiert werden. Wenn Sie einige Player aktualisiert haben, fügen Sie die `sling:configRef` nur für Anzeigen-, Orte- oder Kanalordner, die alle Player auf Feature Pack 6.5.9 aktualisiert haben.

Das folgende Diagramm zeigt die Migrationsstrategie für große Netzwerke:

![Bild](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Um die Funktion zu aktivieren, fügen Sie mindestens eine Zuordnungsregel hinzu und stellen Sie sicher, dass die Konfiguration der Ausgabedarstellung-Zuordnung im Kontext von Anzeigen und Kanälen aufgelöst werden kann. Gehen Sie zur Migration wie folgt vor:

1. Fügen Sie [Zuordnungsregeln für Ausgabedarstellungen](/help/user-guide/adaptive-renditions.md) hinzu.
1. Erstellen Sie einen Ordner für neue Kanäle und fügen Sie einen Verweis hinzu, der auf die Konfiguration der Ausgabedarstellungszuordnung verweist.
1. Erstellen Sie Kanäle, die die alten ersetzen, und laden Sie Ausgabedarstellungen hoch.
1. Weisen Sie den neuen Kanälen neue Anzeigen zu.
1. Fügen Sie einen Verweis zu den migrierten Anzeigen oder Positionen hinzu, die auf die Konfiguration der Ausgabedarstellungszuordnung verweisen.
1. Wiederholen Sie die Schritte 3, 4 und 5 für alle verbleibenden Kanäle und Anzeigen.

   >[!NOTE]
   >Nachdem Sie die Migration abgeschlossen haben, stellen Sie sicher, dass Sie alle Konfigurationsverweise aus Kanälen, Anzeigen und Standorten entfernen und dem Projektinhaltsknoten einen einzelnen hinzufügen.
