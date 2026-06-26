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
TQID: https://experienceleague.adobe.com/4xxCtO5lD71kiS-dSbTjTgycZDiWkQlHPdJOCVDrv38
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2:
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 424
ht-degree: 89%

---

# Videoausgabedarstellungen {#video-renditions}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

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

