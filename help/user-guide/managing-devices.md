---
title: Verwalten von Geräten
description: Erfahren Sie mehr über die Gerätezuweisung und -verwaltung in AEM Screens.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 10749ff2-9128-44e7-9f10-c8e783a6f695
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 41%

---

# Verwalten von Geräten {#managing-devices}

Auf dieser Seite wird die Gerätezuweisung beschrieben.

Über die Gerätekonsole können Sie auf den Geräte-Manager zugreifen, um Ihr Gerät einer Anzeige zuzuweisen.

>[!CAUTION]
>
>Bevor Sie Ihr Gerät zuweisen, registrieren Sie es. Siehe [Geräteregistrierung](device-registration.md).

## Gerätezuweisung {#device-assignment}

Gehen Sie wie folgt vor, um ein Gerät einer Anzeige zuzuweisen:

1. Navigieren Sie zum Ordner „Geräte“ Ihres Projekts, z. B.

   `http://localhost:4502/screens.html/content/screens/TestProject`

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Klicken Sie auf **Geräte** Ordner und klicken Sie auf **Geräte-Manager** in der Aktionsleiste. Die zugewiesenen und nicht zugewiesenen Geräte werden angezeigt.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Klicken Sie auf ein nicht zugewiesenes Gerät in der Liste und klicken Sie auf das **Gerät zuweisen** in der Aktionsleiste.

   ![chlimage_1-34](assets/chlimage_1-34.png)

1. Klicken Sie in der Liste auf die Anzeige, der Sie das Gerät zuweisen möchten, und klicken Sie auf die **Zuweisen**.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. Klicken Sie auf **Beenden** , um den Zuweisungsprozess abzuschließen.


   Das Anzeigen-Dashboard zeigt das zugewiesene Gerät im Bedienfeld **GERÄTE** an.

   ![chlimage_1-37](assets/chlimage_1-37.png)

   Klicken Sie auf (**...**) oben rechts im **Geräte** -Bedienfeld, um entweder die Gerätekonfiguration hinzuzufügen oder die Geräte zu aktualisieren.

   ![chlimage_1-38](assets/chlimage_1-38.png)

>[!NOTE]
>
>Jedes Mal, wenn das erste Gerät zu einem neuen Screens-Projekt hinzugefügt wird, wird eine Benutzergruppe erstellt.
>Wenn der Projektknotenname zum Beispiel *we-retail* lautet, dann lautet der Benutzergruppenname *screens-we-retail-devices*.
>Diese Gruppe wird als Mitglied der **Mitarbeiter** -Gruppe, wie in der folgenden Abbildung dargestellt:

![chlimage_1-39](assets/chlimage_1-39.png)

### Die nächsten Schritte {#the-next-steps}

Wenn Sie mit dem Zuweisen eines Kanals zu einer Anzeige vertraut sind, lesen Sie[Überwachung und Fehlerbehebung](monitoring-screens.md).
