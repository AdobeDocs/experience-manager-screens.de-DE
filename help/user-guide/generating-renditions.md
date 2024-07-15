---
title: Videoausgabedarstellungen
description: Erfahren Sie mehr über das Generieren von Full HD-Ausgabedarstellungen für Ihr AEM Screens-Projekt.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 752c74d7-5d6d-4363-97ef-b96e97d2f6b1
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 100%

---

# Videoausgabedarstellungen {#video-renditions}

Es ist möglich, manuelle und automatische Full HD-Ausgabedarstellungen zu generieren. Im folgenden Abschnitt wird der Workflow zum Hinzufügen von Ausgabedarstellungen zu Assets beschrieben.

## Automatisches Generieren von Full HD-Ausgabeformaten {#automatically-generating-full-hd-renditions}

>[!NOTE]
>
>Falls die AEM Screens-Videoausgabedarstellungen auf Ihrem Gerät nicht optimal wiedergegeben werden, wenden Sie sich an den Hardware-Anbieter, um sich über die Spezifikationen für das Video zu informieren. Auf diese Weise erhalten Sie die beste Leistung auf dem Gerät. Sie können damit Ihr eigenes benutzerdefiniertes Videoprofil erstellen, in dem Sie die entsprechenden Parameter für FFMPEG zur Generierung Ihrer Ausgabedarstellung angeben. Gehen Sie dann wie folgt vor, um Ihr benutzerdefiniertes Videoprofil zur Profilliste hinzuzufügen.
>
>Weitere Informationen zur Fehlerbehebung bei der Wiedergabe von Videos in Ihrem Kanal finden Sie unter [Fehlerbehebung bei Videos](troubleshoot-videos.md).

Führen Sie die folgenden Schritte aus, um automatisch Full-HD-Ausgabedarstellungen zu generieren:

1. Klicken Sie auf den Adobe Experience Manager-Link (oben links) und dann auf das Hammersymbol, um auf **Workflow** klicken zu können.

   Klicken Sie auf **Modelle**.

   ![screen_shot_2018-02-01at123407pm](assets/screen_shot_2018-02-01at123407pm.png)

1. Klicken Sie in der Workflow-Modellverwaltung auf das Modell **DAM-Update-Asset** und klicken Sie dann in der Aktionsleiste auf **Bearbeiten**.

   ![step5_-_edit_thedamupdateassetmodel](assets/step5_-_edit_thedamupdateassetmodel.png)

1. Doppelklicken Sie im Fenster **DAM-Update-Asset** auf den Schritt **FFmpeg-Transkodierung**.

   ![screen_shot_2018-02-01at124454pm](assets/screen_shot_2018-02-01at124454pm.png)

1. Klicken Sie auf die Registerkarte **Prozess**.
1. Geben Sie die vollständigen HD-Profile wie folgt in die Liste unter **Argumente** ein:
   ***`,profile:fullhd-bp,profile:fullhd-hp`***
1. Klicken Sie auf **OK**.

   ![screen_shot_2018-02-02at103340am](assets/screen_shot_2018-02-02at103340am.png)

1. Klicken Sie oben links im Bildschirm **DAM-Update-Asset** auf **Speichern**.

   ![screen_shot_2018-02-02at101830am](assets/screen_shot_2018-02-02at101830am.png)

1. Navigieren Sie zu **Assets** und laden Sie ein neues Video hoch. Klicken Sie auf das Video und öffnen Sie die Seitenleiste „Ausgabedarstellungen“. Beachten Sie die beiden Full HD-Videos.

   ![step10_-_open_thevideoasset](assets/step10_-_open_thevideoasset.png)

1. Öffnen Sie über die Seitenleiste die Option **Wiedergaben**.

   ![step11_-_open_therenditionssiderail](assets/step11_-_open_therenditionssiderail.png)

1. Sie werden zwei neue Full HD-Ausgabedarstellungen bemerken.

   ![step12_-_2_new_renditionsareaddedtothevideo](assets/step12_-_2_new_renditionsareaddedtothevideo.png)

## Manuelles Generieren von Full HD-Wiedergaben {#manually-generating-full-hd-renditions}

Gehen Sie wie folgt vor, um manuell Full HD-Ausgabedarstellungen zu generieren:

1. Klicken Sie auf den Adobe Experience Manager-Link (oben links) und klicken Sie auf das Hammersymbol, um auf Tools und dann auf **Workflow** zu klicken.

   Klicken Sie auf **Modelle**.

   ![screen_shot_2018-02-01at123407pm-1](assets/screen_shot_2018-02-01at123407pm-1.png)

1. Klicken Sie in der Workflow-Modellverwaltung auf das Modell **Screens – Asset aktualisieren** und klicken Sie dann auf **Workflow starten**, wodurch sich das Dialogfeld **Workflow ausführen** öffnet.

   ![step5_-_start_a_newscreensupdateassetworkflow](assets/step5_-_start_a_newscreensupdateassetworkflow.png)

1. Klicken Sie auf das gewünschte Video in der **Payload** und dann auf **Ausführen**.

   ![step6_-_select_thedesiredvideo](assets/step6_-_select_thedesiredvideo.png)

1. Navigieren Sie zu **Assets**, führen Sie einen Drilldown zum gewünschten Asset durch und klicken Sie darauf.

   ![step7_-_open_thevideoasset](assets/step7_-_open_thevideoasset.png)

1. Öffnen Sie die Seitenleiste **Ausgabedarstellungen**. Beachten Sie die neuen Full HD-Ausgabedarstellungen.

   ![step8_-_open_therenditionssiderail](assets/step8_-_open_therenditionssiderail.png)
