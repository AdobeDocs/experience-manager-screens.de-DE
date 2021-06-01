---
title: On-Demand-Inhaltsaktualisierungen
seo-title: On-Demand-Inhaltsaktualisierungen
description: 'Auf dieser Seite erfahren Sie mehr über On-Demand-Inhaltsaktualisierungen.  '
seo-description: 'Auf dieser Seite erfahren Sie mehr über On-Demand-Inhaltsaktualisierungen.  '
uuid: 18b9d175-ff26-42db-86aa-5ea978909f71
contentOwner: Jyotika Syal
feature: Inhaltserstellung in Screens
role: Developer
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 100%

---


# On-Demand-Inhaltsaktualisierungen {#on-demand}

In diesem Abschnitt werden On-Demand-Inhalte für die Verwaltung von Veröffentlichungen beschrieben.

## Verwalten von Veröffentlichungen: Bereitstellen von Inhaltsaktualisierungen vom Autor zur Veröffentlichung auf dem Gerät {#managing-publication-delivering-content-updates-from-author-to-publish-to-device}

Sie können Inhalte in AEM Screens veröffentlichen und deren Veröffentlichung aufheben. Mit der Funktion „Veröffentlichung verwalten“ können Sie Inhaltsaktualisierungen vom Autor an das Gerät senden, um sie zu veröffentlichen. Sie können Inhalte für Ihr gesamtes AEM Screens-Projekt oder nur für einzelne Kanäle, Standorte, Geräte, Anwendungen oder einen Zeitplan veröffentlichen oder die Veröffentlichung aufheben.

### Verwalten von Veröffentlichungen für ein AEM Screens-Projekt {#managing-publication-for-an-aem-screens-project}

Gehen Sie wie folgt vor, um Inhaltsaktualisierungen vom Autor zur Veröffentlichung auf dem Gerät für ein AEM Screens-Projekt bereitzustellen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt.
1. Klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**, um das Projekt in der Veröffentlichungsinstanz zu veröffentlichen.

   ![screen_shot_2019-02-25at21420pm](assets/screen_shot_2019-02-25at21420pm.png)

1. Der Assistent **Veröffentlichung verwalten** wird geöffnet. Sie können die **Aktion** auswählen und auch die Veröffentlichungszeit für jetzt oder später planen. Klicken Sie auf **Weiter**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Markieren Sie das Kästchen, um das gesamte Projekt im Assistenten **Veröffentlichung verwalten** auszuwählen.

   ![screen_shot_2019-02-25at22712pm](assets/screen_shot_2019-02-25at22712pm.png)

1. Klicken Sie in der Aktionsleiste auf **+Untergeordnete Elemente einbeziehen**. Deaktivieren Sie alle Optionen, um alle Module im Projekt zu veröffentlichen, und klicken Sie auf **Hinzufügen**, um sie zu veröffentlichen.

   >[!NOTE]
   >
   >Standardmäßig werden alle Felder markiert und Sie müssen die Kontrollkästchen manuell deaktivieren, um alle Module in Ihrem Projekt zu veröffentlichen.

   ![screen_shot_2019-02-25at23116pm](assets/screen_shot_2019-02-25at23116pm.png)

   **Dialogfeld „Untergeordnete Elemente einbeziehen“**

   Der oben erwähnte Schritt zeigt, wie Sie den gesamten Inhalt veröffentlichen können. Falls Sie die anderen drei verfügbaren Alternativen verwenden möchten, müssen Sie die entsprechende Option aktivieren.
Mit der folgenden Abbildung können Sie z. B. nur die geänderten Seiten in Ihrem Projekt verwalten und aktualisieren:
   ![image](assets/author-publish-manage.png)

   Folgen Sie den nachstehenden Erläuterungen, um die verfügbaren Optionen zu verstehen:

   1. **Nur unmittelbar untergeordnete Elemente einbeziehen**:
Mit dieser Option können Sie Aktualisierungen verwalten, die nur für die Unterknoten in Ihrer Projektstruktur gelten.
   1. **Nur geänderte Seiten einschließen**:
Mit dieser Option können Sie Aktualisierungen verwalten, die nur für die geänderten Seiten des Projekts gelten, auf denen sich die Änderungen in Ihrer Projektstruktur befinden.
   1. **Nur bereits veröffentlichte Seiten einschließen**:
Mit diesen Optionen können Sie Aktualisierungen verwalten, die nur für zuvor veröffentlichte Seiten gelten.


