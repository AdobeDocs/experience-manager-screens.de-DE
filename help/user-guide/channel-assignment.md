---
title: Kanalzuweisung
seo-title: Kanalzuweisung
description: Auf dieser Seite erhalten Sie Informationen zur Kanalzuweisung und zu Dayparting.
seo-description: Auf dieser Seite erhalten Sie Informationen zur Kanalzuweisung und zu Dayparting.
uuid: fe429485-dcc9-4507-864c-b04393cedeee
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 212adcd1-835b-453d-9d3e-775366abf181
docset: aem65
translation-type: tm+mt
source-git-commit: bde770227dfbe72e96254d27ba14e7469eed1b5c

---


# Kanalzuweisung {#channel-assignment}

In diesem Abschnitt werden folgende Themen behandelt:

* **Zuweisen von Kanälen**
* **Eigenschaften des Dialogfelds „Kanalzuweisung“**
* **Dayparting**

Nachdem Sie eine Anzeige definiert haben, müssen Sie ihr einen Kanal zuweisen.

Auf dieser Seite wird beschrieben, wie Sie Ihren Anzeigen einen Kanal zuweisen.

**Voraussetzungen**:

* [Konfigurieren und Bereitstellen von Screens](configuring-screens-introduction.md)
* [Erstellen und Verwalten von Screens-Projekten](creating-a-screens-project.md)
* [Erstellen und Verwalten von Kanälen](managing-channels.md)
* [Erstellen und Verwalten von Standorten](managing-locations.md)
* [Erstellen und Verwalten von Anzeigen](managing-displays.md)

## Zuweisen eines Kanals {#assign-a-channel}

Gehen Sie wie folgt vor, um einer Anzeige einen Kanal zuzuweisen:

1. Navigieren Sie zur gewünschten Anzeige, z. B. **DemoProject** > **Standorte** > **SanJose** > **StoreDisplay**.

   ![screen_shot_2018-08-23at25359pm](assets/screen_shot_2018-08-23at25359pm.png)

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   Oder

   Tippen/klicken Sie auf **Dashboard** und klicken Sie auf **+Kanal zuweisen** im Bedienfeld **ZUGEWIESENE KANÄLE**, um das Dialogfeld **Kanalzuweisung** zu öffnen.

   ![image](/help/user-guide/assets/channel-assign1.png)

   You can configure the following properties from the **Channel Assignment** dialog box in the section below.

### Grundlegendes zu Kanal-Eigenschaften {#channel-properties}

#### Kanal referenzieren {#ref-channel}

Diese Option ermöglicht es Ihnen, einen Verweis zum gewünschten Kanal bereitzustellen, entweder in Form des Namens oder des Pfads des Kanals.

* **nach Pfad**: Sie stellen einen expliziten Verweis durch Angabe des absoluten Pfads des Kanals bereit.

* **nach Name**: Sie geben den Namen des Kanals ein, der entsprechend dem Kontext zu einem tatsächlichen Kanal führt. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, um standortspezifischen Inhalt dynamisch aufzulösen. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

#### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle kann durch verschiedene Aktionen festgelegt werden und ist unabhängig vom eigentlichen Kanal, der der Rolle entspricht.

#### Priorität {#priority-channel}

Mit „Priorität“ können Zuweisungen geordnet werden, falls mehrere die Wiedergabekriterien erfüllen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Wenn es beispielsweise die beiden Kanäle A und B gibt und A eine Priorität von 1 und B eine Priorität von 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Darüber hinaus werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

#### Unterstützte Ereignisse {#supported-events-channel}

* **Erster Ladevorgang**: Lädt den Kanal, wenn der Player gestartet wird. Dies kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden.
* **Bildschirm bei Untätigkeit**: Lädt, wenn der Bildschirm inaktiv ist. Dies kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden.
* **Timer**: Muss eingestellt werden, wenn ein Zeitplan vorhanden ist
* **Benutzerinteraktion**: Der Player wechselt in den angegebenen Kanal, wenn in einem inaktiven Kanal auf dem Bildschirm (Touch) eine Benutzerinteraktion stattfindet, und wird geladen, wenn der Bildschirm berührt wird.

#### Unterbrechungsmethode {#interruption-method-channel}

Als Autor von Inhalten sollten Sie festlegen können, wann ein Kanal unterbrochen wird, damit Sie festlegen können, dass nicht kritische Inhalte abgeschnitten werden sollen. Sie haben jedoch die Möglichkeit, wichtige Inhalte vollständig abspielen zu lassen, bevor die Wiedergabe aufgrund der Zeitplanung abgebrochen wird.
Die folgenden Optionen stehen zum Festlegen der Unterbrechungsmethode im Dialogfeld &quot; **Kanal-Zuweisung** &quot;zur Verfügung:

