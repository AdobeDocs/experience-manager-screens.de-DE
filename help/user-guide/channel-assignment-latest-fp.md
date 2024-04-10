---
title: Kanalzuweisung – Neuestes Feature Pack
description: Erfahren Sie mehr über die Kanalzuweisung und die Tagesaufteilung.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 346eec9a-e291-4b0d-9686-fee1d5a0e7dd
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '1462'
ht-degree: 45%

---

# Kanalzuweisung {#channel-assignment}

>[!IMPORTANT]
>
>In diesem Abschnitt werden Kanalzuweisung und -zeitplanung für das AEM Screens 6.5.5 Feature Pack (und höher) beschrieben.

Nachdem Sie eine Anzeige eingerichtet haben, müssen Sie der Anzeige einen Kanal zuweisen, um Ihren Inhalt anzuzeigen.

Auf dieser Seite wird beschrieben, wie Sie Ihrer Anzeige einen Kanal zuweisen. Außerdem werden Kanaleigenschaften und Dayparting erklärt.

>[!NOTE]
>
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

1. Wählen Sie den Kanal aus und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Beispielsweise werden im Kanal **Cafeteria** jetzt folgende Bilder angezeigt:

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Erstellen Sie einen Standort mit dem Titel **SanJose** und eine Anzeige mit dem Namen **Lobby**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Zuweisen eines Kanals zu einer Anzeige {#assigning-channel-to-display}

Wenn die Projekteinrichtung abgeschlossen ist, müssen Sie den Kanal einem Display zuweisen, um den Inhalt anzuzeigen.

1. Navigieren Sie zur gewünschten Anzeige, z. B. **DemoScreens** > **Speicherorte** > **SanJose** > **Lobby**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Oder

   Tippen/klicken Sie in der Aktionsleiste auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+ Kanal zuweisen**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Unter **Einstellungen** können Sie den Kanal **nach Pfad** oder **nach Namen** auswählen, die **Kanalrolle**, die **Priorität**, die **unterstützten Ereignisse** und die **Unterbrechungsmethoden** eingeben. In diesem Dialogfeld können Sie auch die QuickInfo Attraktion aktivieren.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >
   >Weitere Informationen zu den Kanalzuweisungseigenschaften finden Sie im Abschnitt [Kanaleigenschaften](#channel-properties).

1. Aus dem **Zeitplan** die Option auswählen **Aktivierungsfenster** und **Wiederholungszeitplan**.
   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >
   >Weitere Informationen zu den Kanalzuweisungseigenschaften finden Sie im Abschnitt [Kanaleigenschaften](#channel-properties).

1. Klicken Sie auf **Speichern**, nachdem Sie Ihre Voreinstellungen konfiguriert haben.

### Anzeigen von Inhalten im Chrome-Player {#viewing-content-output}

In diesem Beispiel wird die Ausgabe auf einem Chrome-Player beschrieben. Nachdem Sie den Kanal Ihrer Anzeige zugewiesen haben, müssen Sie das Gerät bei einem Player registrieren.

Informationen zum Registrieren eines Geräts auf einem AEM Screens-Player finden Sie unter [Geräteregistrierung](device-registration.md).

Sie können die folgende Ausgabe für einen Player Ihrer Wahl anzeigen:

![new1](assets/channel-assignment/channel-assign-output.gif)

## Timeline-Ansicht {#timeline-view}

Nachdem Sie einen Kanal einer Anzeige zugewiesen und einen Intervallzeitplan eingerichtet haben, können Sie die Timeline im Bedienfeld **ZUGEWIESENE KANÄLE &amp; ZEITPLÄNE** anzeigen.

Führen Sie die folgenden Schritte aus, um zur Timeline-Ansicht zu navigieren:

1. Navigieren Sie zur gewünschten Anzeige, z. B. **DemoScreens** > **Speicherorte** > **SanJose** > **Lobby**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   Oder

   Tippen/klicken Sie auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **Timeline**.

   ![image](/help/user-guide/assets/channel-assignment/timeline-1.png)

## Verstehen der Kanaleigenschaften im Dialogfeld „Kanalzuweisung“ {#channel-properties}

Die folgenden Eigenschaften werden über die Option **Einstellungen** im Dialogfeld **Kanalzuweisung** festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Kanal auswählen {#select-channel}

Wenn Sie einen Kanal auswählen, können Sie einen Verweis auf den gewünschten Kanal entweder über den Kanalnamen oder über den Kanalpfad angeben.

* **Nach Pfad** - Sie geben eine explizite Referenz unter Verwendung des absoluten Pfads des Kanals an.
* **Nach Name** - Sie geben den Namen des Kanals ein, der anhand des Kontexts zu einem tatsächlichen Kanal aufgelöst wird. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, damit Sie ortsspezifische Inhalte dynamisch auflösen können. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle wird durch verschiedene Aktionen angesprochen und ist unabhängig vom tatsächlichen Kanal, der die Rolle erfüllt.

### Priorität {#priority-channel}

Die Priorität wird verwendet, um die Zuweisungen in eine Reihenfolge zu bringen, wenn mehrere Zuweisungen den Wiedergabekriterien entsprechen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Angenommen, es gibt zwei Kanäle, A und B. Wenn A die Priorität 1 und B die Priorität 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Außerdem werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

### Unterstützte Ereignisse {#supported-events-channel}

* **Vorbelastung** - Lädt den Kanal, wenn der Player gestartet wird. Sie kann mehreren Kanälen mit einem Zeitplan zugewiesen werden.
* **Bildschirm im Leerlauf** - Lädt, wenn der Bildschirm inaktiv ist. Sie kann mehreren Kanälen mit einem Zeitplan zugewiesen werden.
* **Timer** - Muss festgelegt werden, wenn ein Zeitplan bereitgestellt wird.
* **Benutzerinteraktion** - Der Player wechselt in den angegebenen Kanal, wenn eine Benutzerinteraktion auf dem Bildschirm (Touch) in einem inaktiven Kanal stattfindet, und lädt, wenn der Bildschirm berührt wird.

### Unterbrechungsmethode {#interruption-method-channel}

>[!IMPORTANT]
> Diese Option ist nur verfügbar mit <!--AEM 6.4 Feature Pack 8 or-->AEM 6.5 Feature Pack 4.

Als Inhaltsautor können Sie angeben, wann ein Kanal unterbrochen wird. Auf diese Weise können Sie nicht kritische Inhalte abschneiden. Sie haben jedoch auch die Möglichkeit, wichtige Inhalte vollständig wiederzugeben, bevor sie aufgrund von Zeitplänen gekürzt werden.

Wählen Sie eine der folgenden Optionen aus, die zum Festlegen der Unterbrechungsmethode im Dialogfeld **Kanalzuweisung** verfügbar sind:

* **Immediately** - Wenn der Zeitplan aktiviert wird oder eine Aktualisierung empfangen wird, können Sie die Wiedergabe abschneiden und den neuen Inhalt sofort aktualisieren oder wiedergeben
* **Ende des aktuellen Elements** - Wenn ein neuer Zeitplan aktiviert oder eine Aktualisierung empfangen wird, können Sie optional warten, bis das aktuelle Element in der Sequenz die Wiedergabe abgeschlossen hat. Erst danach können Sie den neuen Inhalt aktualisieren oder wiedergeben.

  >[!NOTE]
  >Standardmäßig ist diese Option aktiviert.

* **Am Ende der Sequenz** - Wenn ein neuer Zeitplan aktiviert wird oder eine Aktualisierung empfangen wird, können Sie optional warten, bis die gesamte Sequenz ihr Ende erreicht. Anschließend können Sie direkt vor der gewünschten Sequenz zum ersten Element zurückkehren, es aktualisieren oder den neuen Inhalt wiedergeben.

  >[!NOTE]
  >Die Verwendung der zweiten oder dritten Option kann dazu führen, dass die für die Zuweisung definierten Planungszeiten geringfügig verschoben werden. Der Grund dafür ist, dass der Player vor dem Aktualisieren auf das Ende des Elements oder der Sequenz (nach der angegebenen Zeit) wartet. Die Verzögerung hängt von der Wiedergabedauer des Elements ab.

Die folgenden Eigenschaften werden über die Option **Zeitplan** im Dialogfeld **Kanalzuweisung** festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Aktivierungsfenster {#activation-window}

Im Aktivierungsfenster können Sie eine **Startdatum** und ein **Enddatum** um Ihren Inhalt anzuzeigen.

### Intervallzeitplan {#recurrence-schedule}

Mit dem Wiederholungszeitplan können Sie einen wiederkehrenden Zeitplan für Ihren Inhalt festlegen. Auswählen **+ Zeitplan hinzufügen** , um einen Wiederholungszeitplan zu Ihrem Kanal hinzuzufügen.

>[!NOTE]
>Sie können Ihrem Kanal mehrere Intervallzeitpläne hinzufügen.
>Wiederkehrende Zeitpläne führen ein *DayParting* Dadurch können Sie einen globalen Zeitplan mit mehreren Kanälen festlegen, die zu bestimmten Tageszeiten ausgeführt werden, und diesen Zeitplan dann für alle Ihre Displays gleichzeitig wiederverwenden.

Sie können die folgenden Optionen festlegen:

* **Name** - Titel Ihres Wiederholungszeitplans.
* **Wiederholen** : Auswählen, ob der Zeitplan ausgeführt wird **Täglich**, **Wöchentlich**, **Monatlich**, oder **Jährlich**.
* **Starten** - Die Startzeit für Ihren Zeitplan.
* **Ende** - Die Endzeit für Ihren Zeitplan. Sie können die Einstellung nach Zeit oder Dauer festlegen.
   * **Zeit** - Der Zeitplan endet zu einem bestimmten Zeitpunkt.
   * **Dauer** - Der Zeitplan wird für eine bestimmte Zeitdauer in Stunden oder Minuten ausgeführt.

### DayParting {#dayparting}

Day Parting bezieht sich auf die Aufteilung eines Tages in Zeitschlitze und die Angabe, welcher Inhalt zum gewünschten Zeitpunkt abgespielt wird. Mit AEM Screens können Sie Kanäle in Form von DayParting innerhalb eines Tages, einer Woche oder eines Monats gemäß den Anforderungen planen.

Im Folgenden wird in drei Szenarien beschrieben, wie Dayparting mit Kanälen verwendet werden kann:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

Dieses Beispiel zeigt, wie ein Restaurant DayParting verwendet, um sein Frühstück, Mittag- und Abendmenü jeden Tag zu präsentieren.

Hier wird jeder Tag in verschiedene Zeitfenster unterteilt, sodass der Kanalinhalt gemäß der angegebenen Tageszeit wiedergegeben wird. Legen Sie die folgenden Eigenschaften des Intervallzeitplans für Ihren Kanal fest, um den Inhalt gemäß diesem Verwendungsfall wiederzugeben.

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Frühstück | Täglich | 06:00 | 11:00 |
| Mittagessen | Täglich | 11:00 | 15:00 |
| Abendessen | Täglich | 15:00 | 20:00 |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

Dieses Beispiel zeigt das DayParting in einem Casino, in dem jedes Wochenende von 20:00 bis 22:00 Uhr Live-Veranstaltungen stattfinden und nach 22:00 bis 1:00 Uhr Abendmenüs angeboten werden.

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Wochenende | Wöchentlich: Samstag und Sonntag | 20:00 | 22:00 |
| Sonderangebote | Täglich: Montag bis Freitag | 22:00 | 01:00 |

>[!NOTE]
>
>Außerdem können Sie Folgendes definieren ***Priorität*** für jeden der Kanäle. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird zuerst der Kanal mit höherer Priorität wiedergegeben. Der Mindestwert für die Priorität kann auf 0 festgelegt werden.
