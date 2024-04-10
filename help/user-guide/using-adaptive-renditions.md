---
title: Verwenden adaptiver Ausgabedarstellungen in AEM Screens
description: Auf dieser Seite wird die Verwendung von adaptiven Ausgabedarstellungen in AEM Screens beschrieben.
exl-id: e7f68ed4-73c3-492a-b33a-dd915ef1f8be
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 94%

---

# Verwenden adaptiver Ausgabedarstellungen in AEM Screens {#adaptive-renditions}

## Einführung {#introduction}

Adaptive Ausgabedarstellungen ermöglichen es den Geräten, basierend auf vom Kunden definierten Regeln automatisch die beste Ausgabedarstellung für ein Gerät auszuwählen. Die Geräte laden automatisch die am besten geeignete Ausgabedarstellung eines Assets herunter und geben diese auf Grundlage dieser Regeln wieder, sodass sich die Kunden nur auf die Gestaltung des *eigentlichen* Erlebnisses konzentrieren müssen.

## Ziele {#objective}

Als AEM Screens-Inhaltsautor können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen.
Sobald ein Entwickler die Eigenschaften und Regeln für die Ausgabedarstellungs-Zuordnung hinzugefügt hat, können Sie die Ausgabedarstellungs-Zuordnung nun auf Assets anwenden und diese anschließend in einen AEM Screens-Kanal aufnehmen.

>[!IMPORTANT]
>Bevor Sie mit der Verwendung von adaptiven Ausgabedarstellungen in einem AEM Screens-Kanal beginnen, sollten Sie mehr über die Architekturübersicht und -konfiguration dieser Funktion erfahren. Weitere Informationen hierzu finden Sie in [Adaptive Ausgabedarstellungen: Überblick über die Architektur und Konfigurationen](/help/user-guide/adaptive-renditions.md).

## Verwenden adaptiver Ausgabedarstellungen in Kanälen {#using-adaptive-renditions}

>[!NOTE]
>Nachdem Sie die Eigenschaft [Ausgabedarstellungs-Zuordnung dem Screens-Projekt](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) und den [Zuordnungsregeln für Ausgabedarstellungen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) hinzugefügt haben, sind Sie als Inhaltsautor jetzt bereit, die Ausgabedarstellungen auf Ihre Assets anzuwenden.

### Anwenden von Ausgabedarstellungen auf Assets {#apply-renditions-assets}

Gehen Sie wie folgt vor, um Ausgabedarstellungen auf die Assets anzuwenden, die Sie in Ihrem Screens-Kanal verwenden möchten:

1. Gehen Sie zum Ordner **Assets** in Ihrer AEM-Instanz.

1. Erstellen Sie eine Version des Assets, die der Beschilderungs-Anzeige am besten entspricht, z. B. `seahorse.jpg`.

1. Wählen Sie das Benennungsmuster für die Ausgabedarstellung aus, z. B. `landscape`, ähnlich dem, das in der Eigenschaft **Muster** in **CRXDE Lite** definiert wurde. Siehe [Hinzufügen von Zuordnungsregeln für Ausgabedarstellungen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) für weitere Details.

1. Klicken Sie auf **Ausgabedarstellung hinzufügen**, um die Ausgabedarstellung hochzuladen, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/adaptive-renditions/manage-pub-asset2.png)

1. Wählen Sie die umbenannte Asset-Datei aus. Die Ausgabedarstellung, die Sie hinzufügen, muss das Muster enthalten (definiert in Schritt 3), z. B. `seahorse-landscape.png`.

1. Nachdem Sie das Asset hinzugefügt haben, wählen Sie das Asset aus und klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**, um das Asset zu veröffentlichen.

   ![Bild](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Siehe [On-Demand-Inhaltsaktualisierung](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content.html?lang=de) , um mehr über die Verwaltung von Veröffentlichungen und die Bereitstellung von Inhaltsaktualisierungen vom Autor zur Veröffentlichung auf dem Gerät zu erfahren.


## Migrationsstrategie {#migration-strategy}

>[!IMPORTANT]
>Bei großen Netzwerken wird empfohlen, die Migration schrittweise durchzuführen, um die Risiken zu verringern, da die Funktion Änderungen am Manifest- und Dateispeicherformat einführt. Wenn Sie das `sling:configRef` zum gesamten Projekt hinzufügen, müssen alle Player auf Feature Pack 6.5.9 aktualisiert werden. Falls Sie einige Player aktualisiert haben, müssen Sie das `sling:configRef` nur zu den Anzeigen-, Standort- oder Kanalordnern hinzufügen, in denen alle Player auf Feature Pack 6.5.9 aktualisiert wurden.

Das folgende Diagramm zeigt die Migrationsstrategie für große Netzwerke:

![Bild](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Um die Funktion zu aktivieren, fügen Sie mindestens eine Zuordnungsregel hinzu und stellen Sie sicher, dass die Konfiguration der Ausgabedarstellungs-Zuordnung im Kontext von Anzeigen und Kanälen aufgelöst werden kann. Gehen Sie zur Migration wie folgt vor:

1. Fügen Sie [Zuordnungsregeln für Ausgabedarstellungen](/help/user-guide/adaptive-renditions.md) hinzu.
1. Erstellen Sie einen Ordner für neue Kanäle und fügen Sie einen Verweis hinzu, der auf die Konfiguration der Ausgabedarstellungs-Zuordnungen verweist.
1. Erstellen Sie neue Kanäle, die die alten ersetzen, und laden Sie Ausgabedarstellungen hoch.
1. Weisen Sie den neuen Kanälen neue Anzeigen zu.
1. Fügen Sie einen Verweis zu den migrierten Anzeigen oder Standorten hinzu, die auf die Konfiguration der Ausgabedarstellungs-Zuordnungen verweisen.
1. Wiederholen Sie die Schritte 3, 4 und 5 für alle verbleibenden Kanäle und Anzeigen.

   >[!NOTE]
   >Nachdem Sie die Migration abgeschlossen haben, stellen Sie sicher, dass Sie alle Konfigurationsverweise aus Kanälen, Anzeigen und Standorten entfernen und dem Projektinhaltsknoten einen einzelnen hinzufügen.
