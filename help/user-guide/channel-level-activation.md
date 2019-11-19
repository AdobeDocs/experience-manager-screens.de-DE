---
title: Aktivierung auf Kanalebene - Wiedergabe eines einzelnen Ereignisses
seo-title: Aktivierung auf Kanalebene - Wiedergabe eines einzelnen Ereignisses
description: Befolgen Sie diese Anleitung, um die Aktivierung auf Kanalebene mithilfe der Wiedergabe eines einzelnen Ereignisses zu verstehen.
seo-description: Befolgen Sie diese Anleitung, um die Aktivierung auf Kanalebene mithilfe der Wiedergabe eines einzelnen Ereignisses zu verstehen.
uuid: 87230344-5f9a-42a4-a7a8-ae4203303612
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: c28fd669-f23e-4d53-bec1-a2911274567d
noindex: true
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Aktivierung auf Kanalebene - Wiedergabe eines einzelnen Ereignisses {#channel-level-activation-single-event-playback}

Die Aktivierung auf Kanalebene umfasst die folgenden Themen:

* Überblick
* Aktivieren auf Kanalebene als Wiedergabe eines einzelnen Ereignisses

## Überblick {#overview}

***Die Kanalebenenaktivierung*** ermöglicht es den Kanälen, nach einem bestimmten Zeitplan zu wechseln. Der Kanal für einzelne Ereignisse ersetzt den Hauptkanal nach einem bestimmten Zeitplan und gibt eine bestimmte Zeit ab, bis der Hauptkanal seinen Inhalt erneut wiedergibt.

Das folgende Beispiel bietet eine Lösung, indem der Schwerpunkt auf die folgenden Schlüsselbegriffe gelegt wird:

* einen ***Hauptsequenzkanal*** für die globale Sequenz
* einem ***einzelnen Ereigniskanal*** , der nur einmal zur festgelegten Zeit ausgeführt wird
* einen ***festgelegten Zeitplan und eine Priorität*** für das einzelne Wiedergabeereignis, das innerhalb des Hauptsequenzkanals auftritt

## Aktivieren auf Kanalebene {#using-channel-level-activation}

Im folgenden Abschnitt wird die Erstellung einer einzelnen Ereigniswiedergabe innerhalb eines Kanals für ein AEM Screens-Projekt erläutert.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktion beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen müssen, um die Implementierung der Kanalebenenaktivierung zu starten:

* Erstellen Sie ein AEM Screens-Projekt, in diesem Beispiel die Aktivierung auf **Kanalebene**

* Einen Kanal als **MainAdChannel** unter **Channels** -Ordner erstellen

* Erstellen eines weiteren Kanals als als **TargetedSinglePlay** unter **Channels** -Ordner

* Hinzufügen relevanter Assets zu beiden Kanälen

Die folgende Abbildung zeigt das Projekt zur Aktivierung **auf** Kanalebene mit den Kanälen **MainAdChannel** und **TargetedSinglePlay** im Ordner **Channels** .

![screen_shot_2018-11-27at104500am](assets/screen_shot_2018-11-27at104500am.png)

>[!NOTE]
>
>Weitere Informationen zum Erstellen eines Projekts und zum Erstellen eines Sequenzkanals finden Sie in den nachfolgend aufgeführten Ressourcen:
>
>* [Erstellen und Verwalten von Projekten](creating-a-screens-project.md)
   >
   >
* [Verwalten eines Kanals](managing-channels.md)
>



### Implementierung {#implementation}

Die Implementierung der Aktivierung auf Kanalebene in einem AEM Screens-Projekt umfasst drei Hauptaufgaben:

1. **Einrichten der Projekttaxonomie einschließlich Kanälen, Orten und Anzeigen**
1. **Zuweisen anzuzeigender Kanäle**
1. **Zeitplan und Priorität einrichten**

Gehen Sie wie folgt vor, um die Funktion zu implementieren:

1. **Speicherort erstellen**

   Navigieren Sie zum Ordner " **Speicherorte** "in Ihrem AEM Screens-Projekt und erstellen Sie einen Speicherort als **Region**.

   ![screen_shot_2018-11-27at112112am](assets/screen_shot_2018-11-27at112112am.png)

   >[!NOTE]
   >
   >Informationen zum Erstellen eines Speicherorts finden Sie unter **[Erstellen und Verwalten von Speicherorten](managing-locations.md)**.

1. **Anzeige unter Position erstellen**

   1. Navigieren Sie zu **Kanalebenenaktivierung** &gt; **Speicherorte** &gt; **Region**.
   1. Select **Region** and click **+ Create** from the action bar.
   1. Wählen Sie im Assistenten die Option **Anzeigen** und erstellen Sie eine Anzeige mit dem Titel **RegionDisplay.**
   ![screen_shot_2018-11-27at112216am](assets/screen_shot_2018-11-27at112216am.png)

1. **Anzuzeigende Kanäle**

   Für **MainAdChannel:**

   1. Navigieren Sie zu **Kanalebenenaktivierung** &gt; **Speicherorte** &gt; **Region** &gt; **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal** zuweisen.
   1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.
   1. Select **Reference Channel**.. by path.
   1. Wählen Sie den **Kanalpfad** als **Kanalebenenaktivierung** —&gt; ***Kanäle*** —&gt; ***MainAdChannel***.
   1. Die **Kanalrolle** wird als **Hauptkanal** ausgefüllt.
   1. Wählen Sie die **Priorität** als **1**.
   1. Select the **Supported Events** as **Initial Load** and **Idle Screen**.
   1. Klicken Sie auf **Speichern**.
   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   >
   >Sie können Kanäle auch über das Display-Dashboard zuweisen, indem Sie zu **Kanalebenenaktivierung** —&gt; **Orte** —&gt; **Region** —&gt; **RegionDisplay** navigieren und in der Aktionsleiste auf **Dashboard** klicken. Klicken Sie auf **+ Kanal** zuweisen aus dem Bedienfeld **ZUGEWIESENE KANÄLE &amp; GEPLANTE** .

   Weisen Sie den Kanal **TargetedSinglePlay** für display** zu:

   1. Navigieren Sie zu **Kanalebenenaktivierung** —&gt; **Speicherorte** —&gt; **Region** —&gt; **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal** zuweisen.
   1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.
   1. Select **Reference Channel**.. by path.
   1. Wählen Sie den **Kanalpfad** als **Kanalebenenaktivierung*** —&gt; ***Kanäle*** —&gt; ***TargetedSinglePlay***.
   1. Die **Kanalrolle** wird als **Targeting-Einzelspiel** gefüllt.
   1. Legen Sie die **Priorität** auf **2** fest.
   1. Wählen Sie die **unterstützten Ereignisse** als **anfänglich laden**, **Leerlauf** und **Timer** aus.
   1. Wählen Sie das Datum **aktiv ab** dem 27. November 2018 um 11:59 Uhr und bis **zum 28. November 2018 um 12:05 Uhr** aktiv.
   1. Klicken Sie auf **Speichern**.
   >[!CAUTION]
   Sie müssen die Priorität für den **zielgerichtetenSinglePlay** -Kanal höher als den **MainAdSegment** -Kanal festlegen.

   ![screen_shot_2018-11-27at31206pm](assets/screen_shot_2018-11-27at31206pm.png)

   >[!NOTE]
   Um denselben Tag auszuwählen, müssen Sie den nächsten Tag auswählen und das Datum manuell auf den gleichen Tag, jedoch für einen späteren Zeitpunkt bearbeiten. Dadurch wird der Benutzer daran gehindert, ein vergangenes Datum auszuwählen. Siehe hierzu das Beispiel unten:

   ![new1](assets/new1.gif)

## Ansicht der Ergebnisse {#viewing-the-results}

Sobald Sie die Einrichtung für Kanäle und die Anzeige abgeschlossen haben, starten Sie den AEM Screens Player, um den Inhalt anzuzeigen.

Der Player zeigt den Inhalt von **MainAdChannel** an und genau um 23:59 Uhr (wie im Zeitplan festgelegt) zeigt der Kanal **TargetedSinglePlay** seinen Inhalt bis 12:05 Uhr an. Anschließend wird die Wiedergabe des **MainAdChannel** fortgesetzt.

>[!NOTE]
Weitere Informationen zu AEM Screen Player finden Sie in den folgenden Ressourcen:
* [Downloads von AEM Screens Player](https://download.macromedia.com/screens/)
* [Arbeiten mit AEM Screens Player](working-with-screens-player.md)

