---
title: Inhaltsaktualisierungen mit Screens Launch
description: Erfahren Sie, wie Sie eine zukünftige Version der Kanäle erstellen (auch als Launch bezeichnet) und ein Live-Datum für den Launch festlegen, damit Inhalte auf Geräten oder Playern live geschaltet werden.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 97%

---

# Inhaltsaktualisierungen mit Screens Launch {#launches}

Inhaltsautorinnen und Inhaltsautoren können eine zukünftige Version der Kanäle erstellen und darüber hinaus das Live-Datum für diesen Launch festlegen. Durch diese Funktion kann der Inhalt am angegebenen Live-Datum auf Geräten oder Playern live geschaltet werden.

Mithilfe von ***Screens Launch*** können Autorinnen und Autoren die einzelnen Kanäle im Launch in der Vorschau anzeigen und sollten eine Anfrage zur Überprüfung starten können. Die Gruppe der Genehmigenden erhält eine Benachrichtigung und kann die Anfrage genehmigen oder ablehnen. Wenn das Live-Datum erreicht ist, wird der Inhalt auf den Geräten abgespielt.

Wenn die Autorin oder der Autor z. B. zukünftige Versionen von c1, c2 (Kanäle) erstellen möchte, wird ein Launch generiert und ein Live-Datum festgelegt (z. B. 10. November, 8:00 Uhr). Alle weiteren Aktualisierungen des Inhalts werden zur Überprüfung gesendet.

Nach der Genehmigung wird am Live-Datum (10. November, 8:00 Uhr) der Inhalt dieses Launches auf den Geräten oder Playern wiedergegeben.

## Voraussetzungen {#requirements}

Bevor Sie *Screens Launch* in einem AEM Screens-Projekt verwenden, sollten Sie sich mit dem Konzept der Nachfrist und ihrer Relevanz vertraut machen.

Das Ausführen eines Erlebnisses am festgelegten Live-Datum auf dem Player umfasst Folgendes:

* Launch-Promotion (dauert in der Regel einige Sekunden).

* Veröffentlichen der Ressourcen, um Instanzen zu veröffentlichen (dauert in der Regel einige Minuten, je nach Größe der Kanäle oder Assets, die veröffentlicht werden müssen).

* Zeit, die bis zum Abschluss der Offline-Aktualisierung benötigt wird (in der Regel einige Minuten).

* Zeit, die die Player zum Herunterladen des Inhalts aus der Veröffentlichungsinstanz benötigen (in der Regel je nach Bandbreite und Größe der herunterzuladenden Assets einige Minuten).

* alle Zeitunterschiede zwischen Server und Player.

### Verstehen der Nachfrist {#understanding-grace-period}

Damit der Player am festgelegten Live-Datum mit der Wiedergabe des Inhalts beginnen kann, müssen Sie mit den vorherigen Aktivitäten vor dem Live-Datum beginnen.

Wenn das Live-Datum der *24. November, 9:00 Uhr* ist und die Nachfrist *24 Stunden* beträgt, beginnt die obige Aktionssequenz am (Live-Datum – Nachfrist) 23. November um 9:00 Uhr (Server-Zeit). Durch diese Einstellung erhalten Sie 24 Stunden Zeit, um alle oben genannten Aktionen durchzuführen, damit der Inhalt die Player erreicht. Die Player erkennen, dass es sich bei diesem Zeitraum um Launch-Inhalt handelt. Daher wird der Inhalt nicht sofort wiedergegeben. Player können diesen Inhalt jedoch als zukünftige Version speichern und die Wiedergabe exakt am festgelegten Live-Datum in der Zeitzone des Players starten.

Ein Beispiel: Der Server befindet sich in der Zeitzone „PST“ und die Geräte in der Zeitzone „EST“. Die maximale Zeitdifferenz beträgt drei Stunden. Es wird davon ausgegangen, dass die Promotion 1 Minute dauert, die Veröffentlichung von der Autoren- zur Veröffentlichungsinstanz 10 Minuten dauert und der Player die Ressourcen in der Regel in 10–15 Minuten herunterladen kann. Die Übergangsphase ist dann gleich dem Zeitunterschied (drei Stunden):

* &#x200B;+ die Zeit für die Launch-Promotion (1 Minute)
* &#x200B;+ die Zeit für die Launch-Veröffentlichung (10 Minuten)
* &#x200B;+ die Zeit für den Download im Player (10 bis 15 Minuten)
* &#x200B;+ Puffer (30 Minuten)

Insgesamt sind dies dann 3 Stunden und 56 Minuten (14.160 Sekunden).

Wann immer Sie also den Live-Zeitpunkt für einen Launch planen, beginnt die Promotion um diesen Zeitversatz früher. In der obigen Gleichung nehmen die meisten Punkte nicht viel Zeit in Anspruch. Sie können eine angemessene Schätzung für diesen Offset verwenden, wenn Sie die maximale Zeitdifferenz zwischen dem Server und einem beliebigen Player kennen.

