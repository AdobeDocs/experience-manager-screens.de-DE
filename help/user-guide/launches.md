---
title: Inhaltsaktualisierung mit Screens Launch
description: Erfahren Sie, wie Sie zukünftige Versionen der Kanäle erstellen, die als Launch bezeichnet werden, und ein Live-Datum für den Launch festlegen, damit Inhalte auf Geräten oder Playern live geschaltet werden.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 27%

---

# Inhaltsaktualisierung mit Screens Launch {#launches}

Autoren von Inhalten können zukünftige Versionen der Kanäle erstellen, die als **Screens Launch** und legen Sie das Live-Datum für diesen Launch fest. Dadurch kann der Inhalt am angegebenen Live-Datum auf Geräten oder Playern live geschaltet werden.

Mithilfe von ***Screens Launch*** können Autoren die einzelnen Kanäle im Launch in der Vorschau anzeigen und sollten eine Anfrage zur Überprüfung starten können. Die Gruppe Genehmiger erhält eine Benachrichtigung und kann die Anfrage genehmigen oder ablehnen. Wenn das Live-Datum erreicht ist, wird der Inhalt auf den Geräten abgespielt.

Wenn der Autor beispielsweise zukünftige Versionen von c1, c2 (Kanäle) erstellen möchte, wird ein Launch erstellt und ein Live-Datum festgelegt (z. B. 10.01 Uhr). Weitere Aktualisierungen des Inhalts werden zur Überprüfung gesendet.

Nach der Genehmigung und am Live-Datum (10. November, 8:00 Uhr) wird der Inhalt dieses Launches auf den Geräten oder Playern wiedergegeben.

## Voraussetzungen {#requirements}

Vorbereitung der Verwendung von *Screens Launch* Vergewissern Sie sich, dass Sie mit dem Konzept der Übergangsphase und ihrer Relevanz vertraut sind.

Das Ausführen eines Erlebnisses am festgelegten Live-Datum auf dem Player umfasst Folgendes:

* Promotion des Launches (dauert in der Regel einige Sekunden).

* Veröffentlichen der Ressourcen zur Veröffentlichung von Instanzen (dauert in der Regel einige Minuten, abhängig von der Größe der Kanäle oder Assets, die veröffentlicht werden müssen).

* Zeit, die der Abschluss der Aktualisierung des Offline-Inhalts benötigt (dauert normalerweise einige Minuten).

* Zeit, die die Player zum Herunterladen des Inhalts aus der Veröffentlichungsinstanz benötigen (in der Regel dauert es je nach Bandbreite und Größe der herunterzuladenden Assets einige Minuten).

* Unterschiede zwischen Server und Player.

### Verstehen der Übergangsphase {#understanding-grace-period}

Damit der Player mit der Wiedergabe des Inhalts am festgelegten Live-Datum beginnen kann, starten Sie die vorherigen Aktivitäten vor dem Live-Datum.

Wenn das Live-Datum *24. November, 9:00 Uhr* und die Übergangsphase *24 Stunden*, beginnt die obige Aktionssequenz am (Live-Datum - Übergangsphase) 23. November, 9:00 Uhr Serverzeit. Dadurch erhalten Sie 24 Stunden, um alle oben genannten Aktionen durchzuführen, damit der Inhalt die Player erreicht. Player wissen, dass es sich um einen Launch-Inhalt handelt. Daher wird der Inhalt nicht sofort abgespielt, aber Player können diesen Inhalt als zukünftige Version speichern und die Wiedergabe exakt am festgelegten Live-Datum in der Zeitzone des Players starten lassen.

Beispielsweise befindet sich der Server in PST und die Geräte in EST. Die maximale Zeitdifferenz beträgt in diesem Fall drei Stunden und geht davon aus, dass die Promotion 1 Minute dauert und die Veröffentlichung von der Autoren- zur Veröffentlichungsinstanz 10 Minuten dauert und der Player die Ressourcen in der Regel in 10-15 Minuten herunterladen kann. Dann die Übergangsphase = Zeitdifferenz (drei Stunden):

* Plus Zeit für die Weiterleitung des Launches (1 Minute)
* Plus Zeit zur Veröffentlichung des Launches (10 Minuten)
* Plus Zeit für den Download im Player (10-15 Minuten)
* Plus-Puffer (30 Minuten)

entspricht 3 Stunden 56 Minuten (14160 Sekunden).

Wenn Sie also einen Launch live planen, beginnt die Promotion um diesen Versatz früh. In der obigen Gleichung nehmen die meisten Elemente nicht viel Zeit in Anspruch. Sie können einen angemessenen Schätzwert für diesen Versatz verwenden, wenn Sie den maximalen Zeitunterschied zwischen dem Server und einem Player kennen.

>[!NOTE]
>
>Standardmäßig ist die Übergangsphase für Screens Launch auf 24 Stunden festgelegt. Das bedeutet, dass Sie beim Festlegen des Live-Datums für einen Launch für die Ressourcen unter */content/screens*, beginnt die Promotion mit diesem Versatz.

