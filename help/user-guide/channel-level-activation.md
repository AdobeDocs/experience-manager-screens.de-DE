---
title: Aktivierung auf Kanalebene – Wiedergabe eines einzelnen Ereignisses
description: Erfahren Sie mehr über die Aktivierung auf Kanalebene durch Wiedergabe eines einzelnen Ereignisses.
topic-tags: authoring
feature: Authoring Screens, Channels
role: Admin, Developer
level: Intermediate
exl-id: 51a63429-2488-45be-b8f5-cb755ca69c7f
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: tm+mt
source-wordcount: '1791'
ht-degree: 71%

---

# Aktivierung auf Kanalebene {#channel-level-activation-single-event-playback}

Auf dieser Seite wird die Aktivierung auf Kanalebene für die in Kanälen verwendeten Assets beschrieben.

In diesem Abschnitt werden die folgenden Themen behandelt:

* Überblick
* Aktivierungsfenster
* Verwenden der Aktivierung auf Kanalebene als Wiedergabe eines einzelnen Ereignisses
* Umgang mit sich wiederholenden Assets in einem Kanal
   * Dayparting
   * WeekParting
   * MonthParting
   * Kombination von Aufteilungen
* Verwenden der Aktivierung auf Kanalebene als Wiedergabe eines einzelnen Ereignisses

## Überblick {#overview}

Die ***Aktivierung auf Kanalebene*** ermöglicht den Wechsel von Kanälen nach einem festgelegten Zeitplan. Der Kanal für ein einzelnes Ereignis ersetzt den Hauptkanal nach einem festgelegten Zeitplan und spielt für eine bestimmte Zeit, bis der Hauptkanal seinen Inhalt wiedergibt.

Das folgende Beispiel zeigt eine Lösung mit Konzentration auf die folgenden Schlüsselbegriffe:

* einen ***Hauptsequenzkanal*** für die globale Sequenz
* einen ***Kanal für ein einzelnes Ereignis***, der nur einmal zur festgelegten Zeit ausgeführt wird
* einen ***festgelegten Zeitplan und eine Priorität*** für die einzelne Wiedergabe des Ereignisses, die innerhalb des Hauptsequenzkanals erfolgt

## Aktivierungsfenster {#using-channel-level-activation}

Im folgenden Abschnitt wird die Erstellung der Wiedergabe eines einzelnen Ereignisses innerhalb eines Kanals für ein AEM Screens-Projekt erläutert.

### Voraussetzungen {#prerequisites}

Bevor Sie diese Funktionalität implementieren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen, um mit der Implementierung der Aktivierung auf Kanalebene beginnen zu können:

* Erstellen eines AEM Screens-Projekts, in diesem Beispiel **Aktivierung auf Kanalebene**.

* Erstellen eines Kanals als **MainAdChannel** unter **Kanäle** Ordner.

* Erstellen Sie einen weiteren Kanal als **TargetedSinglePlay** unter **Kanäle** Ordner.

* Fügen Sie relevante Assets zu beiden Kanälen hinzu.

Die folgende Abbildung zeigt die **Aktivierung auf Kanalebene** Projekt mit **MainAdChannel** und **TargetedSinglePlay** Kanäle in **Kanäle** Ordner.

![screen_shot_2018-11-27at104500am](assets/screen_shot_2018-11-27at104500am.png)

>[!NOTE]
>
>Weitere Informationen zum Erstellen eines Projekts und zum Erstellen eines Sequenzkanals finden Sie in den folgenden Ressourcen:
>
>* [Erstellen und Verwalten von Projekten](creating-a-screens-project.md)
>
>* [Verwalten eines Kanals](managing-channels.md)
>

### Implementierung {#implementation}

Die Implementierung der Aktivierung auf Kanalebene in einem AEM Screens-Projekt umfasst drei Hauptaufgaben:

1. **Einrichten des Klassifikationsschemas des Projekts, einschließlich Kanälen, Standorten und Anzeigen**
1. **Zuweisen anzuzeigender Kanäle**
1. **Konfigurieren eines Zeitplan und einer Priorität**

Gehen Sie wie folgt vor, um die Funktion zu implementieren:

1. **Erstellen eines Standorts**

   Navigieren Sie zum Ordner **Standorte** in Ihrem AEM Screens-Projekt und erstellen Sie einen Standort als **Region**.

   ![screen_shot_2018-11-27at112112am](assets/screen_shot_2018-11-27at112112am.png)

   >[!NOTE]
   >
   >Informationen zum Erstellen eines Standorts finden Sie unter **[Erstellen und Verwalten von Standorten](managing-locations.md)**.

