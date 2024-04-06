---
title: Inhaltsaktualisierung mit Screens Launch
seo-title: Content Update using Screens Launch
description: Inhaltsautoren können zukünftige Versionen von Kanälen erstellen, die als Launch bezeichnet werden. Wenn Sie das Live-Datum für diesen Launch festlegen, können Inhalte auf Geräten oder Playern live geschaltet werden.
seo-description: Content authors can create future version of the channel(s), known as Launch and further setting live date for this launch allows content to be live in devices or players.
uuid: fb13117c-b99b-48bd-adb6-040dbd13af16
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 9cd8892b-fe5d-4ad3-9b10-10ff068adba6
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '1593'
ht-degree: 98%

---

# Inhaltsaktualisierung mit Screens Launch {#launches}

Inhaltsautoren können zukünftige Versionen des Kanals/der Kanäle erstellen, die als **Screens Launch** bezeichnet werden, und darüber hinaus das Live-Datum für diesen Launch festlegen. Dadurch kann der Inhalt am angegebenen Live-Datum auf Geräten oder Playern live geschaltet werden.

Mithilfe von ***Screens Launch*** können Autoren die einzelnen Kanäle im Launch in der Vorschau anzeigen und sollten eine Anfrage zur Überprüfung starten können. Die Gruppe der Genehmigenden erhält eine Benachrichtigung und kann die Anfrage genehmigen oder ablehnen. Wenn das Live-Datum erreicht ist, wird der Inhalt auf den Geräten abgespielt.

Wenn der Autor z. B. zukünftige Versionen von c1, c2 (Kanäle) erstellen möchte, wird ein Launch erstellt und ein Live-Datum festgelegt (z. B. 10. November, 08:00 Uhr). Alle weiteren Aktualisierungen des Inhalts werden zur Überprüfung gesendet.

Nach der Genehmigung und am Live-Datum (10. November, 8:00 Uhr) wird der Inhalt dieses Launches auf den Geräten oder Playern wiedergegeben.

## Voraussetzungen {#requirements}

Bevor Sie mit der Nutzung von *Screens Launch* in einem AEM Screens-Projekt beginnen, sollten Sie sich mit dem Konzept der Übergangsphase und ihrer Relevanz vertraut machen.

Das Ausführen eines Erlebnisses am festgelegten Live-Datum auf dem Player umfasst Folgendes:

* Promotion des Launches (dauert in der Regel einige Sekunden)

* Veröffentlichen der Ressourcen, um Instanzen zu veröffentlichen (dauert in der Regel einige Minuten, je nach Größe der Kanäle oder Assets, die veröffentlicht werden müssen)

* Zeit, die der Abschluss der Offline-Aktualisierung dauert (dauert in der Regel einige Minuten)

* Zeit, die die Player zum Herunterladen des Inhalts aus der Veröffentlichungsinstanz benötigen (in der Regel dauert es je nach Bandbreite und Größe der herunterzuladenden Assets einige Minuten)

* alle Zeitunterschiede zwischen Server und Player

### Verstehen der Übergangsphase {#understanding-grace-period}

Damit der Player am festgelegten Live-Datum mit der Wiedergabe des Inhalts beginnen kann, müssen die vorherigen Aktivitäten vor dem Live-Datum begonnen werden.

Wenn das Live-Datum der *24. November, 9.00 Uhr* und die Übergangsphase *24 Stunden* beträgt, beginnt die obige Aktionssequenz am (Live-Datum – Übergangsphase) 23. November, um 9.00 Uhr (Server-Zeit). Dadurch erhalten Sie 24 Stunden Zeit, um alle oben genannten Aktionen durchzuführen, damit der Inhalt die Player erreicht. Player werden verstehen, dass es sich um einen Launch-Inhalt handelt, sodass der Inhalt nicht sofort abgespielt wird. Stattdessen speichern die Player diesen Inhalt als zukünftige Version und beginnen genau am festgelegten Live-Datum in der Zeitzone des Players mit der Wiedergabe.

Angenommen, der Server befindet sich in PST und die Geräte in EST. Die maximale Zeitdifferenz beträgt in diesem Fall 3 Stunden. Es wird davon ausgegangen, dass die Promotion 1 Minute und die Veröffentlichung von der Autoren- auf der Veröffentlichungsinstanz 10 Minuten dauert und der Player die Ressourcen in der Regel in 10-15 Minuten herunterladen kann. Dann ist Übergangsphase = Zeitunterschied (3 Stunden) + Zeit für die Promotion des Launches (1 Min.) + Zeit für die Veröffentlichung des Launches (10 Min.) + Zeit zum Herunterladen auf den Player (10-15 Min.) + Puffer (z. B. 30 Min.) = 3 Stunden 56 Min. = 14160 Sekunden.

