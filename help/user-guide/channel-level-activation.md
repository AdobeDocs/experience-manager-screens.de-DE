---
title: Aktivierung auf Kanalebene – Wiedergabe eines einzelnen Ereignisses
seo-title: Aktivierung auf Kanalebene – Wiedergabe eines einzelnen Ereignisses
description: Befolgen Sie diese Anleitung, um die Aktivierung auf Kanalebene mithilfe der Wiedergabe eines einzelnen Ereignisses zu verstehen.
seo-description: Befolgen Sie diese Anleitung, um die Aktivierung auf Kanalebene mithilfe der Wiedergabe eines einzelnen Ereignisses zu verstehen.
uuid: 87230344-5f9a-42a4-a7a8-ae4203303612
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: c28fd669-f23e-4d53-bec1-a2911274567d
noindex: true
feature: Inhaltserstellung in Screens, Aktivierung auf Kanalebene
role: Administrator, Developer
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: ht
source-wordcount: '1807'
ht-degree: 100%

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

Bevor Sie mit der Implementierung dieser Funktionalität beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen, um mit der Implementierung der Aktivierung auf Kanalebene beginnen zu können:

* Erstellen eines AEM Screens-Projekts, in diesem Beispiel **Channel Level Activation**

* Erstellen eines Kanals als **MainAdChannel** im Ordner **Kanäle**

* Erstellen eines weiteren Kanals als **TargetedSinglePlay** im Ordner **Kanäle**

* Hinzufügen relevanter Assets zu beiden Kanälen

Die folgende Abbildung zeigt das Projekt **Channel Level Activation** mit den Kanälen **MainAdChannel** und **TargetedSinglePlay** im Ordner **Kanäle**.

![screen_shot_2018-11-27at104500am](assets/screen_shot_2018-11-27at104500am.png)

>[!NOTE]
>
>Weitere Infos zum Erstellen eines Projekts und zum Erstellen eines Sequenzkanals finden Sie in den folgenden Ressourcen:
>
>* [Erstellen und Verwalten von Projekten](creating-a-screens-project.md)

* [Verwalten eines Kanals](managing-channels.md)



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
   Informationen zum Erstellen eines Standorts finden Sie unter **[Erstellen und Verwalten von Standorten](managing-locations.md)**.

1. **Erstellen einer Anzeige unter dem Standort**

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region**.
   1. Wählen Sie **Region** aus und klicken Sie in der Aktionsleiste auf **+ Erstellen**.
   1. Wählen Sie im Assistenten die Option **Anzeigen** aus und erstellen Sie eine Anzeige mit dem Titel **RegionDisplay.**

   ![screen_shot_2018-11-27at112216am](assets/screen_shot_2018-11-27at112216am.png)

1. **Zuweisen anzuzeigender Kanäle**

   Für **MainAdChannel:**

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.
   1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.
   1. Wählen Sie als Vorgehensweise für **Kanal referenzieren** die Option „Pfad“ aus.
   1. Wählen Sie unter **Kanalpfad** den Wert **Channel Level Activation** > ***Kanäle*** > ***MainAdChannel*** aus.
   1. Die **Kanalrolle** wird mit **mainadchannel** ausgefüllt.
   1. Wählen Sie als **Priorität** den Wert **1** aus.
   1. Wählen Sie unter **Unterstützte Ereignisse** die Optionen **Erster Ladevorgang** und **Bildschirm bei Untätigkeit** aus.
   1. Klicken Sie auf **Speichern**.

   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   Sie können Kanäle auch über das Anzeigen-Dashboard zuweisen, indem Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** navigieren und in der Aktionsleiste auf **Dashboard** klicken. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+ Kanal zuweisen**.

   Weisen Sie den Kanal **TargetedSinglePlay** für die Anzeige zu:

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.
   1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.
   1. Wählen Sie als Vorgehensweise für **Kanal referenzieren** die Option „Pfad“ aus.
   1. Wählen Sie unter **Kanalpfad** den Wert **Channel Level Activation*** > ***Kanäle*** > ***TargetedSinglePlay*** aus.
   1. Die **Kanalrolle** wird mit **targetedsingleplay** ausgefüllt.
   1. Legen Sie die als **Priorität** den Wert **2** fest.
   1. Wählen Sie unter **Unterstützte Ereignisse** die Optionen **Erster Ladevorgang**, **Bildschirm bei Untätigkeit** und **Timer** aus, wie in der Abbildung unten gezeigt.
   1. Wählen Sie als Datum für **aktiv ab** den 27. November 2018, 23:59 Uhr und für **aktiv bis** den 28. November 2018, 00:05 Uhr aus.
   1. Klicken Sie auf **Speichern**.

   >[!CAUTION]
   Sie müssen die Priorität für den Kanal **TargetedSinglePlay** höher festlegen als für den Kanal **MainAdSegment**.

   ![screen_shot_2018-11-27at31206pm](assets/screen_shot_2018-11-27at31206pm.png)

   >[!NOTE]
   Um denselben Tag auszuwählen, müssen Sie den nächsten Tag auswählen und das Datum manuell auf denselben Tag, jedoch eine spätere Uhrzeit ändern. Dadurch wird der Benutzer daran gehindert, ein vergangenes Datum auszuwählen. Beachten Sie das folgende Beispiel:

   ![new1](assets/new1.gif)

## Anzeigen der Ergebnisse {#viewing-the-results}

Sobald Sie die Einrichtung für Kanäle und die Anzeige abgeschlossen haben, starten Sie den AEM Screens-Player, um den Inhalt anzuzeigen.

