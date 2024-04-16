---
title: Videoausgabedarstellungen
description: Erfahren Sie mehr über das Generieren von Full HD-Wiedergaben für Ihr AEM Screens-Projekt.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 752c74d7-5d6d-4363-97ef-b96e97d2f6b1
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 23%

---

# Videoausgabeformate {#video-renditions}

Es ist möglich, manuelle und automatische Full HD-Ausgabeformate zu generieren. Im folgenden Abschnitt wird der Workflow zum Hinzufügen von Ausgabeformaten zu Assets beschrieben.

## Automatisches Generieren von Full HD-Ausgabeformaten  {#automatically-generating-full-hd-renditions}

>[!NOTE]
>
>Falls die AEM Screens-Videoausgabeformate nicht optimal auf Ihrem Gerät wiedergegeben werden, wenden Sie sich an den Hardware-Anbieter, um die Spezifikationen des Videos zu erhalten. Dies hilft, die beste Leistung auf dem Gerät zu erzielen und erstellt daher Ihr eigenes benutzerdefiniertes Videoprofil, in dem Sie die entsprechenden Parameter für FFMPEG zur Generierung Ihrer Ausgabedarstellung angeben. Gehen Sie dann wie folgt vor, um Ihr benutzerdefiniertes Videoprofil zur Profilliste hinzuzufügen.
>
>Siehe auch [Fehlerbehebung bei Videos](troubleshoot-videos.md) , um die Videowiedergabe in Ihrem Kanal zu debuggen und Fehler zu beheben.

Gehen Sie wie folgt vor, um automatisch Full HD-Wiedergaben zu generieren:

1. Klicken Sie auf den Adobe Experience Manager-Link (oben links) und dann auf das Hammersymbol, damit Sie auf **Workflow**.

   Klicks **Modelle**.

   ![screen_shot_2018-02-01at123407pm](assets/screen_shot_2018-02-01at123407pm.png)

1. Klicken Sie in der Workflow-Modellverwaltung auf die Schaltfläche **DAM-Update-Asset** Modell und klicken Sie **Bearbeiten** in der Aktionsleiste aus.

   ![step5_-_edit_thedamupdateassetmodel](assets/step5_-_edit_thedamupdateassetmodel.png)

1. Im **DAM-Update-Asset** durch Doppelklick auf das **FFmpeg-Transkodierung** Schritt.

   ![screen_shot_2018-02-01at124454pm](assets/screen_shot_2018-02-01at124454pm.png)

1. Klicken Sie auf **Prozess** Registerkarte.
1. Geben Sie die Full HD-Profile in die Liste unter **Argumente** wie folgt:
   ***`,profile:fullhd-bp,profile:fullhd-hp`***
1. Klicken Sie auf **OK**.

   ![screen_shot_2018-02-02at103340am](assets/screen_shot_2018-02-02at103340am.png)

1. Klicks **Speichern** oben links im **DAM-Update-Asset** angezeigt.

   ![screen_shot_2018-02-02at101830am](assets/screen_shot_2018-02-02at101830am.png)

1. Navigieren Sie zu **Assets** und laden Sie ein neues Video hoch. Klicken Sie auf das Video und öffnen Sie die Seitenleiste Ausgabeformate . Beachten Sie die beiden Full HD-Videos.

   ![step10_-_open_thevideoasset](assets/step10_-_open_thevideoasset.png)

1. Öffnen Sie über die Seitenleiste die Option **Wiedergaben**.

   ![step11_-_open_therenditionssiderail](assets/step11_-_open_therenditionssiderail.png)

1. Beachten Sie zwei neue Full HD-Wiedergaben.

   ![step12_-_2_new_renditionsareaddedtothevideo](assets/step12_-_2_new_renditionsareaddedtothevideo.png)

## Manuelles Generieren von Full HD-Wiedergaben {#manually-generating-full-hd-renditions}

Gehen Sie wie folgt vor, um manuell Full HD-Wiedergaben zu generieren:

1. Klicken Sie auf den Link Adobe Experience Manager (oben links) und dann auf das Hammersymbol, damit Sie auf Tools klicken und auf **Workflow**.

   Klicks **Modelle**.

   ![screen_shot_2018-02-01at123407pm-1](assets/screen_shot_2018-02-01at123407pm-1.png)

1. Klicken Sie in der Workflow-Modellverwaltung auf die Schaltfläche **Screens-Asset aktualisieren** und klicken Sie auf das **Workflow starten** , um die **Workflow ausführen** Dialogfeld.

   ![step5_-_start_a_newscreensupdateassetworkflow](assets/step5_-_start_a_newscreensupdateassetworkflow.png)

1. Klicken Sie auf das gewünschte Video im **Nutzlast** und klicken **Ausführen**.

   ![step6_-_select_thedesiredvideo](assets/step6_-_select_thedesiredvideo.png)

1. Navigieren Sie zu **Assets**, führen Sie einen Drilldown zum gewünschten Asset durch und klicken Sie darauf.

   ![step7_-_open_thevideoasset](assets/step7_-_open_thevideoasset.png)

1. Öffnen Sie die **Ausgabeformate** Seitenleiste. Beachten Sie die neuen Full HD-Wiedergaben.

   ![step8_-_open_therenditionssiderail](assets/step8_-_open_therenditionssiderail.png)