1. **Erstellen einer Anzeige unter dem Standort**

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region**.
   1. Klicks **Region** und klicken **+ Erstellen** in der Aktionsleiste aus.
   1. Klicks **Anzeige** aus dem Assistenten erstellen und eine Anzeige mit dem Titel **RegionDisplay.**

   ![screen_shot_2018-11-27at112216am](assets/screen_shot_2018-11-27at112216am.png)

1. **Zuweisen anzuzeigender Kanäle**

   Für **MainAdChannel:**

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.
   1. Im **Kanalzuweisung** Dialogfeld, klicken Sie auf **Referenzkanal** nach Pfad.
   1. Klicken Sie auf **Kanalpfad** Klicken Sie auf **Aktivierung auf Kanalebene** > ***Kanäle*** > ***MainAdChannel***.
   1. Die **Kanalrolle** wird mit **mainadchannel** ausgefüllt.
   1. Klicken Sie auf **Priorität** und auf **1**.
   1. Klicken Sie auf **Unterstützte Ereignisse** wie **Erster Ladevorgang** und **Idle Screen**.
   1. Klicken Sie auf **Speichern**.

   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   >
   >Sie können den Kanal auch über das Anzeigen-Dashboard zuweisen. Navigieren Sie zu **Aktivierung auf Kanalebene** > **Standorte** > **Region** > **RegionDisplay**. Wählen Sie in der Aktionsleiste die Option **Dashboard**. Aus dem **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** Bereich, klicken Sie **+ Kanal zuweisen**.

   Weisen Sie den Kanal **TargetedSinglePlay** für die Anzeige zu:

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.
   1. Im **Kanalzuweisung** Dialogfeld, klicken Sie auf **Referenzkanal** nach Pfad.
   1. Klicken Sie auf **Kanalpfad** Klicken Sie auf **Aktivierung auf Kanalebene** > ***Kanäle*** > ***TargetedSinglePlay***.
   1. Die **Kanalrolle** wird mit **targetedsingleplay** ausgefüllt.
   1. Legen Sie die **Priorität** nach **2**.
   1. Klicken Sie auf **Unterstützte Ereignisse** und legen **Erster Ladevorgang**, **Idle Screen**, und **Timer**, wie in der folgenden Abbildung dargestellt.
   1. In **aktiv aus**, festgelegt als 27. November 2018, 11:59 Uhr und in **aktiv bis**, festgelegt als 28. November 2018, 12:05 Uhr
   1. Klicken Sie auf **Speichern**.

   >[!CAUTION]
   >
   >Legen Sie die Priorität für die **TargetedSinglePlay** Kanal höher als **MainAdSegment** -Kanal.

   ![screen_shot_2018-11-27at31206pm](assets/screen_shot_2018-11-27at31206pm.png)

   >[!NOTE]
   >
   >Um denselben Tag auszuwählen, klicken Sie auf den nächsten Tag und bearbeiten Sie dann das Datum manuell auf den gleichen Tag, aber für einen späteren Zeitpunkt. Dadurch werden Benutzende daran gehindert, ein Datum in der Vergangenheit auszuwählen. Siehe folgendes Beispiel:

   ![new1](assets/new1.gif)

## Anzeigen der Ergebnisse {#viewing-the-results}

Wenn Sie die Einrichtung für Kanäle und die Anzeige abgeschlossen haben, starten Sie den AEM Screens-Player, um den Inhalt anzuzeigen.

Der Player zeigt den Inhalt von **MainAdChannel** an, und genau um 23:59 Uhr (wie im Zeitplan festgelegt) gibt der Kanal **TargetedSinglePlay** seinen Inhalt bis 00:05 Uhr wieder. Anschließend wird die **MainAdChannel**-Wiedergabe fortgesetzt.

>[!NOTE]
>
>Weitere Informationen zum AEM Screens-Player finden Sie unter:
>[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/) 
>[Arbeiten mit dem AEM Screens-Player](working-with-screens-player.md)


## Umgang mit sich wiederholenden Assets in einem Kanal {#handling-recurrence-in-assets}

Sie können planen, dass Assets in einem Kanal gemäß Ihren Anforderungen in bestimmten Intervallen täglich, wöchentlich oder monatlich wiederholt werden.

Angenommen, Sie möchten den Inhalt eines Kanals nur freitags von 13:00 Uhr bis 22:00 Uhr anzeigen. Auf der Registerkarte **Aktivierung** können Sie das gewünschte Wiederholungsintervall für Ihr Asset festlegen.

### DayParting {#day-parting}

1. Klicken Sie auf den Kanal und dann auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin im jeweiligen Tages- und Uhrzeitintervall angezeigt.

