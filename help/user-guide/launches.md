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
source-git-commit: 14a45b58862477ec6be082ab1c059f991b086755

---


# Inhaltsaktualisierung mit Screenstart {#launches}

Autoren von Inhalten können zukünftige Versionen des Kanals/der  erstellen, die als **Bildschirmstart** bezeichnet werden, und das Live-Datum für diesen Start weiter festlegen. Dadurch kann der Inhalt am angegebenen Live-Datum auf Geräten oder Playern live geschaltet werden.

With the help of **Screens Launches**, authors can preview each channel in the launch and should be able to initiate a request for review. Die Gruppe der Genehmigenden erhält eine Benachrichtigung und kann die Anfrage genehmigen oder ablehnen. Wenn das Live-Datum erreicht ist, wird der Inhalt auf den Geräten abgespielt.

Wenn der Autor z. B. zukünftige Versionen von c1, c2 (Kanäle) erstellen möchte, wird ein Launch erstellt und ein Live-Datum festgelegt (z. B. 10. November, 08:00 Uhr). Alle weiteren Aktualisierungen des Inhalts werden zur Überprüfung gesendet. Nach der Genehmigung und am Live-Datum (10. November, 8:00 Uhr) wird der Inhalt dieses Launches auf den Geräten oder Playern wiedergegeben.

## Voraussetzungen {#requirements}

Bevor Sie den Beginn &quot;Screens Launches&quot;in einem AEM Screens-Projekt nutzen, sollten Sie sich mit dem Konzept der Übergangsphase und ihrer Relevanz vertraut machen.

Das Ausführen eines Erlebnisses am festgelegten Live-Datum auf dem Player umfasst Folgendes:

* Förderung des Launch (in der Regel einige Sekunden)

* Veröffentlichen der Ressourcen für Instanzen im Veröffentlichungsmodus (in der Regel einige Minuten, je nach Größe der Kanal oder Assets, die veröffentlicht werden müssen))

* Zeit, die der Abschluss der Offline-Aktualisierung dauert (in der Regel einige Minuten)

* Zeit, die die Player zum Herunterladen des Inhalts aus der Veröffentlichungsinstanz benötigen (in der Regel dauert es je nach Bandbreite und Größe der herunterzuladenden Assets Minuten)

* alle Zeitunterschiede zwischen Server und Player

### Verstehen der Übergangsphase {#understanding-grace-period}

Damit der Player den Beginn beim Abspielen des Inhalts am festgelegten Live-Datum ausführen kann, müssen die zuvor genannten Aktivitäten vor dem Live-Datum Beginn werden.

Wenn das Livedatum 24. *Nov., 9.00 Uhr* und die Übergangsphase *24 Stunden* beträgt, wird die obige Aktionssequenz am (Livedatum - Übergangsphase), d. h. am 23. November, um 9.00 Uhr morgens, Beginn. Dadurch erhalten Sie 24 Stunden Zeit, um alle oben genannten Aktionen durchzuführen, und der Inhalt erreicht die Spieler. Spieler werden verstehen, dass es sich um einen Startinhalt handelt, sodass der Inhalt nicht sofort abgespielt wird. Player speichern diesen Inhalt jedoch als zukünftige Version und werden genau am festgelegten Live-Datum in der Zeitzone des Players abgespielt.

Angenommen, der Server befindet sich in PST und die Geräte in EST. Die maximale Zeitdifferenz beträgt in diesem Fall 3 Stunden. Es wird davon ausgegangen, dass die Promotion 1 Minute und die Veröffentlichung von der Autoren- auf der Veröffentlichungsinstanz 10 Minuten dauert und der Player die Ressourcen in der Regel in 10-15 Minuten herunterladen kann. Dann ist Übergangsphase = Zeitunterschied (3 Stunden) + Zeit für die Promotion des Launches (1 Min.) + Zeit für die Veröffentlichung des Launches (10 Min.) + Zeit zum Herunterladen auf den Player (10-15 Min.) + Puffer (z. B. 30 Min.) = 3 Stunden 56 Min. = 14160 Sekunden. Wann immer wir also einen Launch live planen, beginnt die Promotion um diesen Zeitversatz früher. In der obigen Gleichung nehmen die meisten Elemente nicht viel Zeit in Anspruch. Wenn wir den maximalen Zeitunterschied zwischen dem Server und einem Player kennen, können wir einen guten Schätzwert für diesen Versatz verwenden.

>[!NOTE]
>Out-of-the-box, the grace period for screens launches is set to 24 hours which means that when we set live date for any launch for the resources under */content/screens*, the promotion will start with this offset.

### Updating out-of-the-box Grace Period {#updating-out-of-the-box-grace-period}

In diesem Abschnitt wird beschrieben, wie Sie eine vordefinierte Übergangsphase auf 10 Minuten aktualisieren können:

1. Navigieren Sie zu CRXDE Lite und dann zu `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
2. Klicken Sie mit der rechten Maustaste und kopieren Sie die Datei.
3. Navigieren Sie zum Ordner, klicken Sie mit der rechten Maustaste `/apps/system/config` und fügen Sie ihn ein.
4. Klicken Sie auf die Dublette, `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` um die Datei im Editor in CRXDE Lite zu öffnen. Es muss die Übergangsphase für den Pfad */Inhalt/Bildschirme/* als 86400 angezeigt werden. Ändern Sie diesen Wert in **600**.

Der Inhalt in der Textdatei sollte nun wie folgt aussehen:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Da Sie die Übergangsphase im obigen Beispiel auf 10 Minuten festgelegt haben, wird die Promotion mit diesem Offset Beginn, wenn Sie für jeden Start der Ressourcen unter */content/screens* ein Live-Datum festlegen.

Wenn das Livedatum beispielsweise auf 24. November, 9.00 Uhr und die Übergangsphase auf 600 Sekunden festgelegt ist, wird der Promotion-Auftrag am 24. November um 8.50 Uhr Beginn.

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