* **Sofort**: Wenn der Zeitplan aktiviert oder ein Update empfangen wird, wird die Wiedergabe unterbrochen und der neue Inhalt sofort aktualisiert oder abgespielt
* **Am Ende des aktuellen Elements**: Wenn ein neuer Zeitplan aktiviert oder ein Update empfangen wird, warten wir, bis das aktuelle Element in der Sequenz vollständig abgespielt wird, und erst danach wird der neue Inhalt aktualisiert oder abgespielt
   >[!NOTE]
   >Dies ist die ausgewählte Standardoption.
* **Am Ende der Sequenz**: Wenn ein neuer Zeitplan aktiviert oder ein Update empfangen wird, warten wir, bis die gesamte Sequenz ihr Ende erreicht hat. Kurz bevor wir zum ersten Element zurückkehren, wird der neue Inhalt aktualisiert oder abgespielt

#### Zeitplan {#schedule-channel}

Hiermit können Sie in einer Beschreibung in Textform angeben, wann der Kanal angezeigt werden soll. Sie können damit auch ein Startdatum (**aktiv ab**) und ein Enddatum (**aktiv bis**) definieren, zwischen denen der Kanal angezeigt werden soll.

**Attraktions-QuickInfo anzeigen**:

Mit der Option „Attraktions-QuickInfo anzeigen“ wird definiert, ob die Attraktions-QuickInfo (*Zum Beginnen irgendwo tippen*) angezeigt wird, während der Kanal ausgeführt wird.


### Dayparting  {#dayparting}

Durch die Kombination von Zeitplänen mit **Dayparting** können Sie einen globalen Zeitplan mit mehreren Kanälen festlegen, die zu bestimmten Tageszeiten ausgeführt werden. Diese Einstellung kann dann für alle Anzeigen wiederverwendet werden.

Bei Dayparting wird ein Tag in Zeitfenster unterteilt und festgelegt, welcher Inhalt zum gewünschten Zeitpunkt dargestellt wird. Mit AEM Screens können Sie den Dayparting-Zeitplan von Kanälen nach Bedarf für Tage, Wochen oder Monate festlegen.

Im Folgenden wird in drei Szenarien beschrieben, wie Dayparting mit Kanälen verwendet werden kann:

#### Anzeigen von Inhalten an einem einzigen Tag unterteilt in mehrere Zeitfenster  {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

Im folgenden Beispiel wird veranschaulicht, wie ein Restaurant Dayparting verwendet, um sein Angebot für Frühstück, Mittagessen und Abendessen zu präsentieren.

Wir unterteilen jeden Tag in drei Zeitfenster, sodass der Kanalinhalt gemäß der Tageszeit angezeigt wird:

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| Menü_A | Frühstück |  | nach 6:00 Uhr und vor 11:00 Uhr |
| Menü_B | Mittagessen |  | nach 11:00 Uhr und vor 15:00 Uhr |
| Menü_C | Abendessen |  | nach 15:00 Uhr und vor 20:00 Uhr |

#### Anzeigen von Inhalten an einem bestimmten Wochentag {#playing-content-on-a-particular-day-of-the-week}

In diesem Beispiel wird gezeigt, wie Dayparting in einem Casino umgesetzt wird, wo an jedem Wochenende von 20:00 Uhr bis 22:00 Uhr eine Live-Veranstaltung stattfindet und von 22:00 Uhr bis 1:00 Uhr in der Abendkarte spezielle Gerichte angeboten werden.

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

Hier wird Dayparting auf monatlicher Basis erstellt, sodass der Kanalinhalt an den angegebenen Monaten im Jahr angezeigt wird.

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| Sommerkollektion | Sommer |  | 01. Juni 2017–31. August 2017 |
| Herbstkollektion | Herbst |  | 01. September 2017–30. Oktober 2017 |

>[!NOTE]
>
>Darüber hinaus können Sie für jeden Kanal die ***Priorität*** festlegen. Wenn beispielsweise zwei Kanäle für denselben Tag und dieselbe Uhrzeit oder für denselben Monat festgelegt sind, wird der Kanal mit höherer Priorität zuerst gezeigt. Der Mindestwert für die Priorität beträgt 0.

#### Anzeigen von Inhalt für Kanäle derselben Priorität        {#playing-content-for-channels-with-same-priority}

Diese Beispiele veranschaulichen die Verwendung von Dayparting durch einen Laden, der seine Winterkollektion mit demselben Zeitplan im Dezember präsentiert. Doch da die Priorität von Kanal B in dieser Woche 2 beträgt, wird der Inhalt von Kanal B anstelle des Inhalts von Kanal A gezeigt.

| **Kanal** | **Rolle** | **Priorität** | **Zeitplan** |
|---|---|---|---|
| A | Winter | 1 | 01. Dezember 2017–31. Dezember 2017 |
| B | Weihnachten | 2 | 24. Dezember 2017–31. Dezember 2017 |

>[!IMPORTANT]
> Weitere Informationen zu Dayparting finden Sie in den folgenden Abschnitten:
>* [Umgang mit sich wiederholenden Assets](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling.html#handling-recurrence-in-assets)
>* [Umgang mit sich wiederholenden Assets in einem Kanal](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation.html#handling-recurrence-in-assets)


