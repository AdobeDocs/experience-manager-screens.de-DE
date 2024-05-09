---
title: Aktivierung auf Asset-Ebene
description: Erfahren Sie, wie Sie ein bestimmtes Asset in einem Kanal für einen geplanten Zeitraum aktivieren, und zwar innerhalb der lokalen Zeitzone des Players.
feature: Authoring Screens, Asset Level Activation
role: Admin, Developer
level: Intermediate
exl-id: a2f5b2cc-6797-4397-b49c-72175a2d2ef7
source-git-commit: e82cfee5ecc6b639b7b2b65553d1635943b356ea
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 32%

---

# Aktivierung auf Asset-Ebene {#asset-level-scheduling}

Auf dieser Seite wird die Aktivierung auf der Asset-Ebene für die in Kanälen verwendeten Assets beschrieben.

In diesem Abschnitt werden die folgenden Themen behandelt:

* Überblick
* Aktivierungsfenster
* Wiedergabe eines einzelnen Ereignisses
* Umgang mit sich wiederholenden Assets
   * Dayparting
   * WeekParting
   * MonthParting
   * Kombination von Aufteilungen
* Aktivierung für mehrere Assets
* Globale Überschreibung für universelle Startzeit

<!-- REFERS TO ARCHIVED VERSIONS THAT ADOBE NO LONGER SUPPORTS>
>[!CAUTION]
>
>This AEM Screens functionality is only available if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. When you have permission, you can download it from Package Share. -->

## Überblick {#overview}

***Aktivierung auf Asset-Ebene*** ermöglicht Ihnen, ein bestimmtes Asset in einem Kanal für einen geplanten Zeitraum zu aktivieren, und zwar innerhalb der lokalen Zeitzone des Players. Diese Funktion ist für Bilder, Videos, Transitionen, Seiten und eingebettete Kanäle (dynamisch oder statisch) verfügbar.

*Beispielsweise* soll eine Sonderaktion nur montags und mittwochs während der Happy Hour (14.00 bis 17.00 Uhr) angezeigt werden.

Mit dieser Funktion können Sie nicht nur ein Start- und Enddatum und eine Endzeit, sondern auch ein Wiederholungsmuster angeben.

## Aktivierungsfenster {#single-event-playback}

Die Aktivierung auf der Asset-Ebene erfolgt durch Konfiguration der **Aktivierung** Registerkarte beim Zugriff auf die Eigenschaften eines Assets.

Gehen Sie wie folgt vor, um die Zeitplanung auf der Asset-Ebene durchzuführen:

1. Klicken Sie auf einen beliebigen Kanal und dann auf **Bearbeiten** in der Aktionsleiste aus.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

   >[!NOTE]
   >
   >Detaillierte Informationen zum
   >
   >* Erstellen Sie ein Projekt. Siehe [Erstellen eines neuen Projekts](creating-a-screens-project.md).
   >* Erstellen und Hinzufügen von Inhalten zu einem Kanal Siehe [Kanäle verwalten](managing-channels.md).

1. Klicks **Bearbeiten** Sie können den Kanaleditor öffnen und auf ein Asset klicken, auf das Sie die Planung anwenden möchten.

   ![Bild](/help/user-guide/assets/asset-activation/asset-level2.png)

1. Klicken Sie auf das Asset und dann oben links auf **Konfigurieren** (Schraubenschlüsselsymbol).

   Klicken Sie auf die Registerkarte **Aktivierung**.

   ![image](/help/user-guide/assets/asset-activation/asset-level3.png)

1. Sie können das Datum mithilfe der Datumsauswahl über die Felder **Aktiv ab** und **Aktiv bis** angeben.

   Wenn Sie auf die **Aktiv ab** und **Aktiv bis** Datum und Uhrzeit, wird das Asset nur zwischen Startdatum/Startzeit bzw. Enddatum/Endzeit angezeigt bzw. wiederholt.

   ![Bild](/help/user-guide/assets/asset-activation/asset-level3.png)

## Umgang mit sich wiederholenden Assets {#handling-recurrence-in-assets}

Sie können planen, dass Assets gemäß Ihren Anforderungen in bestimmten Intervallen täglich, wöchentlich oder monatlich wiederholt werden.

Angenommen, Sie möchten ein Bild nur freitags von 13:00 Uhr bis 22:00 Uhr anzeigen. Auf der Registerkarte **Aktivierung** können Sie das gewünschte Wiederholungsintervall für Ihr Asset festlegen.

