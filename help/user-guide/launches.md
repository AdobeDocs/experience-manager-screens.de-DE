---
title: Inhaltsaktualisierung mit Screenstart
seo-title: Inhaltsaktualisierung mit Screenstart
description: Autoren von Inhalten können zukünftige Versionen von Kanälen erstellen, die als Launch bezeichnet werden. Wenn Sie das Live-Datum für diesen Launch festlegen, können Inhalte auf Geräten oder Playern live geschaltet werden.
seo-description: Autoren von Inhalten können zukünftige Versionen von Kanälen erstellen, die als Launch bezeichnet werden. Wenn Sie das Live-Datum für diesen Launch festlegen, können Inhalte auf Geräten oder Playern live geschaltet werden.
uuid: fb13117c-b99b-48bd-adb6-040dbd13af16
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 9cd8892b-fe5d-4ad3-9b10-10ff068adba6
docset: aem65
translation-type: tm+mt
source-git-commit: 9cc4b31ecd66530a85a7a526e306faf1ec371b2e

---


# Inhaltsaktualisierung mit Screenstart {#launches}

Content authors can create future version of the channel(s), known as **Screens Launch** and further setting live date for this launch allows content to be live in devices or players.

Mithilfe künftiger Veröffentlichungen können Autoren jeden Kanal des Starts Vorschau werden und sollten eine Überprüfungsanfrage starten können. Die Gruppe der Genehmigenden erhält eine Benachrichtigung und kann die Anfrage genehmigen oder ablehnen. Wenn das Live-Datum erreicht ist, wird der Inhalt auf den Geräten abgespielt.

Wenn der Autor z. B. zukünftige Versionen von c1, c2 (Kanäle) erstellen möchte, wird ein Launch erstellt und ein Live-Datum festgelegt (z. B. 10. November, 08:00 Uhr). Alle weiteren Aktualisierungen des Inhalts werden zur Überprüfung gesendet. Nach der Genehmigung und am Live-Datum (10. November, 8:00 Uhr) wird der Inhalt dieses Launches auf den Geräten oder Playern wiedergegeben.

## Voraussetzungen {#requirements}

Bevor Sie mit der Implementierung der zukünftigen Veröffentlichung in einem AEM Screens-Projekt fortfahren, sollten Sie sich mit dem Konzept der Übergangsphase und ihrer Relevanz vertraut machen.

Im folgenden Abschnitt werden die Übergangsphase und weitere Schritte zur standardmäßigen Konfiguration beschrieben. Sie können auch eine Beispieltestkonfiguration herunterladen, um deren Verwendung zu verstehen.

### Verstehen der Übergangsphase {#understanding-grace-period}

The following setup allows the admin to configure the ***Grace Period***, required in future publish.

Die **Übergangsphase** umfasst:

* Promotion des Launches
* Veröffentlichen der Ressourcen zur Veröffentlichung von Instanzen
* Zeit, die die Geräte zum Herunterladen des Inhalts von der Veröffentlichungsinstanz benötigen, sowie etwaige Zeitunterschiede zwischen Server und Player

Angenommen, der Server befindet sich in PST und die Geräte in EST. Die maximale Zeitdifferenz beträgt in diesem Fall 3 Stunden. Es wird davon ausgegangen, dass die Promotion 1 Minute und die Veröffentlichung von der Autoren- auf der Veröffentlichungsinstanz 10 Minuten dauert und der Player die Ressourcen in der Regel in 10-15 Minuten herunterladen kann. Dann ist Übergangsphase = Zeitunterschied (3 Stunden) + Zeit für die Promotion des Launches (1 Min.) + Zeit für die Veröffentlichung des Launches (10 Min.) + Zeit zum Herunterladen auf den Player (10-15 Min.) + Puffer (z. B. 30 Min.) = 3 Stunden 56 Min. = 14160 Sekunden. Wann immer wir also einen Launch live planen, beginnt die Promotion um diesen Zeitversatz früher. In der obigen Gleichung nehmen die meisten Elemente nicht viel Zeit in Anspruch. Wenn wir den maximalen Zeitunterschied zwischen dem Server und einem Player kennen, können wir einen guten Schätzwert für diesen Versatz verwenden.

### Konfigurieren der standardmäßigen Übergangsphase {#configuring-out-of-the-box-grace-period}

Standardmäßig ist die Übergangsphase für einen Launch auf 24 Stunden festgelegt. Das bedeutet, dass die Promotion mit diesem Versatz beginnt, wenn wir für einen Launch der Ressourcen unter */content/screens* ein Live-Datum festlegen. Wenn das Live-Datum beispielsweise auf 24. November, 9:00 Uhr und die Übergangsphase auf 24 Stunden eingestellt ist, beginnt der Promotion-Auftrag am 23. November, 09:00 Uhr.

### Herunterladen von Konfigurationen {#downloading-configurations}

Laden Sie die folgenden Testkonfigurationen herunter:

[Datei laden](assets/launches_event_handlerconfig-10.zip)

