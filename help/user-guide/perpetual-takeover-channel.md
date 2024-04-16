---
title: Unbefristeter Übernahmekanal
description: In diesem Nutzungsszenario erfahren Sie, wie Sie einen unbefristeten Übernahmekanal erstellen.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 5d112f33-a7cf-415e-9ea7-dc18a0356a8d
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 38%

---

# Unbefristeter Übernahmekanal {#perpetual-takeover-channel}

Auf der folgenden Seite finden Sie ein Nutzungsszenario, in dem ein Projekt eingerichtet wird. In diesem wird ein unbefristeter Übernahmekanal erstellt, der an einem bestimmten Tag und zu einer bestimmten Zeit kontinuierlich wiedergegeben wird.

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Nutzungsszenario wird erläutert, wie Sie einen Kanal erstellen, der *Übernahme* aus dem normalen Wiedergabekanal für eine Anzeige oder eine Gruppe von Anzeigen. Die Übernahme erfolgt für einen bestimmten Tag und eine bestimmte Uhrzeit, die unbefristet erfolgen.
Beispielsweise gibt es einen unbefristeten Übernahmekanal, der jeden Freitag von 9:00 Uhr bis 10:00 Uhr wiedergegeben wird. Während dieser Zeit sollte kein anderer Kanal wiedergegeben werden. Das folgende Beispiel zeigt die Erstellung eines unbefristeten Übernahmekanals, der es ermöglicht, den Inhalt jeden Mittwoch für zwei Stunden von 14:00 Uhr bis 16:00 Uhr wiederzugeben.

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

1. Klicken Sie auf **MainAdChannel** und klicken **Bearbeiten** in der Aktionsleiste aus. Ziehen Sie einige Assets (Bilder, Videos, eingebettete Sequenzen) in Ihren Kanal.

   ![Asset](assets/p_usecase3.png)


   >[!NOTE]
   >Der Kanal **MainAdChannel** in diesem Beispiel ist ein Sequenzkanal, der Inhalt kontinuierlich wiedergibt.

1. Erstellen Sie eine **TakeOver** -Kanal, der den Inhalt in **MainAdChannel** und spielt jeden Mittwoch von 14:00 bis 16:00 Uhr.

1. Klicken Sie auf **TakeOver** und klicken **Bearbeiten** in der Aktionsleiste aus. Ziehen Sie einige Assets in Ihren Kanal. Im folgenden Beispiel wird gezeigt, wie Sie diesem Kanal ein Bild für eine Einzelzone hinzufügen.

   ![Asset](assets/p_usecase4.png)

1. Richten Sie einen Standort und eine Anzeige für Ihre Kanäle ein. Beispielsweise der folgende Speicherort **MainLobby** und Anzeige **MainLobbyDisplay** für dieses Projekt eingerichtet sind.

   ![Asset](assets/p_usecase5.png)

**Zuweisen von Kanälen zu einer Anzeige**

1. Klicken Sie auf die Anzeige **MainLobbyDisplay** aus dem **Standorte** Ordner. Klicks **Kanal zuweisen** über die Aktionsleiste aus, damit Sie die **Kanalzuweisung** Dialogfeld.

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter **[Kanalzuweisung](channel-assignment.md)**.

1. Füllen Sie die Felder (**Kanalpfad**, **Priorität** und **Unterstützte Ereignisse**) aus dem Dialogfeld **Kanalzuweisung** aus und klicken Sie auf **Speichern**, um Ihrer Anzeige den Kanal **MainAdChannel** zuzuweisen.

   * **Kanalpfad**: Klicken Sie auf den Pfad zum **MainAdChannel** channel
   * **Priorität**: Legen Sie die Priorität dieses Kanals auf „1“ fest.
   * **Unterstützte Ereignisse**: Klicken Sie auf die **Erster Ladevorgang** und **Idle Screen**.

   ![Asset](assets/p_usecase6.png)

1. Klicken Sie auf die Anzeige **TakeOver** aus dem **Standorte** Ordner. Klicks **Kanal zuweisen** über die Symbolleiste, damit Sie den Übernahmekanal zuweisen können.