### DayParting {#day-parting}

1. Klicken Sie auf das Asset und klicken Sie auf **Konfigurieren** (Schraubenschlüsselsymbol), um das Dialogfeld &quot;Eigenschaften&quot;zu öffnen.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in die **Zeitplan** und Ihr Asset für das jeweilige Tages- und Uhrzeitintervall angezeigt wird.

#### Beispielausdrücke für die DayParting {#example-one}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben |
| nach 14:00 Uhr. | Das Asset im Kanal wird täglich nach 14:00 Uhr wiedergegeben |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich 30 Minuten lang nach 12:15 Uhr wiedergegeben. |
| vor 12:15 Uhr auch nach 12:45 Uhr | Das Asset im Kanal wird täglich vor 12:15 Uhr und danach auch nach 12:45 Uhr wiedergegeben. |

>[!NOTE]
>
>Sie können auch _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M* (14:00 Uhr).

### WeekParting {#week-parting}

1. Klicken Sie auf das Asset und dann auf **Konfigurieren** (Schraubenschlüsselsymbol).

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in die **Zeitplan** und Ihr Asset für das jeweilige Tages- und Uhrzeitintervall angezeigt wird.

#### Beispielhafte Ausdrücke für WeekParting {#example-two}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| `Mon,Wed,Fri` | Das Asset im Kanal wird montags, mittwochs und freitags wiedergegeben. |
| `Mon-Thu` | Das Asset im Kanal wird von montags bis donnerstags wiedergegeben. |

>[!NOTE]
>
>Sie können auch _full_ notation (`Monday,Wednesday,Friday`) anstelle von _kurze_ (`Mon,Wed,Fri`).


### MonthParting {#month-parting}

1. Klicken Sie auf das Asset und dann auf **Konfigurieren** (Schraubenschlüsselsymbol).

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in die **Zeitplan** und Ihr Asset für das jeweilige Tages- und Uhrzeitintervall angezeigt wird.

#### Beispielhafte Ausdrücke für MonthParting {#example-three}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| `on February,May,August,November` | Das Asset im Kanal wird im Februar, Mai, August und November wiedergegeben. |
| `on February-July` | Das Asset im Kanal wird von Februar bis Ende Juli wiedergegeben. |

>[!NOTE]
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Abkürzung als auch die vollständige Bezeichnung verwenden, z. B. &quot;Mo.&quot;/&quot;Montag&quot;und &quot;Jan.&quot;/&quot;Januar&quot;.

### Kombination von Aufteilungen {#combined-parting}

1. Klicken Sie auf das Asset und dann auf **Konfigurieren** (Schraubenschlüsselsymbol).

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in die **Zeitplan** und Ihr Asset für das jeweilige Tages- und Uhrzeitintervall angezeigt wird.

#### Beispielausdrücke für die Kombination von Aufteilungen {#example-four}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| `after 6:00 and before 18:00 on Mon,Wed of Jan-Mar` | Das Asset im Kanal wird montags bis mittwochs von Januar bis Ende März zwischen 6 Uhr und 18 Uhr und mittwochs wiedergegeben. |
| `on the 1st day of January after 2:00 P.M. also on the 2nd day of January also on the 3rd day of January before 3:00 A.M.` | Die Wiedergabe des Assets im Kanal beginnt am 1. Januar um 14:00 Uhr und läuft den ganzen Tag am 2. Januar bis 3:00 Uhr am 3. Januar |
| `on the 1-2 days of January after 2:00 P.M. also on the 2-3 days of January before 3:00 A.M.` | Das Asset im Kanal startet den Player am 1. Januar um 14:00 Uhr, läuft bis 2. Januar um 3:00 Uhr und beginnt dann am 2. Januar um 2:00 Uhr und läuft bis 3:00 Uhr am 3. Januar |

>[!NOTE]
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Abkürzung als auch die vollständige Bezeichnung verwenden, z. B. &quot;Mo.&quot;/&quot;Montag&quot;und &quot;Jan.&quot;/&quot;Januar&quot;. Sie können auch _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M*(14:00 Uhr).


## Aktivierung für mehrere Assets {#multi-asset-scheduling}

<!--
>[!CAUTION]
>
>The **Multi-asset Activation** feature is only available if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3. -->

