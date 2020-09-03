---
title: Kanalzuweisung – Neuestes Feature Pack
seo-title: Kanalzuweisung – Neuestes Feature Pack
description: Folgen Sie dieser Seite, um mehr über die Zuweisung von Kanälen und die Tagesaufteilung zu erfahren.
translation-type: tm+mt
source-git-commit: 421174dba8a5a7c39bffcaa2dddb54939eeba3bc
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 78%

---


# Kanalzuweisung {#channel-assignment}

>[!IMPORTANT]
>In diesem Abschnitt werden die Zuweisung und Planung von Kanälen für Kanal AEM 6.5.5 Screens Feature Pack und höher erläutert.

Nachdem Sie eine Anzeige eingerichtet haben, müssen Sie der Anzeige einen Kanal zuweisen, um Ihren Inhalt anzuzeigen.

Diese Seite zeigt Ihnen, wie Sie Ihrer Anzeige einen Kanal zuweisen, wie Sie die Eigenschaften des Kanals und DayParting verstehen.

>[!NOTE]
>Sie können einer Anzeige mehrere Kanäle zuweisen.


## Zuweisen von Kanälen {#assign-a-channel-new-release}

Gehen Sie wie folgt vor, um ein AEM Screens-Projekt zu erstellen und einer Anzeige einen Kanal zuzuweisen.

### Erstellen eines AEM Screens-Projekts und von Kanälen {#creating-project}

Gehen Sie wie folgt vor, um ein Projekt und einen Kanal einzurichten:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Titel **DemoScreens**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >Informationen zum Erstellen eines AEM Screens-Projekts finden Sie unter [Erstellen und Verwalten von Projekten](creating-a-screens-project.md).

1. Erstellen Sie einen Sequenzkanal mit dem Namen **Cafeteria** im Ordner **Kanäle**.

