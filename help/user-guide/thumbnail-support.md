---
title: Unterstützung von Miniaturansichten für Videos in AEM Screens
description: Erfahren Sie, wie Sie in AEM Screens Unterstützung für Miniaturansichten für Videos hinzufügen.
exl-id: d2d87807-1699-47e3-b241-07c5b7e56f15
source-git-commit: 6b4fc934c31640168528fa3e72cf634773f4f8e6
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 69%

---

# Unterstützung von Miniaturansichten für Videos {#thumbnail-support-videos}

## Einführung {#introduction}

Ein Inhaltsautor kann eine Miniaturansicht für Videos definieren, sodass das Bild als Platzhalter verwendet wird. Sie können die Inhaltswiedergabe und das Targeting ordnungsgemäß testen, während das entsprechende Team das eigentliche Video abschließt. Das Bild kann auch verwendet werden, falls die Wiedergabe des Videos fehlschlägt.

Durch das Hinzufügen der Unterstützung für ein Miniaturbild in der Videokomponente können Kundinnen und Kunden eine gültige Komponente mit echtem Inhalt zum Kanal hinzufügen und Targeting-Konfigurationen durchführen, bevor das Video bereitgestellt wird.

>[!NOTE]
>Falls die Videowiedergabe auf dem Player fehlschlägt, wird das Miniaturbild wiedergegeben, sofern es in der Videokomponente festgelegt ist. Mit diesem Fallback können Sie die gewünschte Nachricht an die Zielgruppe senden (indem Sie Inhalte wiedergeben), anstatt sie vollständig zu überspringen.

Mit der Unterstützung von Miniaturansichten können Sie:

* Ein Kanalerlebnis vorbereiten, wenn die Videos noch nicht fertig sind oder wenn Sie nicht unbedingt einen umfangreichen Asset-Download auf die Player testen möchten

* Einen Ausweichmechanismus festlegen, falls auf dem Gerät Wiedergabeprobleme auftreten.

## Verwenden von Miniaturansichten in Videos {#using-thumbnails}

Gehen Sie wie folgt vor, um eine Miniaturansicht in Videos zu verwenden:

1. Navigieren Sie zu einem vorhandenen AEM Screens-Kanal oder erstellen Sie einen Kanal.

1. Klicken Sie auf den Kanal und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-1.png)

1. Fügen Sie eine vorhandene Videokomponente hinzu oder bearbeiten Sie sie, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-2.png)

1. Klicken Sie auf das Video und klicken Sie auf das *Schraubenschlüssel* Symbol.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-3.png)

1. Das Dialogfeld **Video** wird geöffnet, in dem die Ablagefläche **Miniaturansicht** angezeigt wird.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-4.png)

1. Ziehen Sie ein Bild aus der Asset-Auswahl in die Ablagefläche **Miniaturansicht** und klicken Sie auf **Fertig**.

   ![Bild](/help/user-guide/assets/thumbnails/thumbnail-5.png)

1. Klicken Sie auf **Vorschau**. 

1. Wenn für die Komponente ein Video festgelegt ist, wird das Video wiedergegeben. Wenn das nicht der Fall ist und die Miniaturansicht festgelegt ist, wird die Miniaturansicht wiedergegeben. Andernfalls wird die Komponente als nicht konfiguriert betrachtet und übersprungen.

## Unterstützte Anwendungsfälle bei der Verwendung von Miniaturansichten in Videos {#understand-use-case}

Miniaturansichten in Videos unterstützen die folgenden Anwendungsfälle:

* Eine Videokomponente, für die nichts eingerichtet ist, wird übersprungen.

* Bei einer Videokomponente, für die nur die Miniaturansicht festgelegt ist, wird die Miniaturansicht wiedergegeben.

* Bei einer Videokomponente, für die sowohl das Video (wenn das Video eine korrekte Ausgabedarstellung hat) als auch die Miniaturansicht festgelegt sind, wird das Video abgespielt.

* Eine Videokomponente, für die das Video festgelegt ist, spielt die Miniaturansicht ab, wenn ein Wiedergabefehler auftritt, oder springt zum nächsten Element, falls die Miniaturansicht nicht konfiguriert ist.
