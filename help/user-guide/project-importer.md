---
title: Importer für neue Projekte aus Datei
description: Mit dieser Funktionalität können Sie verschiedene Standorte aus einer CSV/XLS-Tabelle per Massenimport in Ihr AEM Screens-Projekt importieren.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
docset: aem65
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3bff9ef3-0d6f-41d8-a8ef-bcc5a795990e
source-git-commit: 2b865165793b1c0f90f1351518e41096a57ea2ff
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 54%

---

# Importer für neue Projekte aus Datei {#new-project-importer-from-file}

In diesem Abschnitt wird eine Funktionalität beschrieben, mit der Sie verschiedene Standorte aus einer CSV/XLS-Tabelle per Massenimport in Ihr AEM Screens-Projekt importieren können.

## Einführung {#introduction}

Wenn Sie ein AEM Screens-Projekt zum ersten Mal in Ihrem Unternehmen einrichten, müssen Sie auch alle Standorte erstellen. Wenn Ihr Projekt viele Standorte umfasst, führt dies zu einer mühsamen Aufgabe, bei der in der Benutzeroberfläche viel geklickt und gewartet wird.

Das Ziel dieser Funktion ist es, die Zeit für die Einrichtung des Projekts zu reduzieren und somit Budgetierungsprobleme zu lösen.

Diese Funktion ermöglicht es dem Autor, eine Tabelle als Eingabedatei bereitzustellen und das System automatisch die Standortstruktur im Back-End erstellen zu lassen:

* *erzielt deutlich bessere Leistung als manuelles Klicken durch die Benutzeroberfläche*
* *ermöglicht es dem Kunden, seine Standorte aus dem eigenen System zu exportieren und einfach direkt in AEM zu importieren*

Dadurch sparen Sie Zeit und Geld bei der ersten Projekteinrichtung oder beim Erweitern bestehender AEM Screens-Projekte auf neue Standorte.

## Architektonischer Überblick {#architectural-overview}

Das folgende Diagramm zeigt die Architekturübersicht für die Projekt-Importer-Funktion:

![screen_shot_2019-05-14at20618pm](assets/screen_shot_2019-05-14at20618pm.png)

### Datenmodell {#data-model}

Im Folgenden wird das Datenmodell für den Projekt-Importer beschrieben:

>[!NOTE]
>
>Die aktuelle Version unterstützt nur das Importieren von Standorten.

| **Eigenschaft** | **Beschreibung** |
|---|---|
| ***`path {string*}`*** | Der Ressourcenpfad für den Standort |
| ***`[./jcr:title] {string*}`*** | Der Name der zu verwendenden Vorlage (d. h. Standort für *screens/core/templates/location*) |
| ***`template {string}`*** | Optionaler Titel für die Seite |
| ***`[./jcr:description] {string}`*** | Optionale Beschreibung für die Seite |

Für die Tabellendatei (CSV/XLS) sind daher die folgenden Spalten erforderlich:

* **path {string}** - Der Pfad für den zu importierenden Speicherort, wobei der Stammordner des Pfades der Standortordner für das Projekt ist (d. h. *`/foo`* importiert in *`/content/screens/<project>/locations/foo`*)
* **template {string}** - Die für den neuen Speicherort zu verwendende Vorlage ist derzeit der einzige zulässige Wert &quot;location&quot;, aber dies wird in Zukunft auf alle Screens-Vorlagen ausgedehnt (`display`, `sequencechannel`usw.)
* **[./*] {string}** - Jede optionale Eigenschaft, die für den Standort festgelegt wird (d. h. `./jcr:title`, `./jcr:description`, `./foo, ./bar`). Die aktuelle Version erlaubt keine Filterung.

>[!NOTE]
>
>Sämtliche Spalten, die nicht mit den oben genannten Bedingungen übereinstimmen, werden ignoriert. Wenn Sie beispielsweise eine andere Spalte in Ihrer Tabellendatei (CSV/XLS) als **path**, **template**, **title**, und **description** in Ihrer -Datei werden diese Felder ignoriert. Und **Projekt-Importer** überprüft diese zusätzlichen Felder nicht, um Ihr Projekt in Ihr AEM Screens-Projekt zu importieren.

## Verwenden des Projekt-Importers {#using-project-importer}

Im folgenden Abschnitt wird beschrieben, wie der Projekt-Importer in einem AEM Screens-Projekt verwendet wird.

>[!CAUTION]
>
>Beschränkungen:
>
>* Andere Dateien als CSV/XLS/XLSX-Erweiterungen werden in der aktuellen Version nicht unterstützt.
>* Für importierte Dateien gibt es keine Filterung der Eigenschaften und es wird alles importiert, was mit „./&quot; importiert.
>

### Voraussetzungen {#prerequisites}

* Erstellen Sie ein Projekt mit dem Titel **DemoProjectImport**

* Verwenden Sie eine CSV- oder Excel-Beispieldatei, die Sie importieren müssen.

Zu Demozwecken können Sie eine Excel-Datei aus dem folgenden Abschnitt herunterladen.

[Datei abrufen](assets/minimal-file.xls)

### Importieren der Datei mit den erforderlichen Mindestfeldern {#importing-the-file-with-minimum-required-fields}

Gehen Sie wie folgt vor, um eine Datei mit den erforderlichen Mindestfeldern in einen Standortordner zu importieren:

>[!NOTE]
>
>Das folgende Beispiel zeigt die vier Felder, die mindestens zum Importieren des Projekts erforderlich sind:

![screen_shot_2019-05-14at21523pm](assets/screen_shot_2019-05-14at21523pm.png)

1. Navigieren Sie zu Ihrem AEM Screens-Projekt (**DemoProjectImport**).

   ![screen_shot_2019-05-12at52651am](assets/screen_shot_2019-05-12at52651am.png)

1. Wählen Sie das Projekt &quot;DemoProjectImporter&quot;aus **>** Erstellen **>** Importverzeichnisse** aus der Seitenleiste.

   ![screen_shot_2019-05-12at52433am](assets/screen_shot_2019-05-12at52433am.png)

1. Die **Import** angezeigt. Wählen Sie die Datei für Ihr Projekt mit Standorten aus oder wählen Sie die Datei (***minimal-file.xls***), die Sie aus dem *Voraussetzungen* Abschnitt.

   Klicken Sie nach Auswahl der Datei auf **Weiter**.

   ![screen_shot_2019-05-15at113718am](assets/screen_shot_2019-05-15at113718am.png)

1. Überprüfen Sie den Inhalt der Datei (Standorte) im Importassistenten und klicken Sie auf **Importieren**.

   ![screen_shot_2019-05-12at53131am](assets/screen_shot_2019-05-12at53131am.png)

1. Daher können Sie jetzt alle in Ihr Projekt importierten Standorte anzeigen.

   ![screen_shot_2019-05-12at53450am](assets/screen_shot_2019-05-12at53450am.png)