>[!NOTE]
>
>Die oben genannte Konfiguration hat in dieser Testkonfiguration 600 Sekunden als Übergangsphase.

#### Aktualisieren der Konfigurationen {#updating-the-configurations}

Wenn Sie die oben beschriebene Konfiguration ändern möchten, gehen Sie wie folgt vor:

* Erstellen Sie die Datei ***sling:OsgiConfig/ nt:file in /apps/system/config*** mit dem Namen **com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config** und Inhalt

   *launches.eventhandler.updatelastmodification=B&quot;false&quot;
launches.eventhandler.launch.promotion.graceperiod=[&quot;/content/screens(/.*):600&quot;]launches.eventhandler.threadpool.maxsize=I&quot;5&quot;
launches.eventhandler.threadpool.priority=&quot;MIN&quot;*

* `launches.eventhandler.launch.promotion.graceperiod=["/content/screens(/.&#42;):600"`, damit können Sie eine Übergangsphase von 600 Sekunden im Pfad */content/screens* einstellen.

Das bedeutet, dass die Promotion mit diesem Versatz beginnt, wenn Sie für einen Launch der Ressourcen unter */content/screens* ein Live-Datum festlegen. Wenn das Live-Datum beispielsweise auf 24. November, 9.00 Uhr und die Übergangsphase auf 600 Sekunden eingestellt ist, beginnt der Promotion-Auftrag am 24. November, 08:50 Uhr.

## Screenstart verwenden {#using-launches}

Führen Sie den folgenden Abschnitt aus, um Starts in Ihrem AEM Screens-Projekt zu implementieren. Dieser Abschnitt behandelt folgende Themen:

1. **Erstellen eines Screenstarts**
1. **Bearbeiten eines Bildschirmstarts zum Festlegen von Live-Datum und -Gültigkeitsbereich**

### Creating a Screens Launch {#creating-a-launch}

Führen Sie die folgenden Schritte aus, um die Funktionen für Startvorgänge in Ihr AEM Screens-Projekt zu implementieren:

1. Create a sequence channel in your AEM Screens project, for example **LaunchesDemo** --> **Channels** --> **FutureLaunch**, as shown below.

   >[!CAUTION]
   >
   >Sie müssen einen Launch aus einem bereits vorhandenen Kanal in Ihrem AEM Screens-Projekt erstellen.

   ![Bild](/help/user-guide/assets/launches-images/launches-11.png)

1. Select the channel **FutureLaunch** and click **Create Launch** from the action bar.

   ![Bild](/help/user-guide/assets/launches-images/launches-12.png)

1. Der Assistent **Launch erstellen** wird geöffnet. Sie können entweder den Kanal auswählen, der bereits im Assistenten angezeigt wird, oder auf **+ Hinzufügen Kanal** klicken, um den Kanal hinzuzufügen, für den Sie den Start erstellen möchten.


#### Verwenden des vorhandenen Kanals {#existing-channel-launch}

1. Wählen Sie den Kanal aus, der bereits im Assistenten zum **Erstellen des Startvorgangs** vorhanden ist, und klicken Sie auf **Weiter**.

   ![image](/help/user-guide/assets/launches-images/launches-b.png)

1. Select the channel and click **Next** from the action bar.

   >[!NOTE]
   >**Die Option &quot;Unterseiten** einschließen&quot;ist standardmäßig aktiviert.

   ![Bild](/help/user-guide/assets/launches-images/launches-b.png)