#### Beispielausdrücke für die DayParting {#example-one}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben. |
| nach 14:00 Uhr | Das Asset im Kanal wird täglich nach 14:00 Uhr wiedergegeben. |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich 30 Minuten lang nach 12:15 Uhr wiedergegeben. |
| vor 12:15 Uhr auch nach 12:45 Uhr | Das Asset im Kanal wird täglich vor 12:15 Uhr und danach auch nach 12:45 Uhr wiedergegeben. |
| Mo., Di., Mi. oder Mo.–Mi. | Das Asset im Kanal wird von Montag bis Mittwoch wiedergegeben. |
| am ersten Januar nach 14:00 Uhr, auch am zweiten Januar und am dritten Januar vor 3:00 Uhr. | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr und weiterhin den ganzen Tag am 2. Januar bis um 3:00 Uhr am 3. Januar wiedergegeben. |
| am 1./2. Januar nach 14:00 Uhr, auch am 2./3. Januar vor 3:00 Uhr | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. Dann wird es erneut vom 2. Januar um 14:00 Uhr bis zum 3. Januar um 3:00 Uhr wiedergegeben. |

>[!NOTE]
>
>Statt mit dem _24-Stunden-Format_ (z. B. 14:00 Uhr) kann die Zeit auch mit *A.M./P.M* (z. B. 2:00 P.M.) angegeben werden.

### WeekParting {#week-parting}

1. Klicken Sie auf den Kanal und dann auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin im jeweiligen Tages- und Uhrzeitintervall angezeigt.

#### Beispielhafte Ausdrücke für WeekParting {#example-two}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| Mo., Di., Mi. oder Mo.–Mi. | Das Asset im Kanal wird von Montag bis Mittwoch wiedergegeben. |
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben. |
| nach 14:00 Uhr | Das Asset im Kanal wird täglich nach 14:00 Uhr wiedergegeben. |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich 30 Minuten lang nach 12:15 Uhr wiedergegeben. |
| vor 12:15 Uhr auch nach 12:45 Uhr | Der Kanal wird täglich vor 12:15 Uhr und danach auch nach 12:45 Uhr wiedergegeben |

>[!NOTE]
>
>Statt mit dem _24-Stunden-Format_ (z. B. 14:00 Uhr) kann die Zeit auch mit *A.M./P.M* (z. B. 2:00 P.M.) angegeben werden.


### MonthParting {#month-parting}

1. Klicken Sie auf den Kanal und dann auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin im jeweiligen Tages- und Uhrzeitintervall angezeigt.

#### Beispielhafte Ausdrücke für MonthParting {#example-three}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| im `February,May,August,November` | Das Asset im Kanal wird im Februar, Mai, August und November wiedergegeben. |

>[!NOTE]
>
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Abkürzung als auch die vollständige Bezeichnung verwenden, beispielsweise „Mo.“/„Montag“ und „Jan.“/„Januar“.

>[!NOTE]
>
>Statt mit dem _24-Stunden-Format_ (z. B. 14:00 Uhr) kann die Zeit auch mit *A.M./P.M* (z. B. 2:00 P.M.) angegeben werden.

### Kombination von Aufteilungen {#combined-parting}

1. Klicken Sie auf den Kanal und dann auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin im jeweiligen Tages- und Uhrzeitintervall angezeigt.

#### Beispielausdrücke für die Kombination von Aufteilungen {#example-four}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| nach 6:00 und vor 18:00 Uhr am Mo., Mi. im Jan.–Mrz. | Das Asset im Kanal wird montags bis mittwochs von Januar bis Ende März zwischen 6 Uhr und 18 Uhr und mittwochs wiedergegeben. |
| am ersten Januar nach 14:00 Uhr, auch am zweiten Januar und am dritten Januar vor 3:00 Uhr. | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr und weiterhin den ganzen Tag am 2. Januar bis um 3:00 Uhr am 3. Januar wiedergegeben. |
| am 1./2. Januar nach 14:00 Uhr, auch am 2./3. Januar vor 3:00 Uhr | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. Dann wird es erneut vom 2. Januar um 14:00 Uhr bis zum 3. Januar um 3:00 Uhr wiedergegeben. |

>[!NOTE]
>
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Abkürzung als auch die vollständige Bezeichnung verwenden, beispielsweise „Mo.“/„Montag“ und „Jan.“/„Januar“. Statt mit dem _24-Stunden-Format_ (z. B. 14:00) kann die Zeit auch mit *A.M./P.M* (z. B. 2:00 P.M.) angegeben werden.
