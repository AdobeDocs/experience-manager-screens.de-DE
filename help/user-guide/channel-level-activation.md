---
title: Aktivierung auf Kanalebene – Wiedergabe eines einzelnen Ereignisses
description: Erfahren Sie mehr über die Aktivierung auf Kanalebene mithilfe der Wiedergabe eines einzelnen Ereignisses.
topic-tags: authoring
feature: Authoring Screens, Channels
role: Admin, Developer
level: Intermediate
exl-id: 51a63429-2488-45be-b8f5-cb755ca69c7f
source-git-commit: c142830a37461a36baae15f543bd43b0ae8a62a7
workflow-type: tm+mt
source-wordcount: '1769'
ht-degree: 50%

---

# Aktivierung auf Kanalebene {#channel-level-activation-single-event-playback}

Auf dieser Seite wird die Aktivierung auf Kanalebene für die in Kanälen verwendeten Assets beschrieben.

In diesem Abschnitt werden die folgenden Themen behandelt:

* Überblick
* Aktivierungsfenster
* Verwenden der Aktivierung auf Kanalebene als Wiedergabe eines einzelnen Ereignisses
* Umgang mit sich wiederholenden Assets in einem Kanal
   * DayParting
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

Bevor Sie mit der Implementierung dieser Funktion beginnen, stellen Sie sicher, dass Sie über die folgenden Voraussetzungen verfügen, um mit der Implementierung der Aktivierung auf Kanalebene zu beginnen:

* Erstellen eines AEM Screens-Projekts, in diesem Beispiel **Channel Level Activation**

* Erstellen eines Kanals als **MainAdChannel** im Ordner **Kanäle**

* Erstellen eines weiteren Kanals als **TargetedSinglePlay** im Ordner **Kanäle**

* Hinzufügen relevanter Assets zu beiden Kanälen

Die folgende Abbildung zeigt das Projekt **Channel Level Activation** mit den Kanälen **MainAdChannel** und **TargetedSinglePlay** im Ordner **Kanäle**.

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
   1. Wählen Sie **Region** aus und klicken Sie in der Aktionsleiste auf **+ Erstellen**.
   1. Wählen Sie im Assistenten die Option **Anzeigen** aus und erstellen Sie eine Anzeige mit dem Titel **RegionDisplay.**

   ![screen_shot_2018-11-27at112216am](assets/screen_shot_2018-11-27at112216am.png)

1. **Zuweisen anzuzeigender Kanäle**

   Für **MainAdChannel:**

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.
   1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.
   1. Auswählen **Referenzkanal** Nach Pfad.
   1. Wählen Sie die **Kanalpfad** als **Aktivierung auf Kanalebene** > ***Kanäle*** > ***MainAdChannel***.
   1. Die **Kanalrolle** wird mit **mainadchannel** ausgefüllt.
   1. Wählen Sie als **Priorität** den Wert **1** aus.
   1. Wählen Sie unter **Unterstützte Ereignisse** die Optionen **Erster Ladevorgang** und **Bildschirm bei Untätigkeit** aus.
   1. Wählen Sie **Speichern** aus.

   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   >
   >Sie können auch einen Kanal über das Display-Dashboard zuweisen, indem Sie zu navigieren. **Aktivierung auf Kanalebene** > **Speicherorte** > **Region** > **RegionDisplay** und Klicken auf **Dashboard** in der Aktionsleiste aus. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+ Kanal zuweisen**.

   Weisen Sie den Kanal **TargetedSinglePlay** für die Anzeige zu:

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.
   1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.
   1. Auswählen **Referenzkanal** Nach Pfad.
   1. Wählen Sie die **Kanalpfad** als **Aktivierung auf Kanalebene*** > ***Kanäle*** > ***TargetingSinglePlay***.
   1. Die **Kanalrolle** wird mit **targetedsingleplay** ausgefüllt.
   1. Legen Sie die als **Priorität** den Wert **2** fest.
   1. Wählen Sie die **Unterstützte Ereignisse** als **Vorbelastung**, **Bildschirm im Leerlauf**, und **Timer**, wie in der folgenden Abbildung dargestellt.
   1. Datum auswählen in **Aktives Formular** wie 27. November 2018 23:59 Uhr und in **aktiv bis** wie 28. November 2018 12:05 Uhr
   1. Wählen Sie **Speichern** aus.

   >[!CAUTION]
   >
   >Priorität festlegen für **TargetingSinglePlay** Kanal höher als **MainAdSegment** Kanal.

   ![screen_shot_2018-11-27at31206pm](assets/screen_shot_2018-11-27at31206pm.png)

   >[!NOTE]
   >
   >Um denselben Tag auszuwählen, wählen Sie den nächsten Tag aus und bearbeiten Sie das Datum manuell auf denselben Tag, jedoch für einen späteren Zeitpunkt. Dies hindert den Benutzer daran, ein Datum in der Vergangenheit auszuwählen. Siehe folgendes Beispiel:

   ![new1](assets/new1.gif)

## Anzeigen der Ergebnisse {#viewing-the-results}

Wenn Sie die Einrichtung für Kanäle abgeschlossen haben und die Anzeige abgeschlossen ist, starten Sie den AEM Screens-Player, um den Inhalt anzuzeigen.

Der Player zeigt den Inhalt von **MainAdChannel** und genau um 23:59 Uhr (wie im Zeitplan festgelegt) **TargetingSinglePlay** Der Kanal zeigt seinen Inhalt bis 00:05 Uhr an und danach **MainAdChannel** nimmt die Wiedergabe des Inhalts wieder auf.

