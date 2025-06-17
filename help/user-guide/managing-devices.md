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
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 92%

---

# Verwalten von Geräten {#managing-devices}

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

   Klicken Sie oben rechts im Bedienfeld **GERÄTE** auf die Auslassungspunkte (**…**), um entweder eine Gerätekonfiguration hinzuzufügen oder die Geräte zu aktualisieren.

   ![chlimage_1-38](assets/chlimage_1-38.png)

>[!NOTE]
>
>Jedes Mal, wenn das erste Gerät zu einem neuen Screens-Projekt hinzugefügt wird, wird eine Benutzergruppe erstellt.
>>Wenn der Projektknotenname zum Beispiel *we-retail* lautet, dann lautet der Benutzergruppenname *screens-we-retail-devices*.
>>Diese Gruppe wird als Mitglied der Gruppe der **Mitwirkenden** hinzugefügt, wie in der folgenden Abbildung dargestellt:

![chlimage_1-39](assets/chlimage_1-39.png)

### Die nächsten Schritte {#the-next-steps}

Nachdem Sie nun damit vertraut sind, wie ein Kanal einer Anzeige zugewiesen wird, fahren Sie mit dem Thema [Überwachung und Fehlerbehebung](monitoring-screens.md) fort.
