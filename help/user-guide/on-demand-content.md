---
title: On-Demand Content Update
seo-title: On-Demand Content Update
description: 'Folgen Sie dieser Seite, um mehr über das On-Demand Content Update zu erfahren.  '
seo-description: 'Folgen Sie dieser Seite, um mehr über das On-Demand Content Update zu erfahren.  '
uuid: 18b9d175-ff26-42db-86aa-5ea978909f71
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 221243c537e708aac44145c8d5d5a181ea80a293

---


# On-Demand Content Update {#on-demand}

In diesem Abschnitt werden On-Demand-Inhalte für die Verwaltung von Veröffentlichungen beschrieben.

## Verwalten von Veröffentlichungen: Bereitstellen von Inhaltsaktualisierungen vom Autor zum Veröffentlichen auf dem Gerät {#managing-publication-delivering-content-updates-from-author-to-publish-to-device}

Sie können Inhalte über AEM-Bildschirme veröffentlichen und die Veröffentlichung rückgängig machen. Mit der Funktion "Veröffentlichung verwalten"können Sie Inhaltsaktualisierungen vom Autor an das Gerät senden, um sie zu veröffentlichen. Sie können Inhalte für Ihr gesamtes AEM Screens-Projekt oder nur für einen Ihrer Kanäle, Standorte, Geräte, Anwendungen oder einen Zeitplan veröffentlichen oder die Veröffentlichung rückgängig machen.

### Verwalten von Veröffentlichungen für ein AEM Screens-Projekt {#managing-publication-for-an-aem-screens-project}

Führen Sie die folgenden Schritte aus, um Inhaltsaktualisierungen vom Autor zum Veröffentlichen auf dem Gerät für ein AEM Screens-Projekt bereitzustellen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt.
1. Klicken Sie in der Aktionsleiste auf Veröffentlichung **verwalten** , um das Projekt zur Veröffentlichungsinstanz zu veröffentlichen.

   ![screen_shot_2019-02-25at21420pm](assets/screen_shot_2019-02-25at21420pm.png)

1. The **Manage Publication** wizard opens. Sie können die **Aktion** auswählen und auch die Veröffentlichungszeit für jetzt oder später planen. Klicken Sie auf **Weiter**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Markieren Sie das Kästchen, um das gesamte Projekt im Assistenten **"Veröffentlichung** verwalten"auszuwählen.

   ![screen_shot_2019-02-25at22712pm](assets/screen_shot_2019-02-25at22712pm.png)

1. Klicken Sie in der Aktionsleiste auf **+ Untergeordnete Elemente** einschließen, deaktivieren Sie alle Optionen, um alle Module im Projekt zu veröffentlichen, und klicken Sie auf **Hinzufügen** , um sie zu veröffentlichen.

   >[!NOTE]
   >
   >Standardmäßig werden alle Felder markiert und Sie müssen die Kontrollkästchen manuell deaktivieren, um alle Module in Ihrem Projekt zu veröffentlichen.

   ![screen_shot_2019-02-25at23116pm](assets/screen_shot_2019-02-25at23116pm.png)

   **Dialogfeld "Untergeordnete Elemente einschließen"**

   Der oben erwähnte Schritt zeigt, wie Sie den gesamten Inhalt veröffentlichen können. Falls Sie die anderen drei verfügbaren Alternativen verwenden möchten, müssen Sie diese Option aktivieren.
Beispielsweise können Sie mit der folgenden Abbildung nur die geänderten Seiten in Ihrem Projekt verwalten und aktualisieren:
   ![image](assets/author-publish-manage.png)

   Befolgen Sie die folgenden Erläuterungen, um die verfügbaren Optionen zu verstehen:

   1. **Nur unmittelbar untergeordnete Elemente**einschließen:
Mit dieser Option können Sie Updates nur für die Unterknoten in Ihrer Projektstruktur verwalten.
   1. **Nur geänderte Seiten**einschließen:
Mit dieser Option können Sie nur Updates auf den geänderten Seiten des Projekts verwalten, auf denen die Änderungen in Ihrer Projektstruktur gefunden werden.
   1. **Nur bereits veröffentlichte Seiten**einschließen:
Mit diesen Optionen können Updates nur für die zuvor veröffentlichten Seiten verwaltet werden.


