---
title: Unbefristeter Übernahmekanal
description: In diesem Nutzungsszenario erfahren Sie, wie Sie einen unbefristeten Übernahmekanal erstellen.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 5d112f33-a7cf-415e-9ea7-dc18a0356a8d
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 49%

---

# Unbefristeter Übernahmekanal {#perpetual-takeover-channel}

Auf der folgenden Seite finden Sie ein Nutzungsszenario, in dem ein Projekt eingerichtet wird. In diesem wird ein unbefristeter Übernahmekanal erstellt, der an einem bestimmten Tag und zu einer bestimmten Zeit kontinuierlich wiedergegeben wird.

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Anwendungsbeispiel wird erläutert, wie Sie einen Kanal erstellen, der *übernimmt* Vom normalen Wiedergabekanal für ein Display oder eine Gruppe von Displays. Die Übernahme erfolgt an einem bestimmten Tag und zu einer bestimmten Uhrzeit ständig.
Zum Beispiel gibt es einen Perpetual TakeOver-Kanal, der jeden Freitag von 9:00 bis 10:00 Uhr spielt. Während dieser Zeit sollte kein anderer Kanal abgespielt werden. Das folgende Beispiel zeigt die Erstellung eines unbefristeten Übernahmekanals, in dem der Inhalt jeden Mittwoch von 14:00 bis 16:00 Uhr wiedergegeben wird.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Nutzungsszenario beginnen, sollten Sie sich mit den folgenden Themen vertraut machen:

