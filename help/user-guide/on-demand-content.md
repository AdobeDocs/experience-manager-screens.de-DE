---
title: On-Demand-Inhaltsaktualisierungen
description: Erfahren Sie mehr über On-Demand-Inhaltsaktualisierungen zum Verwalten von Veröffentlichungen.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer
level: Intermediate
exl-id: 9ffdb1eb-a1ba-42ac-a30f-260004e5b165
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 31%

---

# On-Demand-Inhaltsaktualisierungen {#on-demand}

In diesem Abschnitt werden On-Demand-Inhalte für die Verwaltung von Veröffentlichungen beschrieben.

## Veröffentlichung verwalten: Bereitstellen von Inhaltsaktualisierungen von der Autoren- zur Veröffentlichungsinstanz auf dem Gerät {#managing-publication-delivering-content-updates-from-author-to-publish-to-device}

Sie können Inhalte in AEM Screens veröffentlichen und deren Veröffentlichung aufheben. Mit der Funktion „Veröffentlichung verwalten“ können Sie Inhaltsaktualisierungen von der Autoren- zur Veröffentlichungsinstanz auf dem Gerät bereitstellen. Sie können Inhalte für Ihr gesamtes AEM Screens-Projekt oder nur für einen Ihrer Kanäle, Standorte, Geräte, Programme oder einen Zeitplan veröffentlichen bzw. die Veröffentlichung aufheben.

### Verwalten von Veröffentlichungen für ein AEM Screens-Projekt {#managing-publication-for-an-aem-screens-project}

Gehen Sie wie folgt vor, um Inhaltsaktualisierungen für ein AEM Screens-Projekt von der Autoren- zur Veröffentlichungsinstanz auf das Gerät zu übertragen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt.
1. Auswählen **Veröffentlichung verwalten** in der Aktionsleiste aus, damit Sie das Projekt in Ihrer Veröffentlichungsinstanz veröffentlichen können.

   ![screen_shot_2019-02-25at21420pm](assets/screen_shot_2019-02-25at21420pm.png)

1. Der Assistent **Veröffentlichung verwalten** wird geöffnet. Sie können die **Aktion** auswählen und auch die Veröffentlichungszeit für jetzt oder später planen. Wählen Sie **Weiter** aus.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Aktivieren Sie das Kontrollkästchen, um das gesamte Projekt aus der **`Manage Publication`** Assistent.

   ![screen_shot_2019-02-25at22712pm](assets/screen_shot_2019-02-25at22712pm.png)

1. Auswählen **+ Untergeordnete Elemente einbeziehen** in der Aktionsleiste aus und deaktivieren Sie alle Optionen, damit Sie alle Module in Ihrem Projekt veröffentlichen und auswählen können **Hinzufügen** zur Veröffentlichung.

   >[!NOTE]
   >
   >Standardmäßig sind alle Kontrollkästchen aktiviert. Sie müssen die Kontrollkästchen manuell deaktivieren, um alle Module in Ihrem Projekt zu veröffentlichen.

   ![screen_shot_2019-02-25at23116pm](assets/screen_shot_2019-02-25at23116pm.png)

   **Dialogfeld „Untergeordnete Elemente einbeziehen“**

   Die oben genannten Schritte zeigen, wie Sie den gesamten Inhalt veröffentlichen können. Wenn Sie die anderen drei verfügbaren Alternativen verwenden möchten, müssen Sie diese bestimmte Option aktivieren.
Die folgende Abbildung zeigt beispielsweise, wie Sie nur die geänderten Seiten in Ihrem Projekt verwalten und aktualisieren können:
   ![Bild](assets/author-publish-manage.png)

   Befolgen Sie die unten stehenden Erläuterungen, um die verfügbaren Optionen zu verstehen:

   1. **Nur unmittelbar untergeordnete Elemente einbeziehen**: Mit dieser Option können Sie Aktualisierungen nur für die Unterknoten in Ihrer Projektstruktur verwalten.
   1. **Nur geänderte Seiten einbeziehen**: Mit dieser Option können Sie Aktualisierungen nur für die geänderten Seiten des Projekts verwalten, auf denen sich die Änderungen in Ihrer Projektstruktur befinden.
   1. **Nur bereits veröffentlichte Seiten einbeziehen**: Mit dieser Option können Sie Aktualisierungen nur für die Seiten verwalten, die zuvor veröffentlicht wurden.


