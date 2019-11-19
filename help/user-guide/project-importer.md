---
title: Neuer Project Importer aus Datei
seo-title: Neuer Project Importer aus Datei
description: Mit dieser Funktion können Sie eine Gruppe von Speicherorten aus einer CSV/XLS-Tabelle in Ihr AEM Screens-Projekt stapelweise importieren.
seo-description: Mit dieser Funktion können Sie eine Gruppe von Speicherorten aus einer CSV/XLS-Tabelle in Ihr AEM Screens-Projekt stapelweise importieren.
uuid: e1ad76ae-6925-4d72-80ce-8343a76125ce
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
discoiquuid: f1df8d05-bb61-4bc9-aea1-c6af9e3519b4
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Neuer Project Importer aus Datei {#new-project-importer-from-file}

In diesem Abschnitt wird eine Funktion beschrieben, mit der eine Gruppe von Speicherorten aus einer CSV-/XLS-Tabelle in Ihr AEM Screens-Projekt stapelweise importiert werden kann.

## Einführung {#introduction}

Wenn Sie ein AEM Screens-Projekt einrichten, müssen Sie zum ersten Mal in Ihrem Unternehmen auch alle Standorte erstellen. Wenn Ihr Projekt eine große Anzahl von Orten umfasst, führt dies zu einer mühsamen Aufgabe, bei der in der Benutzeroberfläche viel geklickt und gewartet wird.

Das Ziel dieser Funktion ist es, die für die Einrichtung des Projekts erforderliche Zeit zu verkürzen und damit Haushaltsprobleme zu lösen.

Diese Funktion ermöglicht es dem Autor, eine Tabelle als Eingabedatei bereitzustellen und das System automatisch die Standortstruktur im Back-End erstellen zu lassen.

* *erzielt deutlich bessere Leistungen als durch manuelles Klicken auf die Benutzeroberfläche*
* *ermöglicht Kunden den Export der Speicherorte aus ihrem eigenen System und den einfachen Import direkt in AEM*

Dadurch sparen Sie Zeit und Geld bei der ersten Projekteinrichtung oder beim Erweitern der vorhandenen AEM-Bildschirme auf neue Standorte.

## Architekturüberblick {#architectural-overview}

Das folgende Diagramm zeigt die Architekturübersicht für die Funktion Project Importer:

![screen_shot_2019-05-14at20618pm](assets/screen_shot_2019-05-14at20618pm.png)

### Datenmodell {#data-model}

Das Datenmodell für den Project Importer wird nachfolgend beschrieben:

>[!NOTE]
>
>Die aktuelle Version unterstützt nur das Importieren von Speicherorten.

| **Eigenschaft** | **Beschreibung** |
|---|---|
| ***path {string*}** | Der Ressourcenpfad für den Speicherort |
| ***[./jcr:title]{string*}** | Der Name der zu verwendenden Vorlage (d. h. Speicherort für *Bildschirme/Core/Vorlagen/Speicherort*) |
| ***template {string}*** | Optionaler Titel für die Seite |
| ***[./jcr:description]{string}*** | Optionale Beschreibung für die Seite |

Für die Tabellendatei (CSV/XLS) sind daher die folgenden Spalten erforderlich:

* **path {string}** Der Pfad für den zu importierenden Speicherort, wobei der Stammordner des Pfades der Ordner für das Projekt ist (d. h. */foo* wird in */content/screens//locations/foo* importiert)

* **template {string}** Die für den neuen Speicherort zu verwendende Vorlage ist derzeit der einzige zulässige Wert "location", dieser Wert wird jedoch künftig auf alle Bildschirmvorlagen ("display", "sequencechannel"usw.) erweitert
* [**./*] {string}** Jede optionale Eigenschaft, die an der Position festgelegt wird (d. h./jcr:title, ./jcr:description, ./foo, ./bar). Die aktuelle Version ermöglicht derzeit keine Filterung

>[!NOTE]
>
>Sämtliche Spalten, die nicht den oben genannten Bedingungen entsprechen, werden einfach ignoriert. Wenn Sie beispielsweise eine andere Spalte als **Pfad**,**Vorlage**,**Titel** und **Beschreibung** in Ihrer Datei (CSV/XLS) definiert haben, werden diese Felder ignoriert und **Project Importer** überprüft diese zusätzlichen Felder nicht, um Ihr Projekt in Ihr AEM Screens-Projekt zu importieren.

## Verwenden des Project Importers {#using-project-importer}

Im folgenden Abschnitt wird beschrieben, wie der Project Importer in einem AEM Screens-Projekt verwendet wird.

>[!CAUTION]
>
>Beschränkungen:
>
>* Andere Dateien als CSV/XLS/XLSX-Erweiterungen werden in der aktuellen Version nicht unterstützt.
>* Für importierte Dateien gibt es keine Filterung der Eigenschaften und alles, was mit " beginnt./" wird importiert.
>



### Voraussetzungen {#prerequisites}

* Neues Projekt mit dem Titel **DemoProjectImport erstellen**

* Verwenden Sie eine CSV- oder Excel-Beispieldatei, die Sie importieren müssen.

Zu Demozwecken können Sie eine Excel-Datei aus dem folgenden Abschnitt herunterladen.

[Datei abrufen](assets/minimal-file.xls)

### Importieren der Datei mit den erforderlichen Mindestfeldern {#importing-the-file-with-minimum-required-fields}

Gehen Sie wie folgt vor, um eine Datei in den Ordner "Speicherorte"mit den erforderlichen Mindestfeldern zu importieren:

>[!NOTE]
>
>Das folgende Beispiel zeigt die vier Felder, die mindestens zum Importieren des Projekts erforderlich sind:

![screen_shot_2019-05-14at21523pm](assets/screen_shot_2019-05-14at21523pm.png)

1. Navigieren Sie zu Ihrem AEM Screens-Projekt (**DemoProjectImport**).

   ![screen_shot_2019-05-12at52651am](assets/screen_shot_2019-05-12at52651am.png)

1. Wählen Sie das Projekt** DemoProjectImporter **—&gt;** Erstellen **—&gt;** Orte importieren** aus der Seitenleiste.

   ![screen_shot_2019-05-12at52433am](assets/screen_shot_2019-05-12at52433am.png)

1. Der **Importassistent** wird geöffnet. Wählen Sie die Datei mit den Speicherorten für Ihr Projekt aus oder wählen Sie die Datei (***minimal-file.xls***) aus, die Sie im Abschnitt *Voraussetzungen* heruntergeladen haben.

   Klicken Sie nach Auswahl der Datei auf **Weiter**.

   ![screen_shot_2019-05-15at13718am](assets/screen_shot_2019-05-15at113718am.png)

1. Überprüfen Sie den Inhalt der Datei (Speicherorte) im Importassistenten und klicken Sie auf **Importieren**.

   ![screen_shot_2019-05-12at53131am](assets/screen_shot_2019-05-12at53131am.png)

1. Daher können Sie jetzt alle in Ihr Projekt importierten Orte anzeigen.

   ![screen_shot_2019-05-12at53450am](assets/screen_shot_2019-05-12at53450am.png)

