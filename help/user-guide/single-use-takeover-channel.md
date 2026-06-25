---
title: Übernahmekanal für die einmalige Verwendung
description: In diesem Anwendungsfall erfahren Sie, wie Sie einen Übernahmekanal für die einmalige Verwendung erstellen.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3317f07a-784f-4c4a-93ea-c84f4e42e9f2
TQID: https://experienceleague.adobe.com/iK5EH0E-vKteNer-Dr0mDRaJke4OTmJr9JQfwTaqAt4
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2: id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: d4664dd5678eaccabe656398c437dca264d4675e
workflow-type: tm+mt
source-wordcount: 672
ht-degree: 77%

---

# Übernahmekanal für die einmalige Verwendung {#single-use-takeover-channel}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Auf der folgenden Seite finden Sie einen Anwendungsfall zur Projekteinrichtung, bei dem ein Übernahmekanal für die einmalige Verwendung erstellt wird, der Inhalte einmal für eine bestimmte Zeit wiedergibt.

## Anwendungsfall – Beschreibung {#use-case-description}

In diesem Anwendungsfall wird erläutert, wie Sie einen Kanal erstellen, der die Funktion des normalerweise zur Wiedergabe verwendeten Kanals für eine Anzeige oder eine Gruppe von Anzeigen *übernimmt*. Die Übernahme erfolgt nur einmal und für eine bestimmte Zeit.

Zum Beispiel gibt es einen einzelnen TakeOver-Kanal, der am Freitag, :00 Uhr bis 10 Uhr :00 wird. Während dieser Zeit sollte kein anderer Kanal abgespielt werden. Vor und nach dieser Zeit erfolgt keine Wiedergabe über den Übernahmekanal für die einmalige Verwendung. Das folgende Beispiel zeigt die Erstellung eines einzigen Übernahmekanals, in dem der Inhalt 2 Minuten vor 12 :00 Uhr am 31. Dezember bis 12 Uhr :01 wiedergegeben werden kann.

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

1. Erstellen Sie ein AEM Screens-Projekt mit dem Namen **SingleUseTakeOver**, wie unten dargestellt.

   ![Asset](assets/single-takeover1.png)

1. Erstellen Sie einen Kanal **MainAdChannel** im Ordner **Kanäle**.

   ![Asset](assets/single-takeover2.png)

1. Klicken Sie auf den Kanal **MainAdChannel** und dann in der Aktionsleiste auf **Bearbeiten**. Ziehen Sie einige Assets (Bilder, Videos, eingebettete Sequenzen) in Ihren Kanal.

   ![Asset](assets/single-takeover2.png)


   >[!NOTE]
   >Der Kanal **MainAdChannel** in diesem Beispiel ist ein Sequenzkanal, der Inhalt kontinuierlich wiedergibt.

   ![Asset](assets/single-takeover3.png)

1. Erstellen Sie einen Kanal **TakeOver**, der den Inhalt des Kanals **MainAdChannel** übernimmt und diesen nur einmal an einem bestimmten Tag und zu einer bestimmten Uhrzeit wiedergibt.

1. Wählen Sie den Kanal **TakeOver** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Ziehen Sie einige Assets in Ihren Kanal. Im folgenden Beispiel wird gezeigt, wie Sie diesem Kanal ein Bild für eine Einzelzone hinzufügen.

   ![Asset](assets/single-takeover4.png)

1. Richten Sie einen Standort und eine Anzeige für Ihre Kanäle ein. Beispielsweise werden für dieses Projekt der Standort **Lobby** und die Anzeige **MainLobbyDisplay** eingerichtet.

   ![Asset](assets/single-takeover5.png)

**Zuweisen von Kanälen zu einer Anzeige**

1. Wählen Sie die Anzeige **MainLobbyDisplay** aus dem Ordner **Standorte** aus. Klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   ![Asset](assets/single-takeover6.png)

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter **[Kanalzuweisung](channel-assignment.md)**.

1. Füllen Sie die Felder (**Kanalpfad**, **Priorität** und **unterstützte Ereignisse**) im Dialogfeld **Kanalzuweisung** aus und klicken Sie auf **Speichern**. Sie haben Ihrer Anzeige den Kanal **MainAdChannel** zugewiesen.

   ![Asset](assets/single-takeover7.png)

1. Wählen Sie die Anzeige **TakeOver** aus dem Ordner **Standorte** aus. Klicken Sie in der Aktionsleiste auf **Kanal zuweisen**, um den Übernahmekanal für die einmalige Verwendung zuzuweisen.

1. Weisen Sie den Kanal **TakeOver** Ihrer Anzeige zu einem geplanten Zeitpunkt zu, füllen Sie die folgenden Felder im Dialogfeld **Kanalzuweisung** aus und klicken Sie auf **Speichern**:

   * **Kanalpfad**: Klicken Sie auf den Pfad zum Kanal „TakeOver“
   * **Priorität**: Legen Sie die Priorität dieses Kanals höher als die von **MainAdChannel** fest. Die in diesem Beispiel eingestellte Priorität ist beispielsweise „8“.

     >[!NOTE]
     >Die Priorität kann ein beliebiger Wert sein, der höher als die Priorität des normalerweise zur Wiedergabe verwendeten Kanals ist.
   * **Unterstützte Ereignisse**: Klicken Sie auf **Bildschirm bei Untätigkeit** und **Timer**.
   * **Zeitplan**: Geben Sie den Text für den Zeitplan ein, nach dem dieser Kanal in der Anzeige ausgeführt werden soll. Beispielsweise ermöglicht der Text hier die Wiedergabe des Inhalts 2 Minuten vor 12 :00 am 31. Dezember bis 12 :01 Uhr morgens.
Der Text im **Zeitplan** in diesem Beispiel ist *am 31. Dezember nach dem 23:58 und auch am 1. Januar vor 00.01*.

     ![Asset](assets/single-takeover8.png)

     Navigieren Sie mit **SingleUseTakeOver** > **Standorte** > **Lobby** > **MainLobbyDisplay** zur Anzeige. Klicken Sie in der Aktionsleiste auf **Dashboard**, um die zugewiesenen Kanäle mit ihren Prioritäten anzuzeigen, wie unten dargestellt.

     >[!NOTE]
     >Es ist zwingend erforderlich, die Priorität des Übernahmekanals auf die höchste Stufe zu setzen.

     ![Asset](assets/single-takeover9.png)

>[!NOTE]
>
>Es empfiehlt sich, den Übernahmekanal für die einmalige Verwendung nach der Wiedergabe zu löschen.