***Aktivierung für mehrere Assets*** ermöglicht dem Benutzer das Klicken auf mehrere Assets und das Anwenden eines Wiedergabezeitplans auf alle ausgewählten Assets.

### Voraussetzungen {#prerequisites}

Um die Aktivierung für mehrere Assets zu verwenden, erstellen Sie ein AEM Screens-Projekt mit einem Sequenzkanal. Im folgenden Anwendungsbeispiel wird die Implementierung der Funktion veranschaulicht:

* Erstellen Sie ein AEM Screens-Projekt mit dem Titel **MultiAssetDemo**.
* Erstellen Sie einen Kanal mit dem Titel **MultiAssetChannel** und fügen Sie dem Kanal Inhalte hinzu, wie in der folgenden Abbildung dargestellt.

![screen_shot_2018-12-21at70128am](assets/screen_shot_2018-12-21at70128am.png)

Gehen Sie wie folgt vor, um auf mehrere Assets zu klicken und ihre Anzeige in einem AEM Screens-Projekt zu planen:

1. Klicks **MultiAssetChannel** Klicken Sie auf **Bearbeiten** in der Aktionsleiste aus.

   ![screen_shot_2018-12-21at70313am](assets/screen_shot_2018-12-21at70313am.png)

1. Klicken Sie im Editor auf mehrere Assets und dann auf **Aktivierung bearbeiten** (Symbol oben links).

   ![screen_shot_2018-12-21at70550am](assets/screen_shot_2018-12-21at70550am.png)

1. Klicken Sie auf Datum und Uhrzeit in **Aktiv ab** und **Aktiv bis** aus dem **Komponentenaktivierung** Dialogfeld. Klicken Sie auf das Häkchen, nachdem Sie die Zeitpläne ausgewählt haben.

   ![screen_shot_2018-12-17at20337pm](assets/screen_shot_2018-12-17at20337pm.png)

1. Klicken Sie auf Aktualisieren , um die Assets zu überprüfen, auf die der Multi-Asset-Zeitplan angewendet wird.

   >[!NOTE]
   >
   >Das Zeitplansymbol wird in der oberen rechten Ecke für Assets angezeigt, die eine Aktivierung für mehrere Assets aufweisen.

   ![screen_shot_2018-12-21at70722am](assets/screen_shot_2018-12-21at70722am.png)

## Globale Überschreibung für universelle Startzeit {#global-override-scheduling}

***Globale Überschreibung für universelle Startzeit*** ist eine Einstellung, mit der der Inhaltsautor die Wiedergabe eines Bild- oder Video-Assets basierend auf einer bestimmten Zeit definieren kann. Die Zeit-/Zeitzoneneinstellung eines einzelnen Players wird nicht verwendet.

Normalerweise bestimmt die lokale Zeit eines bestimmten Players die Wiedergabe. Mit der globalen Außerkraftsetzung kann jedoch eine bestimmte universelle Startzeit verwendet werden, um die Wiedergabe des Assets zu starten.

Daher kann der Inhaltsautor die Wiedergabe eines bestimmten Assets festlegen. Sie können sie unabhängig von der lokalen Uhr auf allen Playern mit zugewiesenem Inhalt zu einem bestimmten Datum/zu einer bestimmten Uhrzeit ausführen lassen.

***Globale Überschreibung für universelle Startzeit*** wird durch die Konfiguration der **Aktivierung** Registerkarte beim Zugriff auf die Eigenschaften eines Assets. Um eine globale Überschreibung für die Asset-Planung durchzuführen, gehen Sie wie folgt vor:

1. Klicken Sie auf einen beliebigen Kanal und dann auf **Bearbeiten** über die Aktionsleiste aus, damit Sie Inhalte in Ihrem Kanal hinzufügen oder bearbeiten können.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

1. Klicken Sie auf **Bearbeiten**.
1. Klicken Sie im Kanaleditor auf ein Asset, dessen Zeitplan Sie darauf anwenden möchten.

   ![screen_shot_2018-12-21at70550am](/help/user-guide/assets/asset-activation/Asset-level4.png)

1. Geben Sie für eine globale Überschreibung die Aktivierungszeit in das Feld **Zeitzonen-Überschreibung** für das Asset. Wenn Sie in diesem Bereich nichts eingeben, wird die Zeitzone des Players angewendet.


