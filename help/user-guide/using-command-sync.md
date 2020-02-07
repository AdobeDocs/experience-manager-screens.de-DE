---
title: Verwenden der Befehlssynchronisierung
seo-title: Verwenden der Befehlssynchronisierung
description: Auf dieser Seite erfahren Sie, wie Sie die Befehlssynchronisierung verwenden.
seo-description: Auf dieser Seite erfahren Sie, wie Sie die Befehlssynchronisierung verwenden.
translation-type: tm+mt
source-git-commit: c46f246f9c5b8ab09f1100c798d0a1a240388c18

---


# Befehlssynchronisierung {#command-sync}

Auf der folgenden Seite wird die Verwendung der Befehlssynchronisierung beschrieben. Die Befehlssynchronisierung ermöglicht die synchronisierte Wiedergabe über verschiedene Player hinweg. Die Player können unterschiedliche Inhalte abspielen, aber jedes Asset muss dieselbe Dauer haben.

## Überblick {#overview}

Die Lösungen für digitale Schilder müssen Videowände und synchronisierte Wiedergabe unterstützen, um Szenarien wie Neujahrszählungen oder große Videoschnitte zu unterstützen, die über mehrere Bildschirme verteilt abgespielt werden können. In diesem Fall kommt die Befehlssynchronisierung sofort zum Einsatz.

To use Command Sync, one player acts as a *master* and sends command and all the other players act as *clients* and play when they receive the command.

Der *Master* sendet einen Befehl an alle registrierten Clients, wenn er im Begriff ist, die Wiedergabe eines Elements zu starten. Die Nutzlast kann hier der Index bzw. der äußere HTML-Code des abzuspielenden Elements sein.

## Implementieren der Befehlssynchronisierung {#using-command-sync}

Im folgenden Abschnitt wird beschrieben, wie Sie die Befehlssynchronisierung in einem AEM Screens-Projekt verwenden können.

### Einrichten des Projekts {#setting-up}

Bevor Sie die Funktion zur Befehlssynchronisierung verwenden, stellen Sie sicher, dass Sie ein Projekt und einen Kanal mit Inhalten für Ihr Projekt eingerichtet haben.

1. Das folgende Beispiel veranschaulicht ein Demoprojekt mit dem Namen **CommandSyncDemo** und einem Sequenzkanal namens **ChannelLobby**.

   ![image1](assets/command-sync/command-sync1-1.png)

   >[!NOTE]
   >
   >Informationen zum Erstellen eines Kanals oder Hinzufügen von Inhalten zu einem Kanal finden Sie unter [Erstellen und Verwalten von Kanälen](/help/user-guide/managing-channels.md)

   Der Kanal enthält den folgenden Inhalt, wie in der Abbildung unten dargestellt.

   ![image1](assets/command-sync/command-sync2-1.png)

1. Erstellen Sie eine Anzeige im Ordner **Standorte**, wie in der Abbildung unten dargestellt.
   ![image1](assets/command-sync/command-sync3-1.png)

1. Weisen Sie den Kanal **ChannelLobby** Ihrem **LobbyDisplay** zu.
   ![image1](assets/command-sync/command-sync4-1.png)

   >[!NOTE]
   >
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md).

1. Navigieren Sie zum Ordner **Geräte** und klicken Sie in der Aktionsleiste auf **Geräte-Manager**, um die Geräte zu registrieren.

   ![image1](assets/command-sync5.png)

   >[!NOTE]
   >
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md)

1. Zu Demozwecken werden in diesem Beispiel ein Chrome-Gerät und ein Windows-Player als zwei separate Geräte dargestellt. Beide Geräte verweisen auf dieselbe Anzeige.
   ![image1](assets/command-sync6.png)

### Kanaleinstellungen aktualisieren

1. Navigieren Sie zu **ChannelLobby** und klicken Sie in der Aktionsleiste auf **Bearbeiten** , um die Kanaleinstellungen zu aktualisieren.

1. Wählen Sie den gesamten Kanal aus, wie in der Abbildung unten dargestellt.
   ![image1](assets/command-sync/command-sync7-1.png)

1. Klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld &quot; **Seite** &quot;zu öffnen.
   ![image1](assets/command-sync/command-sync8-1.png)

1. Geben Sie den *synchronisierten* Suchbegriff in das Feld &quot; **Strategie** &quot;ein.

   ![image1](assets/command-sync/command-sync9-1.png)


### Einrichten eines Master-Geräts {#setting-up-master}

1. Navigieren Sie zum Anzeige-Dashboard über **CommandSyncDemo** > **Standorte** > **Lobby** > **LobbyDisplay** und klicken Sie in der Aktionsleiste auf **Dashboard**.
You will see the two devices (chrome and windows player) in **DEVICES** panel, as shown in the figure below.
   ![image1](assets/command-sync/command-sync10-1.png)

1. Wählen Sie im Bedienfeld **GERÄTE** das Gerät aus, das Sie als Master verwenden möchten. Das folgende Beispiel zeigt, wie Sie das Chrome-Gerät als Master einrichten. Klicken Sie auf **Als Master-Gerät einrichten**.

   ![image1](assets/command-sync/command-sync11-1.png)

1. Geben Sie in **Als Master-Gerät einrichten** die IP-Adresse ein und klicken Sie auf **Speichern**.

   ![image1](assets/command-sync/command-sync12-1.png)

>[!NOTE]
> Sie können mehrere Geräte als Master einrichten.

### Synchronisieren mit dem Master {#sync-up-master}

1. Nachdem Sie das Chrome-Gerät als Master festgelegt haben, können Sie das andere Gerät (in diesem Fall den Windows-Player) synchronisieren, um es mit dem Master zu synchronisieren.
Select the other device (in this case, windows player) from the **DEVICES** panel and click on **Sync to master device**, as shown in the figure below.

   ![image1](assets/command-sync/command-sync13-1.png)

1. Wählen Sie das Gerät in der Liste aus und klicken Sie auf **Speichern**.

   >[HINWEIS:]
   > Im Dialogfeld &quot;Mit **Mastergerät** synchronisieren&quot;wird die Liste der Mastergeräte angezeigt. Sie können die gewünschte Voreinstellung auswählen.

1. Nachdem das Gerät (Windows-Player) mit dem Master (Chrome-Player) synchronisiert wurde, wird das Gerät im **Gerätebedienfeld** synchronisiert.

   ![image1](assets/command-sync/command-sync14-1.png)

### Synchronisierung mit dem Master {#desync-up-master}

Nachdem Sie ein oder mehrere Geräte mit einem Master synchronisiert haben, können Sie die Zuweisung von diesem Gerät aus desynchronisieren. Gehen Sie wie folgt vor, um die Synchronisierung vom Hauptgerät zu entfernen:

1. Navigieren Sie zum **Bedienfeld &quot;GERÄTE** &quot;und wählen Sie das Gerät aus.

1. Klicken Sie auf **Desync-Geräte,** um den Client vom Master-Gerät zu trennen.

   ![image1](assets/command-sync/command-sync15-1.png)

1. Klicken Sie auf **Bestätigen** , um die Synchronisierung des ausgewählten Geräts vom Master zu deaktivieren.

   >[HINWEIS:]
   > Wenn Sie das Mastergerät auswählen und die Option desync verwenden, werden alle mit dem Master verbundenen Geräte in einem Schritt deaktiviert.

