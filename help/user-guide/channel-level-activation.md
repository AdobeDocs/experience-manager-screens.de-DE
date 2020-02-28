---
title: Aktivierung auf der Kanalebene – Wiedergabe eines einzelnen Ereignisses
seo-title: Aktivierung auf der Kanalebene – Wiedergabe eines einzelnen Ereignisses
description: Befolgen Sie diese Anleitung, um die Aktivierung auf der Kanalebene mithilfe der Wiedergabe eines einzelnen Ereignisses zu verstehen.
seo-description: Befolgen Sie diese Anleitung, um die Aktivierung auf der Kanalebene mithilfe der Wiedergabe eines einzelnen Ereignisses zu verstehen.
uuid: 87230344-5f9a-42a4-a7a8-ae4203303612
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: c28fd669-f23e-4d53-bec1-a2911274567d
noindex: true
translation-type: tm+mt
source-git-commit: 1dbbe62875cdc1a0c1c7d5fe45221d7ebd12207f

---


# Channel Level Activation {#channel-level-activation-single-event-playback}

Die Aktivierung auf der Kanalebene umfasst die folgenden Themen:

* Überblick
* Verwenden der Aktivierung auf der Kanalebene als Wiedergabe eines einzelnen Ereignisses

## Überblick {#overview}

Die ***Aktivierung auf der Kanalebene*** ermöglicht den Wechsel von Kanälen nach einem festgelegten Zeitplan. Der Kanal für ein einzelnes Ereignis ersetzt den Hauptkanal nach einem festgelegten Zeitplan und spielt für eine bestimmte Zeit, bis der Hauptkanal seinen Inhalt wiedergibt.

Das folgende Beispiel zeigt eine Lösung mit Konzentration auf die folgenden Schlüsselbegriffe:

* einen ***Hauptsequenzkanal*** für die globale Sequenz,
* einen ***Kanal für ein einzelnes Ereignis***, der nur einmal zur festgelegten Zeit ausgeführt wird
* einen ***festgelegten Zeitplan und eine Priorität*** für die einzelne Wiedergabe des Ereignisses, die innerhalb des Hauptsequenzkanals erfolgt

## Verwenden der Aktivierung auf Kanalebene {#using-channel-level-activation}

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
   >
   >
* [Verwalten eines Kanals](managing-channels.md)
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
   1. Wählen Sie als Vorgehensweise für **Kanal referenzieren** die Option „Pfad“ aus.
   1. Select the **Channel Path** as **Channel Level Activation** --> ***Channels*** --> ***MainAdChannel***.
   1. Die **Kanalrolle** wird mit **mainadchannel** ausgefüllt.
   1. Wählen Sie als **Priorität** den Wert **1** aus.
   1. Wählen Sie unter **Unterstützte Ereignisse** die Optionen **Erster Ladevorgang** und **Bildschirm bei Untätigkeit** aus.
   1. Klicken Sie auf **Speichern**.
   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   >
   >Sie können Kanäle auch über das Anzeigen-Dashboard zuweisen, indem Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** navigieren und in der Aktionsleiste auf **Dashboard** klicken. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+ Kanal zuweisen**.

   Weisen Sie den Kanal **TargetedSinglePlay** für die Anzeige zu:

   1. Navigieren Sie zu **Channel Level Activation** > **Standorte** > **Region** > **RegionDisplay** und klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.
   1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.
   1. Wählen Sie als Vorgehensweise für **Kanal referenzieren** die Option „Pfad“ aus.
   1. Select the **Channel Path** as **Channel Level Activation*** --> ***Channels*** --> ***TargetedSinglePlay***.
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
* [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/)
* [Arbeiten mit dem AEM Screens-Player](working-with-screens-player.md)

