---
title: Erstellen und Verwalten von Zeitplänen
description: Erfahren Sie mehr über Zeitpläne, mit denen Sie Kanäle in wiederverwendbare Gruppen organisieren können, damit Sie ihre Zuweisung nicht einzeln wiederholen müssen.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: dc9c5413-3b03-4f1f-bac5-aa599443254a
TQID: https://experienceleague.adobe.com/FJomd-Wz-r8vJZK7PH6wgL4LY3zRmOucBhIbTdjUmQ4
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2:
  - id: ba4275ba-c29a-4197-90dc-5a633402ca3c
  - id: cf6d61d1-acb6-4411-ad1b-25fb57e94db6
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 0b0bfcd803c3da9298122200a0a1715fc2d5e49c
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 73%

---

# Erstellen und Verwalten von Zeitplänen {#creating-and-managing-schedules}

Mit **Zeitplänen** in AEM Screens können Sie Kanäle zu wiederverwendbaren Gruppen zusammenfassen. Dies bedeutet, dass Sie die Zuweisung nicht für jeden Bildschirm, auf dem Sie Ihre Inhalte anzeigen möchten, wiederholen müssen.

Durch die Kombination von Zeitplänen mit ***Dayparting*** können Sie einen globalen Zeitplan mit mehreren Kanälen festlegen, die zu bestimmten Tageszeiten ausgeführt werden. Diese Einstellung können dann für alle Anzeigen wiederverwendet werden.

>[!NOTE]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie das Feature Pack 1 für AEM 6.3 Sites installiert haben. Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Nachdem Sie die erforderlichen Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

## Zeitplan erstellen {#creating-a-schedule}

Sie können für Ihr Screens-Projekt einen Zeitplan erstellen, in dem alle Aktivitäten für Ihren Anwendungsfall verwaltet werden.

Führen Sie die folgenden Schritte aus, um einen Zeitplan für Ihren Kanal zu erstellen:

1. Klicken Sie auf den Link zu Adobe Experience Manager (oben links) und dann auf „Screens“. Sie haben auch die Möglichkeit, direkt zur folgenden URL zu wechseln: `http://localhost:4502/screens.html/content/screens`.
1. Navigieren Sie zum Screens-Projekt und klicken Sie auf **Zeitpläne**.
1. Klicken Sie in der Aktionsleiste auf **Erstellen**.
1. Klicken Sie im Assistenten **Erstellen** auf **Zeitplan** und dann auf **Weiter**.

1. Geben Sie den **Namen** und den **Titel** ein und klicken Sie auf **Erstellen**.

In Ihrem Projekt wird daraufhin ein Zeitplanordner mit dem zugewiesenen Namen und Titel dargestellt.


## Dashboard anzeigen {#viewing-dashboard}

Sobald Sie den Zeitplanordner in Ihrem Projekt erstellt haben, können Sie sich die Details im Zeitplan-Dashboard ansehen.

Führen Sie die folgenden Schritte aus, um sich das Dashboard für den Zeitplan anzeigen zu lassen. Das folgende Beispiel veranschaulicht, wie das Dashboard des `We.Retail`-Projekts angezeigt wird:

1. Navigieren Sie zum Ordner **Zeitpläne** des Screens-Projekts (z. B. `We.Retail`).

   ![chlimage_1](assets/chlimage_1.png)

1. Klicken Sie in der Aktionsleiste auf **Dashboard**.

   Dort finden Sie drei Bedienfelder: **ZEITPLANINFORMATIONEN**, **ZUGEWIESENE KANÄLE** und **ZUGEWIESENE ANZEIGEN**.

   ![chlimage_1-1](assets/chlimage_1-1.png)

   **Bedienfeld Zeitplaninformationen** - Klicken Sie oben rechts im Bedienfeld Zeitplaninformationen auf Eigenschaften , um die Eigenschaften des Zeitplans anzuzeigen bzw. zu ändern.

   **Bedienfeld „Zugewiesene Kanäle** - Klicken Sie oben rechts im Bedienfeld „ZUGEWIESENE KANÄLE“ auf + Kanal zuweisen , um das Dialogfeld „Kanalzuweisung“ zu öffnen.

   **Bedienfeld „Zugewiesene Displays** - Klicken Sie auf eines der Displays aus dem Bedienfeld „ZUGEWIESENE DISPLAYS“, um das Display-Dashboard zu öffnen.
