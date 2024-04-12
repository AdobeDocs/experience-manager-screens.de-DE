---
title: Kanalzuweisung – Neuestes Feature Pack
description: Erfahren Sie mehr über Kanalzuweisung und Tagesaufteilung.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 346eec9a-e291-4b0d-9686-fee1d5a0e7dd
source-git-commit: ba5327077e4a2d30cc7b77f02123da5a240c67ae
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 41%

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

Nach Abschluss der Projekteinrichtung müssen Sie den Kanal einer Anzeige zuweisen, um den Inhalt anzuzeigen.

1. Navigieren Sie zur gewünschten Anzeige, beispielsweise **DemoScreens** > **Standorte** > **SanJose** > **Lobby**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Oder

   Tippen/klicken Sie in der Aktionsleiste auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+ Kanal zuweisen**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Unter **Einstellungen** können Sie den Kanal **nach Pfad** oder **nach Namen** auswählen, die **Kanalrolle**, die **Priorität**, die **unterstützten Ereignisse** und die **Unterbrechungsmethoden** eingeben. Außerdem können Sie die Attraktions-QuickInfo in diesem Dialogfeld aktivieren.

   ![Bild](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >
   >Weitere Informationen zu den Kanalzuweisungseigenschaften finden Sie unter [Kanaleigenschaften](#channel-properties) Abschnitt.

1. Aus dem **Zeitplan** auswählen, wählen Sie die **Aktivierungsfenster** und **Wiederholungsplan**.
   ![Bild](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >
   >Weitere Informationen zu den Kanalzuweisungseigenschaften finden Sie unter [Kanaleigenschaften](#channel-properties) Abschnitt.

1. Klicken Sie auf **Speichern**, nachdem Sie Ihre Voreinstellungen konfiguriert haben.

### Anzeigen von Inhalten im Chrome-Player {#viewing-content-output}

In diesem Beispiel wird die Ausgabe auf einem Chrome-Player beschrieben. Nachdem Sie den Kanal Ihrer Anzeige zugewiesen haben, müssen Sie das Gerät bei einem Player registrieren.

Informationen zum Registrieren eines Geräts auf einem AEM Screens-Player finden Sie unter [Geräteregistrierung](device-registration.md).

Sie können die folgende Ausgabe auf Ihrem Player anzeigen:

![new1](assets/channel-assignment/channel-assign-output.gif)

## Timeline-Ansicht {#timeline-view}

Nachdem Sie einen Kanal einer Anzeige zugewiesen und einen Intervallzeitplan eingerichtet haben, können Sie die Timeline im Bedienfeld **ZUGEWIESENE KANÄLE &amp; ZEITPLÄNE** anzeigen.

Führen Sie die folgenden Schritte aus, um zur Timeline-Ansicht zu navigieren:

1. Navigieren Sie zur gewünschten Anzeige, beispielsweise **DemoScreens** > **Standorte** > **SanJose** > **Lobby**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   Oder

   Tippen/klicken Sie auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **Timeline**.

   ![image](/help/user-guide/assets/channel-assignment/timeline-1.png)

## Verstehen der Kanaleigenschaften im Dialogfeld „Kanalzuweisung“ {#channel-properties}

Die folgenden Eigenschaften werden über die Option **Einstellungen** im Dialogfeld **Kanalzuweisung** festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Kanal auswählen {#select-channel}

Wenn Sie einen Kanal auswählen, können Sie einen Verweis auf den gewünschten Kanal entweder nach Kanalname oder nach Kanalpfad bereitstellen.

* **Nach Pfad** - Sie stellen einen expliziten Verweis mithilfe des absoluten Pfads des Kanals bereit.
* **Nach Name** - Sie geben den Namen des Kanals ein, der nach Kontext zu einem tatsächlichen Kanal aufgelöst wird. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, damit Sie standortspezifischen Inhalt dynamisch auflösen können. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle wird durch verschiedene Aktionen angesprochen und ist unabhängig vom tatsächlichen Kanal, der die Rolle erfüllt.

### Priorität {#priority-channel}

Die Priorität wird verwendet, um die Zuweisungen in eine Reihenfolge zu bringen, wenn mehrere Zuweisungen den Wiedergabekriterien entsprechen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Angenommen, es gibt zwei Kanäle, A und B. Wenn A die Priorität 1 und B die Priorität 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Außerdem werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

### Unterstützte Ereignisse {#supported-events-channel}

* **Erster Ladevorgang** - Lädt den Kanal, wenn der Player gestartet wird. Er kann mehreren Kanälen mit einem Zeitplan zugewiesen werden.
* **Idle Screen** - Wird geladen, wenn der Bildschirm inaktiv ist. Er kann mehreren Kanälen mit einem Zeitplan zugewiesen werden.
* **Timer** - Muss festgelegt werden, wenn ein Zeitplan angegeben wird.
* **Benutzerinteraktion** - Der Player wechselt zum angegebenen Kanal, wenn eine Benutzerinteraktion auf dem Bildschirm (Touch) in einem inaktiven Kanal stattfindet und geladen wird, wenn der Bildschirm berührt wird.

### Unterbrechungsmethode {#interruption-method-channel}

>[!IMPORTANT]
> Diese Option ist nur verfügbar mit <!--AEM 6.4 Feature Pack 8 or-->AEM 6.5 Feature Pack 4.

Als Inhaltsautor können Sie festlegen, wann ein Kanal unterbrochen wird. Auf diese Weise können Sie nichtkritische Inhalte abbrechen. Es bietet Ihnen jedoch auch die Möglichkeit, wichtige Inhalte vollständig wiederzugeben, bevor Sie sie aufgrund der Planung kürzen.

Wählen Sie eine der folgenden Optionen aus, die zum Festlegen der Unterbrechungsmethode im Dialogfeld **Kanalzuweisung** verfügbar sind:

* **Sofort** - Wenn der Zeitplan aktiviert oder eine Aktualisierung empfangen wird, können Sie die Wiedergabe abbrechen und den neuen Inhalt sofort aktualisieren oder wiedergeben
* **Ende des aktuellen Elements** - Wenn ein neuer Zeitplan aktiviert oder eine Aktualisierung empfangen wird, können Sie optional warten, bis die Wiedergabe des aktuellen Elements in der Sequenz abgeschlossen ist. Danach können Sie den neuen Inhalt aktualisieren oder wiedergeben.

  >[!NOTE]
  >Standardmäßig ist diese Option aktiviert.

* **Am Ende der Sequenz** - Wenn ein neuer Zeitplan aktiviert oder eine Aktualisierung empfangen wird, können Sie optional warten, bis die gesamte Sequenz ihr Ende erreicht. Kurz vor der gewünschten Sequenz können Sie dann zum ersten Element zurückkehren, den neuen Inhalt aktualisieren oder wiedergeben.

  >[!NOTE]
  >Die Verwendung der zweiten oder dritten Option kann dazu führen, dass die für die Zuweisung festgelegten Planungszeiten geringfügig verschoben werden. Der Grund dafür ist, dass der Player vor der Aktualisierung auf das Ende des Elements oder der Sequenz (nach der angegebenen Zeit) wartet. Die Verzögerung hängt von der Wiedergabedauer des Elements ab.

Die folgenden Eigenschaften werden über die Option **Zeitplan** im Dialogfeld **Kanalzuweisung** festgelegt.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Aktivierungsfenster {#activation-window}

Im Aktivierungsfenster können Sie eine **Startdatum** und **Enddatum** , um Ihren Inhalt anzuzeigen.

### Intervallzeitplan {#recurrence-schedule}

Mit dem Intervallzeitplan können Sie einen Zeitplan für Ihren Inhalt festlegen. Auswählen **+ Zeitplan hinzufügen** , um Ihrem Kanal einen Intervallzeitplan hinzuzufügen.

>[!NOTE]
>Sie können Ihrem Kanal mehrere Intervallzeitpläne hinzufügen.
>Einführung in Intervallzeitpläne *Dayparting* ermöglicht Ihnen, einen globalen Zeitplan mit mehreren Kanälen festzulegen, die zu bestimmten Tageszeiten ausgeführt werden, und diese für alle Anzeigen wiederzuverwenden.

Sie können die folgenden Optionen festlegen:

* **Name** - Titel Ihres Intervallzeitplans.
* **Wiederholen** - Legen Sie fest, ob der Zeitplan ausgeführt werden soll **Täglich**, **Wöchentlich**, **Monatlich** oder **Jährlich**.
* **Starten** - Die Startzeit für Ihren Zeitplan.
* **Ende** - Die Endzeit Ihres Zeitplans. Sie können die Einstellung nach Zeit oder Dauer festlegen.
   * **Zeit** - Der Zeitplan endet zu einem bestimmten Zeitpunkt.
   * **Dauer** - Der Zeitplan wird für eine bestimmte Zeitdauer in Stunden oder Minuten ausgeführt.

### DayParting {#dayparting}

Tagesaufteilung bezeichnet die Aufteilung eines Tages in Zeitfenster und die Angabe, welcher Inhalt zum gewünschten Zeitpunkt dargestellt wird. Mit AEM Screens können Sie die Planung von Kanälen in Form von Dayparting nach Bedarf für einen Tag, eine Woche oder einen Monat festlegen.

Im Folgenden wird in drei Szenarien beschrieben, wie Dayparting mit Kanälen verwendet werden kann:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In diesem Beispiel wird gezeigt, wie ein Restaurant Dayparting verwendet, um täglich sein Angebot für Frühstück, Mittagessen und Abendessen zu präsentieren.

Hier wird jeder Tag in verschiedene Zeitfenster unterteilt, sodass der Kanalinhalt gemäß der angegebenen Tageszeit wiedergegeben wird. Legen Sie die folgenden Eigenschaften des Intervallzeitplans für Ihren Kanal fest, um den Inhalt gemäß diesem Verwendungsfall wiederzugeben.

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Frühstück | Täglich | 06:00 Uhr | 11:00 Uhr |
| Mittagessen | Täglich | 11:00 Uhr | 15:00 Uhr |
| Abendessen | Täglich | 15:00 Uhr | 20:00 Uhr |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

In diesem Beispiel wird gezeigt, wie Dayparting in einem Casino umgesetzt wird, wo an jedem Wochenende von 20:00 Uhr bis 22:00 Uhr eine Live-Veranstaltung stattfindet und von 22:00 Uhr bis 13:00 Uhr in der Abendkarte spezielle Gerichte angeboten werden.

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Wochenende | Wöchentlich: Samstag und Sonntag | 20:00 Uhr | 22:00 Uhr |
| Sonderangebote | Täglich: Montag bis Freitag | 22:00 Uhr | 13:00 Uhr |

>[!NOTE]
>
>Außerdem können Sie ***Priorität*** für jeden Kanal. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird der Kanal mit höherer Priorität zuerst wiedergegeben. Der Mindestwert für die Priorität kann auf 0 gesetzt werden.
