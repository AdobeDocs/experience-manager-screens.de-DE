---
title: Inhaltsaktualisierung mit Screens Launch
description: Erfahren Sie, wie Sie eine zukünftige Version der Kanäle namens Launch erstellen und ein Live-Datum für den Launch festlegen, um Inhalte auf Geräten oder Playern live zu schalten.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
source-git-commit: c142830a37461a36baae15f543bd43b0ae8a62a7
workflow-type: tm+mt
source-wordcount: '1559'
ht-degree: 33%

---

# Inhaltsaktualisierung mit Screens Launch {#launches}

Inhaltsautoren können zukünftige Versionen der Kanäle erstellen, die als **Screens Launch** und legen Sie außerdem das Live-Datum für diesen Launch fest. Dadurch kann der Inhalt am angegebenen Live-Datum auf Geräten oder Playern live geschaltet werden.

Mithilfe von ***Screens Launch*** können Autoren die einzelnen Kanäle im Launch in der Vorschau anzeigen und sollten eine Anfrage zur Überprüfung starten können. Die Gruppe der genehmigenden Personen erhält eine Benachrichtigung und kann die Anfrage genehmigen oder ablehnen. Wenn das Live-Datum erreicht ist, wird der Inhalt auf den Geräten abgespielt.

Wenn der Autor beispielsweise zukünftige Versionen von c1, c2 (Kanäle) erstellen möchte, wird ein Launch erstellt und ein Live-Datum festgelegt (z. B. 10. November um 8:00 Uhr). Alle weiteren Aktualisierungen des Inhalts werden zur Überprüfung versendet.

Nach der Genehmigung und am Live-Datum (10. November, 8:00 Uhr) wird der Inhalt dieses Launches auf den Geräten oder Playern wiedergegeben.

## Voraussetzungen {#requirements}

Bevor Sie mit der Verwendung von beginnen *Screens Launch* Vergewissern Sie sich in einem AEM Screens-Projekt, dass Sie das Konzept der Übergangsphase und ihre Relevanz verstehen.

Das Ausführen eines Erlebnisses am festgelegten Live-Datum auf dem Player umfasst Folgendes:

* Weiterleitung des Launches (dauert normalerweise einige Sekunden).

* Das Veröffentlichen der Ressourcen in Veröffentlichungsinstanzen (dauert in der Regel einige Minuten, je nach Größe der Kanäle oder Assets, die veröffentlicht werden müssen).

* Dauer der Aktualisierung von Offline-Inhalten (dauert in der Regel einige Minuten).

* Die Zeit, die Player zum Herunterladen des Inhalts von der Veröffentlichungsinstanz benötigen, dauert in der Regel mehrere Minuten, je nach Bandbreite und Größe der Assets, die heruntergeladen werden müssen.

* Jederzeit vorhandene Unterschiede zwischen Server und Player.

### Verstehen der Übergangsphase {#understanding-grace-period}

Damit der Player die Wiedergabe des Inhalts am festgelegten Live-Datum starten kann, müssen Sie die vorherigen Aktivitäten vor dem Live-Datum starten.

Wenn das Live-Datum ist *24. November, 9:00 Uhr* und die Übergangsphase ist *24 Stunden*, dann beginnt die obige Sequenz von Aktionen um (Live-Datum - Übergangsphase), d. h. am 23. November um 9:00 Uhr Server-Zeit. Dies gibt 24 Stunden, um alle oben genannten Aktionen abzuschließen, damit der Inhalt die Player erreicht. Die Player verstehen, dass es sich um einen Launch-Inhalt handelt. Daher wird der Inhalt nicht sofort wiedergegeben, aber Player können diesen Inhalt als zukünftige Version speichern und ihn genau zum festgelegten Live-Datum in der Zeitzone des Players abspielen lassen.

Beispielsweise befindet sich der Server in der PST und die Geräte befinden sich in der EST-Phase. Der maximale Zeitunterschied beträgt in diesem Fall drei Stunden. Es wird davon ausgegangen, dass die Promotion 1 Minute dauert und die Veröffentlichung von der Autoren- zur Veröffentlichungsinstanz 10 Minuten dauert und der Player die Ressourcen in der Regel in 10-15 Minuten herunterladen kann. Dann gilt die Übergangsphase = Zeitdifferenz (drei Stunden):

* Plus Zeit für die Veröffentlichung (1 Minute)
* Plus Zeit für die Veröffentlichung des Launches (10 Minuten)
* Plus Zeit zum Herunterladen am Player (10-15 Minuten)
* Plus-Puffer (30 Minuten)

Gleich 3 Stunden 56 Minuten ( Sekunden).

Wenn Sie also einen Start live planen, beginnt die Promotion frühzeitig um diesen Versatz. In der obigen Gleichung beanspruchen die meisten Elemente nicht viel Zeit. Sie können eine vernünftige Schätzung für diesen Offset verwenden, wenn Sie die maximale Zeitdifferenz zwischen dem Server und einem beliebigen Player kennen.

