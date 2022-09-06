---
title: Verwenden der Befehlssynchronisierung
seo-title: Using Command Sync
description: Auf dieser Seite erfahren Sie, wie Sie die Befehlssynchronisierung verwenden.
seo-description: Follow this page to learn about how to use Command Sync.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3314e0b5-0001-4bce-8ec6-5a6ffbb20f7b
source-git-commit: 43ac19cf7ef63ec17611cf19ca357f791dca6e87
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 61%

---

# Befehlssynchronisierung {#command-sync}

Auf der folgenden Seite wird die Verwendung der Befehlssynchronisierung beschrieben. Mithilfe der Befehlssynchronisierung kann die Wiedergabe über verschiedene Player hinweg synchronisiert werden. Die Player können unterschiedliche Inhalte wiedergeben, aber jedes Asset muss dieselbe Dauer haben.

>[!IMPORTANT]
>
>Diese Funktion unterstützt keine eingebetteten Sequenzen, dynamischen eingebetteten Sequenzen, Anwendungskanäle oder Übergänge.

## Überblick {#overview}

Digital-Signage-Lösungen müssen Videowände und die synchronisierte Wiedergabe unterstützen, um Szenarien wie Neujahrs-Countdowns oder große Videos zu ermöglichen, die auf mehreren Bildschirmen wiedergegeben werden. Hier kommt die Befehlssynchronisierung zum Tragen.

Zur Verwendung der Befehlssynchronisierung dient ein Player als *primary* und sendet den Befehl und alle anderen Player agieren wie *Clients* und spielen, wenn sie den Befehl erhalten.

Die *primary* sendet einen Befehl an alle registrierten Clients, wenn er im Begriff ist, die Wiedergabe eines Elements zu starten. Die Nutzlast kann hier der Index bzw. der äußere HTML-Code des abzuspielenden Elements sein.

## Implementieren der Befehlssynchronisierung {#using-command-sync}

Im folgenden Abschnitt wird beschrieben, wie Sie die Befehlssynchronisierung in einem AEM Screens-Projekt verwenden können.

>[!NOTE]
>
>Für die synchronisierte Wiedergabe ist es erforderlich, dass alle Hardwaregeräte über dieselben Spezifikationen und vorzugsweise über dasselbe Betriebssystem verfügen. Eine Synchronisierung zwischen verschiedenen Hardware- und Betriebssystemen wird nicht empfohlen.

### Einrichten des Projekts {#setting-up}

Bevor Sie die Funktion zur Befehlssynchronisierung verwenden, stellen Sie sicher, dass Sie ein Projekt und einen Kanal mit Inhalten für Ihr Projekt eingerichtet haben.

1. Das folgende Beispiel veranschaulicht ein Demoprojekt mit dem Namen **CommandSyncDemo** und einem Sequenzkanal namens **ChannelLobby**.

   ![image1](assets/command-sync/command-sync1-1.png)

   >[!NOTE]
   >
   >Informationen zum Erstellen eines Kanals oder Hinzufügen von Inhalten zu einem Kanal finden Sie unter [Erstellen und Verwalten von Kanälen](/help/user-guide/managing-channels.md)

   Der Kanal enthält den folgenden Inhalt, wie in der Abbildung unten dargestellt.

   ![image1](assets/command-sync/command-sync2-1.png)

1. Erstellen Sie einen Speicherort **Lobby** und anschließend eine Anzeige mit dem Titel **LobbyDisplay** im Ordner **Speicherorte**, wie in der Abbildung unten gezeigt.
   ![image1](assets/command-sync/command-sync3-1.png)

1. Weisen Sie den Kanal **ChannelLobby** Ihrem **LobbyDisplay** zu. Sie können jetzt den der Anzeige zugewiesenen Kanal im Anzeige-Dashboard anzeigen.
   ![image1](assets/command-sync/command-sync4-1.png)

   >[!NOTE]
   >
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md).

1. Navigieren Sie zum Ordner **Geräte** und klicken Sie in der Aktionsleiste auf **Geräte-Manager**, um die Geräte zu registrieren.

   ![image1](assets/command-sync5.png)

   >[!NOTE]
   >
   >Informationen zum Registrieren eines Geräts finden Sie unter [Geräteregistrierung](/help/user-guide/device-registration.md)