1. Klicken Sie im Assistenten "Veröffentlichung **verwalten"auf**"Veröffentlichen **".**

   ![screen_shot_2019-02-25at23341pm](assets/screen_shot_2019-02-25at23341pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.
   >
   >
   >Die Funktion "Veröffentlichung **** verwalten"mit Offlineinhalt aktualisieren ist ein zweistufiger Vorgang und die Schritte müssen in der richtigen Reihenfolge ausgeführt werden.
   >
   >
   >
   >    1. Der Arbeitsablauf funktioniert nicht, wenn **Offline-Inhalte** aktualisieren vor der Veröffentlichung mit **Veröffentlichung** verwalten ausgelöst wird.
      >
      >    
   1. Der Arbeitsablauf funktioniert nicht, wenn keine Änderungen am Projekt vorgenommen wurden und keine **Offline-Inhalte** aktualisiert werden müssen.
   >    1. Der Workflow funktioniert nicht, wenn der Autor den Replizierungsprozess nicht abgeschlossen hat (Inhalte werden weiterhin in die Veröffentlichungsinstanz hochgeladen), nachdem im Arbeitsablauf für die Verwaltung der Veröffentlichung auf die Schaltfläche " **Veröffentlichen** "geklickt wurde.


1. Nachdem Sie den Arbeitsablauf zum Verwalten von Veröffentlichungen abgeschlossen haben, müssen Sie den Offlineinhalt des Autors aktualisieren, damit das Update offline in der Autoreninstanz erstellt wird.

   Navigieren Sie zum Projekt und klicken Sie in der Aktionsleiste auf "Offline-Inhalte **aktualisieren"** . Mit dieser Aktion wird derselbe Befehl an die Veröffentlichungsinstanz weitergeleitet, sodass die Offline-Zips auch in der Veröffentlichungsinstanz erstellt werden.

   ![screen_shot_2019-02-25at23451pm](assets/screen_shot_2019-02-25at23451pm.png)

   >[!CAUTION]
   >
   >Zunächst müssen Sie den Offlineinhalt aktualisieren und dann auslösen, wie in den vorherigen Schritten zusammengefasst.

### Verwalten der Veröffentlichung für einen Kanal {#managing-publication-for-a-channel}

Führen Sie die folgenden Schritte aus, um Inhaltsaktualisierungen vom Autor zum Veröffentlichen auf einem Gerät für einen Kanal in einem AEM-Screens-Projekt bereitzustellen:

>[!NOTE]
>
>Befolgen Sie diesen Abschnitt nur, wenn Änderungen in einem Kanal vorliegen. Wenn in einem Kanal nach der vorherigen Aktualisierung des Offlineinhalts keine Änderungen vorgenommen wurden, funktioniert der Arbeitsablauf zur Verwaltung der Veröffentlichung für einen einzelnen Kanal nicht.

1. Navigieren Sie zu Ihrem Screens-Projekt und wählen Sie den Kanal aus.
1. Klicken Sie in der Aktionsleiste auf Veröffentlichung **verwalten** , um den Kanal zur Veröffentlichungsinstanz zu veröffentlichen.

   ![screen_shot_2019-02-07at115800am](assets/screen_shot_2019-02-07at115800am.png)

1. The **Manage Publication** wizard opens. Sie können die **Aktion** auswählen und auch die Veröffentlichungszeit für jetzt oder später planen. Klicken Sie auf **Weiter**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Klicken Sie im Assistenten "Veröffentlichung **verwalten"auf**"Veröffentlichen **".**

   ![screen_shot_2019-02-07at120507pm](assets/screen_shot_2019-02-07at120507pm.png)

   >[!NOTE]
   >
   >Warten Sie einige Sekunden/Minuten, damit der Inhalt die Veröffentlichungsinstanz erreicht.

1. Nachdem Sie den Arbeitsablauf zum Verwalten von Veröffentlichungen abgeschlossen haben, müssen Sie den Offlineinhalt des Autors aktualisieren, damit das Update offline in der Autoreninstanz erstellt wird.

   Navigieren Sie zum Kanal-Dashboard und klicken Sie auf Offline-Inhalt **aktualisieren**. Mit dieser Aktion wird derselbe Befehl an die Veröffentlichungsinstanz weitergeleitet, sodass die Offline-Zips auch in der Veröffentlichungsinstanz erstellt werden.

   ![screen_shot_2019-02-07at21608pm](assets/screen_shot_2019-02-07at21608pm.png)

   >[!CAUTION]
   >
   >Zunächst müssen Sie den Offlineinhalt aktualisieren und dann auslösen, wie in den vorherigen Schritten zusammengefasst.

### Kanal- und Gerätewiederzuweisung: {#channel-and-device-re-assignment}

Wenn Sie ein Gerät neu zugewiesen haben, müssen Sie sowohl die Erstanzeige als auch die neue Anzeige veröffentlichen, nachdem das Gerät der neuen Anzeige neu zugewiesen wurde.

Wenn Sie einen Kanal erneut zugewiesen haben, müssen Sie sowohl die Erstanzeige als auch die neue Anzeige veröffentlichen, sobald der Kanal der neuen Anzeige neu zugewiesen wurde.