1. Klicken Sie auf **Veröffentlichen** im Assistenten **Veröffentlichung verwalten**.

   ![screen_shot_2019-02-25at23341pm](assets/screen_shot_2019-02-25at23341pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.
   >
   >
   >    1. Der Workflow funktioniert nicht, wenn keine Änderungen am Projekt vorgenommen wurden und keine **Offline-Inhalte aktualisiert** werden.
   >    1. Der Workflow funktioniert nicht, wenn der Autor den Replikationsprozess nicht abgeschlossen hat (Inhalte werden weiterhin in die Veröffentlichungsinstanz hochgeladen), nachdem im Workflow für die Verwaltung der Veröffentlichung auf **Veröffentlichen** geklickt wurde.


   >[!CAUTION]
   >Wenn Sie als Autor oder Ersteller von Inhalten die Änderungen auf den Geräten sehen möchten, die mit der Autoreninstanz verbunden sind, klicken Sie im Kanal-Dashboard auf **Offline-Inhalte aktualisieren** oder wählen Sie das Projekt aus. In diesem Fall wird der Offline-Inhalt nur in der Autoreninstanz aktualisiert.

1. Navigieren Sie zum Projekt und klicken Sie in der Aktionsleiste auf **Offline-Inhalt aktualisieren**. Mit dieser Aktion wird derselbe Befehl an die Veröffentlichungsinstanz weitergeleitet, sodass die Offline-ZIP-Dateien auch in der Veröffentlichungsinstanz erstellt werden.

   ![screen_shot_2019-02-25at23451pm](assets/screen_shot_2019-02-25at23451pm.png)


   >[!NOTE]
   >
   >Nachdem Sie den Workflow zum Verwalten von Veröffentlichungen abgeschlossen haben, müssen Sie die Aktualisierung der Offline-Inhalte des Autors auslösen, wenn ein Player auf die Autoreninstanz verweist. Dadurch wird die Aktualisierung offline auf der Autoreninstanz durchgeführt.

   >[!CAUTION]
   >
   >Sie müssen die Aktualisierung der Offline-Inhalte in der Autoreninstanz auslösen, wenn Sie einen beim Autorenserver registrierten Player haben. Die Aktualisierung von Offline-Inhalten ist für den in der Veröffentlichungsinstanz registrierten Player nicht erforderlich.

### Verwalten der Veröffentlichung für einen Kanal {#managing-publication-for-a-channel}

Gehen Sie wie folgt vor, um Inhaltsaktualisierungen vom Autor zur Veröffentlichung auf dem Gerät für einen Kanal in einem AEM Screens-Projekt bereitzustellen:

>[!NOTE]
>
>Folgen Sie diesem Abschnitt nur, wenn Änderungen in einem Kanal vorliegen. Wenn ein Kanal nach der vorherigen Aktualisierung der Offline-Inhalte keine Änderungen aufweist, funktioniert der Verwaltungs-Workflow für die Veröffentlichung eines einzelnen Kanals nicht.

1. Navigieren Sie zu Ihrem Screens-Projekt und wählen Sie den Kanal aus.
1. Klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**, um den Kanal in der Veröffentlichungsinstanz zu veröffentlichen.

   ![screen_shot_2019-02-07at115800am](assets/screen_shot_2019-02-07at115800am.png)

1. Der Assistent **Veröffentlichung verwalten** wird geöffnet. Sie können die **Aktion** auswählen und auch die Veröffentlichungszeit für jetzt oder später planen. Klicken Sie auf **Weiter**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Klicken Sie auf **Veröffentlichen** im Assistenten **Veröffentlichung verwalten**.

   ![screen_shot_2019-02-07at120507pm](assets/screen_shot_2019-02-07at120507pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.

1. Der Auslöser **Offline-Inhalte aktualisieren** im Kanal-Dashboard sendet den Offline-Inhalt nur an die Autoreninstanz, nicht aber an die Veröffentlichungsinstanz. Schritte 1 bis 4 dienen zum Senden von Offline-Inhalten an die Veröffentlichungsinstanz.

   ![screen_shot_2019-02-07at21608pm](assets/screen_shot_2019-02-07at21608pm.png)

   >[!CAUTION]
   >
   >Sie müssen zuerst die Offline-Inhalte veröffentlichen und dann die Aktualisierung auslösen, wie in den vorhergehenden Schritten zusammengefasst.

### Neuzuweisung von Kanälen und Geräten: {#channel-and-device-re-assignment}

Wenn Sie ein Gerät neu zugewiesen haben, müssen Sie sowohl die Erstanzeige als auch die neue Anzeige veröffentlichen, nachdem das Gerät der neuen Anzeige neu zugewiesen wurde.

Wenn Sie einen Kanal erneut zugewiesen haben, müssen Sie sowohl die Erstanzeige als auch die neue Anzeige veröffentlichen, sobald der Kanal der neuen Anzeige neu zugewiesen wurde.