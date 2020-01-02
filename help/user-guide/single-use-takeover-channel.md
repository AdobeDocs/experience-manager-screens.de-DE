---
title: Einmalige Verwendung Übernahmekanal
seo-title: Einmalige Verwendung Übernahmekanal
description: Folgen Sie diesem Verwendungsfall für die Erstellung eines Single Use TakeOver-Kanals.
seo-description: Folgen Sie diesem Verwendungsfall für die Erstellung eines Single Use TakeOver-Kanals.
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: 58229f2ecbc098522d5d62972ba7f9362a538997

---


# Einmalige Verwendung Übernahmekanal {#single-use-takeover-channel}

Auf der folgenden Seite wird ein Anwendungsfall beschrieben, der sich mit der Einrichtung eines Projekts zur Erstellung eines Übernahmekanals befasst, der nur einmal wiedergegeben wird.

Zur Überprüfung bereit.

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Verwendungsfall wird erläutert, wie ein Kanal erstellt wird, der den normalen Wiedergabekanal für eine Anzeige oder Gruppe von Bildschirmen *übernimmt* . Die Übernahme erfolgt nur ein- und mehrmals.
So gibt es zum Beispiel einen Single TakeOver-Kanal, der am Freitag von 9 Uhr bis 10 Uhr abgespielt wird. Während dieser Zeit sollte kein anderer Kanal wiedergegeben werden. Vor und nach dieser Zeit wird der Einmal-Use-Übernahmekanal nicht wiedergegeben. Das folgende Beispiel zeigt die Erstellung eines einzelnen Übernahmekanals, der abgespielt wird, sodass der Inhalt 2 Minuten vor 12:00 Uhr am 31. Dezember bis 12:01 Uhr abgespielt werden kann.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Anwendungsfall beginnen, sollten Sie wissen, wie:

* **[Kanäle erstellen und verwalten](managing-channels.md)**
* **[Orte erstellen und verwalten](managing-locations.md)**
* **[Zeitpläne erstellen und verwalten](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Inhaltsersteller

## Setting up the Project {#setting-up-the-project}

Gehen Sie wie folgt vor, um ein Projekt einzurichten:

**Einrichten der Kanäle und Anzeigen**

1. Erstellen Sie ein AEM Screens-Projekt mit dem Titel **TakeoverLoop**, wie unten dargestellt.

   ![Asset](assets/single-takeover1.png)

1. Erstellen Sie einen **MainAdChannel** im Ordner &quot; **Channels** &quot;.

   ![Asset](assets/single-takeover2.png)

1. Wählen Sie den **MainAdChannel** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten** . Ziehen Sie Elemente (Bilder, Videos, eingebettete Sequenzen) per Drag &amp; Drop in Ihren Kanal.

   ![Asset](assets/single-takeover2.png)

   >[!Note]
   > Der **MainAdChannel** in diesem Beispiel zeigt einen Sequenzkanal, der Inhalt kontinuierlich wiedergibt.

   ![Asset](assets/single-takeover3.png)

1. Erstellen Sie einen **TakeOver** -Kanal, der den Inhalt in **MainAdChannel** übernimmt und nur für einen bestimmten Tag und eine bestimmte Zeit abspielt.

1. Wählen Sie das **Übernehmen** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten** . Ziehen Sie Elemente per Drag &amp; Drop in Ihren Kanal. Im folgenden Beispiel wird ein Bild für eine einzelne Zone gezeigt, das diesem Kanal hinzugefügt wurde.

   ![Asset](assets/single-takeover4.png)

1. Richten Sie einen Ort und eine Anzeige für Ihre Kanäle ein. Beispielsweise wird für dieses Projekt der folgende Speicherort **Lobby** und **MainLobbyDisplay** eingerichtet.

   ![Asset](assets/single-takeover5.png)

**Zuweisen von Kanälen zu einer Anzeige**

1. Wählen Sie die Anzeige **MainLobbyDisplay** aus dem Ordner **Locations** . Click **Assign Channel** from the action bar.

   ![Asset](assets/single-takeover6.png)

   >[!NOTE]
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter **[Kanalzuweisung](channel-assignment.md)**.

1. Füllen Sie die Felder (**Kanalpfad**, **Priorität** und **unterstützte Ereignisse**) im Dialogfeld &quot;Kanalzuweisung **&quot;aus und klicken Sie auf** Speichern ****. Jetzt haben Sie den **MainAdChannel** Ihrem Display zugewiesen.

   ![Asset](assets/single-takeover7.png)

1. Wählen Sie die Anzeige **TakeOver** aus dem Ordner **Locations** . Klicken Sie in der Aktionsleiste auf Kanal **zuweisen** , um den Übernahmekanal für einzelne Benutzer zuzuweisen.

1. So weisen Sie der Anzeige den **TakeOver** -Kanal zu einem geplanten Zeitpunkt zu und füllen die folgenden Felder im Dialogfeld &quot; **Kanalzuweisung** &quot;aus und klicken auf **Speichern**:

   * **Kanalpfad**: Wählen Sie den Pfad zum TakeOver-Kanal
   * **Priorität**: Legen Sie die Priorität dieses Kanals höher als **MainAdChannel** fest. Die in diesem Beispiel eingestellte Priorität ist beispielsweise 8.
   * **Unterstützte Ereignisse**: Wählen Sie den **Leerbildschirm** und den **Timer** aus.
   * **Plan**: Geben Sie den Text für den Zeitplan ein, in dem die Anzeige ausgeführt werden soll. Der Text hier ermöglicht es zum Beispiel, den Inhalt 2 Minuten vor 12:00 Uhr am 31. Dezember bis 12:01 Uhr abzuspielen.
Der in diesem Beispiel erwähnte Text im **Zeitplan** ist *am 31. Dezember nach 23:58 Uhr und am 1. Januar vor 00.01*.

      ![Asset](assets/single-takeover8.png)

      >[!NOTE]
      >Sie können den Zeitplan für verschiedene Anwendungsfälle erwähnen. Weitere Informationen finden Sie unter Perpetual Use Case.