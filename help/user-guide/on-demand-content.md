---
title: On-Demand-Inhaltsaktualisierung
description: Erfahren Sie mehr über On-Demand-Inhaltsaktualisierungen für die Verwaltung von Veröffentlichungen.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer
level: Intermediate
exl-id: 9ffdb1eb-a1ba-42ac-a30f-260004e5b165
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 81%

---

# On-Demand-Inhaltsaktualisierung {#on-demand}

In diesem Abschnitt werden On-Demand-Inhalte für die Verwaltung von Veröffentlichungen beschrieben.

## Verwalten von Veröffentlichungen: Bereitstellen von Inhaltsaktualisierungen von der Autoreninstanz in der Veröffentlichungsinstanz und dann auf dem Gerät {#managing-publication-delivering-content-updates-from-author-to-publish-to-device}

Sie können Inhalte in AEM Screens veröffentlichen und deren Veröffentlichung aufheben. Mit der Funktion „Veröffentlichung verwalten“ können Sie Inhaltsaktualisierungen von der Autoreninstanz in der Veröffentlichungsinstanz und dann auf Geräten bereitstellen. Sie können Inhalte für Ihr gesamtes AEM Screens-Projekt oder nur für einzelne Kanäle, Standorte, Geräte, Anwendungen oder einen Zeitplan veröffentlichen bzw. die Veröffentlichung aufheben. 

### Verwalten von Veröffentlichungen für ein AEM Screens-Projekt {#managing-publication-for-an-aem-screens-project}

Gehen Sie wie folgt vor, um für ein AEM Screens-Projekt Inhaltsaktualisierungen von der Autoreninstanz in der Veröffentlichungsinstanz und von dort auf einem Gerät bereitzustellen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt.
1. Klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**, um das Projekt in Ihrer Veröffentlichungsinstanz zu veröffentlichen.

   ![screen_shot_2019-02-25at21420pm](assets/screen_shot_2019-02-25at21420pm.png)

1. Die **Veröffentlichung verwalten** Der Assistent wird geöffnet. Sie können auf die **Aktion** klicken und auch den Zeitpunkt der Veröffentlichung für jetzt oder später planen. Klicken Sie auf **Weiter**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Markieren Sie das Kontrollkästchen, damit Sie das gesamte Projekt aus dem **`Manage Publication`**-Assistenten anklicken können.

   ![screen_shot_2019-02-25at22712pm](assets/screen_shot_2019-02-25at22712pm.png)

1. Klicken Sie in der Aktionsleiste auf **+ Untergeordnete Elemente einbeziehen** und deaktivieren Sie alle Optionen, damit Sie alle Module in Ihrem Projekt veröffentlichen können. Klicken Sie dann zum Veröffentlichen auf **Hinzufügen**.

   >[!NOTE]
   >
   >Standardmäßig sind alle Kästchen markiert und Sie müssen die Kontrollkästchen manuell deaktivieren, um alle Module in Ihrem Projekt zu veröffentlichen.

   ![screen_shot_2019-02-25at23116pm](assets/screen_shot_2019-02-25at23116pm.png)

   **Dialogfeld „Untergeordnete Elemente einbeziehen“**

   Die oben beschriebenen Schritte zeigen, wie Sie den gesamten Inhalt veröffentlichen können. Falls Sie die anderen drei verfügbaren Alternativen verwenden möchten, müssen Sie die entsprechende Option aktivieren.
Die folgende Abbildung zeigt beispielsweise, wie Sie nur die geänderten Seiten in Ihrem Projekt verwalten und aktualisieren können:
   ![Bild](assets/author-publish-manage.png)

   Lesen Sie die nachstehenden Erläuterungen, um sich mit den verfügbaren Optionen vertraut zu machen:

   1. **Nur unmittelbar untergeordnete Elemente einbeziehen**:
Mit dieser Option können Sie Aktualisierungen verwalten, die nur für die Unterknoten in Ihrer Projektstruktur gelten.
   1. **Nur geänderte Seiten einschließen**:
Mit dieser Option können Sie Aktualisierungen verwalten, die nur für die geänderten Seiten des Projekts gelten, auf denen sich die Änderungen in Ihrer Projektstruktur befinden.
   1. **Nur bereits veröffentlichte Seiten einschließen**:
Mit dieser Option können Sie Aktualisierungen verwalten, die nur für zuvor veröffentlichte Seiten gelten.


