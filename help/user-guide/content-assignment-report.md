---
title: Inhaltszuweisungsbericht
description: Erfahren Sie mehr über das Herunterladen und Verwenden des Inhaltszuweisungsberichts im Zusammenhang mit AEM Screens.
feature: Authoring Screens
role: Developer
level: Intermediate
exl-id: 7397aa99-97fc-45c2-a157-c1bd7b1700b5
TQID: https://experienceleague.adobe.com/Pwq3ebRrbCufXFMk7R-FJj90xq4b7gLOcLvslch2L5o
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2: id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: d4664dd5678eaccabe656398c437dca264d4675e
workflow-type: tm+mt
source-wordcount: 397
ht-degree: 80%

---

# Inhaltszuweisungsbericht {#content-assignment-report}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Mit der Funktion „Inhaltszuweisungsbericht“ kann ein AEM Screens-Administrator oder ein Autor einen *Inhaltszuweisungsbericht* in ein Tabellenformat exportieren.

## Verwenden des Inhaltszuweisungsberichts {#using-content-assignment-report}

Mit dem Inhaltszuweisungsbericht kann eine Autorin oder ein Autor bzw. eine Administratorin oder Administrator in AEM Screens einen Bericht herunterladen, der sämtliche Assets wie Bilder und Videos in allen Kanälen enthält, die in einem AEM Screens-Projekt erstellt wurden. Außerdem enthält er Informationen zu allen Kanälen, die allen vorgesehenen Anzeigen zugewiesen sind, und damit auch alle Geräte, die ihren jeweiligen Anzeigen zugeordnet sind.

Der Inhaltszuweisungsbericht ermöglicht nicht nur eine Vorschau aller Kanäle, Assets, Anzeigen und Geräte im ausgewählten AEM Screens-Projekt, sondern liefert auch eine allgemeine Struktur Ihres Projekts.


### Voraussetzungen {#pre-reqs}

Stellen Sie vor dem Herunterladen des Inhaltszuweisungsberichts sicher, dass Sie ein AEM Screens-Projekt mit Kanälen, Standorten und Geräten eingerichtet haben.
Weitere Informationen finden Sie in den folgenden Ressourcen:

1. [Erstellen und Verwalten von Projekten](/help/user-guide/creating-a-screens-project.md)
1. [Erstellen und Verwalten von Kanälen](/help/user-guide/managing-channels.md)
1. [Erstellen und Verwalten von Standorten](/help/user-guide/managing-locations.md)
1. [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md)
1. [Erstellen von Geräten](/help/user-guide/managing-devices.md)
1. [Zuweisen von Kanälen](/help/user-guide/channel-assignment-latest-fp.md)


## Herunterladen des Inhaltszuweisungsberichts {#downloading-content-assignment-report-fp}

Wenn Sie Ihr AEM Screens-Projekt eingerichtet und jedem Standort Anzeigen zugewiesen haben, wie in den vorherigen Schritten gezeigt, laden Sie den Inhaltszuweisungsbericht herunter.

>[!NOTE]
>Auf die Funktion „Inhaltszuweisungsbericht“ kann nur auf Projektebene zugegriffen werden.

Folgen Sie den nachstehenden Anweisungen, um den Inhaltszuweisungsbericht herunterzuladen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt und klicken Sie auf das Projekt **DemoScreens**.

1. Klicken Sie in der Aktionsleiste auf **Inhaltszuweisungsbericht**.

   ![Bild](/help/user-guide/assets/content-assignment-report/can-download.png)

1. Das heruntergeladene Arbeitsblatt besteht aus zwei Registerkarten, z. B **&quot;**&quot; und **Inhalt**. Die Registerkarte „Standort“ besteht aus vier Spalten (**Standorte**, **Anzeigen**, **Kanäle** und **Geräte**), mit denen diese vier Entitäten Ihres AEM Screens-Projekts untersucht werden können.

   ![Bild](/help/user-guide/assets/content-assignment-report/report-sheet1.png)

   >[!NOTE]
   >Die im Arbeitsblatt angezeigten Daten sind alphabetisch in einem leicht lesbaren Format sortiert.

1. Durch Auswahl eines beliebigen Kanals in der Spalte **Kanäle**, wird die Registerkarte **Inhalt** geöffnet. Darüber gelangen Sie wiederum direkt zu diesem Kanal und erhalten Informationen zu Assets (Bildern und Videos), die mit diesem Kanal verknüpft sind.

   ![image](/help/user-guide/assets/content-assignment-report/report-sheet2.png)
