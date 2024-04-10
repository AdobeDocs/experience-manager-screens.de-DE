---
title: Aktivierung auf Asset-Ebene
description: Erfahren Sie, wie Sie ein bestimmtes Asset in einem Kanal für einen geplanten Zeitraum in der lokalen Zeitzone des Players aktivieren.
feature: Authoring Screens, Asset Level Activation
role: Admin, Developer
level: Intermediate
exl-id: a2f5b2cc-6797-4397-b49c-72175a2d2ef7
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '1460'
ht-degree: 54%

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
>To get access to this Feature Pack, you must contact Adobe Support and request access. When you have permission, you can download it from Package Share. -->

## Übersicht {#overview}

***Aktivierung auf Asset-Ebene*** Ermöglicht die Aktivierung eines bestimmten Assets in einem Kanal für einen geplanten Zeitraum in der lokalen Zeitzone des Players. Diese Funktion ist für Bilder, Videos, Übergänge, Seiten und eingebettete Kanäle (dynamisch oder statisch) verfügbar.

*Beispielsweise* soll eine Sonderaktion nur montags und mittwochs während der Happy Hour (14.00 bis 17.00 Uhr) angezeigt werden.

Mit der Funktion können Sie nicht nur Start- und Enddatum sowie -zeit, sondern auch ein Wiederholungsmuster angeben.

## Aktivierungsfenster {#single-event-playback}

Die Aktivierung auf der Asset-Ebene erfolgt durch Konfiguration der Registerkarte **Aktivierung** beim Zugriff auf die Eigenschaften eines Assets.

Gehen Sie wie folgt vor, um die Zeitplanung auf der Asset-Ebene durchzuführen:

1. Wählen Sie einen beliebigen Kanal aus und klicken Sie dann auf **Bearbeiten** in der Aktionsleiste aus.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

   >[!NOTE]
   >
   >Detaillierte Informationen zum
   >
   >* Erstellen eines Projekts finden Sie unter [Erstellen eines neuen Projekts](creating-a-screens-project.md).
   >* Erstellen von Inhalten und Hinzufügen zu einem Kanal finden Sie unter [Verwalten von Kanälen](managing-channels.md).

1. Auswählen **Bearbeiten** Sie können also den Kanaleditor öffnen und ein Asset auswählen, auf das Sie die Planung anwenden möchten.

   ![Bild](/help/user-guide/assets/asset-activation/asset-level2.png)

1. Wählen Sie das Asset aus und klicken Sie dann links oben **Konfigurieren von** (Schraubenschlüsselsymbol).

   Wählen Sie die **Aktivierung** Tabulator.

   ![image](/help/user-guide/assets/asset-activation/asset-level3.png)

1. Sie können das Datum mithilfe der Datumsauswahl über die Felder **Aktiv ab** und **Aktiv bis** angeben.

   Wenn Sie die **Aktives Formular** und **Aktiv bis** Datum und Uhrzeit, wird das Asset nur zwischen dem Startdatum/der Startzeit und dem Enddatum/der Endzeit angezeigt und in einer Schleife dargestellt.

   ![Bild](/help/user-guide/assets/asset-activation/asset-level3.png)

## Umgang mit sich wiederholenden Assets {#handling-recurrence-in-assets}

Sie können eine Wiederholung von Assets Ihren Anforderungen entsprechend in bestimmten Intervallen auf Tages-, Wochen- oder Monatsbasis planen.

Angenommen, Sie möchten ein Bild nur freitags von 13:00 bis 22:00 Uhr anzeigen. Auf der Registerkarte **Aktivierung** können Sie das gewünschte Wiederholungsintervall für Ihr Asset festlegen.

### DayParting {#day-parting}

