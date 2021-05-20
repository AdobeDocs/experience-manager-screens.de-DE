---
title: Unbefristeter Übernahmekanal
seo-title: Unbefristeter Übernahmekanal
description: In diesem Nutzungsszenario erfahren Sie, wie Sie einen unbefristeten Übernahmekanal erstellen.
seo-description: In diesem Nutzungsszenario erfahren Sie, wie Sie ein Projekt einrichten, in dem ein unbefristeter Übernahmekanal erstellt wird, der an einem bestimmten Tag und zu einer bestimmten Zeit kontinuierlich wiedergegeben wird.
contentOwner: jsyal
feature: Inhaltserstellung in Screens
role: Administrator, Developer
level: Intermediate
exl-id: 5d112f33-a7cf-415e-9ea7-dc18a0356a8d
source-git-commit: 60a6583dd3bf79ef09099506107705bf0bce1e07
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 100%

---

# Unbefristeter Übernahmekanal {#perpetual-takeover-channel}

Auf der folgenden Seite finden Sie ein Nutzungsszenario, in dem ein Projekt eingerichtet wird, in dem ein unbefristeter Übernahmekanal erstellt wird, der an einem bestimmten Tag und zu einer bestimmten Zeit kontinuierlich wiedergegeben wird.

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Nutzungsszenario wird erläutert, wie Sie einen Kanal erstellen, der den normalerweise wiedergegebenen Kanal für eine Anzeige oder eine Gruppe von Anzeigen *übernimmt*. Die Übernahme erfolgt unbefristet an einem bestimmten Tag und zu einer bestimmten Zeit.
Beispielsweise gibt es einen unbefristeten Übernahmekanal, der jeden Freitag von 9:00 Uhr bis 10:00 Uhr wiedergegeben wird. Während dieser Zeit sollte kein anderer Kanal wiedergegeben werden. Das folgende Beispiel zeigt die Erstellung eines unbefristeten Übernahmekanals, der es ermöglicht, den Inhalt jeden Mittwoch für 2 Stunden von 14:00 Uhr bis 16:00 Uhr wiederzugeben.

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

1. Erstellen Sie einen Kanal **TakeOver**, der den Inhalt des Kanals **MainAdChannel** übernimmt und jeden Mittwoch von 14:00 bis 16:00 Uhr wiedergibt.

1. Wählen Sie den Kanal **TakeOver** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Ziehen Sie einige Assets in Ihren Kanal. Im folgenden Beispiel wird gezeigt, wie Sie diesem Kanal ein Bild für eine Einzelzone hinzufügen.

   ![Asset](assets/p_usecase4.png)

1. Richten Sie einen Standort und eine Anzeige für Ihre Kanäle ein. Beispielsweise werden für dieses Projekt der Standort **MainLobby** und die Anzeige **MainLobbyDisplay** eingerichtet.

   ![Asset](assets/p_usecase5.png)

**Zuweisen von Kanälen zu einer Anzeige**

1. Wählen Sie die Anzeige **MainLobbyDisplay** aus dem Ordner **Standorte** aus. Klicken Sie in der Aktionsleiste auf **Kanal zuweisen**, um das Dialogfeld **Kanalzuweisung** zu öffnen.

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter **[Kanalzuweisung](channel-assignment.md)**.

1. Füllen Sie die Felder (**Kanalpfad**, **Priorität** und **Unterstützte Ereignisse**) aus dem Dialogfeld **Kanalzuweisung** aus und klicken Sie auf **Speichern**, um Ihrer Anzeige den Kanal **MainAdChannel** zuzuweisen.

   * **Kanalpfad**: Wählen Sie den Pfad zum Kanal **MainAdChannel** aus
   * **Priorität**: Legen Sie die Priorität dieses Kanals auf „1“ fest.
   * **Unterstützte Ereignisse**: Wählen Sie **Erster Ladevorgang** und **Bildschirm bei Untätigkeit** aus.

   ![Asset](assets/p_usecase6.png)