### Aktualisieren der standardmäßigen Übergangsphase {#updating-out-of-the-box-grace-period}

In diesem Abschnitt wird beschrieben, wie Sie eine vordefinierte Übergangsphase auf 10 Minuten aktualisieren können.

1. Navigieren Sie zu CRXDE Lite und dann zu `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
1. Klicken Sie mit der rechten Maustaste und kopieren Sie die Datei.
1. Navigieren Sie zu `/apps/system/config`, klicken Sie mit der rechten Maustaste und fügen Sie den Inhalt ein.
1. Doppelklicken `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` damit Sie die Datei im Editor unter CRXDE Lite öffnen können. Die Übergangsphase für den Pfad */content/screens/* muss als **86400** angezeigt werden. Ändern Sie diesen Wert in **600**.

Der Inhalt in der Textdatei sollte nun wie folgt aussehen:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Da Sie die Übergangsphase im vorherigen Beispiel auf 10 Minuten festgelegt haben, wenn Sie ein Live-Datum für einen beliebigen Launch der Ressourcen unter */content/screens*, beginnt die Promotion mit diesem Versatz.

Wenn das Live-Datum beispielsweise auf den 24. November, 9.00 Uhr und die Übergangsphase auf 600 Sekunden eingestellt ist, beginnt der Promotion-Auftrag am 24. November um 8:50 Uhr.

## Verwenden von Screens Launch {#using-launches}

In diesem Abschnitt wird die Implementierung von Screens Launch in Ihrem AEM Screens-Projekt erläutert.

### Erstellen eines Screens Launch {#creating-a-launch}

Gehen Sie gemäß nachstehendem Abschnitt vor, um Screens Launch-Funktionen in Ihrem AEM Screens-Projekt zu implementieren:

1. Erstellen Sie einen Sequenzkanal in Ihrem AEM Screens-Projekt, beispielsweise **LaunchesDemo** > **Kanäle** > **FutureLaunch**, wie unten dargestellt.

   >[!CAUTION]
   >
   >Erstellen Sie einen Launch aus einem bereits vorhandenen Kanal in Ihrem AEM Screens-Projekt.

   ![Bild](/help/user-guide/assets/launches-images/launches-11.png)

1. Kanal auswählen **FutureLaunch** und wählen **Launch erstellen** in der Aktionsleiste aus.

   ![Bild](/help/user-guide/assets/launches-images/launches-12.png)

1. Der Assistent **Launch erstellen** wird geöffnet. Sie können entweder den Kanal auswählen, der bereits im Assistenten angezeigt wird, oder auswählen **+ Kanäle hinzufügen** , um den Kanal hinzuzufügen, für den Sie den Launch erstellen möchten.

1. Auswählen **Nächste** aus dem **Launch erstellen** Assistent. Die Option **Unterseiten einschließen** ist standardmäßig ausgewählt.

   ![Bild](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >Sie können **+ Kanäle hinzufügen** -Option, um einen weiteren Kanal hinzuzufügen, für den Sie den Launch erstellen möchten.

   Verwendung **Kanäle hinzufügen** -Option, navigieren Sie zu dem Kanal, für den Sie den Launch erstellen möchten, und wählen Sie **Auswählen**.

   Die **Auswählen** ist deaktiviert, wenn Sie versuchen, mehrere Kanäle oder einen Ordner zum Hinzufügen des Launches auszuwählen.

   ![Bild](/help/user-guide/assets/launches-images/launches-14.png)

   Nachdem Sie den Kanal/die Kanäle ausgewählt haben, wählen Sie **Nächste**.


1. Geben Sie unter **Launch-Titel** den Wert **SummerPromotions** ein. Sie müssen für **Launch-Datum** keinen Wert festlegen, wie in der folgenden Abbildung dargestellt. Wählen Sie **Erstellen** aus.

   >[!NOTE]
   >
   >Wenn Sie die Option **Quellseiten-Live-Daten übernehmen** *aktivieren*, können die Kanäle im Launch als Live Copies erstellt werden. Wenn Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen automatisch auf die Launch-Kanäle angewendet.
   >
   >
   >*Deaktivieren* **Quellseiten-Live-Daten übernehmen** ermöglicht das Kopieren der Kanäle ohne Live-Beziehung im Launch. Wenn also Änderungen am ursprünglichen Kanal vorgenommen werden, werden diese Änderungen nicht auf die Launch-Kanäle angewendet.

   ![Bild](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >Sie können das Live-Launch-Datum in diesem Schritt festlegen oder es später einrichten, während Sie die Eigenschaften des Launches bearbeiten, nachdem er bereits erstellt wurde.

   **Der Umfang der Launch-Promotion**

   * **Vollständigen Launch bewerben** - Alle Kanäle des Launches werden am festgelegten Live-Datum beworben.
   * **Geänderte Seiten bewerben** - Es werden nur geänderte Launch-Ressourcen beworben. Verwenden Sie diese Option, wenn keine Überprüfung des Launches erforderlich ist.
   * **Genehmigte Seiten bewerben** - Für diese Option muss der Arbeitsablauf für die Launch-Genehmigung auf den Launch-Kanälen ausgeführt werden. Am festgelegten Live-Datum werden nur genehmigte Seiten beworben.

     >[!CAUTION]
     >
     >Beim Live-Datum des Launches wird die Zeitzone des Players/Geräts und nicht die des Servers berücksichtigt.

1. Beachten Sie, dass Ihr Launch erstellt wurde. Sie können entweder **Öffnen** , um die Seiten im Editor anzuzeigen, oder wählen Sie **Fertig** , um zu Ihrem Projekt zurückzukehren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Auswählen **Fertig** Sie können zurück zu Ihrer **FutureLaunch** -Kanal.

   ![Bild](/help/user-guide/assets/launches-images/launches-16.png)


### Bearbeiten der Launch-Eigenschaften zum Festlegen des Live-Datums und des Umfangs {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nachdem der Launch erstellt wurde, können Sie die Eigenschaften wie Live-Datum, Launch-Titel und Promotion-Umfang aktualisieren, indem Sie **Launch-Eigenschaften**.

* **Launch-Datum** - Das Live-Datum, d. h. das Datum oder die Uhrzeit der Wiedergabe des Inhalts im Screens-Player gemäß der Zeitzone des Players.
* **Produktionsbereit** - Ermöglicht die Veröffentlichung der Kanäle nach der Promotion. Diese Option ist standardmäßig aktiviert, sodass Sie sie nicht ändern müssen.
* **Anwendungsbereich** - Entscheidet, welche Kanäle während der Launch-Promotion beworben werden.

Gehen Sie wie folgt vor, um die Eigenschaften für den Launch zu bearbeiten:

1. Navigieren zum Kanal **FutureLaunch** *(der ausstehende Start)* und wählen Sie den Kanal aus, wie in der Abbildung unten dargestellt.

   ![Bild](/help/user-guide/assets/launches-images/launches-17.png)

1. Auswählen **Dashboard** in der Aktionsleiste angezeigt wird. **AUSSTEHENDE LAUNCHES** im Kanal-Dashboard aus.

   ![Bild](/help/user-guide/assets/launches-images/launches-18.png)

1. Wählen Sie den Launch aus und wählen Sie **Launch-Eigenschaften** aus dem **AUSSTEHENDE LAUNCHES** Bedienfeld.

   ![Bild](/help/user-guide/assets/launches-images/launches-19.png)

### Bearbeiten von Screens Launch zum Hinzufügen oder Entfernen von Kanälen  {#editing-the-screens-launch-to-add-or-remove-channels}

Nachdem Sie den Launch erstellt haben, können Sie Kanäle zum Launch hinzufügen, bzw. daraus entfernen, indem Sie die Option **Launch bearbeiten** verwenden.

Wenn Sie fertig sind, wählen Sie **Speichern** zurück zu navigieren **FutureLaunch** -Kanal.

### Manuelles Bewerben des Screens Launch{#promote-the-screens-launch-manually}

Sie können den Launch manuell bewerben, indem Sie die **`Promote Launch`** Option aus der **AUSSTEHENDE LAUNCHES** Bedienfeld.

Sie können die Ressourcen, die Sie im Rahmen dieser manuellen Promotion bewerben möchten, im Assistenten **Launch bewerben** auswählen.

![Bild](/help/user-guide/assets/launches-images/launches-e.png)

1. Sie können die Option zum Löschen des Launches nach der Produktion aktivieren oder deaktivieren.
1. Sie können die **Anwendungsbereich** des Launches mit den folgenden Optionen:
   * **Vollständigen Launch bewerben** - Alle Kanäle des Launches werden am festgelegten Live-Datum beworben.
   * **Geänderte Seiten bewerben** - Es werden nur geänderte Launch-Ressourcen beworben. Verwenden Sie diese Option, wenn keine Überprüfung des Launches erforderlich ist.
   * **Genehmigte Seiten bewerben** - Für diese Option muss der Arbeitsablauf für die Launch-Genehmigung auf den Launch-Kanälen ausgeführt werden. Am festgelegten Live-Datum werden nur genehmigte Seiten beworben.
   * **Aktuelle Seite bewerben** - Für diese Option muss der Arbeitsablauf für die Launch-Genehmigung nur für die aktuelle Seite ausgeführt werden.
1. Auswählen **Nächste** im **Launch bewerben** Assistent.
1. Auswählen **Bewerben** um den Launch zu bewerben.

### Löschen eines Screens Launch

Sie können den Launch löschen, indem Sie im Bedienfeld **AUSSTEHENDE LAUNCHES** die Option **Launch löschen** wählen.

>[!CAUTION]
>
>Durch diese Aktion werden auch alle untergeordneten Elemente (verschachtelte Launches) gelöscht.
