---
title: Kanalzuweisung
description: Erfahren Sie mehr über die Kanalzuweisung und die Day-Parting.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 6ed86bfc-38c7-4ced-b472-db2a362585c5
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 36%

---

# Kanalzuweisung {#channel-assignment}

>[!IMPORTANT]
>In diesem Abschnitt wird die Kanalzuweisung und -zeitplanung für Feature Packs beschrieben, die älter als AEM 6.5.5 Screens sind.

Nachdem Sie eine Anzeige eingerichtet haben, müssen Sie der Anzeige einen Kanal zuweisen, um Ihren Inhalt anzuzeigen.

Auf dieser Seite wird beschrieben, wie Sie Ihrer Anzeige einen Kanal zuweisen.

>[!NOTE]
>Sie können einer Anzeige mehrere Kanäle zuweisen.

## Zuweisen von Kanälen {#assign-a-channel}

Gehen Sie wie folgt vor, um einer Anzeige einen Kanal zuzuweisen:

1. Navigieren Sie zur gewünschten Anzeige, z. B. **Demoprojekt** > **Speicherorte** > **SanJose** > **StoreDisplay**.

   ![Bild](assets/screen_shot_2018-08-23at25359pm.png)

1. Auswählen **Kanal zuweisen** In der Aktionsleiste.

   oder

   Auswählen **Dashboard** und wählen Sie **+Kanal zuweisen** vom **ZUGEWIESENE KANÄLE** Bedienfeld zum Öffnen der **Kanalzuweisung** Dialogfeld.

   ![image](/help/user-guide/assets/channel-assign1.png)

   Sie können die Eigenschaften im Dialogfeld **Kanalzuweisung** im nachstehenden Abschnitt konfigurieren. Weitere Informationen zu den Kanaleigenschaften finden Sie im Abschnitt [Kanaleigenschaften](#channel-properties).

## Verstehen der Kanaleigenschaften bei Kanalzuweisung {#channel-properties}

### Kanal referenzieren {#ref-channel}

Mit dem Referenzkanal können Sie einen Verweis auf den gewünschten Kanal entweder über den Kanalnamen oder über den Kanalpfad bereitstellen.

* **Nach Pfad** - Sie geben eine explizite Referenz unter Verwendung des absoluten Pfads des Kanals an.

* **Nach Name** - Sie geben den Namen des Kanals ein, der anhand des Kontexts zu einem tatsächlichen Kanal aufgelöst wird. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, um standortspezifische Inhalte dynamisch aufzulösen. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle wird durch verschiedene Aktionen angesprochen und ist unabhängig vom tatsächlichen Kanal, der die Rolle erfüllt.

### Priorität {#priority-channel}

Die Priorität wird verwendet, um die Zuweisungen in eine Reihenfolge zu bringen, wenn mehrere Zuweisungen den Wiedergabekriterien entsprechen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Angenommen, es gibt zwei Kanäle, A und B. Wenn A die Priorität 1 und B die Priorität 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Außerdem werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

### Unterstützte Ereignisse {#supported-events-channel}

* **Vorbelastung** - Lädt den Kanal, wenn der Player gestartet wird. Sie kann mehreren Kanälen mit einem Zeitplan zugewiesen werden.
* **Bildschirm im Leerlauf** - Lädt, wenn der Bildschirm inaktiv ist. Sie kann mehreren Kanälen mit einem Zeitplan zugewiesen werden.
* **Timer** - Muss festgelegt werden, wenn ein Zeitplan bereitgestellt wird.
* **Benutzerinteraktion** - Der Player wechselt in den angegebenen Kanal, wenn eine Benutzerinteraktion auf dem Bildschirm (Touch) in einem inaktiven Kanal stattfindet, und lädt, wenn der Bildschirm berührt wird.

### Unterbrechungsmethode {#interruption-method-channel}

>[!IMPORTANT]
>
> Diese Option ist nur verfügbar mit <!--AEM 6.4 Feature Pack 8 or -->AEM 6.5 Feature Pack 4.

Geben Sie als Inhaltsautor an, wann ein Kanal unterbrochen wird. Auf diese Weise können Sie nicht kritische Inhalte abschneiden, aber optional wichtige Inhalte abspielen lassen, bevor Sie die Wiedergabe aufgrund einer Planung abschneiden.

Wählen Sie eine der folgenden Optionen aus, die zum Festlegen der Unterbrechungsmethode im Dialogfeld **Kanalzuweisung** verfügbar sind:

* **Immediately** - Wenn der Zeitplan aktiviert wird oder eine Aktualisierung empfangen wird, können Sie die Wiedergabe abschneiden und den neuen Inhalt sofort aktualisieren oder wiedergeben.
* **Am Ende des aktuellen Elements** - Wenn ein neuer Zeitplan aktiviert oder eine Aktualisierung empfangen wird, können Sie optional warten, bis das aktuelle Element in der Sequenz die Wiedergabe abgeschlossen hat. Erst danach können Sie den neuen Inhalt aktualisieren oder wiedergeben.

  >[!NOTE]
  >Standardmäßig ist diese Option aktiviert.
* **Am Ende der Sequenz** - Wenn ein neuer Zeitplan aktiviert wird oder eine Aktualisierung empfangen wird, können Sie optional warten, bis die gesamte Sequenz ihr Ende erreicht. Anschließend können Sie direkt vor der gewünschten Sequenz zum ersten Element zurückkehren, es aktualisieren oder den neuen Inhalt wiedergeben.

  >[!NOTE]
  >Die Verwendung der zweiten oder dritten Option kann dazu führen, dass die für die Zuweisung definierten Planungszeiten geringfügig verschoben werden. Der Grund dafür ist, dass der Player vor dem Aktualisieren auf das Ende des Elements oder der Sequenz (nach der angegebenen Zeit) wartet. Die Verzögerung hängt von der Wiedergabedauer des Elements ab.

### Zeitplan {#schedule-channel}

Mit Zeitplan können Sie eine Beschreibung im Text angeben, wann der Kanal angezeigt werden soll. Außerdem können Sie ein Startdatum (**Aktives Formular**) und ein Enddatum (**aktiv bis**) für den Kanal, der angezeigt werden soll.

**Quickinfo für Attraktion anzeigen**

Die QuickInfo „Attraktion anzeigen“ definiert, ob die QuickInfo „Attraktion“ (“*Zu Beginn irgendwo berühren*„) muss angezeigt werden oder nicht, während der Kanal läuft.

### Dayparting {#dayparting}

Zeitpläne in Kombination mit **DayParting** Mit können Sie einen globalen Zeitplan mit mehreren Kanälen festlegen, die zu bestimmten Tageszeiten ausgeführt werden, und diesen Zeitplan dann für alle Ihre Displays gleichzeitig wiederverwenden.

Bei Dayparting wird ein Tag in Zeitfenster unterteilt und festgelegt, welcher Inhalt zum gewünschten Zeitpunkt dargestellt wird. Mit AEM Screens können Sie Kanäle in Form von DayParting innerhalb eines Tages, einer Woche oder eines Monats je nach Anforderung planen.

In den folgenden Beispielen wird die Day-Parting-Methode in Kanälen in drei verschiedenen Szenarien erläutert:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

Dieses Beispiel zeigt, wie ein Restaurant DayParting verwendet, um sein Frühstück, Mittagessen und Abendmenü zu präsentieren.

Hier unterteilen Sie jeden Tag in drei verschiedene Zeitschlitze, sodass der Kanalinhalt gemäß der festgelegten Tageszeit wiedergegeben wird:

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| Menü_A | Frühstück |  | Nach 6:00 Uhr und vor 11:00 Uhr |
| Menü_B | Mittagessen |  | Nach 11:00 Uhr und vor 15:00 Uhr |
| Menü_C | Abendessen |  | Nach 15:00 und vor 20:00 Uhr |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

Dieses Beispiel zeigt den DayParting in einem Casino, in dem jedes Wochenende von 20:00 bis 22:00 Uhr Live-Veranstaltungen stattfinden und nach 22:00 bis 1:00 Uhr Abendmenüs angeboten werden.

<table>
 <tbody>
  <tr>
   <td><strong>Kanal</strong></td>
   <td><strong>Rolle</strong></td>
   <td><strong>Priorität</strong></td>
   <td><strong>Zeitplan</strong></td>
  </tr>
  <tr>
   <td>Live-Konzert</td>
   <td>Wochenende</td>
   <td> </td>
   <td>21. Oktober 2017 - 22. Oktober 2017 <br /> Nach 20:00 bis 22:00 Uhr</td>
  </tr>
  <tr>
   <td>Spezialitätenkarte</td>
   <td>Wochenende</td>
   <td> </td>
   <td>21. Oktober 2017 - 22. Oktober 2017 <br /> Nach 22:00 bis 13:00 Uhr</td>
  </tr>
 </tbody>
</table>

#### Anzeigen von Inhalten für einen bestimmten Monat oder mehrere Monate {#playing-content-for-a-particular-month-months}

Dieses Beispiel veranschaulicht Dayparting für einen Laden, der seine Sommerkollektion von Juni bis August und die Herbstkollektion von September bis Ende Oktober präsentiert.

Hier erstellen Sie DayParting nach Monat, sodass Kanalinhalte nach den angegebenen Monaten des Jahres wiedergegeben werden.

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| Sommerkollektion | Sommer |  | 1. Juni 2017 - 31. August 2017 |
| Herbstkollektion | Herbst |  | 1. September 2017 - 30. Oktober 2017 |

>[!NOTE]
>
>Außerdem können Sie Folgendes definieren ***Priorität*** für jeden der Kanäle. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird zuerst der Kanal mit höherer Priorität wiedergegeben. Der Mindestwert für die Priorität kann auf 0 festgelegt werden.

#### Anzeigen von Inhalt für Kanäle derselben Priorität {#playing-content-for-channels-with-same-priority}

Dieses Beispiel zeigt die DayParting -Methode für einen Store, der seine Winterkollektion mit demselben Zeitplan im Monat Dezember anzeigt. Doch da die Priorität von Kanal B in dieser Woche 2 beträgt, wird der Inhalt von Kanal B anstelle des Inhalts von Kanal A gezeigt.

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| A | Winter | 1 | 1. Dezember 2017 - 31. Dezember 2017 |
| B | Weihnachten | 2 | 24. Dezember 2017 - 31. Dezember 2017 |


>[!NOTE]
>
> Weitere Informationen zu Dayparting finden Sie in den folgenden Abschnitten:
>
>* [Umgang mit sich wiederholenden Assets](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling)
>* [Umgang mit sich wiederholenden Assets in einem Kanal](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation)
