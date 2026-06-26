---
title: Verwalten von Geräten
description: Erfahren Sie mehr über die Zuweisung und Verwaltung von Geräten in AEM Screens.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 10749ff2-9128-44e7-9f10-c8e783a6f695
TQID: https://experienceleague.adobe.com/BtVUYTZ9GisSxK6-M-QsYRGdykFB51IchqI7CX-vsa8
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2: id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 70%

---

# Verwalten von Geräten {#managing-devices}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Auf dieser Seite wird die Gerätezuweisung beschrieben.

Die Gerätekonsole erlaubt es Ihnen, auf den Geräte-Manager zuzugreifen, um Ihr Gerät einer Anzeige zuzuweisen.

>[!CAUTION]
>
>Registrieren Sie das Gerät, bevor Sie es zuweisen. Siehe [Geräteregistrierung](device-registration.md).

## Gerätezuweisung {#device-assignment}

Gehen Sie wie folgt vor, um ein Gerät einer Anzeige zuzuweisen:

1. Navigieren Sie zum Ordner „Geräte“ Ihres Projekts, z. B.

   `http://localhost:4502/screens.html/content/screens/TestProject`

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Klicken Sie auf den Ordner **Geräte** und dann in der Aktionsleiste auf **Geräte-Manager**. Die zugewiesenen und nicht zugewiesenen Geräte werden angezeigt.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Klicken Sie auf ein nicht zugewiesenes Gerät in der Liste und dann in der Aktionsleiste auf **Gerät zuweisen**.

   ![chlimage_1-34](assets/chlimage_1-34.png)

1. Klicken Sie in der Liste auf die Anzeige, die dem Gerät zugewiesen werden soll, und dann auf **Zuweisen**.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. Klicken Sie auf **Beenden**, um die Zuweisung abzuschließen.


   Das Anzeigen-Dashboard zeigt das zugewiesene Gerät im Bedienfeld **GERÄTE** an.

   ![chlimage_1-37](assets/chlimage_1-37.png)

   Klicken Sie auf (**…**) in der oberen rechten Ecke des Bedienfelds **GERÄTE**, um die Gerätekonfiguration hinzuzufügen oder die Geräte zu aktualisieren.

   ![chlimage_1-38](assets/chlimage_1-38.png)

>[!NOTE]
>
>Jedes Mal, wenn das erste Gerät zu einem neuen Screens-Projekt hinzugefügt wird, wird eine Benutzergruppe erstellt.Wenn der Projektknotenname zum Beispiel *we-retail* lautet, dann lautet der Benutzergruppenname *screens-we-retail-devices*.Diese Gruppe wird als Mitglied der Gruppe der **Mitwirkenden** hinzugefügt, wie in der folgenden Abbildung dargestellt:

![chlimage_1-39](assets/chlimage_1-39.png)

### Die nächsten Schritte {#the-next-steps}

Nachdem Sie nun damit vertraut sind, wie ein Kanal einer Anzeige zugewiesen wird, fahren Sie mit dem Thema [Überwachung und Fehlerbehebung](monitoring-screens.md) fort.

