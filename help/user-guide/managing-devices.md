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
source-git-commit: 1e8beb9dfaf579250138d4a41eeec88cc81f2d39
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 62%

---

# Verwalten von Geräten {#managing-devices}

Auf dieser Seite wird die Gerätezuweisung beschrieben.

Über die Gerätekonsole können Sie auf den Geräte-Manager zugreifen, um Ihr Gerät einer Anzeige zuzuweisen.

>[!CAUTION]
>
>Bevor Sie Ihr Gerät zuweisen, müssen Sie es registrieren. Weitere Informationen finden Sie unter [Geräteregistrierung](device-registration.md).

## Gerätezuweisung {#device-assignment}

Gehen Sie wie folgt vor, um ein Gerät einer Anzeige zuzuweisen:

1. Navigieren Sie zum Ordner „Geräte“ Ihres Projekts, z. B.

   `http://localhost:4502/screens.html/content/screens/TestProject`

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Wählen Sie den Ordner **Geräte** aus und tippen/klicken Sie in der Aktionsleiste auf **Geräte-Manager**. Die zugewiesenen und nicht zugewiesenen Geräte werden angezeigt.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Wählen Sie ein nicht zugewiesenes Gerät aus der Liste aus und tippen/klicken Sie in der Aktionsleiste auf **Gerät zuweisen**.

   ![chlimage_1-34](assets/chlimage_1-34.png)

1. Wählen Sie die Anzeige aus, der Sie das Gerät aus der Liste zuweisen möchten, und tippen/klicken Sie auf die **Zuweisen**.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. Tippen/klicken Sie auf **Abschließen**, um die Zuweisung abzuschließen.


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

Wenn Sie damit vertraut sind, wie ein Kanal einer Anzeige zugewiesen wird, sehen Sie sich die folgenden Ressourcen an:

* [Überwachung und Fehlerbehebung](monitoring-screens.md)
