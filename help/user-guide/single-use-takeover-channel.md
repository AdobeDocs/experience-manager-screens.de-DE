---
title: Übernahmekanal für einmaligen Gebrauch
description: In diesem Anwendungsbeispiel wird beschrieben, wie Sie einen Übernahmekanal für den einmaligen Gebrauch erstellen.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3317f07a-784f-4c4a-93ea-c84f4e42e9f2
source-git-commit: c142830a37461a36baae15f543bd43b0ae8a62a7
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 48%

---

# Übernahmekanal für die einmalige Verwendung {#single-use-takeover-channel}

Auf der folgenden Seite finden Sie ein Anwendungsbeispiel, in dem ein Projekt eingerichtet wird. Es wird beschrieben, wie ein Single-TakeOver-Kanal erstellt wird, der einmal für eine bestimmte Zeit wiedergegeben wird.


## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Anwendungsbeispiel wird erläutert, wie Sie einen Kanal erstellen, der *übernimmt* Vom normalen Wiedergabekanal für ein Display oder eine Gruppe von Displays. Die Übernahme erfolgt nur einmal und für einen bestimmten Zeitpunkt.

Zum Beispiel gibt es einen einzelnen Übernahmekanal, der am Freitag von 9:00 bis 10:00 Uhr wiedergegeben wird. Während dieser Zeit sollte kein anderer Kanal abgespielt werden. Vor und nach dieser Zeit wird der Übernahmekanal für die einmalige Verwendung nicht wiedergegeben. Das folgende Beispiel zeigt die Erstellung eines einzigen Übernahmekanals, in dem der Inhalt 2 Minuten vor 12:00 Uhr am 31. Dezember bis 12:01 Uhr abgespielt werden kann.

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

1. Wählen Sie den Kanal **MainAdChannel** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**. Ziehen Sie einige Assets (Bilder, Videos, eingebettete Sequenzen) in Ihren Kanal.

   ![Asset](assets/single-takeover2.png)


   >[!NOTE]
   >Der Kanal **MainAdChannel** in diesem Beispiel ist ein Sequenzkanal, der Inhalt kontinuierlich wiedergibt.

   ![Asset](assets/single-takeover3.png)

1. Erstellen eines **übernehmen** Kanal, der den Inhalt in übernimmt **MainAdChannel** und spielt nur an einem bestimmten Tag und zu einer bestimmten Uhrzeit.

1. Wählen Sie die **übernehmen** und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus. Ziehen Sie einige Assets in Ihren Kanal. Im folgenden Beispiel wird gezeigt, wie Sie diesem Kanal ein Bild für eine Einzelzone hinzufügen.

   ![Asset](assets/single-takeover4.png)

1. Richten Sie einen Standort und eine Anzeige für Ihre Kanäle ein. Zum Beispiel **Lobby** Standort und  **MainLobbyDisplay** Für dieses Projekt sind Anzeigen eingerichtet.

   ![Asset](assets/single-takeover5.png)

**Zuweisen von Kanälen zu einer Anzeige**

1. Wählen Sie die Anzeige **MainLobbyDisplay** aus dem Ordner **Standorte** aus. Klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   ![Asset](assets/single-takeover6.png)

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter **[Kanalzuweisung](channel-assignment.md)**.

1. Füllen Sie die Felder (**Kanalpfad**, **Priorität** und **unterstützte Ereignisse**) im Dialogfeld **Kanalzuweisung** aus und klicken Sie auf **Speichern**. Sie haben Ihrer Anzeige den Kanal **MainAdChannel** zugewiesen.

   ![Asset](assets/single-takeover7.png)

1. Wählen Sie die Anzeige **TakeOver** aus dem Ordner **Standorte** aus. Klick **Kanal zuweisen** über die Aktionsleiste aus, sodass Sie den Übernahmekanal für die einmalige Verwendung zuweisen können.

1. Zuweisen von **übernehmen** zu einem geplanten Zeitpunkt zu Ihrer Anzeige leiten und die folgenden Felder aus der **Kanalzuweisung** und klicken Sie auf **Speichern**:

   * **Kanalpfad**: Wählen Sie den Pfad zum Kanal „TakeOver“ aus
   * **Priorität**: Legen Sie die Priorität dieses Kanals höher als die von **MainAdChannel** fest. Die in diesem Beispiel eingestellte Priorität ist beispielsweise „8“.

     >[!NOTE]
     >Priorität kann jeder Wert sein, der höher ist als der Prioritätswert des normalen Wiedergabekanals.
   * **Unterstützte Ereignisse**: Wählen Sie **Bildschirm bei Untätigkeit** und **Timer** aus.
   * **Zeitplan**: Geben Sie den Text für den Zeitplan ein, nach dem dieser Kanal die Anzeige ausführen soll. Beispielsweise ermöglicht der Text hier die Wiedergabe des Inhalts 2 Minuten vor 12:00 Uhr am 31. Dezember bis 12:01 Uhr. Der Text im **Zeitplan** In diesem Beispiel wird Folgendes erwähnt *am 31. Dezember nach 23:58 Uhr und auch am 1. Januar vor 00.01 Uhr*.

     ![Asset](assets/single-takeover8.png)

     Navigieren Sie zur Anzeige über **einmalige VerwendungÜbernahme** > **Speicherorte** > **Lobby** > **MainLobbyDisplay** und klicken Sie auf **Dashboard** in der Aktionsleiste aus, sodass Sie die zugewiesenen Kanäle mit ihren Prioritäten anzeigen können, wie unten dargestellt.

     >[!NOTE]
     >Es ist zwingend erforderlich, die Priorität des Übernahmekanals auf die höchste zu setzen.

     ![Asset](assets/single-takeover9.png)

>[!NOTE]
>
>Es empfiehlt sich, den Übernahmekanal für die einmalige Verwendung nach der Wiedergabe zu löschen.
