---
title: Importer für neue Projekte aus Datei
description: Mit dieser Funktion können Sie eine Reihe von Speicherorten aus einer CSV/XLS-Tabelle per Massenimport in Ihr AEM Screens-Projekt importieren.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
docset: aem65
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3bff9ef3-0d6f-41d8-a8ef-bcc5a795990e
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 50%

---

# Importer für neue Projekte aus Datei {#new-project-importer-from-file}

In diesem Abschnitt wird eine Funktionalität beschrieben, mit der Sie verschiedene Standorte aus einer CSV/XLS-Tabelle per Massenimport in Ihr AEM Screens-Projekt importieren können.

## Einführung {#introduction}

Wenn Sie ein AEM Screens-Projekt zum ersten Mal in Ihrem Unternehmen einrichten, müssen Sie auch alle Standorte erstellen. Wenn Ihr Projekt viele Standorte umfasst, führt dies zu einer mühsamen Aufgabe, die viele Klicks und Wartezeiten in der Benutzeroberfläche erfordert.

Das Ziel dieser Funktion ist es, die Zeit für die Einrichtung des Projekts zu reduzieren und somit Budgetierungsprobleme zu lösen.

Diese Funktion ermöglicht es dem Autor, eine Tabelle als Eingabedatei bereitzustellen und das System automatisch die Standortstruktur im Back-End erstellen zu lassen:

* *Erreicht eine deutlich bessere Leistung als das manuelle Klicken über die Benutzeroberfläche*
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

Die Tabellenkalkulationsdatei (CSV/XLS) erfordert daher die folgenden Spalten:

* **Pfad {string}** - Der Pfad für den zu importierenden Speicherort, wobei der Stamm des Pfads der Speicherort-Ordner für das Projekt ist (d. h. *`/foo`* wird in importiert *`/content/screens/<project>/locations/foo`*)
* **Schablone {string}** - Die Vorlage, die für den neuen Speicherort verwendet werden soll. Derzeit ist der einzige zulässige Wert „location„, dieser wird jedoch in Zukunft auf alle Screens-Vorlagen erweitert (`display`, `sequencechannel`usw.)
* **[./*] {string}** - Jede optionale Eigenschaft, die für den Speicherort festgelegt werden soll (d. h. `./jcr:title`, `./jcr:description`, `./foo, ./bar`). In der aktuellen Version ist keine Filterung zulässig.

>[!NOTE]
>
>Jede Spalte, die nicht den oben genannten Bedingungen entspricht, wird ignoriert. Wenn Sie beispielsweise eine andere Spalte in Ihrer Tabellendatei (CSV/XLS) definiert haben als **Pfad**, **Schablone**, **Anrede**, und **Beschreibung** In Ihrer Datei werden diese Felder ignoriert. und **Projekt-Import-Tool** Validiert diese zusätzlichen Felder nicht für den Import Ihres Projekts in Ihr AEM Screens-Projekt.

## Verwenden des Projekt-Importers {#using-project-importer}

Im folgenden Abschnitt wird beschrieben, wie der Projekt-Importer in einem AEM Screens-Projekt verwendet wird.

>[!CAUTION]
>
>Beschränkungen:
>
>* Andere Dateien als CSV/XLS/XLSX-Erweiterungen werden in der aktuellen Version nicht unterstützt.
>* Für importierte Dateien gibt es keine Filterung der Eigenschaften und es wird alles importiert, was mit „./“ importiert.
>

### Voraussetzungen {#prerequisites}

* Erstellen Sie ein Projekt mit dem Titel **DemoProjectImport**

* Verwenden Sie eine CSV- oder Excel-Beispieldatei, die Sie importieren müssen.

Zu Demozwecken können Sie eine Excel-Datei aus dem folgenden Abschnitt herunterladen.

[Datei abrufen](assets/minimal-file.xls)

### Importieren der Datei mit den erforderlichen Mindestfeldern {#importing-the-file-with-minimum-required-fields}

Gehen Sie wie folgt vor, um eine Datei in einen Speicherort-Ordner mit mindestens erforderlichen Feldern zu importieren:

>[!NOTE]
>
>Das folgende Beispiel zeigt die vier Felder, die mindestens zum Importieren des Projekts erforderlich sind:

![screen_shot_2019-05-14at21523pm](assets/screen_shot_2019-05-14at21523pm.png)

1. Navigieren Sie zu Ihrem AEM Screens-Projekt (**DemoProjectImport**).

   ![screen_shot_2019-05-12at52651am](assets/screen_shot_2019-05-12at52651am.png)

1. Wählen Sie das Projekt aus** DemoProjectImporter **>** Erstellen **>** Importieren Sie Standorte** aus der Seitenleiste.

   ![screen_shot_2019-05-12at52433am](assets/screen_shot_2019-05-12at52433am.png)

1. Die **importieren** Der Assistent wird angezeigt. Wählen Sie die Datei für Ihr Projekt mit Speicherorten aus oder wählen Sie die Datei (***minimal-file.xls***), die Sie von der *Voraussetzungen* -Abschnitt.

   Klicken Sie nach Auswahl der Datei auf **Weiter**.

   ![screen_shot_2019-05-15at113718am](assets/screen_shot_2019-05-15at113718am.png)

1. Überprüfen Sie den Inhalt der Datei (Standorte) im Importassistenten und klicken Sie auf **Importieren**.

   ![screen_shot_2019-05-12at53131am](assets/screen_shot_2019-05-12at53131am.png)

1. Dadurch können Sie jetzt alle in Ihr Projekt importierten Speicherorte anzeigen.

   ![screen_shot_2019-05-12at53450am](assets/screen_shot_2019-05-12at53450am.png)