1. Wählen Sie die Anzeige **TakeOver** aus dem Ordner **Standorte** aus. Klicken Sie in der Aktionsleiste auf **Kanal zuweisen**, um den Übernahmekanal zuzuweisen.

1. Um den **TakeOver**-Kanal Ihrer Anzeige zu einem geplanten Zeitpunkt zuzuweisen, füllen die folgenden Felder im Dialogfeld **Kanalzuweisung** aus und klicken Sie auf **Speichern**:

   * **Kanalpfad**: Wählen Sie den Pfad zum Kanal **TakeOver** aus
   * **Priorität**: Legen Sie die Priorität dieses Kanals höher als die von **MainAdChannel** fest. Die in diesem Beispiel eingestellte Priorität ist beispielsweise „8“.
   * **Unterstützte Ereignisse**: Wählen Sie **Bildschirm bei Untätigkeit** und **Timer** aus.
   * **Zeitplan**: Geben Sie den Text für den Zeitplan ein, nach dem dieser Kanal die Anzeige ausführen soll. Der in diesem Beispiel erwähnte Text im **Zeitplan** ist *am Mittwoch nach 14:00 und vor 16:00 Uhr*.

      >[!NOTE]
      >Weitere Informationen zu den Ausdrücken, die Sie dem **Zeitplan** hinzufügen können, finden Sie im Abschnitt [Beispielausdrücke](#example-expressions) unten.
   * **aktiv von**: Startdatum und -zeit.
   * **aktiv bis**: Enddatum und -zeit.

      Zum Beispiel ermöglicht der Text in **Zeitplan** und **aktiv von** und **aktiv bis** Datum und Uhrzeit, dass der Inhalt jeden Mittwoch von 14:00 bis 16:00 Uhr wiedergegeben wird.


      ![Asset](assets/p_usecase7.png)

      Navigieren Sie zur Anzeige unter **TakeOver** > **Standorte** > **MainLobby** > **MainLobbyDisplay** und klicken Sie in der Aktionsleiste auf **Dashboard**, um die zugewiesenen Kanäle mit ihren Prioritäten anzuzeigen (siehe unten).

      >[!NOTE]
      >Es ist zwingend erforderlich, die Priorität des Übernahmekanals auf die höchste zu setzen.

      ![asset](assets/p_usecase8.png)
Jetzt übernimmt der Kanal **TakeOver** den Kanal **MainAdChannel** jeden Mittwoch um 14:00 Uhr für zwei Stunden bis 16:00 Uhr und gibt seinen Inhalt vom 09. Januar 2020 bis zum 31. Januar 2020 wieder.

## Beispielausdrücke {#example-expressions}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | der Kanal wird täglich vor 8:00 Uhr wiedergegeben |
| nach 14:00 Uhr | der Kanal wird täglich nach 14.00 Uhr wiedergegeben |
| nach 12:15 Uhr und vor 12:45 Uhr | der Kanal wird täglich für 30 Minuten nach 12:15 Uhr wiedergegeben |
| vor 12:15 Uhr auch nach 12:45 Uhr | Der Kanal wird täglich vor 12:15 Uhr und danach auch nach 12:45 Uhr wiedergegeben |
| am 1. Januar nach 14:00 Uhr auch am 2. Januar, auch am 3. Januar vor 3:00 Uhr | Der Kanal beginnt die Wiedergabe am 1. Januar um 14:00 Uhr, läuft den ganzen Tag am 2. Januar, bis um 3:00 Uhr am 3. Januar |
| am 1./2. Januar nach 14:00 Uhr auch am 2./3. Januar vor 3:00 Uhr | Der Kanal startet den Player am 1. Januar um 14:00 Uhr, läuft bis 3:00 Uhr am 2. Januar und beginnt dann am 2. Januar um 14:00 Uhr und läuft bis 3:00 Uhr am 3. Januar |

>[!NOTE]
>
>Sie können das _24-Stunden-Format_ (d. h. 14:00 Uhr) oder die *am/pm*-Notation (d. h. 2:00 pm) verwenden.