1. Zuweisen der **TakeOver** zu einer geplanten Zeit zu Ihrer Anzeige zu gelangen und die folgenden Felder aus dem **Kanalzuweisung** Dialogfeld und Auswahl **Speichern**:

   * **Kanalpfad**: Klicken Sie auf den Pfad zum **TakeOver** channel
   * **Priorität**: Legen Sie die Priorität dieses Kanals höher als die von **MainAdChannel** fest. Die in diesem Beispiel eingestellte Priorität ist beispielsweise „8“.
   * **Unterstützte Ereignisse**: Klicken Sie auf die **Idle Screen** und **Timer**.
   * **Zeitplan**: Geben Sie den Text für den Zeitplan ein, nach dem dieser Kanal die Anzeige ausführen soll. Der in diesem Beispiel erwähnte Text im **Zeitplan** ist *am Mittwoch nach 14:00 und vor 16:00 Uhr*.

     >[!NOTE]
     >Weitere Informationen zu den Ausdrücken, die Sie zum **Zeitplan**, siehe [Beispielausdrücke](#example-expressions) unten.
   * **aktiv ab**: Startdatum und -zeit.
   * **aktiv bis**: Enddatum und -zeit.

     Beispielsweise der Text in **Zeitplan** und **aktiv aus** und **aktiv bis** Datum und Uhrzeit hier erlaubt es, den Inhalt jeden Mittwoch von 14:00 Uhr bis 16:00 Uhr wiederzugeben.


     ![Asset](assets/p_usecase7.png)

     Zur Anzeige navigieren von **TakeOver** > **Standorte** > **MainLobby** > **MainLobbyDisplay** und klicken **Dashboard** in der Symbolleiste, damit Sie die zugewiesenen Kanäle mit ihren Prioritäten anzeigen können, wie unten dargestellt.

     >[!NOTE]
     >Es ist zwingend erforderlich, die Priorität des Übernahmekanals auf die höchste zu setzen.

     ![Asset](assets/p_usecase8.png)
Nun, die **TakeOver** Der Kanal übernimmt **MainAdChannel** um 14:00 Uhr für zwei Stunden bis 16:00 Uhr jeden Mittwoch und spielt seinen Inhalt von 09. Januar 2020 bis 31. Januar 2020.

## Beispielausdrücke {#example-expressions}

Die folgende Tabelle enthält einige Beispielausdrücke, die Sie dem Zeitplan hinzufügen können, während Sie einer Anzeige einen Kanal zuweisen.

| **Ausdruck** | **Interpretation** |
|---|---|
| vor 8:00 Uhr | Der Kanal wird täglich vor 8:00 Uhr wiedergegeben. |
| nach 14:00 Uhr. | Der Kanal wird täglich nach 14:00 Uhr wiedergegeben. |
| nach 12:15 Uhr und vor 12:45 Uhr | Der Kanal wird täglich 30 Minuten lang nach 12:15 Uhr wiedergegeben. |
| vor 12:15 Uhr auch nach 12:45 Uhr | Der Kanal wird täglich vor 12:15 Uhr und danach auch nach 12:45 Uhr wiedergegeben. |
| am ersten Januar nach 14:00 Uhr auch am zweiten Januar, auch am dritten Januar vor 3:00 Uhr. | Der Kanal beginnt am 1. Januar um 14:00 Uhr und läuft den ganzen Tag am 2. Januar bis 3:00 Uhr am 3. Januar |
| an den 1-2 Tagen des Januar nach 14:00 Uhr auch an den 2-3 Tagen des Januar vor 3:00 Uhr. | Der Kanal startet den Player am 1. Januar um 14:00 Uhr, läuft bis 3:00 Uhr am 2. Januar und beginnt dann am 2. Januar um 2:00 Uhr und läuft bis 3:00 Uhr am 3. Januar |

>[!NOTE]
>
>Sie können auch _Militärzeit_ Notation (14:00) anstelle von *A.M./P.M* (14:00 Uhr).
