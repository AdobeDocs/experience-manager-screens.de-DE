---
title: Zuweisung von Kanälen - neueste RP
seo-title: Zuweisung von Kanälen - neueste RP
description: Folgen Sie dieser Seite, um mehr über die Zuweisung von Kanälen und die Tagesaufteilung zu erfahren.
translation-type: tm+mt
source-git-commit: c326c9e83b8c7edcda535b0c775c62c50dd3a29f
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 45%

---


# Kanalzuweisung {#channel-assignment}

>[!IMPORTANT]
>In diesem Abschnitt werden die Zuweisung und Planung von Kanälen für Kanal AEM 6.5.5 Screens Feature Pack und höher erläutert.

Nachdem Sie eine Anzeige eingerichtet haben, müssen Sie einem Display einen Kanal zuweisen, um den Inhalt Ansicht.

Diese Seite zeigt Ihnen, wie Sie Ihrer Anzeige einen Kanal zuweisen, wie Sie die Eigenschaften des Kanals und DayParting verstehen.

>[!NOTE]
>Sie können einer Anzeige mehrere Kanal zuweisen.


## Zuweisen von Kanälen {#assign-a-channel-new-release}

Gehen Sie wie folgt vor, um ein AEM Screens-Projekt zu erstellen und einem Display einen Kanal zuzuweisen.

### Erstellen eines AEM Screens-Projekts und von Kanälen {#creating-project}

Gehen Sie wie folgt vor, um ein Projekt und einen Kanal einzurichten:

1. Create an AEM Screens Project titled as **DemoScreens**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >Informationen zum Erstellen eines AEM Screens-Projekts finden Sie unter [Erstellen und Verwalten von Projekten](creating-a-screens-project.md) .

1. Erstellen Sie einen Sequenzordner mit dem Titel **Cafeteria** im Kanal **Kanal** .