1. Zu Demozwecken werden in diesem Beispiel ein Chrome-Gerät und ein Windows-Player als zwei separate Geräte dargestellt. Beide Geräte verweisen auf dieselbe Anzeige.
   ![image1](assets/command-sync6.png)

### Aktualisieren von Kanaleinstellungen

1. Navigieren Sie zu **ChannelLobby** und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um die Kanaleinstellungen zu aktualisieren.

1. Wählen Sie den gesamten Kanal aus, wie in der Abbildung unten dargestellt.
   ![image1](assets/command-sync/command-sync7-1.png)

1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld **Seite** zu öffnen.
   ![image1](assets/command-sync/command-sync8-1.png)

1. Geben Sie das *synchronisierte* Keyword in das Feld **Strategie** ein.

   ![image1](assets/command-sync/command-sync9-1.png)


### Einrichten einer primären {#setting-up-primary}

1. Rufen Sie das Anzeigen-Dashboard auf, indem Sie zu **CommandSyncDemo** > **Standorte** > **Lobby** > **LobbyDisplay** navigieren und in der Aktionsleiste auf **Dashboard** klicken.
Im Bedienfeld **GERÄTE** werden die beiden Geräte (Chrome- und Windows-Player) angezeigt, wie in der folgenden Abbildung dargestellt.
   ![image1](assets/command-sync/command-sync10-1.png)

1. Aus dem **GERÄTE** -Bedienfeld das Gerät auswählen, das Sie als primär festlegen möchten. Das folgende Beispiel zeigt, wie das Chrome-Gerät als primäres Gerät eingerichtet wird. Klicken Sie auf **Als primäres Gerät festlegen**.

   ![image1](assets/command-sync/command-sync11-1.png)

1. Geben Sie die IP-Adresse in **Als primäres Gerät festlegen** und klicken Sie auf **Speichern**.

   ![image1](assets/command-sync/command-sync12-1.png)

>[!NOTE]
>
>Sie können mehrere Geräte als primäre Geräte einrichten.

### Synchronisieren mit Primären {#sync-up-primary}

1. Nachdem Sie das Chrome-Gerät als primäres Gerät festgelegt haben, können Sie das andere Gerät (in diesem Fall den Windows-Player) mit dem primären Gerät synchronisieren.
Wählen Sie das andere Gerät (in diesem Fall den Windows-Player) aus dem **GERÄTE** Bedienfeld und klicken Sie auf **Mit Primärgerät synchronisieren**, wie in der folgenden Abbildung dargestellt.

   ![image1](assets/command-sync/command-sync13-1.png)

1. Wählen Sie das Gerät in der Liste aus und klicken Sie auf **Speichern**.

   >[HINWEIS:]
   > Die **Mit Primärgerät synchronisieren** zeigt die Liste der Primärgeräte an. Sie können die gewünschte Voreinstellung auswählen.

1. Nachdem das Gerät (Windows-Player) mit dem primären (Chrome-Player) synchronisiert wurde, wird das Gerät im **GERÄTE** Bereich.

   ![image1](assets/command-sync/command-sync14-1.png)

### Aufheben der Synchronisierung mit dem Primären {#desync-up-primary}

Nachdem Sie ein Gerät oder Geräte mit einem primären Gerät synchronisiert haben, können Sie die Synchronisierung mit diesem Gerät aufheben.

>[!NOTE]
>
>Wenn Sie die Synchronisierung eines Primärgeräts aufheben, wird auch die Verknüpfung aller mit diesem primären Gerät verknüpften Client-Geräte aufgehoben.

Gehen Sie wie folgt vor, um die Synchronisierung vom primären Gerät zu entfernen:

1. Navigieren Sie zum Bedienfeld **GERÄTE** und wählen Sie das Gerät aus.

1. Klicken Sie auf **Synchronisierung von Geräten aufheben** , um die Synchronisierung des Clients mit dem primären Gerät aufzuheben.

   ![image1](assets/command-sync/command-sync15-1.png)

1. Klicken **Bestätigen** , um die Synchronisierung des ausgewählten Geräts mit dem primären Gerät aufzuheben.

   >[HINWEIS:]
   > Wenn Sie das Primärgerät auswählen und die Option &quot;Synchronisierung aufheben&quot;verwenden, wird die Synchronisierung aller mit dem Primärgerät verbundenen Geräte in einem Schritt aufgehoben.