>[!NOTE]
>
>Standardmäßig ist die Übergangsphase für Screens Launch auf 24 Stunden festgelegt. Das bedeutet, dass Sie beim Festlegen des Live-Datums für einen Launch für die Ressourcen unter */content/screens*, die Promotion beginnt mit diesem Versatz.

### Aktualisieren der standardmäßigen Übergangsphase {#updating-out-of-the-box-grace-period}

In diesem Abschnitt wird beschrieben, wie Sie eine vordefinierte Übergangsphase auf 10 Minuten aktualisieren können.

1. Navigieren Sie zu CRXDE Lite und dann zu `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
1. Klicken Sie mit der rechten Maustaste und kopieren Sie die Datei .
1. Navigieren Sie zu `/apps/system/config`, klicken Sie mit der rechten Maustaste und fügen Sie den Inhalt ein.
1. Doppelklick `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` So können Sie die Datei im Editor in CRXDE Lite öffnen. Die Übergangsphase für den Pfad */content/screens/* muss als **86400** angezeigt werden. Ändern Sie diesen Wert in **600**.

Der Inhalt in der Textdatei sollte nun wie folgt aussehen:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Da Sie im vorherigen Beispiel die Übergangsphase auf 10 Minuten festgelegt hatten, legen Sie das Live-Datum für jeden Launch für die Ressourcen unter fest. */content/screens*, die Promotion beginnt mit diesem Versatz.

Wenn das Live-Datum beispielsweise auf 24. November, 9.00 Uhr und die Übergangsphase auf 600 Sekunden festgelegt ist, beginnt der Promotion-Auftrag am 24. November um 8.50 Uhr.

## Verwenden von Screens Launch {#using-launches}

In diesem Abschnitt wird die Implementierung von Screens Launch in Ihrem AEM Screens-Projekt erläutert.

### Erstellen eines Screens Launch {#creating-a-launch}

Gehen Sie gemäß nachstehendem Abschnitt vor, um Screens Launch-Funktionen in Ihrem AEM Screens-Projekt zu implementieren:

1. Erstellen Sie einen Sequenzkanal in Ihrem AEM Screens-Projekt, z. B. **LaunchesDemo** > **Kanäle** > **FutureLaunch**, wie unten dargestellt.

   >[!CAUTION]
   >
   >Erstellen Sie einen Launch aus einem bereits vorhandenen Kanal in Ihrem AEM Screens-Projekt.

   ![Bild](/help/user-guide/assets/launches-images/launches-11.png)

1. Wählen Sie den Kanal **FutureLaunch** aus und klicken Sie in der Aktionsleiste auf **Launch erstellen**.

   ![Bild](/help/user-guide/assets/launches-images/launches-12.png)

1. Der Assistent **Launch erstellen** wird geöffnet. Sie können entweder den Kanal auswählen, der bereits im Assistenten angezeigt wird, oder auf **+ Kanäle hinzufügen** klicken, um den Kanal hinzuzufügen, für den Sie den Launch erstellen möchten.

1. Klicken Sie im Assistenten **Launch erstellen** auf **Weiter**. Die Option **Unterseiten einschließen** ist standardmäßig ausgewählt.

   ![Bild](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >Sie können Folgendes verwenden **+ Kanäle hinzufügen** Option zum Hinzufügen eines weiteren Kanals, für den Sie den Launch erstellen möchten.

   Um die Option **Kanäle hinzufügen** zu verwenden, navigieren Sie zu dem Kanal, für den Sie den Launch erstellen möchten, und klicken Sie auf **Auswählen**.

   Die **Auswählen** Diese Option ist deaktiviert, wenn Sie versuchen, mehrere Kanäle oder einen Ordner zum Hinzufügen des Launches auszuwählen.

   ![Bild](/help/user-guide/assets/launches-images/launches-14.png)

   Klicken Sie nach Auswahl des Kanals/der Kanäle auf **Weiter**.


1. Geben Sie unter **Launch-Titel** den Wert **SummerPromotions** ein. Sie müssen für **Launch-Datum** keinen Wert festlegen, wie in der folgenden Abbildung dargestellt. Klicken Sie auf **Erstellen**.

   >[!NOTE]
   >
   >Wenn Sie die Option **Quellseiten-Live-Daten übernehmen** *aktivieren*, können die Kanäle im Launch als Live Copies erstellt werden. Wenn Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen automatisch auf die Launch-Kanäle angewendet.
   >
   >
   >*Deaktivieren oder Deaktivieren* **Live-Daten der Quellseite übernehmen** ermöglicht das Kopieren der Kanäle ohne Live-Beziehung im Launch. Wenn also Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen nicht auf die Launch-Kanäle angewendet.

   ![Bild](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >Sie können das Live-Launch-Datum in diesem Schritt festlegen oder es später einrichten, während Sie die Eigenschaften des Launches bearbeiten, nachdem er bereits erstellt wurde.

   **Der Umfang der Launch-Promotion**

   * **Vollständigen Launch hochstufen** - Alle Kanäle des Launches werden zum festgelegten Live-Datum hochgestuft.
   * **Geänderte Seiten hochstufen** - Nur geänderte Launch-Ressourcen werden beworben. Verwenden Sie diese Option, wenn die Launch-Überprüfung nicht erforderlich ist.
   * **Genehmigte Seiten hochstufen** - Für diese Option ist der Workflow für die Launch-Genehmigung erforderlich, damit er auf den Launch-Kanälen ausgeführt wird. Nur genehmigte Seiten werden zum festgelegten Live-Datum hochgestuft.

     >[!CAUTION]
     >
     >Beim Live-Datum des Launches wird die Zeitzone des Players/Geräts und nicht die des Servers berücksichtigt.

1. Beachten Sie, dass Ihr Launch erstellt wurde. Sie können entweder **Öffnen Sie** So zeigen Sie die Seiten im Editor an oder wählen **Fertig** , um zu Ihrem Projekt zurückzukehren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Auswählen **Fertig** Navigieren Sie zurück zu Ihrem **FutureLaunch** Kanal.

   ![Bild](/help/user-guide/assets/launches-images/launches-16.png)


### Bearbeiten der Launch-Eigenschaften zum Festlegen des Live-Datums und des Umfangs {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nachdem der Launch erstellt wurde, können Sie die Eigenschaften wie Live-Datum, Launch-Titel und Promotion-Umfang mithilfe von aktualisieren. **Launch-Eigenschaften**.

* **Startdatum** - Das Live-Datum, d. h. das Datum oder die Uhrzeit, zu der der Inhalt im Screens-Player gemäß der Zeitzone des Players wiedergegeben wird.
* **Produktionsbereit** - Ermöglicht die Veröffentlichung der Kanäle, nachdem diese beworben wurden. Dies ist standardmäßig aktiviert, sodass Sie dies nicht ändern müssen.
* **Scope** - Legt fest, welche Kanäle während der Launch-Promotion beworben werden.

Gehen Sie wie folgt vor, um die Eigenschaften für den Launch zu bearbeiten:

1. Navigieren Sie zum Kanal **FutureLaunch** *(der ausstehende Launch)* und wählen Sie den Kanal wie in der folgenden Abbildung dargestellt aus.

   ![Bild](/help/user-guide/assets/launches-images/launches-17.png)

1. Auswählen **Dashboard** in der Aktionsleiste und Sie sehen die **AUSSTEHENDE LAUNCHES** Bedienfeld im Kanal-Dashboard.

   ![Bild](/help/user-guide/assets/launches-images/launches-18.png)

1. Wählen Sie den Launch aus und klicken Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** auf **Launch-Eigenschaften**.

   ![Bild](/help/user-guide/assets/launches-images/launches-19.png)

### Bearbeiten von Screens Launch zum Hinzufügen oder Entfernen von Kanälen  {#editing-the-screens-launch-to-add-or-remove-channels}

Nachdem Sie den Launch erstellt haben, können Sie Kanäle zum Launch hinzufügen, bzw. daraus entfernen, indem Sie die Option **Launch bearbeiten** verwenden.

Wenn Sie fertig sind, wählen Sie **Speichern** Navigieren zurück zu **FutureLaunch** Kanal.

### Manuelles Bewerben des Screens Launch{#promote-the-screens-launch-manually}

Sie können den Launch manuell über die **`Promote Launch`** Option aus dem **AUSSTEHENDE LAUNCHES** Bedienfeld.

Sie können die Ressourcen, die Sie im Rahmen dieser manuellen Promotion bewerben möchten, im Assistenten **Launch bewerben** auswählen.

![Bild](/help/user-guide/assets/launches-images/launches-e.png)

1. Sie können die Option zum Löschen des Launches nach der Produktion aktivieren oder deaktivieren.
1. Sie können Folgendes festlegen **Scope** des Launches mit den folgenden Optionen:
   * **Vollständigen Launch hochstufen** - Alle Kanäle des Launches werden zum festgelegten Live-Datum hochgestuft.
   * **Geänderte Seiten hochstufen** - Nur geänderte Launch-Ressourcen werden beworben. Verwenden Sie diese Option, wenn die Launch-Überprüfung nicht erforderlich ist.
   * **Genehmigte Seiten hochstufen** - Für diese Option ist der Workflow für die Launch-Genehmigung erforderlich, damit er auf den Launch-Kanälen ausgeführt wird. Nur genehmigte Seiten werden zum festgelegten Live-Datum hochgestuft.
   * **Aktuelle Seite hochstufen** - Diese Option erfordert, dass der Workflow für die Launch-Genehmigung nur für die aktuelle Seite ausgeführt wird.
1. Auswählen **Weiter** in der **Launch hochstufen** Assistent.
1. Auswählen **befördern** um den Launch zu bewerben.

### Löschen eines Screens Launch

Sie können den Launch löschen, indem Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** die Option **Launch löschen** wählen.

>[!CAUTION]
>
>Diese Aktion löscht auch alle untergeordneten Elemente (verschachtelte Launches).