* **[Erstellen und Verwalten von Kanälen](managing-channels.md)**
* **[Erstellen und Verwalten von Standorten](managing-locations.md)**
* **[Erstellen und Verwalten von Zeitplänen](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Autoren von Inhalten

## Einrichten des Projekts {#setting-up-the-project}

Gehen Sie wie folgt vor, um ein Projekt einzurichten:

**Einrichten der Kanäle und Anzeigen**

1. Erstellen Sie ein AEM Screens-Projekt mit dem Namen **PerpetualTakeOver**, wie unten dargestellt.

   ![Asset](assets/p_usecase1.png)

1. Erstellen Sie einen Kanal **MainAdChannel** im Ordner **Kanäle**.

   ![Asset](assets/p_usecase2.png)

1. Wählen Sie den Kanal **MainAdChannel** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Ziehen Sie einige Assets (Bilder, Videos, eingebettete Sequenzen) in Ihren Kanal.

   ![Asset](assets/p_usecase3.png)


   >[!NOTE]
   >Der Kanal **MainAdChannel** in diesem Beispiel ist ein Sequenzkanal, der Inhalt kontinuierlich wiedergibt.

1. Erstellen eines **übernehmen** Kanal, der den Inhalt in übernimmt **MainAdChannel** und spielt jeden Mittwoch von 14:00 bis 16:00 Uhr.

1. Wählen Sie die **übernehmen** und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus. Ziehen Sie einige Assets in Ihren Kanal. Im folgenden Beispiel wird gezeigt, wie Sie diesem Kanal ein Bild für eine Einzelzone hinzufügen.

   ![Asset](assets/p_usecase4.png)

1. Richten Sie einen Standort und eine Anzeige für Ihre Kanäle ein. Beispielsweise der folgende Speicherort **Hauptlobby** und Anzeige **MainLobbyDisplay** sind für dieses Projekt eingerichtet.

   ![Asset](assets/p_usecase5.png)

**Zuweisen von Kanälen zu einer Anzeige**

1. Wählen Sie die Anzeige **MainLobbyDisplay** aus dem Ordner **Standorte** aus. Klick **Kanal zuweisen** in der Aktionsleiste aus, damit Sie die **Kanalzuweisung** Dialogfeld.

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter **[Kanalzuweisung](channel-assignment.md)**.

1. Füllen Sie die Felder (**Kanalpfad**, **Priorität** und **Unterstützte Ereignisse**) aus dem Dialogfeld **Kanalzuweisung** aus und klicken Sie auf **Speichern**, um Ihrer Anzeige den Kanal **MainAdChannel** zuzuweisen.

   * **Kanalpfad**: Wählen Sie den Pfad zum Kanal **MainAdChannel** aus
   * **Priorität**: Legen Sie die Priorität dieses Kanals auf „1“ fest.
   * **Unterstützte Ereignisse**: Wählen Sie **Erster Ladevorgang** und **Bildschirm bei Untätigkeit** aus.

   ![Asset](assets/p_usecase6.png)

1. Wählen Sie die Anzeige **TakeOver** aus dem Ordner **Standorte** aus. Klick **Kanal zuweisen** in der Aktionsleiste aus, sodass Sie den Übernahmekanal zuweisen können.

1. Zuweisen von **übernehmen** zum Anzeigen zu einem geplanten Zeitpunkt zu verwenden und die folgenden Felder aus dem **Kanalzuweisung** Dialogfeld und Klicken auf **Speichern**:

   * **Kanalpfad**: Wählen Sie den Pfad zum Kanal **TakeOver** aus
   * **Priorität**: Legen Sie die Priorität dieses Kanals höher als die von **MainAdChannel** fest. Die in diesem Beispiel eingestellte Priorität ist beispielsweise „8“.
   * **Unterstützte Ereignisse**: Wählen Sie **Bildschirm bei Untätigkeit** und **Timer** aus.
   * **Zeitplan**: Geben Sie den Text für den Zeitplan ein, nach dem dieser Kanal die Anzeige ausführen soll. Der in diesem Beispiel erwähnte Text im **Zeitplan** ist *am Mittwoch nach 14:00 und vor 16:00 Uhr*.

     >[!NOTE]
     >Weitere Informationen zu den Ausdrücken, die Sie dem **Zeitplan** hinzufügen können, finden Sie im Abschnitt [Beispielausdrücke](#example-expressions) unten.
   * **aktiv ab**: Startdatum und -zeit.
   * **aktiv bis**: Enddatum und -zeit.

     Beispiel: der Text in **Zeitplan** und **Aktives Formular** und **aktiv bis** Datum und Uhrzeit, zu der der Inhalt jeden Mittwoch von 14.00 bis 16.00 Uhr wiedergegeben wird.


     ![Asset](assets/p_usecase7.png)

     Navigieren Sie zur Anzeige über **übernehmen** > **Speicherorte** > **Hauptlobby** > **MainLobbyDisplay** und klicken Sie auf **Dashboard** in der Aktionsleiste aus, sodass Sie die zugewiesenen Kanäle mit ihren Prioritäten anzeigen können, wie unten dargestellt.

     >[!NOTE]
     >Es ist zwingend erforderlich, die Priorität des Übernahmekanals auf die höchste zu setzen.

     ![Asset](assets/p_usecase8.png)
Nun, die **übernehmen** Der Kanal übernimmt die **MainAdChannel** jeden Mittwoch um 14:00 Uhr für zwei Stunden bis 16:00 Uhr und spielt seinen Inhalt vom 9. Januar 2020 bis zum 31. Januar 2020 ab.

## Beispielausdrücke {#example-expressions}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | Der Kanal spielt jeden Tag vor 8:00 Uhr |
| nach 14:00 Uhr | Der Kanal spielt jeden Tag nach 14:00 Uhr |
| nach 12:15 Uhr und vor 12:45 Uhr | Der Kanal spielt täglich nach 12:15 Uhr für 30 Minuten |
| vor 12:15 Uhr auch nach 12:45 Uhr | Der Kanal spielt jeden Tag vor 12:15 Uhr und dann auch nach 12:45 Uhr. |
| am ersten Januartag nach 14:00 Uhr auch am zweiten Januartag ebenfalls am dritten Januartag vor 3:00 Uhr. | Der Kanal beginnt nach 14:00 Uhr am 1. Januar und spielt den ganzen Tag am 2. Januar bis 3:00 Uhr am 3. Januar weiter |
| an den 1-2 Tagen im Januar nach 14:00 Uhr auch an den 2-3 Tagen im Januar vor 3:00 Uhr. | Der Kanal beginnt am 1. Januar nach 14:00 Uhr mit der Wiedergabe bis zum 2. Januar um 3:00 Uhr, startet dann am 2. Januar um 14:00 Uhr wieder und läuft bis zum 3. Januar um 3:00 Uhr |

>[!NOTE]
>
>Sie können auch Folgendes verwenden _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M.* (14:00 UHR)