1. Geben Sie unter **Launch-Titel** den Wert **SummerPromotions** ein. Sie müssen für **Launch-Datum** keinen Wert festlegen, wie in der folgenden Abbildung dargestellt. Klicken Sie auf **Erstellen**.

   >[!NOTE]
   >
   >Wenn Sie die Option **Quellseiten-Live-Daten übernehmen** *aktivieren*, können die Kanäle im Launch als Live Copies erstellt werden. Wenn Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen automatisch auf die Launch-Kanäle angewendet.
   >
   >
   >Durch *Deaktivieren* der Option **Quellseiten-Live-Daten übernehmen** können die Kanäle ohne Live-Beziehung in den Launch kopiert werden. Wenn also Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen nicht auf die Launch-Kanäle angewendet.

   ![Bild](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >Sie können das Live-Launch-Datum in diesem Schritt festlegen oder es später einrichten, während Sie die Eigenschaften des Launches bearbeiten, nachdem er bereits erstellt wurde.

1. Sie sehen, dass Ihr Launch erstellt wurde. Sie können entweder auf **Öffnen** klicken, um die Seiten im Editor anzuzeigen, oder auf **Fertig**, um zu Ihrem Projekt zurückzukehren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Clicking **Done** allows you to navigate back to your **FutureLaunch** channel.

   ![Bild](/help/user-guide/assets/launches-images/launches-16.png)


#### Verwenden der Option &quot;Hinzufügen Kanal&quot; {#add-channel-launch}

1. Klicken Sie auf **+ Hinzufügen Kanal** , um den Kanal hinzuzufügen, für den Sie den Start erstellen möchten.

   ![image](/help/user-guide/assets/launches-images/launches-13.png)

   >[!NOTE]
   >Die **Option &quot;Auswählen** &quot;wird deaktiviert, wenn Sie versuchen, mehrere Kanal oder einen Ordner zum Hinzufügen des Launches auszuwählen.

1. Navigieren Sie zu dem Kanal, für den Sie den Start erstellen möchten, und klicken Sie auf **Auswählen**.

   ![image](/help/user-guide/assets/launches-images/launches-14.png)

1. Jetzt können Sie den hinzugefügten Kanal auswählen, um einen Start für zu erstellen, und auf **Weiter** klicken.

   ![image](/help/user-guide/assets/launches-images/launches-15.png)

1. Geben Sie unter **Launch-Titel** den Wert **SummerPromotions** ein. Sie müssen für **Launch-Datum** keinen Wert festlegen, wie in der folgenden Abbildung dargestellt. Klicken Sie auf **Erstellen**.

   >[!NOTE]
   >
   >Wenn Sie die Option **Quellseiten-Live-Daten übernehmen** *aktivieren*, können die Kanäle im Launch als Live Copies erstellt werden. Wenn Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen automatisch auf die Launch-Kanäle angewendet.
   >
   >
   >Durch *Deaktivieren* der Option **Quellseiten-Live-Daten übernehmen** können die Kanäle ohne Live-Beziehung in den Launch kopiert werden. Wenn also Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen nicht auf die Launch-Kanäle angewendet.

   ![Bild](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >Sie können das Live-Launch-Datum in diesem Schritt festlegen oder es später einrichten, während Sie die Eigenschaften des Launches bearbeiten, nachdem er bereits erstellt wurde.

1. Sie sehen, dass Ihr Launch erstellt wurde. Sie können entweder auf **Öffnen** klicken, um die Seiten im Editor anzuzeigen, oder auf **Fertig**, um zu Ihrem Projekt zurückzukehren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Clicking **Done** allows you to navigate back to your **FutureLaunch** channel.

   ![Bild](/help/user-guide/assets/launches-images/launches-16.png)

### Bearbeiten der Launch-Eigenschaften zum Festlegen des Live-Datums und des Umfangs {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nachdem Sie den Launch erstellt haben, müssen Sie die Launch-Eigenschaften bearbeiten, um das Live-Datum und den Umfang des Launches festzulegen.

Gehen Sie wie folgt vor, um die Eigenschaften für den Launch zu bearbeiten:

1. Navigieren Sie zum Kanal **FutureLaunch**, *(d. h. dem ausstehenden Start)* , und wählen Sie den Kanal aus, wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/launches-images/launches-17.png)

1. Klicken Sie in der Aktionsleiste auf **Dashboard** und Sie sehen das Fenster **AUSSTEHENDE LAUNCHES** im Dashboard Kanal.

   ![image](/help/user-guide/assets/launches-images/launches-18.png)

1. Wählen Sie den Start aus und klicken Sie auf eine der gewünschten Aktionen im Bereich **AUSSTEHENDE LAUNCHES** .

   ![image](/help/user-guide/assets/launches-images/launches-19.png)

1. Sie können beispielsweise auf **Starteigenschaften** klicken, um die Eigenschaften für den Start **SummerPromotions** zu bearbeiten.

   ![image](/help/user-guide/assets/launches-images/launches-20.png)

1. Sie können den **Luanch-Titel** bearbeiten und die folgenden Felder ausfüllen:

   * Wählen Sie das **Launch-Datum** aus
   * Aktivieren Sie **Produktionsbereit**
   * Wählen Sie **Genehmigte Seiten bewerben** aus **Umfang** aus
   **Verstehen der Launch-Einträge unter Automatische Promotion:**

   * **Launch-Datum** bezieht sich auf das Live-Datum, d. h. das Datum (und die Uhrzeit), zu dem der Inhalt im Screens-Player gemäß der Zeitzone des Players wiedergegeben wird.
   * **Produktionsbereit** ermöglicht die Promotion von Kanälen und bedeutet, dass der Launch verwendet werden kann.
   * **Umfang** bezieht sich auf die Kanäle, die während eines Launches beworben werden können.
   Die folgenden drei Optionen stehen zur Einrichtung des Umfangs zur Verfügung:

   * **Vollständigen Launch bewerben**: Alle Kanäle des Launches werden am festgelegten Live-Datum beworben.
   * **Geänderte Seiten bewerben**: Es werden nur bearbeitete Launch-Ressourcen beworben. Es wird empfohlen, diese Option zu verwenden, wenn keine Launch-Überprüfung erforderlich ist. Dadurch können Änderungen in den Launch-Kanälen beworben werden.
   * **Genehmigte Seiten bewerben**: Nur genehmigte Seiten werden am festgelegten Live-Datum beworben.

      >[!CAUTION]
      >
      >Bei der Promotion des Launches wird die Zeitzone des Players/Geräts und nicht die des Servers berücksichtigt.



1. Klicken Sie auf **Speichern und schließen**, um zurück zum Kanal **FutureLaunch** zu navigieren.