1. Klicken Sie im **`Manage Publication wizard`** auf **Veröffentlichen**.

   ![screen_shot_2019-02-25at23341pm](assets/screen_shot_2019-02-25at23341pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.
   >
   >
   >    1. Der Workflow funktioniert nicht, wenn keine Änderungen am Projekt vorgenommen wurden und keine **Offline-Inhalte aktualisiert** werden.
   >    1. Der Workflow funktioniert nicht, wenn der Autor den Replikationsprozess nicht abgeschlossen hat (Inhalte werden weiterhin in die Veröffentlichungsinstanz hochgeladen), nachdem Sie die **Veröffentlichen** im Workflow zur Verwaltung von Veröffentlichungen.

   >[!CAUTION]
   >Wenn Sie als Inhaltsersteller die Änderungen auf den Geräten sehen möchten, die mit der Autoreninstanz verbunden sind, klicken Sie auf **Offline-Inhalt aktualisieren** über das Kanal-Dashboard oder durch Auswahl des Projekts. In diesem Fall wird die Aktualisierung von Offline-Inhalten nur in der Autoreninstanz durchgeführt.

1. Navigieren Sie zum Projekt und klicken Sie in der Aktionsleiste auf **Offline-Inhalt aktualisieren**. Mit dieser Aktion wird derselbe Befehl an die Veröffentlichungsinstanz weitergeleitet, sodass die Offline-Zips auch auf Ihrer Veröffentlichungsinstanz erstellt werden.

   ![screen_shot_2019-02-25at23451pm](assets/screen_shot_2019-02-25at23451pm.png)


   >[!NOTE]
   >
   >Nachdem Sie den Workflow für die Verwaltung von Veröffentlichungen abgeschlossen haben und wenn ein Player auf die Autoreninstanz verweist, sollten Sie „Offline-Inhalt aktualisieren“ in der Autoreninstanz auslösen. Dadurch wird die Offline-Aktualisierung in der Autoreninstanz erstellt.

   >[!CAUTION]
   >
   >Lösen Sie „Offline-Inhalt aktualisieren“ in der Autoreninstanz aus, wenn Sie über einen beim Autoren-Server registrierten Player verfügen. Für den in der Veröffentlichungsinstanz registrierten Player ist keine Aktualisierung des Offline-Inhalts erforderlich.

### Verwalten von Veröffentlichungen für einen Kanal {#managing-publication-for-a-channel}

Gehen Sie wie folgt vor, um Inhaltsaktualisierungen von der Autoreninstanz in der Veröffentlichungsinstanz und von dort auf einem Gerät für einen Kanal in einem AEM Screens-Projekt bereitzustellen:

>[!NOTE]
>
>Folgen Sie diesem Abschnitt nur, wenn Änderungen in einem Kanal vorliegen. Wenn ein Kanal nach der vorherigen Aktualisierung der Offline-Inhalte keine Änderungen aufweist, funktioniert der Verwaltungs-Workflow für die Veröffentlichung eines einzelnen Kanals nicht.

1. Navigieren Sie zu Ihrem AEM Screens-Projekt und klicken Sie auf den Kanal.
1. Klicken Sie in der Aktionsleiste auf die Option **Veröffentlichung verwalten**, um den Kanal in der Veröffentlichungsinstanz zu veröffentlichen.

   ![screen_shot_2019-02-07at115800am](assets/screen_shot_2019-02-07at115800am.png)

1. Die **Veröffentlichung verwalten** Der Assistent wird geöffnet. Sie können auf die **Aktion** klicken und auch den Zeitpunkt der Veröffentlichung für jetzt oder später planen. Klicken Sie auf **Weiter**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Klicken Sie im Assistenten **`Manage Publication`** auf die Option **Veröffentlichen**. 

   ![screen_shot_2019-02-07at120507pm](assets/screen_shot_2019-02-07at120507pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.

1. Wenn Sie **Offline-Inhalt aktualisieren** im Kanal-Dashboard auslösen, wird der Offline-Inhalt lediglich per Push an die Autoreninstanz übertragen, nicht aber an die Veröffentlichungsinstanz. Die Schritte 1 bis 4 dienen zur Push-Übertragung von Offline-Inhalten an die Veröffentlichungsinstanz.

   ![screen_shot_2019-02-07at21608pm](assets/screen_shot_2019-02-07at21608pm.png)

   >[!CAUTION]
   >
   >Veröffentlichen Sie zuerst die Offline-Inhalte und lösen Sie dann „Offline-Inhalt aktualisieren“ aus, wie in den vorhergehenden Schritten zusammengefasst.

### Neuzuweisung von Kanälen und Geräten: {#channel-and-device-re-assignment}

Wenn Sie ein Gerät neu zugewiesen haben, veröffentlichen Sie sowohl die Erstanzeige als auch die neue Anzeige, nachdem das Gerät der neuen Anzeige neu zugewiesen wurde.

Wenn Sie einen Kanal erneut zugewiesen haben, veröffentlichen Sie sowohl die Erstanzeige als auch die neue Anzeige, nachdem der Kanal der neuen Anzeige neu zugewiesen wurde.