1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um dem Kanal Inhalte hinzuzufügen.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Beispielsweise werden im Kanal **Cafeteria** jetzt folgende Bilder angezeigt:

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Erstellen Sie einen Standort mit dem Titel **SanJose** und eine Anzeige mit dem Namen **Lobby**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Zuweisen eines Kanals zu einer Anzeige {#assigning-channel-to-display}

Nachdem das Projekt eingerichtet wurde, müssen Sie den Kanal einer Anzeige zuweisen, um den Inhalt Ansicht.

1. Navigieren Sie zur gewünschten Anzeige, z. B. **DemoScreens** > **Standorte** > **SanJose** > **Lobby**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Oder

   Tap/click **Dashboard** from the action bar and click **+Assign Channel** from the **ASSIGNED CHANNELS &amp; SCHEDULES** panel.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. From the **Settings** option, you can choose the channel **by path** or **by name**, enter the **Channel Role**, **Priority**, **Supported Events**, and **Interruption Methods**. Darüber hinaus können Sie die für Attraktions-QuickInfos in diesem Dialogfeld aktivieren.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >Refer to [Channel Properties](#channel-properties) section to learn more about channel assignment properties.

1. From the **Schedule** option select the **Activation Window** and **Recurrence Schedule**.
   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >Refer to [Channel Properties](#channel-properties) section to learn more about channel assignment properties.

1. Klicken Sie auf **Speichern**, nachdem Sie Ihre Voreinstellungen konfiguriert haben.

### Anzeigen von Inhalten im Chrome-Player {#viewing-content-output}

In diesem Beispiel wird die Ausgabe auf einem Chrome-Player beschrieben. Nachdem Sie den Kanal Ihrer Anzeige zugewiesen haben, müssen Sie das Gerät bei einem Player registrieren.

Informationen zum Registrieren eines Geräts auf einem AEM Screens-Player finden Sie unter [Geräteregistrierung](device-registration.md).

Sie werden die folgende Ausgabe auf Ihrem Player sehen:

![new1](assets/channel-assignment/channel-assign-output.gif)

## Timeline View {#timeline-view}

Nachdem Sie einen Kanal einer Anzeige zugewiesen und einen Wiederholungsplan eingerichtet haben, können Sie die Zeitschiene im Bedienfeld &quot; **ZUGEWIESENE KANAL &amp; ZEITPLAN** &quot;Ansicht haben.

Gehen Sie wie folgt vor, um zur Ansicht der Zeitschiene zu navigieren:

1. Navigieren Sie zur gewünschten Anzeige, z. B. **DemoScreens** > **Standorte** > **SanJose** > **Lobby**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   Oder

   Tap/click **Dashboard** and click **Timeline** from the **ASSIGNED CHANNELS &amp; SCHEDULES** panel.

   ![image](/help/user-guide/assets/channel-assignment/timeline-1.png)

## Understanding Channel Properties from Channel Assignment Dialog Box {#channel-properties}

Die folgenden Eigenschaften werden über die Option **Einstellungen** im Dialogfeld **Kanalzuweisung** festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Kanal auswählen {#select-channel}

Mit der Auswahl eines Kanals können Sie einen Verweis zum gewünschten Kanal bereitstellen, entweder in Form des Namens oder des Pfads des Kanals.

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


Die folgenden Eigenschaften werden über die Option **Zeitplan** im Dialogfeld **Kanalzuweisung** festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Aktivierungsfenster {#activation-window}

Im Aktivierungsfenster können Sie ein **Anfangsdatum** und ein **Enddatum** für die Inhaltsanzeige auswählen.

### Intervallzeitplan {#recurrence-schedule}

Mit dem Intervallzeitplan können Sie einen Zeitplan für Ihre Inhalte festlegen. Klicken Sie auf **+ Zeitplan hinzufügen**, um Ihrem Kanal einen Intervallzeitplan hinzuzufügen.

>[!NOTE]
>Sie können Ihrem Kanal mehrere Intervallzeitpläne hinzufügen.
>Mit den Intervallzeitplänen wird *Dayparting* eingeführt, wodurch Sie einen globalen Zeitplan mit mehreren Kanälen festlegen können, die zu bestimmten Tageszeiten ausgeführt werden. Diese Einstellung kann dann für alle Anzeigen wiederverwendet werden.

Sie können die folgenden Optionen festlegen:

* **Name**: Titel des Intervallzeitplans.
* **Wiederholen**: Wählen Sie aus, ob der Plan **täglich**, **wöchentlich**, **monatlich** oder **jährlich** ausgeführt werden soll.
* **Anfang**: Die Startzeit Ihres Zeitplans.
* **Ende**: Die Endzeit Ihres Zeitplans. Sie können die Einstellung nach Zeit oder Dauer festlegen.
   * **Zeit**: Der Zeitplan endet zu einer bestimmten Zeit.
   * **Dauer**: Der Zeitplan wird für eine bestimmte Zeitdauer in Stunden oder Minuten ausgeführt.

### Dayparting {#dayparting}

DayParting bezieht sich auf die Aufteilung eines Tages in Zeitnischen und die Angabe, welche Inhalte zur gewünschten Zeit abgespielt werden. Mit AEM Screens können Sie den Dayparting-Zeitplan von Kanälen nach Bedarf für Tage, Wochen oder Monate festlegen.

Im Folgenden wird in drei Szenarien beschrieben, wie Dayparting mit Kanälen verwendet werden kann:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster       {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

Dieses Beispiel zeigt, wie ein Restaurant mit DayParting täglich sein Frühstück-, Mittag- und Abendmenü präsentiert.

Hier unterteilen wir jeden Tag in verschiedene Zeiträume, sodass der Kanal-Inhalt gemäß der angegebenen Tageszeit abgespielt wird. Legen Sie die folgenden Eigenschaften des Zeitplans für die Wiederkehrung fest, damit der Kanal den Inhalt gemäß diesem Verwendungsfall wiedergeben kann.

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Frühstück | Täglich | 06:00 Uhr | 11:00 Uhr |
| Mittagessen | Täglich | 11:00 Uhr | 15:00 Uhr |
| Abendessen | Täglich | 15:00 Uhr | 20:00 Uhr |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

Dieses Beispiel zeigt die DayParting in einem Casino implementiert, in dem Live-Ereignis an jedem Wochenende von 20:00 bis 22:00 Uhr stattfindet und Spezialitäten für das Abendmenü nach 22:00 Uhr bis 13:00 Uhr zur Verfügung stehen.

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Wochenende | Wöchentlich: Samstag, Sonntag | 20:00 Uhr | 22:00 |
| Sonderaktionen | Täglich: Montag bis Freitag | 22:00 | 1:00 Uhr |

>[!NOTE]
>
>Darüber hinaus können Sie für jeden Kanal die ***Priorität*** festlegen. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird der Kanal mit höherer Priorität zuerst gezeigt. Der Mindestwert für die Priorität beträgt 0.