>[!NOTE]
>
>Weitere Informationen zum AEM Screen Player finden Sie in den folgenden Ressourcen:
>[AEM Screens Player-Downloads](https://download.macromedia.com/screens/)
>[Arbeiten mit dem AEM Screens-Player](working-with-screens-player.md)


## Umgang mit sich wiederholenden Assets in einem Kanal {#handling-recurrence-in-assets}

Sie können eine Wiederholung von Assets in einem Kanal Ihren Anforderungen entsprechend in bestimmten Intervallen auf Tages-, Wochen- oder Monatsbasis planen.

Angenommen, Sie möchten den Inhalt eines Kanals nur freitags von 13:00 bis 22:00 Uhr anzeigen. Auf der Registerkarte **Aktivierung** können Sie das gewünschte Wiederholungsintervall für Ihr Asset festlegen.

### DayParting {#day-parting}

1. Wählen Sie den Kanal aus und klicken Sie auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und das Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielausdrücke für die DayParting {#example-one}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben |
| nach 14:00 Uhr | Das Asset im Kanal wird jeden Tag nach 14:00 Uhr wiedergegeben |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich nach 12:15 Uhr für 30 Minuten wiedergegeben |
| vor 12:15 Uhr auch nach 12:45 Uhr | Das Asset im Kanal wird täglich vor 12:15 Uhr und dann auch nach 12:45 Uhr wiedergegeben. |
| Mo, Di, Mi oder Mo-Mi | Das Asset im Kanal wird von Montag bis Mittwoch wiedergegeben. |
| am ersten Januartag nach 14:00 Uhr auch am zweiten Januartag ebenfalls am dritten Januartag vor 3:00 Uhr. | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr wiedergegeben und läuft am 2. Januar den ganzen Tag bis zum 3. Januar um 3:00 Uhr weiter |
| an den 1-2 Tagen im Januar nach 14:00 Uhr auch an den 2-3 Tagen im Januar vor 3:00 Uhr. | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. Dann wird es am 2. Januar um 14:00 Uhr erneut gestartet und bis zum 3. Januar um 3:00 Uhr wiedergegeben |

>[!NOTE]
>
>Sie können auch Folgendes verwenden _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M.* (14:00 UHR)

### WeekParting {#week-parting}

1. Wählen Sie den Kanal aus und klicken Sie auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und das Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielhafte Ausdrücke für WeekParting {#example-two}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| Mo, Di, Mi oder Mo-Mi | Das Asset im Kanal wird von Montag bis Mittwoch wiedergegeben. |
| vor 8:00 Uhr | Das Asset im Kanal wird täglich vor 8:00 Uhr wiedergegeben |
| nach 14:00 Uhr | Das Asset im Kanal wird jeden Tag nach 14:00 Uhr wiedergegeben |
| nach 12:15 Uhr und vor 12:45 Uhr | Das Asset im Kanal wird täglich nach 12:15 Uhr für 30 Minuten wiedergegeben |
| vor 12:15 Uhr auch nach 12:45 Uhr | Der Kanal spielt jeden Tag vor 12:15 Uhr und dann auch nach 12:45 Uhr. |

>[!NOTE]
>
>Sie können auch Folgendes verwenden _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M.* (14:00 UHR)


### MonthParting {#month-parting}

1. Wählen Sie den Kanal aus und klicken Sie auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und das Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielhafte Ausdrücke für MonthParting {#example-three}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| von `February,May,August,November` | Das Asset wird im Februar, Mai, August, November im Kanal wiedergegeben |

>[!NOTE]
>
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Kurz- als auch die Vollnamennotation verwenden, z. B. Mo/Montag und Jan/Januar.

>[!NOTE]
>
>Sie können auch Folgendes verwenden _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M.* (14:00 UHR)

### Kombination von Aufteilungen {#combined-parting}

1. Wählen Sie den Kanal aus und klicken Sie auf **Dashboard** in der Aktionsleiste aus.

1. Nach Eingabe von Startdatum/Startzeit und Enddatum/Endzeit im Dialogfeld **Kanalzuweisung** können Sie einen Ausdruck oder eine natürliche Textversion verwenden, um Ihren Wiederholungsplan anzugeben.

   >[!NOTE]
   >
   >Sie können die Felder **Aktiv ab** und **Aktiv bis** überspringen oder einbeziehen und den Ausdruck entsprechend Ihren Anforderungen zum Feld „Zeitpläne“ hinzufügen.

1. Geben Sie den Ausdruck in das **Zeitplan** und das Asset für das jeweilige Tages- und Zeitintervall angezeigt wird.

#### Beispielausdrücke für die Kombination von Aufteilungen {#example-four}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| nach 6:00 und vor 18:00 Uhr am Mo, Mi. Jan-Mar | Das Asset im Kanal wird montags bis mittwochs von Januar bis Ende März zwischen 6 Uhr und 18 Uhr und mittwochs wiedergegeben. |
| am ersten Januartag nach 14:00 Uhr auch am zweiten Januartag ebenfalls am dritten Januartag vor 3:00 Uhr. | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr wiedergegeben und läuft am 2. Januar den ganzen Tag bis zum 3. Januar um 3:00 Uhr weiter |
| an den 1-2 Tagen im Januar nach 14:00 Uhr auch an den 2-3 Tagen im Januar vor 3:00 Uhr. | Das Asset im Kanal wird ab dem 1. Januar um 14:00 Uhr bis zum 2. Januar um 3:00 Uhr wiedergegeben. Dann wird es am 2. Januar um 14:00 Uhr erneut gestartet und bis zum 3. Januar um 3:00 Uhr wiedergegeben |

>[!NOTE]
>
>Bei der Definition von Wochentagen und Monaten können Sie sowohl die Kurz- als auch die Vollnamennotation verwenden, z. B. Mo/Montag und Jan/Januar. Außerdem können Sie Folgendes verwenden _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M.* (14:00 UHR)