1. Aus dem **`Manage Publication wizard`**, auswählen **Veröffentlichen**.

   ![screen_shot_2019-02-25at23341pm](assets/screen_shot_2019-02-25at23341pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.
   >
   >
   >    1. Der Workflow funktioniert nicht, wenn sich das Projekt nicht ändert und es keine Änderungen für gibt. **Offline-Inhalt aktualisieren**.
   >    1. Der Workflow funktioniert nicht, wenn der Autor den Replikationsprozess nicht abgeschlossen hat (Inhalte werden weiterhin in die Veröffentlichungsinstanz hochgeladen), nachdem im Workflow für die Verwaltung der Veröffentlichung auf **Veröffentlichen** geklickt wurde.

   >[!CAUTION]
   >Wenn Sie als Autor oder Ersteller von Inhalten die Änderungen auf den Geräten sehen möchten, die mit der Autoreninstanz verbunden sind, klicken Sie im Kanal-Dashboard auf **Offline-Inhalte aktualisieren** oder wählen Sie das Projekt aus. In diesem Fall wird der Offline-Inhalt nur in der Autoreninstanz aktualisiert.

1. Navigieren Sie zum Projekt und klicken Sie in der Aktionsleiste auf **Offline-Inhalt aktualisieren**. Diese Aktion leitet denselben Befehl an die Veröffentlichungsinstanz weiter, sodass die Offline-ZIPs auch auf der Veröffentlichungsinstanz erstellt werden.

   ![screen_shot_2019-02-25at23451pm](assets/screen_shot_2019-02-25at23451pm.png)


   >[!NOTE]
   >
   >Nachdem Sie den Workflow Veröffentlichung verwalten abgeschlossen haben und ein Player auf die Autoreninstanz verweist, müssen Sie den Trigger Offline-Inhalte in der Autoreninstanz aktualisieren ausführen. Dadurch wird die Aktualisierung offline in der Autoreninstanz erstellt.

   >[!CAUTION]
   >
   >Trigger : Aktualisieren von Offline-Inhalten in der Autoreninstanz, wenn ein Player auf dem Autorenserver registriert ist. Die Aktualisierung von Offline-Inhalten ist für den Player, der bei der Veröffentlichungsinstanz registriert ist, nicht erforderlich.

### Verwalten der Veröffentlichung für einen Kanal {#managing-publication-for-a-channel}

Gehen Sie wie folgt vor, um Inhaltsaktualisierungen für einen Kanal in einem AEM Screens-Projekt über Autor > Veröffentlichen > Gerät bereitzustellen:

>[!NOTE]
>
>Folgen Sie diesem Abschnitt nur, wenn Änderungen in einem Kanal vorliegen. Wenn ein Kanal nach der vorherigen Aktualisierung der Offline-Inhalte keine Änderungen aufweist, funktioniert der Verwaltungs-Workflow für die Veröffentlichung eines einzelnen Kanals nicht.

1. Navigieren Sie zu Ihrem AEM Screens-Projekt und wählen Sie den Kanal aus.
1. Auswählen **Veröffentlichung verwalten** in der Aktionsleiste aus, damit Sie den Kanal in Ihrer Veröffentlichungsinstanz veröffentlichen können.

   ![screen_shot_2019-02-07at115800am](assets/screen_shot_2019-02-07at115800am.png)

1. Der Assistent **Veröffentlichung verwalten** wird geöffnet. Sie können die **Aktion** auswählen und auch die Veröffentlichungszeit für jetzt oder später planen. Wählen Sie **Weiter** aus.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Auswählen **Veröffentlichen** vom **`Manage Publication`** Assistent.

   ![screen_shot_2019-02-07at120507pm](assets/screen_shot_2019-02-07at120507pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.

1. Auslösen **Offline-Inhalt aktualisieren** im Kanal-Dashboard überträgt nur den Offline-Inhalt an die Autoreninstanz, nicht aber an die Veröffentlichungsinstanz. Die Schritte 1-4 dienen zum Pushen von Offline-Inhalten an die Veröffentlichungsinstanz.

   ![screen_shot_2019-02-07at21608pm](assets/screen_shot_2019-02-07at21608pm.png)

   >[!CAUTION]
   >
   >Veröffentlichen Sie zuerst und aktualisieren Sie dann den Offline-Inhalt mit einem Trigger, wie in den vorherigen Schritten zusammengefasst.

### Neuzuweisung von Kanälen und Geräten: {#channel-and-device-re-assignment}

Wenn Sie ein Gerät neu zugewiesen haben, müssen Sie sowohl das erste Display als auch das neue Display veröffentlichen, sobald das Gerät dem neuen Display neu zugewiesen wurde.

Wenn Sie einen Kanal neu zugewiesen haben, müssen Sie entsprechend sowohl die erste als auch die neue Anzeige veröffentlichen, sobald der Kanal der neuen Anzeige neu zugewiesen wurde.
