---
title: Unterstützung von Miniaturansichten für Videos in AEM Screens
description: Auf dieser Seite wird beschrieben, wie Sie Miniaturansichten für Videos in Screens hinzufügen.
exl-id: d2d87807-1699-47e3-b241-07c5b7e56f15
source-git-commit: ec58cd9171e359b451eaad7015d42b41ef1bff3f
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 1%

---

# Unterstützung von Miniaturansichten für Videos {#thumbnail-support-videos}

## Einführung {#introduction}

Ein Inhaltsautor kann eine Miniaturansicht für Videos definieren, sodass das Bild als Platzhalter verwendet und die Inhaltswiedergabe und das Targeting ordnungsgemäß getestet werden kann, während das eigentliche Video vom entsprechenden Team fertig gestellt wird. Das Bild kann auch verwendet werden, falls die Wiedergabe des Videos fehlschlägt.

Durch das Hinzufügen der Unterstützung für ein Miniaturbild in der Videokomponente kann der Kunde eine gültige Komponente mit tatsächlichem Inhalt zum Kanal hinzufügen und Zielgruppenkonfigurationen durchführen, bevor das Video tatsächlich bereitgestellt wird.

>[!NOTE]
>Das Miniaturbild wird wiedergegeben, wenn es in der Videokomponente festgelegt ist, falls die Videowiedergabe auf dem Player fehlschlägt. Auf diese Weise können Sie die gewünschte Nachricht an die Zielgruppe senden (indem Sie Inhalte wiedergeben), anstatt sie vollständig zu überspringen.

Mit der Unterstützung von Miniaturansichten können Sie:

* Bereiten Sie ein Kanalerlebnis vor, wenn die Videos noch nicht bereit sind oder Sie nicht unbedingt einen großen Asset-Download auf den Playern testen möchten

* Legen Sie einen Ausweichmechanismus fest, falls auf dem Gerät Wiedergabeprobleme auftreten.

## Verwenden von Miniaturansichten in Videos {#using-thumbnails}

Gehen Sie wie folgt vor, um Miniaturansichten in Videos zu verwenden:

1. Navigieren Sie zu einem vorhandenen Screens-Kanal oder erstellen Sie einen neuen Kanal.

1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Bearbeiten** , um den Editor zu öffnen.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-1.png)

1. Fügen Sie eine vorhandene Videokomponente hinzu oder bearbeiten Sie sie, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-2.png)

1. Wählen Sie das Video aus und klicken Sie auf das Symbol *Schraubenschlüssel* , um die Videoeigenschaften zu öffnen.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-3.png)

1. Das Dialogfeld **Video** wird geöffnet, in dem Sie die Dropzone **Miniaturansicht** anzeigen.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-4.png)

1. Ziehen Sie ein Bild aus der Asset-Auswahl in die Dropzone **Miniatur** und klicken Sie auf **Fertig**.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-5.png)

1. Klicken Sie auf **Vorschau**.

1. Wenn ein Video für die Komponente festgelegt ist, wird das Video wiedergegeben. Wenn nicht, und die Miniaturansicht festgelegt ist, wird die Miniaturansicht wiedergegeben. Andernfalls wird die Komponente als nicht konfiguriert betrachtet und übersprungen.

## Unterstützte Anwendungsfälle bei der Verwendung von Miniaturansichten in Videos {#understand-use-case}

Miniaturansichten in Videos unterstützen die folgenden Anwendungsfälle:

* Eine Videokomponente, für die nichts eingerichtet ist, wird übersprungen.

* Eine Videokomponente mit nur der Miniaturansicht wird die Miniaturansicht wiedergegeben.

* Eine Videokomponente mit sowohl dem Video (wenn das Video die richtige Wiedergabe aufweist) als auch dem Miniaturbild-Set gibt das Video wieder.

* Eine Videokomponente mit dem Videoset gibt die Miniaturansicht im Fall eines Wiedergabefehlers wieder oder springt einfach zum nächsten Element, falls die Miniaturansicht nicht konfiguriert ist.