Wann immer wir also einen Launch live planen, beginnt die Promotion um diesen Zeitversatz früher. In der obigen Gleichung nehmen die meisten Elemente nicht viel Zeit in Anspruch. Wenn wir den maximalen Zeitunterschied zwischen dem Server und einem Player kennen, können wir einen guten Schätzwert für diesen Versatz verwenden.

>[!NOTE]
>
>Standardmäßig ist die Übergangsphase für Screens Launch auf 24 Stunden festgelegt. Das bedeutet, dass die Promotion mit diesem Versatz beginnt, wenn wir für einen Launch der Ressourcen unter */content/screens* ein Live-Datum festlegen.

### Aktualisieren der standardmäßigen Übergangsphase {#updating-out-of-the-box-grace-period}

In diesem Abschnitt wird beschrieben, wie Sie eine vordefinierte Übergangsphase auf 10 Minuten aktualisieren können.

1. Navigieren Sie zu CRXDE Lite und dann zu `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
2. Klicken Sie mit der rechten Maustaste und kopieren Sie die Datei.
3. Navigieren Sie zu `/apps/system/config`, klicken Sie mit der rechten Maustaste und fügen Sie den Inhalt ein.
4. Klicken Sie auf `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`, um die Datei im Editor in CRXDE Lite zu öffnen. Die Übergangsphase für den Pfad */content/screens/* muss als **86400** angezeigt werden. Ändern Sie diesen Wert in **600**.

Der Inhalt in der Textdatei sollte nun wie folgt aussehen:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Da Sie die Übergangsphase im obigen Beispiel auf 10 Minuten festgelegt haben, beginnt die Promotion mit diesem Versatz, wenn Sie für einen beliebigen Launch der Ressourcen unter */content/screens* ein Live-Datum festlegen.

Wenn das Live-Datum beispielsweise auf 24. November, 9.00 Uhr und die Übergangsphase auf 600 Sekunden eingestellt ist, beginnt der Promotion-Auftrag am 24. November um 08:50 Uhr.

## Verwenden von Screens Launch {#using-launches}

In diesem Abschnitt wird die Implementierung von Screens Launch in Ihrem AEM Screens-Projekt erläutert.

### Erstellen eines Screens Launch {#creating-a-launch}

Gehen Sie gemäß nachstehendem Abschnitt vor, um Screens Launch-Funktionen in Ihrem AEM Screens-Projekt zu implementieren:

1. Erstellen Sie einen Sequenzkanal in Ihrem AEM Screens-Projekt, beispielsweise **LaunchesDemo** > **Kanäle** > **FutureLaunch**, wie unten dargestellt.

   >[!CAUTION]
   >
   >Sie müssen einen Launch aus einem bereits vorhandenen Kanal in Ihrem AEM Screens-Projekt erstellen.

   ![Bild](/help/user-guide/assets/launches-images/launches-11.png)

1. Wählen Sie den Kanal **FutureLaunch** aus und klicken Sie in der Aktionsleiste auf **Launch erstellen**.

   ![Bild](/help/user-guide/assets/launches-images/launches-12.png)

1. Der Assistent **Launch erstellen** wird geöffnet. Sie können entweder den Kanal auswählen, der bereits im Assistenten angezeigt wird, oder auf **+ Kanäle hinzufügen** klicken, um den Kanal hinzuzufügen, für den Sie den Launch erstellen möchten.

1. Klicken Sie im Assistenten **Launch erstellen** auf **Weiter**. Die Option **Unterseiten einschließen** ist standardmäßig ausgewählt.

   ![Bild](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >Mit der Option **+ Kanäle hinzufügen** können Sie einen weiteren Kanal hinzufügen, für den Sie den Launch erstellen möchten.

   Um die Option **Kanäle hinzufügen** zu verwenden, navigieren Sie zu dem Kanal, für den Sie den Launch erstellen möchten, und klicken Sie auf **Auswählen**.

   Die Option **Auswählen** wird deaktiviert, wenn Sie versuchen, mehrere Kanäle oder einen Ordner zum Hinzufügen des Launches auszuwählen.

   ![Bild](/help/user-guide/assets/launches-images/launches-14.png)

   Klicken Sie nach Auswahl des Kanals/der Kanäle auf **Weiter**.


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

   **Der Umfang der Launch-Promotion**

   * **Vollständigen Launch bewerben**: Alle Kanäle des Launches werden am festgelegten Live-Datum beworben.
   * **Geänderte Seiten bewerben**: Es werden nur bearbeitete Launch-Ressourcen beworben. Es wird empfohlen, diese Option zu verwenden, wenn keine Launch-Überprüfung erforderlich ist.
   * **Genehmigte Seiten bewerben**: Für diese Option muss der Arbeitsablauf für die Launch-Genehmigung in den Kanälen ausgeführt werden. Nur genehmigte Seiten werden am festgelegten Live-Datum beworben.

     >[!CAUTION]
     >
     >Beim Live-Datum des Launches wird die Zeitzone des Players/Geräts und nicht die des Servers berücksichtigt.

1. Sie sehen, dass Ihr Launch erstellt wurde. Sie können entweder auf **Öffnen** klicken, um die Seiten im Editor anzuzeigen, oder auf **Fertig**, um zu Ihrem Projekt zurückzukehren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Durch Klicken auf **Fertig** können Sie zurück zu Ihrem Kanal **FutureLaunch** navigieren.

   ![Bild](/help/user-guide/assets/launches-images/launches-16.png)


### Bearbeiten der Launch-Eigenschaften zum Festlegen des Live-Datums und des Umfangs {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nach dem Erstellen des Launches können Sie Eigenschaften wie das Live-Datum, den Launch-Titel und den Promotion-Umfang über die Option **Launch-Eigenschaften** aktualisieren.

* **Launch-Datum** bezieht sich auf das Live-Datum, d. h. das Datum (und die Uhrzeit), zu dem der Inhalt im Screens-Player gemäß der Zeitzone des Players wiedergegeben wird.
* **Produktionsbereit** bietet die Möglichkeit zur Veröffentlichung der Kanäle nach der Promotion. Diese Option ist standardmäßig aktiviert, Sie müssen sie also nicht ändern.
* **Umfang** bestimmt, welche Kanäle während der Launch-Promotion beworben werden.


Gehen Sie wie folgt vor, um die Eigenschaften für den Launch zu bearbeiten:

1. Navigieren Sie zum Kanal **FutureLaunch** *(d. h. dem ausstehenden Start)* und wählen Sie den Kanal aus, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/launches-images/launches-17.png)

1. Klicken Sie in der Aktionsleiste auf **Dashboard**. Das Fenster **AUSSTEHENDE LAUNCHES** wird im Kanal-Dashboard angezeigt.

   ![Bild](/help/user-guide/assets/launches-images/launches-18.png)

1. Wählen Sie den Launch aus und klicken Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** auf **Launch-Eigenschaften**.

   ![Bild](/help/user-guide/assets/launches-images/launches-19.png)

### Bearbeiten von Screens Launch zum Hinzufügen oder Entfernen von Kanälen  {#editing-the-screens-launch-to-add-or-remove-channels}

Nachdem Sie den Launch erstellt haben, können Sie Kanäle zum Launch hinzufügen, bzw. daraus entfernen, indem Sie die Option **Launch bearbeiten** verwenden.

Klicken Sie anschließend auf **Speichern**, um zurück zum Kanal **FutureLaunch** zu gelangen.

### Manuelles Bewerben des Screens Launch{#promote-the-screens-launch-manually}

Sie können den Launch manuell bewerben, indem Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** die Option **Launch bewerben** wählen.

Sie können die Ressourcen, die Sie im Rahmen dieser manuellen Promotion bewerben möchten, im Assistenten **Launch bewerben** auswählen.

![Bild](/help/user-guide/assets/launches-images/launches-e.png)

1. Sie können die Option zum Löschen des Launches nach der Produktion aktivieren oder deaktivieren.
1. Sie können den **Umfang** des Launches mit den folgenden Optionen festlegen:
   1. **Vollständigen Launch bewerben**: Alle Kanäle des Launches werden am festgelegten Live-Datum beworben.
   1. **Geänderte Seiten bewerben**: Es werden nur bearbeitete Launch-Ressourcen beworben. Es wird empfohlen, diese Option zu verwenden, wenn keine Launch-Überprüfung erforderlich ist.
   1. **Genehmigte Seiten bewerben**: Für diese Option muss der Arbeitsablauf für die Launch-Genehmigung in den Kanälen ausgeführt werden. Nur genehmigte Seiten werden am festgelegten Live-Datum beworben.
   1. **Aktuelle Seite bewerben**: Für diese Option muss der Arbeitsablauf für die Launch-Genehmigung nur für die aktuelle Seite ausgeführt werden.
1. Klicken Sie im Assistenten **Launch bewerben** auf **Weiter**.
1. Klicken Sie auf **Bewerben**, um den Launch zu bewerben.

### Löschen eines Screens Launch {#deleting-the-screens-launch}

Sie können den Launch löschen, indem Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** die Option **Launch löschen** wählen.

>[!CAUTION]
>
>Durch diese Aktion werden auch alle untergeordneten Elemente (verschachtelten Launches) gelöscht.