Der Player zeigt den Inhalt von **MainAdChannel** an und genau um 23:59 Uhr (wie im Zeitplan festgelegt) zeigt der Kanal **TargetedSinglePlay** seinen Inhalt bis 00:05 Uhr an. Anschließend wird die Wiedergabe des **MainAdChannel** fortgesetzt.

>[!NOTE]
Weitere Informationen zum AEM Screens-Player finden Sie in den folgenden Ressourcen:
[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/)
[Arbeiten mit dem AEM Screens-Player](working-with-screens-player.md)


## Umgang mit sich wiederholenden Assets in einem Kanal {#handling-recurrence-in-assets}

Sie können eine Wiederholung von Assets in einem Kanal Ihren Anforderungen entsprechend in bestimmten Intervallen auf Tages-, Wochen- oder Monatsbasis planen.

Angenommen, Sie möchten Inhalte eines Kanals nur freitags von 13:00 bis 22:00 Uhr anzeigen. Auf der Registerkarte **Aktivierung** können Sie das gewünschte Wiederholungsintervall für Ihr Asset festlegen.

### Tagesaufteilung {#day-parting}

1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Dashboard**, um das Kanal-Dashboard zu öffnen.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin für das jeweilige Tages- und Uhrzeitintervall angezeigt.

#### Beispielausdrücke für die Tagesaufteilung {#example-one}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben. |
| nach 14:00 Uhr | Das Asset im Kanal wird täglich nach 14:00 Uhr wiedergegeben. |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich 30 Minuten lang nach 12:15 Uhr wiedergegeben. |
| vor 12:15 Uhr auch nach 12:45 Uhr | Das Asset im Kanal wird täglich vor 12:15 Uhr und danach auch nach 12:45 Uhr wiedergegeben. |
| Mo., Di., Mi. oder Mo.–Mi. | Das Asset im Kanal wird von Montag bis Mittwoch wiedergegeben. |
| am 1. Januar nach 14:00 Uhr auch am 2. Januar, auch am 3. Januar vor 3:00 Uhr | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr und weiterhin den ganzen Tag am 2. Januar bis um 3:00 Uhr am 3. Januar wiedergegeben. |
| am 1./2. Januar nach 14:00 Uhr auch am 2./3. Januar vor 3:00 Uhr | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. Dann wird es erneut am 2. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. |

>[!NOTE]
Sie können das _24-Stunden-Format_ (d. h. 14:00 Uhr) oder die *am/pm*-Notation (d. h. 2:00 pm) verwenden.

### WeekParting {#week-parting}

1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Dashboard**, um das Kanal-Dashboard zu öffnen.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin für das jeweilige Tages- und Uhrzeitintervall angezeigt.

#### Beispielhafte Ausdrücke für WeekParting {#example-two}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| Mo., Di., Mi. oder Mo.–Mi. | Das Asset im Kanal wird von Montag bis Mittwoch wiedergegeben. |
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben. |
| nach 14:00 Uhr | Das Asset im Kanal wird täglich nach 14:00 Uhr wiedergegeben. |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich 30 Minuten lang nach 12:15 Uhr wiedergegeben. |
| vor 12:15 Uhr auch nach 12:45 Uhr | Der Kanal wird täglich vor 12:15 Uhr und danach auch nach 12:45 Uhr wiedergegeben |

>[!NOTE]
Sie können das _24-Stunden-Format_ (d. h. 14:00 Uhr) oder die *am/pm*-Notation (d. h. 2:00 pm) verwenden.


### MonthParting {#month-parting}

1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Dashboard**, um das Kanal-Dashboard zu öffnen.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin für das jeweilige Tages- und Uhrzeitintervall angezeigt.

#### Beispielhafte Ausdrücke für MonthParting {#example-three}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| Februar, Mai, August, November | Das Asset im Kanal wird im Februar, Mai, August, November wiedergegeben. |

>[!NOTE]
Bei der Definition von Wochentagen und Monaten können Sie sowohl die Abkürzung als auch die vollständige Bezeichnung verwenden, beispielsweise „Mo.“/„Montag“ und „Jan.“/„Januar“.

>[!NOTE]
Sie können das _24-Stunden-Format_ (d. h. 14:00 Uhr) oder die *am/pm*-Notation (d. h. 2:00 pm) verwenden.

### Kombination von Aufteilungen {#combined-parting}

1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Dashboard**, um das Kanal-Dashboard zu öffnen.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in den **Zeitplan** ein. Ihr Asset wird daraufhin für das jeweilige Tages- und Uhrzeitintervall angezeigt.

#### Beispielausdrücke für die Kombination von Aufteilungen {#example-four}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| nach 6:00 und vor 18:00 Uhr am Mo.,Mi. im Jan-Mrz | Das Asset im Kanal wird montags bis mittwochs von Januar bis Ende März zwischen 6 Uhr und 18 Uhr und mittwochs wiedergegeben. |
| am 1. Januar nach 14:00 Uhr auch am 2. Januar, auch am 3. Januar vor 3:00 Uhr | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr und weiterhin den ganzen Tag am 2. Januar bis um 3:00 Uhr am 3. Januar wiedergegeben. |
| am 1./2. Januar nach 14:00 Uhr auch am 2./3. Januar vor 3:00 Uhr | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. Dann wird es erneut am 2. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. |

>[!NOTE]
Bei der Definition von Wochentagen und Monaten können Sie sowohl die Abkürzung als auch die vollständige Bezeichnung verwenden, beispielsweise „Mo.“/„Montag“ und „Jan.“/„Januar“.  Außerdem können Sie das _24-Stunden-Format_ (d. h. 14:00 Uhr) oder die *am/pm*-Notation (d. h. 2:00 pm) verwenden.