1. Wählen Sie das Asset aus und klicken Sie auf **Konfigurieren von** (Schraubenschlüsselsymbol), um das Dialogfeld „Eigenschaften“ zu öffnen.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und Ihr Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielausdrücke für die DayParting {#example-one}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben |
| nach 14:00 Uhr | Das Asset im Kanal wird jeden Tag nach 14:00 Uhr wiedergegeben |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich nach 12:15 Uhr für 30 Minuten wiedergegeben |
| vor 12:15 Uhr auch nach 12:45 Uhr | Das Asset im Kanal wird täglich vor 12:15 Uhr und dann auch nach 12:45 Uhr wiedergegeben. |

>[!NOTE]
>
>Sie können auch Folgendes verwenden _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M.* (14:00 UHR)

### WeekParting {#week-parting}

1. Wählen Sie das Asset aus und klicken Sie auf **Konfigurieren von** (Schraubenschlüsselsymbol).

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und das Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielhafte Ausdrücke für WeekParting {#example-two}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| `Mon,Wed,Fri` | Das Asset wird montags, mittwochs und freitags im Kanal von wiedergegeben |
| `Mon-Thu` | Das Asset im Kanal wird von montags bis donnerstags wiedergegeben. |

>[!NOTE]
>
>Sie können auch Folgendes verwenden _Voll_ Notation (`Monday,Wednesday,Friday`) anstelle von _kurzhändig_ (`Mon,Wed,Fri`).


### MonthParting {#month-parting}

1. Wählen Sie das Asset aus und klicken Sie auf **Konfigurieren von** (Schraubenschlüsselsymbol).

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und das Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielhafte Ausdrücke für MonthParting {#example-three}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| `on February,May,August,November` | Das Asset wird im Februar, Mai, August und November im Kanal wiedergegeben |
| `on February-July` | Das Asset wird von Februar bis Ende Juli im Kanal wiedergegeben |

>[!NOTE]
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Kurz- als auch die Vollnamennotation verwenden, z. B. Mo/Montag und Jan/Januar.

### Kombination von Aufteilungen {#combined-parting}

1. Wählen Sie das Asset aus und klicken Sie auf **Konfigurieren von** (Schraubenschlüsselsymbol).

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und das Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielausdrücke für die Kombination von Aufteilungen {#example-four}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| `after 6:00 and before 18:00 on Mon,Wed of Jan-Mar` | Das Asset im Kanal wird montags bis mittwochs von Januar bis Ende März zwischen 6 Uhr und 18 Uhr und mittwochs wiedergegeben. |
| `on the 1st day of January after 2:00 P.M. also on the 2nd day of January also on the 3rd day of January before 3:00 A.M.` | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr wiedergegeben und läuft am 2. Januar den ganzen Tag bis zum 3. Januar um 3:00 Uhr weiter |
| `on the 1-2 days of January after 2:00 P.M. also on the 2-3 days of January before 3:00 A.M.` | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. Dann wird es am 2. Januar um 14:00 Uhr erneut gestartet und bis zum 3. Januar um 3:00 Uhr wiedergegeben |

>[!NOTE]
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Kurz- als auch die Vollnamennotation verwenden, z. B. Mo/Montag und Jan/Januar. Außerdem können Sie Folgendes verwenden _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M.*(14:00 UHR)


## Aktivierung für mehrere Assets {#multi-asset-scheduling}

<!--
>[!CAUTION]
>
>The **Multi-asset Activation** feature is only available if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3. -->

***Aktivierung für mehrere Assets*** Ermöglicht Benutzenden die Auswahl mehrerer Assets und die Anwendung eines Wiedergabezeitplans auf alle ausgewählten Assets.

### Voraussetzungen {#prerequisites}

Um die Aktivierung für mehrere Assets zu verwenden, erstellen Sie ein AEM Screens-Projekt mit einem Sequenzkanal. Im folgenden Anwendungsbeispiel wird die Implementierung der Funktion veranschaulicht:

* Erstellen Sie ein AEM Screens-Projekt mit dem Titel **MultiAssetDemo**.
* Erstellen Sie einen Kanal mit dem Titel **MultiAssetChannel** und fügen Sie dem Kanal Inhalte hinzu, wie in der folgenden Abbildung dargestellt.

![screen_shot_2018-12-21at70128am](assets/screen_shot_2018-12-21at70128am.png)

Gehen Sie wie folgt vor, um mehrere Assets auszuwählen und ihre Anzeige in einem AEM Screens-Projekt zu planen:

1. Auswählen **MultiAssetChannel** und wählen Sie dann **Bearbeiten** in der Aktionsleiste aus.

   ![screen_shot_2018-12-21at70313am](assets/screen_shot_2018-12-21at70313am.png)

1. Wählen Sie im Editor mehrere Assets aus und klicken Sie dann auf **Aktivierung bearbeiten** (Symbol oben links).

   ![screen_shot_2018-12-21at70550am](assets/screen_shot_2018-12-21at70550am.png)

1. Wählen Sie Datum und Uhrzeit in **Aktiv ab** und **Aktiv bis** im Dialogfeld **Komponentenaktivierung** aus. Wählen Sie das Häkchensymbol aus, wenn Sie mit der Auswahl der Zeitpläne fertig sind.

   ![screen_shot_2018-12-17at20337pm](assets/screen_shot_2018-12-17at20337pm.png)

1. Wählen Sie Aktualisieren aus, um die Assets zu überprüfen, auf die der Zeitplan für mehrere Assets angewendet wird.

   >[!NOTE]
   >
   >Das Zeitplansymbol wird in der oberen rechten Ecke für die Assets angezeigt, die über eine Aktivierung mit mehreren Assets verfügen.

   ![screen_shot_2018-12-21at70722am](assets/screen_shot_2018-12-21at70722am.png)

## Globale Überschreibung für universelle Startzeit {#global-override-scheduling}

***Globale Überschreibung für universelle Startzeit*** ist eine Einstellung, mit der der Inhaltsautor die Wiedergabe eines Bild- oder Video-Assets basierend auf einer bestimmten Zeit definieren kann. Die Zeit-/Zeitzoneneinstellung eines einzelnen Players wird nicht verwendet.

Normalerweise wird die Wiedergabe von der lokalen Zeit eines bestimmten Players bestimmt; mit der globalen Überschreibung kann aber eine bestimmte universelle Startzeit verwendet werden, um die Wiedergabe des Assets zu starten.

Damit kann der Inhaltsautor festlegen, dass die Wiedergabe eines bestimmten Assets zu einem bestimmten Datum/zu einer bestimmten Uhrzeit erfolgt, unabhängig von der lokalen Uhr auf allen Playern, denen der Inhalt zugewiesen wurde.

Die globale Überschreibung der universellen Startzeit erfolgt durch Konfiguration der Registerkarte **Aktivierung**, während auf die Eigenschaften eines Assets zugegriffen wird. Um eine globale Überschreibung für die Asset-Planung durchzuführen, gehen Sie wie folgt vor:

1. Wählen Sie einen beliebigen Kanal aus und klicken Sie dann auf **Bearbeiten** über die Aktionsleiste aus, damit Sie Inhalte in Ihrem Kanal hinzufügen oder bearbeiten können.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

1. Wählen Sie **Bearbeiten** aus.
1. Wählen Sie im Kanaleditor ein Asset aus, dessen Zeitplan Sie auf das Asset anwenden möchten.

   ![screen_shot_2018-12-21at70550am](/help/user-guide/assets/asset-activation/Asset-level4.png)

1. Für eine globale Überschreibung geben Sie die Aktivierungszeit in das Feld **Zeitzonen-Überschreibung** -Abschnitt für das Asset. Wenn Sie in diesem Bereich nichts eingeben, wird die Zeitzone des Players angewendet.


