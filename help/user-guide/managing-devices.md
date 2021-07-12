---
title: Verwalten von Geräten
seo-title: Verwalten von Geräten
description: Auf dieser Seite wird die Gerätezuweisung beschrieben.
seo-description: Folgen Sie dieser Seite, um sich über Gerätezuweisung zu informieren. Die Gerätekonsole erlaubt es Ihnen, auf den Geräte-Manager zuzugreifen, um Ihr Gerät einer Anzeige zuzuweisen.
uuid: 889cc11c-60f7-4966-82b5-9ebdd082a3c5
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 8dc08e29-a377-4e84-84ee-442470c19019
feature: Inhaltserstellung in Screens
role: Admin, Developer
level: Intermediate
exl-id: 10749ff2-9128-44e7-9f10-c8e783a6f695
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 100%

---

# Verwalten von Geräten {#managing-devices}

Auf dieser Seite wird die Gerätezuweisung beschrieben.

Die Gerätekonsole erlaubt es Ihnen, auf den Geräte-Manager zuzugreifen, um Ihr Gerät einer Anzeige zuzuweisen.

>[!CAUTION]
>
>Vor dem Zuweisen müssen Sie das Gerät registrieren. Weitere Informationen finden Sie unter [Geräteregistrierung](device-registration.md).

## Gerätezuweisung {#device-assignment}

Gehen Sie wie folgt vor, um ein Gerät einer Anzeige zuzuweisen:

1. Navigieren Sie zum Ordner „Geräte“ Ihres Projekts, z. B.

   `http://localhost:4502/screens.html/content/screens/TestProject`

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Wählen Sie den Ordner **Geräte** aus und tippen/klicken Sie in der Aktionsleiste auf **Geräte-Manager**. Die zugewiesenen und nicht zugewiesenen Geräte werden angezeigt.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Wählen Sie ein nicht zugewiesenes Gerät aus der Liste aus und tippen/klicken Sie in der Aktionsleiste auf **Gerät zuweisen**.

   ![chlimage_1-34](assets/chlimage_1-34.png)

1. Wählen Sie die Anzeige, die Sie dem aus der Liste ausgewählten Gerät zuweisen möchten, und tippen/klicken Sie auf **Zuweisen**.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. Tippen/klicken Sie auf **Abschließen**, um die Zuweisung abzuschließen.


   Das Anzeigen-Dashboard zeigt das zugewiesene Gerät im Bedienfeld **GERÄTE** an.

   ![chlimage_1-37](assets/chlimage_1-37.png)

   Klicken Sie in der oberen rechten Ecke des Bedienfelds **GERÄTE** auf (**...**), um entweder eine Gerätekonfiguration hinzuzufügen oder die Geräte zu aktualisieren.

   ![chlimage_1-38](assets/chlimage_1-38.png)

>[!NOTE]
>
>Jedes Mal, wenn das erste Gerät zu einem neuen Screens-Projekt hinzugefügt wird, wird eine Benutzergruppe erstellt.
>Wenn der Projektknotenname zum Beispiel *we-retail* lautet, dann lautet der Benutzergruppenname *screens-we-retail-devices*.
>Diese Gruppe wird als Mitglied der Gruppe **Mitwirkende** hinzugefügt, wie in der folgenden Abbildung gezeigt:

![chlimage_1-39](assets/chlimage_1-39.png)

### Die nächsten Schritte {#the-next-steps}

Wenn Sie damit vertraut sind, wie ein Kanal einer Anzeige zugewiesen wird, sehen Sie sich die folgenden Ressourcen an:

* [Überwachung und Fehlerbehebung](monitoring-screens.md)