>[!NOTE]
>
>Standardmäßig ist die Übergangsphase für Screens Launch auf 24 Stunden festgelegt. Das bedeutet, dass die Promotion mit diesem Versatz beginnt, wenn Sie für einen Launch der Ressourcen unter */content/screens* ein Live-Datum festlegen. 

### Aktualisieren der standardmäßigen Nachfrist {#updating-out-of-the-box-grace-period}

In diesem Abschnitt wird beschrieben, wie Sie eine standardmäßige Nachfrist auf 10 Minuten aktualisieren können.

1. Navigieren Sie zu CRXDE Lite und dann zu `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
1. Klicken Sie mit der rechten Maustaste und kopieren Sie die Datei.
1. Navigieren Sie zu `/apps/system/config`, klicken Sie mit der rechten Maustaste und fügen Sie den Inhalt ein.
1. Doppelklicken Sie auf `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`, um die Datei im Editor unter CRXDE Lite zu öffnen. Die Übergangsphase für den Pfad */content/screens/* muss als **86400** angezeigt werden. Ändern Sie diesen Wert in **600**.

Der Inhalt in der Textdatei sollte nun wie folgt aussehen:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Sie legen die Nachfrist im obigen Beispiel auf 10 Minuten fest. Daher beginnt die Promotion mit diesem Versatz, wenn Sie für einen Launch der Ressourcen unter */content/screens* ein Live-Datum festlegen.

Wenn das Live-Datum beispielsweise auf den 24. November um 9:00 Uhr und die Nachfrist auf 600 Sekunden eingestellt ist, beginnt der Promotions-Auftrag am 24. November um 8:50 Uhr.

## Verwenden von Screens Launch {#using-launches}

In diesem Abschnitt wird die Implementierung von Screens Launch in Ihrem AEM Screens-Projekt erläutert.

### Erstellen eines Screens Launch {#creating-a-launch}

Gehen Sie gemäß nachstehendem Abschnitt vor, um Screens Launch-Funktionen in Ihrem AEM Screens-Projekt zu implementieren:

1. Erstellen Sie einen Sequenzkanal in Ihrem AEM Screens-Projekt, z. B. **LaunchesDemo** > **Kanäle** > **FutureLaunch**, wie unten dargestellt.

   >[!CAUTION]
   >
   >Erstellen Sie einen Launch aus einem bereits vorhandenen Kanal in Ihrem AEM Screens-Projekt.

   ![Bild](/help/user-guide/assets/launches-images/launches-11.png)

1. Klicken Sie auf den Kanal **FutureLaunch** und dann in der Aktionsleiste auf **Launch erstellen**.

   ![Bild](/help/user-guide/assets/launches-images/launches-12.png)

1. Der Assistent **Launch erstellen** wird geöffnet. Sie können entweder auf den Kanal klicken, der bereits im Assistenten angezeigt wird, oder auf **+ Kanäle hinzufügen** klicken, um den Kanal hinzuzufügen, für den Sie den Launch erstellen möchten.

1. Klicken Sie im Assistenten **Launch erstellen** auf **Weiter**. Die Option **Unterseiten einschließen** ist standardmäßig ausgewählt.

   ![Bild](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >Mit der Option **+ Kanäle hinzufügen** können Sie einen weiteren Kanal hinzufügen, für den Sie den Launch erstellen möchten.

   Um die Option **Kanäle hinzufügen** zu verwenden, navigieren Sie zu dem Kanal, für den Sie den Launch erstellen möchten, und klicken Sie auf **Auswählen**.

   Die Option **Auswählen** wird deaktiviert, wenn Sie versuchen, zum Hinzufügen des Launches auf mehrere Kanäle oder einen Ordner zu klicken.

   ![Bild](/help/user-guide/assets/launches-images/launches-14.png)

   Klicken Sie nach Auswahl des Kanals/der Kanäle auf **Weiter**.


1. Geben Sie unter **Launch-Titel** den Wert **SummerPromotions** ein. Sie müssen für **Launch-Datum** keinen Wert festlegen, wie in der folgenden Abbildung dargestellt. Klicken Sie auf **Erstellen**.

   >[!NOTE]
   >
   >Wenn Sie die Option **Quellseiten-Live-Daten übernehmen** *aktivieren*, können die Kanäle im Launch als Live Copies erstellt werden. Wenn Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen automatisch auf die Launch-Kanäle angewendet.
   >
   >
   >Durch *Deaktivieren* der Option **Quellseiten-Livedaten übernehmen** können die Kanäle ohne Live-Beziehung in den Launch kopiert werden. Wenn also Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen nicht auf die Launch-Kanäle angewendet.

   ![Bild](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >Sie können das Live-Launch-Datum in diesem Schritt festlegen oder es später einrichten, während Sie die Eigenschaften des Launches bearbeiten, nachdem er bereits erstellt wurde.

   **Der Umfang der Launch-Promotion**

   * **Vollständigen Launch bewerben**: Alle Kanäle des Launches werden am festgelegten Live-Datum beworben.
   * **Geänderte Seiten bewerben**: Es werden nur bearbeitete Launch-Ressourcen beworben. Verwenden Sie diese Option, wenn keine Launch-Überprüfung erforderlich ist.
   * **Genehmigte Seiten bewerben**: Für diese Option muss der Workflow „Launch-Bestätigung“ in den Launch-Kanälen ausgeführt werden. Nur genehmigte Seiten werden am festgelegten Live-Datum beworben.

     >[!CAUTION]
     >
     >Beim Live-Datum des Launches wird die Zeitzone des Players/Geräts und nicht die des Servers berücksichtigt.

1. Ihr Launch wurde erstellt. Sie können entweder auf **Öffnen** klicken, um die Seiten im Editor anzuzeigen, oder auf **Fertig**, um zu Ihrem Projekt zurückzukehren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Wenn Sie **Fertig** auswählen, können Sie zurück zu Ihrem Kanal **FutureLaunch** navigieren.

   ![Bild](/help/user-guide/assets/launches-images/launches-16.png)


### Bearbeiten der Launch-Eigenschaften zum Festlegen des Live-Datums und des Umfangs {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nach dem Erstellen des Launches können Sie Eigenschaften wie das Live-Datum, den Launch-Titel und den Promotion-Umfang über die Option **Launch-Eigenschaften** aktualisieren.

* **Launch-Datum**: Bezieht sich auf das Live-Datum, d. h. das Datum (und die Uhrzeit), zu dem der Inhalt im Screens-Player gemäß der Zeitzone des Players wiedergegeben wird.
* **Produktionsbereit**: Nach der Promotion können die Kanäle veröffentlicht und native Aktionen aktiviert werden, sodass keine Änderungen erforderlich sind.
* **Bereich**: Bestimmt, welche Kanäle während der Launch-Promotion beworben werden.

Gehen Sie wie folgt vor, um die Eigenschaften für den Launch zu bearbeiten:

1. Navigieren Sie zum Kanal **FutureLaunch** *(d. h. dem ausstehenden Launch)* und klicken Sie auf den Kanal, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/launches-images/launches-17.png)

1. Klicken Sie in der Aktionsleiste auf die Option **Dashboard**. Daraufhin wird das Bedienfeld **AUSSTEHENDE LAUNCHES** im Kanal-Dashboard angezeigt.

   ![Bild](/help/user-guide/assets/launches-images/launches-18.png)

1. Klicken Sie auf den Launch und dann im Bedienfeld **AUSSTEHENDE LAUNCHES** auf **Launch-Eigenschaften**.

   ![Bild](/help/user-guide/assets/launches-images/launches-19.png)

### Bearbeiten von Screens Launch zum Hinzufügen oder Entfernen von Kanälen {#editing-the-screens-launch-to-add-or-remove-channels}

Nachdem Sie den Launch erstellt haben, können Sie Kanäle zum Launch hinzufügen, bzw. daraus entfernen, indem Sie die Option **Launch bearbeiten** verwenden.

Klicken Sie anschließend auf **Speichern**, um zurück zum Kanal **FutureLaunch** zu gelangen.

### Manuelles Bewerben des Screens-Launch{#promote-the-screens-launch-manually}

Sie können den Launch manuell bewerben, indem Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** die Option **`Promote Launch`** auswählen.

Sie können die Ressourcen, die Sie im Rahmen dieser manuellen Promotion bewerben möchten, im Assistenten **Launch bewerben** auswählen.

![Bild](/help/user-guide/assets/launches-images/launches-e.png)

1. Sie können die Option zum Löschen des Launches nach der Produktion aktivieren oder deaktivieren.
1. Sie können den **Umfang** des Launches mit den folgenden Optionen festlegen:
   * **Vollständigen Launch bewerben**: Alle Kanäle des Launches werden am festgelegten Live-Datum beworben.
   * **Geänderte Seiten bewerben**: Es werden nur bearbeitete Launch-Ressourcen beworben. Verwenden Sie diese Option, wenn keine Launch-Überprüfung erforderlich ist.
   * **Genehmigte Seiten bewerben**: Für diese Option muss der Workflow „Launch-Bestätigung“ in den Launch-Kanälen ausgeführt werden. Nur genehmigte Seiten werden am festgelegten Live-Datum beworben.
   * **Aktuelle Seite bewerben**: Für diese Option darf der Workflow „Launch-Bestätigung“ nur für die aktuelle Seite ausgeführt werden.
1. Klicken Sie im Assistenten **Launch bewerben** auf **Weiter**.
1. Klicken Sie auf **Bewerben**, um den Launch zu bewerben.

### Löschen eines Screens Launch

Sie können den Launch löschen, indem Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** die Option **Launch löschen** auswählen.

>[!CAUTION]
>
>Durch diese Aktion werden alle untergeordneten Elemente (verschachtelten Launches) ebenfalls gelöscht.
