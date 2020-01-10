---
title: Dauerhafter Übernahmekanal
seo-title: Dauerhafter Übernahmekanal
description: Folgen Sie diesem Verwendungsfall für die Erstellung eines permanenten TakeOver-Kanals.
seo-description: Befolgen Sie diesen Verwendungsfall beim Einrichten eines Projekts, das einen permanenten TakeOver-Kanal erstellt, der für einen bestimmten Tag und eine bestimmte Zeit kontinuierlich wiedergegeben wird.
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: 5c89be38d0a8dade2f829bcce6fb3154789d3579

---


# Dauerhafter Übernahmekanal {#perpetual-takeover-channel}

Auf der folgenden Seite wird ein Anwendungsfall vorgestellt, der sich auf die Einrichtung eines Projekts zur Erstellung eines Perpetual TakeOver-Kanals konzentriert, der für einen bestimmten Zeitraum und Tag kontinuierlich wiedergegeben wird.

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Verwendungsfall wird erläutert, wie ein Kanal erstellt wird, der den normalen Wiedergabekanal für eine Anzeige oder Gruppe von Bildschirmen *übernimmt* . Die Übernahme wird für einen bestimmten Tag und eine bestimmte Zeit dauernd erfolgen.
So gibt es zum Beispiel einen Kanal für &quot;Perpetual TakeOver&quot;, der jeden Freitag von 9.00 Uhr bis 10.00 Uhr abgespielt wird. Während dieser Zeit sollte kein anderer Kanal wiedergegeben werden. Das folgende Beispiel zeigt die Erstellung eines permanenten Übernahmekanals, der abgespielt wird und den Inhalt jeden Mittwoch für 2 Stunden von 17.00 Uhr bis 19.00 Uhr wiedergeben kann.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Nutzungsszenario beginnen, sollten Sie sich mit den folgenden Themen vertraut machen:

* **[Erstellen und Verwalten von Kanälen](managing-channels.md)**
* **[Erstellen und Verwalten von Standorten](managing-locations.md)**
* **[Erstellen und Verwalten von Zeitplänen](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Autoren von Inhalten

## Setting up the Project {#setting-up-the-project}

Gehen Sie wie folgt vor, um ein Projekt einzurichten:

**Einrichten der Kanäle und Anzeigen**

1. Create an AEM Screens Project titled as **PerpetualTakeOver**, as shown below.

   ![Asset](assets/p_usecase1.png)

1. Erstellen Sie einen **MainAdChannel** im Ordner &quot; **Channels** &quot;.

   ![Asset](assets/p_usecase2.png)

1. Select the **MainAdChannel** and click **Edit** from the action bar. Ziehen Sie Elemente (Bilder, Videos, eingebettete Sequenzen) per Drag &amp; Drop in Ihren Kanal.

   ![Asset](assets/p_usecase3.png)


   >[!NOTE]
   >Der **MainAdChannel** in diesem Beispiel zeigt einen Sequenzkanal, der Inhalt kontinuierlich wiedergibt.

1. Erstellen Sie einen **TakeOver** -Kanal, der den Inhalt in **MainAdChannel** übernimmt und jeden Mittwoch von 14:00 bis 16:00 Uhr abspielt.

1. Select the the **TakeOver** and click **Edit** from the action bar. Ziehen Sie Elemente per Drag &amp; Drop in Ihren Kanal. Im folgenden Beispiel wird ein Bild für eine einzelne Zone gezeigt, das diesem Kanal hinzugefügt wurde.

   ![Asset](assets/p_usecase4.png)

1. Richten Sie einen Ort und eine Anzeige für Ihre Kanäle ein. Beispielsweise wird für dieses Projekt der folgende Speicherort **MainLobby** und **MainLobbyDisplay** eingerichtet.

   ![Asset](assets/p_usecase5.png)

**Zuweisen von Kanälen zu einer Anzeige**

1. Wählen Sie die Anzeige **MainLobbyDisplay** aus dem Ordner **Locations** . Klicken Sie in der Aktionsleiste auf Kanal **zuweisen** , um das Dialogfeld &quot; **Kanalzuweisung** &quot;zu öffnen.

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter **[Kanalzuweisung](channel-assignment.md)**.

1. Füllen Sie die Felder (**Kanalpfad**, **Priorität** und **Unterstützte Ereignisse**) aus dem Dialogfeld &quot;Kanalzuweisung **&quot;aus und klicken Sie auf** Speichern ******** , um Ihrer Anzeige die Option &quot;MainAdChannel&quot;zuzuweisen.

   * **Kanalpfad**: Wählen Sie den Pfad zum **MainAdChannel** -Kanal
   * **Priorität**: Legen Sie die Priorität dieses Kanals auf 1 fest.
   * **Unterstützte Ereignisse**: Wählen Sie den **Startbildschirm** und den **Leerlaufbildschirm**.
   ![Asset](assets/p_usecase6.png)

1. Wählen Sie die Anzeige **TakeOver** aus dem Ordner **Locations** . Klicken Sie in der Aktionsleiste auf Kanal **zuweisen** , um den Übernahmekanal zuzuweisen.

1. So weisen Sie der Anzeige den **TakeOver** -Kanal zu einem geplanten Zeitpunkt zu und füllen die folgenden Felder im Dialogfeld &quot; **Kanalzuweisung** &quot;aus und klicken auf **Speichern**:

   * **Kanalpfad**: Wählen Sie den Pfad zum **TakeOver** -Kanal
   * **Priorität**: Legen Sie die Priorität dieses Kanals höher als **MainAdChannel** fest. Die in diesem Beispiel eingestellte Priorität ist beispielsweise 8.
   * **Unterstützte Ereignisse**: Wählen Sie den **Leerbildschirm** und den **Timer** aus.
   * **Plan**: Geben Sie den Text für den Zeitplan ein, in dem die Anzeige ausgeführt werden soll. Der in diesem Beispiel erwähnte Text im **Zeitplan** ist *am Mittwoch nach 14:00 und vor 16:00* Uhr.
   * **aktiv von**: Startdatum und -zeit.
   * **aktiv bis**: Enddatum und -zeit.
   Beispielsweise kann der Text in **Plan** und **aktiv von** und **aktiv bis** Datum und Uhrzeit hier jeden Mittwoch von 14.00 bis 16.00 Uhr abgespielt werden.


   ![Asset](assets/p_usecase7.png)

   Navigieren Sie zur Anzeige unter **Übernehmen** —> **Positionen** —> **Hauptlobby** —> **MainLobbyDisplay** und klicken Sie in der Aktionsleiste auf **Dashboard** , um die zugewiesenen Kanäle mit ihren Prioritäten anzuzeigen, wie unten dargestellt.

   >[!NOTE]
   >Es ist obligatorisch, die Priorität des Übernahmekanals auf die höchste zu setzen.

   ![asset](assets/p_usecase8.png)Now, der **TakeOver** -Kanal übernimmt den **MainAdChannel** um 14:00 Uhr für zwei Stunden bis 16:00 Uhr jeden Mittwoch und spielt seinen Inhalt von 09.01.2020 bis 31.01.2020.

### Example Expressions {#example-expressions}

Die folgende Tabelle fasst einige Beispielausdrücke zusammen, die Sie dem Zeitplan hinzufügen können, während Sie einem Display einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| nach 12:15 und vor 12:45 | der Kanal wird 30 Minuten lang täglich nach 22:15 Uhr abgespielt |
