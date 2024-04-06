---
title: Kanalzuweisung – Neuestes Feature Pack
seo-title: Channel Assignment - Latest FP
description: Auf dieser Seite erhalten Sie Informationen zur Kanalzuweisung und zu Dayparting.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 346eec9a-e291-4b0d-9686-fee1d5a0e7dd
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 88%

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

1. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um dem Kanal Inhalte hinzuzufügen.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Beispielsweise werden im Kanal **Cafeteria** jetzt folgende Bilder angezeigt:

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Erstellen Sie einen Standort mit dem Titel **SanJose** und eine Anzeige mit dem Namen **Lobby**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Zuweisen eines Kanals zu einer Anzeige {#assigning-channel-to-display}

Nachdem das Projekt fertig eingerichtet wurde, müssen Sie den Kanal einem Display zuweisen, um den Inhalt anzuzeigen.

1. Navigieren Sie zur gewünschten Anzeige, beispielsweise **DemoScreens** > **Standorte** > **SanJose** > **Lobby**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Oder

   Tippen/klicken Sie in der Aktionsleiste auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+ Kanal zuweisen**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Unter **Einstellungen** können Sie den Kanal **nach Pfad** oder **nach Namen** auswählen, die **Kanalrolle**, die **Priorität**, die **unterstützten Ereignisse** und die **Unterbrechungsmethoden** eingeben. Darüber hinaus können Sie die Attraktions-QuickInfos in diesem Dialogfeld aktivieren.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >
   >Weitere Informationen zu den Kanalzuweisungseigenschaften finden Sie im Abschnitt [Kanaleigenschaften](#channel-properties).

1. Wählen Sie unter **Zeitplan** die Optionen **Aktivierungsfenster** und **Intervallzeitplan** aus.
   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >
   >Weitere Informationen zu den Kanalzuweisungseigenschaften finden Sie im Abschnitt [Kanaleigenschaften](#channel-properties).

1. Klicken Sie auf **Speichern**, nachdem Sie Ihre Voreinstellungen konfiguriert haben.

### Anzeigen von Inhalten im Chrome-Player {#viewing-content-output}

In diesem Beispiel wird die Ausgabe auf einem Chrome-Player beschrieben. Nachdem Sie den Kanal Ihrer Anzeige zugewiesen haben, müssen Sie das Gerät bei einem Player registrieren.

Informationen zum Registrieren eines Geräts auf einem AEM Screens-Player finden Sie unter [Geräteregistrierung](device-registration.md).

Sie werden die folgende Ausgabe auf Ihrem Player sehen:

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

Mit der Auswahl eines Kanals können Sie einen Verweis zum gewünschten Kanal bereitstellen, entweder in Form des Namens oder des Pfads des Kanals.

* **nach Pfad**: Sie stellen einen expliziten Verweis durch Angabe des absoluten Pfads des Kanals bereit.

* **nach Name**: Sie geben den Namen des Kanals ein, der entsprechend dem Kontext zu einem tatsächlichen Kanal führt. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, um standortspezifischen Inhalt dynamisch aufzulösen. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle kann durch verschiedene Aktionen festgelegt werden und ist unabhängig vom eigentlichen Kanal, der der Rolle entspricht.

### Priorität {#priority-channel}

Mit „Priorität“ können Zuweisungen geordnet werden, falls mehrere die Wiedergabekriterien erfüllen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Angenommen, es gibt zwei Kanäle, A und B. Wenn A die Priorität 1 und B die Priorität 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Darüber hinaus werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

### Unterstützte Ereignisse {#supported-events-channel}

* **Erster Ladevorgang**: Lädt den Kanal beim Start des Players. Er kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden
* **Bildschirm bei Untätigkeit**: Lädt, wenn der Bildschirm inaktiv ist. Er kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden
* **Timer**: muss festgelegt werden, wenn ein Zeitplan bereitgestellt wird.
* **Benutzerinteraktion**: Der Player wechselt zum angegebenen Kanal, wenn sich auf dem Bildschirm eine Benutzerinteraktion (Touch) im Leerlauf befindet, und wird geladen, wenn der Bildschirm berührt wird.

### Unterbrechungsmethode {#interruption-method-channel}

>[!IMPORTANT]
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

Bei Dayparting wird ein Tag in Zeitfenster unterteilt und festgelegt, welcher Inhalt zum gewünschten Zeitpunkt dargestellt wird. Mit AEM Screens können Sie den Dayparting-Zeitplan von Kanälen nach Bedarf für Tage, Wochen oder Monate festlegen.

Im Folgenden wird in drei Szenarien beschrieben, wie Dayparting mit Kanälen verwendet werden kann:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

Im folgenden Beispiel wird veranschaulicht, wie ein Restaurant Dayparting verwendet, um täglich sein Angebot für Frühstück, Mittagessen und Abendessen zu präsentieren.

Wir unterteilen jeden Tag in verschiedene Zeitfenster, sodass der Kanalinhalt gemäß der Tageszeit angezeigt wird. Legen Sie die folgenden Eigenschaften des Intervallzeitplans für Ihren Kanal fest, um den Inhalt gemäß diesem Verwendungsfall wiederzugeben.

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Frühstück | Täglich | 06:00 Uhr | 11:00 Uhr |
| Mittagessen | Täglich | 11:00 Uhr | 15:00 Uhr |
| Abendessen | Täglich | 15:00 Uhr | 20:00 Uhr |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

In diesem Beispiel wird gezeigt, wie Dayparting in einem Casino umgesetzt wird, wo an jedem Wochenende von 20:00 Uhr bis 22:00 Uhr eine Live-Veranstaltung stattfindet und von 22:00 Uhr bis 1:00 Uhr in der Abendkarte spezielle Gerichte angeboten werden

| **Name** | **Wiederholungen** | **Anfang** | **Ende** |
|---|---|---|---|
| Wochenende | Wöchentlich: Samstag, Sonntag | 20:00 Uhr | 22:00 Uhr |
| Sonderangebote | Täglich: Montag bis Freitag | 22:00 Uhr | 01:00 Uhr |

>[!NOTE]
>
>Darüber hinaus können Sie für jeden Kanal die ***Priorität*** festlegen. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird der Kanal mit höherer Priorität zuerst wiedergegeben. Der Mindestwert für die Priorität kann auf 0 gesetzt werden.
