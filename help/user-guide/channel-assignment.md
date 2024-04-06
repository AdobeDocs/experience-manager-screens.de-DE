---
title: Kanalzuweisung
seo-title: Channel Assignment
description: Auf dieser Seite erhalten Sie Informationen zur Kanalzuweisung und zu Dayparting.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 6ed86bfc-38c7-4ced-b472-db2a362585c5
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 84%

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

1. Navigieren Sie zur gewünschten Anzeige, beispielsweise **DemoProject** > **Standorte** > **SanJose** > **StoreDisplay**.

   ![image](assets/screen_shot_2018-08-23at25359pm.png)

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   Oder

   Tippen/klicken Sie auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE** auf **+ Kanal zuweisen**, um das Dialogfeld **Kanalzuweisung** zu öffnen.

   ![image](/help/user-guide/assets/channel-assign1.png)

   Sie können die Eigenschaften im Dialogfeld **Kanalzuweisung** im nachstehenden Abschnitt konfigurieren. Weitere Informationen zu den Kanaleigenschaften finden Sie im Abschnitt [Kanaleigenschaften](#channel-properties).


## Verstehen der Kanaleigenschaften bei Kanalzuweisung {#channel-properties}

### Kanal referenzieren {#ref-channel}

Mit dem Referenzkanal können Sie einen Verweis auf den gewünschten Kanal entweder nach Kanalname oder nach Kanalpfad bereitstellen.

* **nach Pfad**: Sie stellen einen expliziten Verweis durch Angabe des absoluten Pfads des Kanals bereit.

* **nach Name**: Sie geben den Namen des Kanals ein, der entsprechend dem Kontext zu einem tatsächlichen Kanal führt. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, um standortspezifischen Inhalt dynamisch aufzulösen. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle kann durch verschiedene Aktionen festgelegt werden und ist unabhängig vom eigentlichen Kanal, der der Rolle entspricht.

### Priorität {#priority-channel}

Mit „Priorität“ können Zuweisungen geordnet werden, falls mehrere die Wiedergabekriterien erfüllen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Angenommen, es gibt zwei Kanäle, A und B. Wenn A die Priorität 1 und B die Priorität 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Darüber hinaus werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

### Unterstützte Ereignisse {#supported-events-channel}

* **Erster Ladevorgang**: Lädt den Kanal beim Start des Players. Er kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden
* **Bildschirm bei Untätigkeit**: Lädt, wenn der Bildschirm inaktiv ist. Er kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden
* **Timer**: muss festgelegt werden, wenn ein Zeitplan bereitgestellt wird.
* **Benutzerinteraktion**: Der Player wechselt zum angegebenen Kanal, wenn sich auf dem Bildschirm eine Benutzerinteraktion (Touch) im Leerlauf befindet, und wird geladen, wenn der Bildschirm berührt wird.

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

### Zeitplan {#schedule-channel}

Hiermit können Sie in einer Beschreibung in Textform angeben, wann der Kanal angezeigt werden soll. Sie können damit auch ein Startdatum (**aktiv ab**) und ein Enddatum (**aktiv bis**) definieren, zwischen denen der Kanal angezeigt werden soll.

**Attraktions-QuickInfo anzeigen**:

Anzeigen der Attraktions-QuickInfo definiert, ob die Attraktions-QuickInfo (&quot;*Alles berühren, um zu beginnen*&quot;) muss angezeigt werden oder nicht, während der Kanal ausgeführt wird.

### Dayparting {#dayparting}

Durch die Kombination von Zeitplänen mit **Dayparting** können Sie einen globalen Zeitplan mit mehreren Kanälen festlegen, die zu bestimmten Tageszeiten ausgeführt werden. Diese Einstellung kann dann für alle Anzeigen wiederverwendet werden.

Bei Dayparting wird ein Tag in Zeitfenster unterteilt und festgelegt, welcher Inhalt zum gewünschten Zeitpunkt dargestellt wird. Mit AEM Screens können Sie den Dayparting-Zeitplan von Kanälen nach Bedarf für Tage, Wochen oder Monate festlegen.

Im Folgenden wird in drei Szenarien beschrieben, wie Dayparting mit Kanälen verwendet werden kann:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

Im folgenden Beispiel wird veranschaulicht, wie ein Restaurant Dayparting verwendet, um sein Angebot für Frühstück, Mittagessen und Abendessen zu präsentieren.

Wir unterteilen jeden Tag in drei Zeitfenster, sodass der Kanalinhalt gemäß der Tageszeit angezeigt wird:

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| Menü_A | Frühstück |  | nach 6:00 Uhr und vor 11:00 Uhr |
| Menü_B | Mittagessen |  | nach 11:00 Uhr und vor 15:00 Uhr |
| Menü_C | Abendessen |  | nach 15:00 Uhr und vor 20:00 Uhr |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

In diesem Beispiel wird gezeigt, wie Dayparting in einem Casino umgesetzt wird, wo an jedem Wochenende von 20:00 Uhr bis 22:00 Uhr eine Live-Veranstaltung stattfindet und von 22:00 Uhr bis 1:00 Uhr in der Abendkarte spezielle Gerichte angeboten werden

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
   <td>21. Oktober 2017–22. Oktober 2017 <br /> nach 20:00 Uhr und vor 22:00 Uhr</td>
  </tr>
  <tr>
   <td>Spezialitätenkarte</td>
   <td>Wochenende</td>
   <td> </td>
   <td>21. Oktober 2017–22. Oktober 2017 <br /> nach 22:00 Uhr und vor 01:00 Uhr</td>
  </tr>
 </tbody>
</table>

#### Anzeigen von Inhalten für einen bestimmten Monat oder mehrere Monate {#playing-content-for-a-particular-month-months}

Dieses Beispiel veranschaulicht Dayparting für einen Laden, der seine Sommerkollektion von Juni bis August und die Herbstkollektion von September bis Ende Oktober präsentiert.

Hier wird Dayparting auf monatlicher Basis erstellt, sodass der Kanalinhalt für die angegebenen Monate des Jahres abgespielt wird.

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| Sommerkollektion | Sommer |  | 01. Juni 2017–31. August 2017 |
| Herbstkollektion | Herbst |  | 01. September 2017–30. Oktober 2017 |

>[!NOTE]
>
>Darüber hinaus können Sie für jeden Kanal die ***Priorität*** festlegen. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird der Kanal mit höherer Priorität zuerst wiedergegeben. Der Mindestwert für die Priorität kann auf 0 gesetzt werden.

#### Anzeigen von Inhalt für Kanäle derselben Priorität {#playing-content-for-channels-with-same-priority}

Diese Beispiele veranschaulichen die Verwendung von Dayparting durch einen Laden, der seine Winterkollektion mit demselben Zeitplan im Dezember präsentiert. Doch da die Priorität von Kanal B in dieser Woche 2 beträgt, wird der Inhalt von Kanal B anstelle des Inhalts von Kanal A gezeigt.

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| A | Winter | 1 | 01. Dezember 2017–31. Dezember 2017 |
| B | Weihnachten | 2 | 24. Dezember 2017–31. Dezember 2017 |


>[!NOTE]
>
> Weitere Informationen zu Dayparting finden Sie in den folgenden Abschnitten:
>
>* [Umgang mit sich wiederholenden Assets](https://docs.adobe.com/content/help/de-DE/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling.html#handling-recurrence-in-assets)
>* [Umgang mit sich wiederholenden Assets in einem Kanal](https://docs.adobe.com/content/help/de-DE/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation.html#handling-recurrence-in-assets)