1. Select the channel and click **Edit** from the action bar to add content to your channel.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Beispielsweise werden im **Cafeteria** -Kanal jetzt folgende Bilder angezeigt:

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Erstellen Sie eine Location mit dem Titel **SanJose** und eine Anzeige mit dem Namen **Lobby**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Assigning Channel to a Display {#assigning-channel-to-display}

Nachdem das Projekt eingerichtet wurde, müssen Sie den Kanal einer Anzeige zuweisen, um den Inhalt Ansicht.

1. Navigate to the required display, for example, **DemoScreens** --> **Locations** --> **SanJose** --> **Lobby**.

1. Tap/click **Assign Channel** from the action bar.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Oder

   Tippen/klicken Sie in der Aktionsleiste auf **Dashboard** und klicken Sie auf **+Kanal** zuweisen im Bedienfeld **ZUGEWIESENE KANAL &amp; GEPLANTE** .

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. The **Channel Assignment** dialog box opens.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Wählen Sie unter &quot; **Einstellungen** &quot;den Kanal **nach Pfad** oder **nach Namen** aus, geben Sie die Optionen **Kanal Rolle**, **Priorität**********,Unterstützte EreignisundUnterbrechungsmethoden ein. Darüber hinaus können Sie die QuickInfo der Attraktion in diesem Dialogfeld aktivieren.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >Weitere Informationen zu den Eigenschaften von Kanälen finden Sie im Abschnitt [Kanal-Eigenschaften](#channel-properties) .

1. Wählen Sie unter der Option **Plan** die **Referenz-Zeitzone**, das Fenster **Aktivierung** und den Zeitplan **für die**Wiederholung aus.
   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >Weitere Informationen zu den Eigenschaften von Kanälen finden Sie im Abschnitt [Kanal-Eigenschaften](#channel-properties) .

1. Klicken Sie auf **Speichern** , nachdem Sie Ihre Voreinstellungen konfiguriert haben.

### Viewing the Content in Chrome Player {#viewing-content-output}

Dieses Beispiel zeigt die Ausgabe auf einem Chrome Player. Nachdem Sie den Kanal Ihrem Display zugewiesen haben, müssen Sie das Gerät für einen Player registrieren.

Informationen zum Registrieren eines Geräts auf einem AEM Screens-Player finden Sie unter [Geräteregistrierung](device-registration.md) .

Sie werden die folgende Ausgabe auf Ihrem Player-Ansicht:

![new1](assets/channel-assignment/channel-assign-output.gif)

## Timeline View {#timeline-view}

Nachdem Sie einen Kanal einer Anzeige zugewiesen und einen Wiederholungsplan eingerichtet haben, können Sie die Zeitschiene im Bedienfeld &quot; **ZUGEWIESENE KANAL &amp; ZEITPLAN** &quot;Ansicht haben.

Gehen Sie wie folgt vor, um zur Ansicht der Zeitschiene zu navigieren:

1. Navigate to the required display, for example, **DemoScreens** --> **Locations** --> **SanJose** --> **Lobby**.

1. Tap/click **Assign Channel** from the action bar.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Oder

   Tippen/klicken Sie auf **Dashboard** und klicken Sie im Bedienfeld &quot; **ZUGEWIESENE KANAL und GEPLANTE** &quot;auf **Zeitschiene** .

1. Ausstehende Bilder (zu korrigieren)

## Understanding Channel Properties from Channel Assignment Dialog Box {#channel-properties}

Die folgenden Eigenschaften werden über die Option **Einstellungen** im Dialogfeld &quot; **Kanal-Zuweisung** &quot;festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Kanal auswählen {#select-channel}

Wenn Sie einen Kanal auswählen, können Sie einen Verweis auf den gewünschten Kanal entweder nach dem Kanal oder nach dem Kanal-Pfad angeben.

* **nach Pfad**: Sie stellen einen expliziten Verweis durch Angabe des absoluten Pfads des Kanals bereit.

* **nach Name**: Sie geben den Namen des Kanals ein, der entsprechend dem Kontext zu einem tatsächlichen Kanal führt. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, um standortspezifischen Inhalt dynamisch aufzulösen. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle kann durch verschiedene Aktionen festgelegt werden und ist unabhängig vom eigentlichen Kanal, der der Rolle entspricht.

### Priorität {#priority-channel}

Mit „Priorität“ können Zuweisungen geordnet werden, falls mehrere die Wiedergabekriterien erfüllen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Wenn es beispielsweise die beiden Kanäle A und B gibt und A eine Priorität von 1 und B eine Priorität von 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Darüber hinaus werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

### Unterstützte Ereignisse {#supported-events-channel}

* **Erster Ladevorgang**: Lädt den Kanal, wenn der Player gestartet wird. Dies kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden.
* **Bildschirm bei Untätigkeit**: Lädt, wenn der Bildschirm inaktiv ist. Dies kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden.
* **Timer**: Muss eingestellt werden, wenn ein Zeitplan vorhanden ist
* **Benutzerinteraktion**: Der Player wechselt in den angegebenen Kanal, wenn in einem inaktiven Kanal auf dem Bildschirm (Touch) eine Benutzerinteraktion stattfindet, und wird geladen, wenn der Bildschirm berührt wird.

### Unterbrechungsmethode {#interruption-method-channel}

>[!IMPORTANT]
>
> Diese Option ist nur mit AEM 6.4 Feature Pack 8 oder AEM 6.5 Feature Pack 4 verfügbar.

Als Autor von Inhalten sollten Sie festlegen können, wann ein Kanal unterbrochen wird, damit nicht kritische Inhalte abgeschnitten werden können, wichtige Inhalte jedoch vollständig abgespielt werden, bevor die Wiedergabe aufgrund der Zeitplanung abgebrochen wird.

Wählen Sie eine der folgenden Optionen aus, die zum Festlegen der Unterbrechungsmethode im Dialogfeld **Kanalzuweisung** verfügbar sind:

* **Sofort**: Wenn der Zeitplan aktiviert oder eine Aktualisierung empfangen wird, können Sie die Wiedergabe abbrechen und den neuen Inhalt sofort aktualisieren oder wiedergeben.
* **Am Ende des aktuellen Elements**: Wenn ein neuer Zeitplan aktiviert wird oder eine Aktualisierung empfangen wird, haben Sie die Möglichkeit zu warten, bis die Wiedergabe des aktuellen Elements in der Sequenz abgeschlossen ist. Danach aktualisieren Sie den neuen Inhalt und geben ihn wieder.
   >[!NOTE]
   >Standardmäßig ist diese Option aktiviert.
* **Am Ende der Sequenz**: Wenn ein neuer Zeitplan aktiviert oder eine Aktualisierung empfangen wird, haben Sie die Möglichkeit zu warten, bis die gesamte Sequenz ihr Ende erreicht. Kurz vor der gewünschten Sequenz kehren Sie zurück zum ersten Element, aktualisieren den neuen Inhalt oder spielen diesen ab.

   >[!NOTE]
   >Die Verwendung der zweiten oder dritten Option kann dazu führen, dass die für die Zuweisung festgelegten Zeiträume geringfügig verschoben werden, da der Player vor dem Aktualisieren auf das Ende des Elements oder der Sequenz (nach der angegebenen Zeit) wartet. Die Verzögerung hängt von der Wiedergabedauer des Elements ab.


Die folgenden Eigenschaften werden über die Option &quot; **Plan** &quot;im Dialogfeld &quot; **Kanal-Zuweisung** &quot;festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Referenzzeitzone {#reference-timezone}

Mit der Referenz-Zeitzone können Sie die Zeitzone für die Inhaltsanzeige auswählen.

### Aktivierungsfenster {#activation-window}

Im Fenster &quot;Aktivierung&quot;können Sie ein **Beginn-Datum** und ein **Enddatum** zur Inhaltsanzeige auswählen.

### Intervallzeitplan {#recurrence-schedule}

Mit dem Zeitplan für die Wiederholung können Sie einen Zeitplan für Ihre Inhalte festlegen. Klicken Sie auf **+ Hinzufügen Plan** , um Ihrem Kanal einen Zeitplan für eine Wiederholung hinzuzufügen.

>[!NOTE]
>Sie können Ihrem Kanal mehrere wiederkehrende Zeitpläne hinzufügen.
>Recurrence Schedules introduces *DayParting*, that allows you to set a global schedule with multiple channels running at specific times of the day, and re-use that setup for all your displays at once.

Sie können die folgenden Optionen festlegen:

* **Name**: Titel des Zeitplans für die Wiederholung.
* **Wiederholen**: Wählen Sie aus, ob der Plan **täglich**, **wöchentlich**, **monatlich** oder **jährlich** ausgeführt werden soll.
* **Beginn**: Die Zeitdauer des Beginns für Ihren Zeitplan.
* **Ende**: Die Endzeit Ihres Zeitplans. Sie können die Einstellung nach Zeit oder Dauer festlegen.
   * **Zeit**: Der Zeitplan endet zu einem bestimmten Zeitpunkt.
   * **Dauer**: Der Zeitplan läuft für eine bestimmte Dauer in Stunden oder Minuten.

### DayParting {#dayparting}

Bei Dayparting wird ein Tag in Zeitfenster unterteilt und festgelegt, welcher Inhalt zum gewünschten Zeitpunkt dargestellt wird. Mit AEM Screens können Sie Kanal in Form von DayParting innerhalb eines Tages, einer Woche oder eines Monats nach Bedarf planen.

Die folgenden Beispiele erklären DayParting in Kanälen in drei verschiedenen Szenarien:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster     {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

Dieses Beispiel zeigt, wie ein Restaurant mit DayParting täglich sein Frühstück-, Mittag- und Abendmenü präsentiert.

Hier unterteilen wir jeden Tag in verschiedene Zeiträume, sodass der Kanal-Inhalt gemäß der angegebenen Tageszeit abgespielt wird. Legen Sie die folgenden Eigenschaften des Zeitplans für die Wiederkehrung fest, damit der Kanal den Inhalt gemäß diesem Verwendungsfall wiedergeben kann.

| **Name** | **Wiederholen** | **Anfang** | **Ende** |
|---|---|---|---|
| Frühstück | Täglich | 06:00 | 11:00 Uhr |
| Mittagessen | Täglich | 11:02 | 15:00 |
| Abendessen | Täglich | 15:01 | 20:00 |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

Dieses Beispiel zeigt die DayParting in einem Casino implementiert, in dem Live-Ereignis an jedem Wochenende von 20:00 bis 22:00 Uhr stattfindet und Spezialitäten für das Abendmenü nach 22:00 Uhr bis 13:00 Uhr zur Verfügung stehen.

| **Name** | **Wiederholen** | **Anfang** | **Ende** |
|---|---|---|---|
| Wochenende | Wöchentlich | 20:00 | 22:00 |
| Spezial | Täglich | 22:00 | 01:00 |

>[!NOTE]
>
>Darüber hinaus können Sie für jeden Kanal die ***Priorität*** festlegen. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird der Kanal mit höherer Priorität zuerst gezeigt. Der Mindestwert für die Priorität beträgt 0.

