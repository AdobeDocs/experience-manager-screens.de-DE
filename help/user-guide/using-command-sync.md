---
title: Verwenden der Befehlssynchronisierung
description: Erfahren Sie mehr über die Verwendung der Befehlssynchronisierung in AEM Screens.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3314e0b5-0001-4bce-8ec6-5a6ffbb20f7b
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 37%

---

# Befehlssynchronisierung {#command-sync}

Auf der folgenden Seite wird die Verwendung der Befehlssynchronisierung beschrieben. Mithilfe der Befehlssynchronisierung kann die Wiedergabe über verschiedene Player hinweg synchronisiert werden. Die Player können unterschiedliche Inhalte wiedergeben, aber jedes Asset muss dieselbe Dauer haben.

>[!IMPORTANT]
>
>Diese Funktion unterstützt keine eingebetteten Sequenzen, dynamischen eingebetteten Sequenzen, Anwendungskanäle oder Übergänge.

## Überblick {#overview}

Digital Signage-Lösungen müssen Videowände und die synchronisierte Wiedergabe unterstützen. Dieses Szenario trifft zu, wenn Sie Szenarien wie Neujahrszählungen oder große Videos unterstützen möchten, die auf mehreren Bildschirmen abgespielt werden. In solchen Szenarien kommt die Befehlssynchronisierung zum Tragen.

Zur Verwendung der Befehlssynchronisierung dient ein Player als *primary* und sendet den Befehl und alle anderen Player agieren wie *Clients* und spielen, wenn sie den Befehl erhalten.

Das *Primärgerät* sendet einen Befehl an alle registrierten Clients, wenn es im Begriff ist, die Wiedergabe eines Elements zu starten. Die Nutzlast dieser Aktion kann der Index des abzuspielenden Elements oder der äußere HTML-Code des abzuspielenden Elements oder beides sein.

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
   >Informationen zum Erstellen eines Kanals oder Hinzufügen von Inhalten zu einem Kanal finden Sie unter [Erstellen und Verwalten von Kanälen](/help/user-guide/managing-channels.md).

   Der Kanal enthält den folgenden Inhalt, wie in der Abbildung unten dargestellt.

   ![image1](assets/command-sync/command-sync2-1.png)

1. Erstellen eines Standorts **Lobby** und dann eine Anzeige mit dem Titel **LobbyDisplay** im **Standorte** -Ordner, wie in der folgenden Abbildung dargestellt.
   ![image1](assets/command-sync/command-sync3-1.png)

1. Weisen Sie den Kanal **ChannelLobby** Ihrem **LobbyDisplay** zu. Sie können jetzt den der Anzeige zugewiesenen Kanal im Anzeige-Dashboard anzeigen.
   ![image1](assets/command-sync/command-sync4-1.png)

   >[!NOTE]
   >
   >Informationen zum Zuweisen eines Kanals zu einer Anzeige finden Sie unter [Erstellen und Verwalten von Anzeigen](/help/user-guide/managing-displays.md).

1. Navigieren Sie zum **Geräte** Ordner.
1. Klicken Sie in der Aktionsleiste auf **Geräte-Manager**.

   ![image1](assets/command-sync5.png)

   >[!NOTE]
   >
   >Informationen zum Registrieren eines Geräts finden Sie unter [Geräteregistrierung](/help/user-guide/device-registration.md).

1. Zu Demozwecken werden in diesem Beispiel ein Chrome-Gerät und ein Windows Player als zwei separate Geräte dargestellt. Beide Geräte verweisen auf dieselbe Anzeige.
   ![image1](assets/command-sync6.png)

### Aktualisieren von Kanaleinstellungen

1. Navigieren Sie zu **ChannelLobby**.
1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**. 
1. Klicken Sie auf den gesamten Kanal, wie in der Abbildung unten dargestellt.
   ![image1](assets/command-sync/command-sync7-1.png)

1. Klicken Sie auf das Schraubenschlüsselsymbol.
   ![image1](assets/command-sync/command-sync8-1.png)

1. Im **Seite** eingeben. *synchronisiert* Suchbegriff in **Strategie** -Feld.
   ![image1](assets/command-sync/command-sync9-1.png)


### Einrichten eines Primärgeräts {#setting-up-primary}

1. Navigieren Sie über zum Anzeigen-Dashboard. **CommandSyncDemo** > **Standorte**  > **Lobby** > **LobbyDisplay**. Klicken Sie anschließend auf **Dashboard** in der Aktionsleiste aus.
Beachten Sie die beiden Geräte (Chrome und Windows Player) in **Geräte** -Bedienfeld, wie im Folgenden gezeigt:
   ![image1](assets/command-sync/command-sync10-1.png)

1. Aus dem **Geräte** auf das Gerät, das Sie als primär festlegen möchten. Das folgende Beispiel zeigt, wie das Chrome-Gerät als primäres Gerät eingerichtet wird. Klicks **Als primäres Gerät festlegen**.

   ![image1](assets/command-sync/command-sync11-1.png)

1. Geben Sie die IP-Adresse in **Als primäres Gerät festlegen** und klicken **Speichern**.

   ![image1](assets/command-sync/command-sync12-1.png)

>[!NOTE]
>
>Sie können mehrere Geräte als primäre Geräte einrichten.

### Synchronisieren mit dem Primärgerät {#sync-up-primary}

1. Nachdem Sie das Chrome-Gerät als primäres Gerät festgelegt haben, synchronisieren Sie das andere Gerät (in diesem Fall den Windows-Player) mit dem primären Gerät.
Klicken Sie auf das andere Gerät (in diesem Fall auf Windows Player) aus dem **Geräte** Bedienfeld und klicken Sie **Mit Primärgerät synchronisieren**.

   ![image1](assets/command-sync/command-sync13-1.png)

1. Klicken Sie auf das Gerät in der Liste und klicken Sie auf **Speichern**.

   >[HINWEIS:]
   > Die **Mit Primärgerät synchronisieren** zeigt die Liste der Primärgeräte an. Wählen Sie den bevorzugten aus.

1. Wenn das Gerät (Windows Player) mit dem primären (Chrome Player) synchronisiert wird, wird das Gerät im **Geräte** Bedienfeld.

   ![image1](assets/command-sync/command-sync14-1.png)

### Aufheben der Synchronisierung mit dem Primärgerät {#desync-up-primary}

Nachdem Sie ein Gerät oder Geräte mit einem primären Gerät synchronisiert haben, können Sie die Synchronisierung mit diesem Gerät aufheben.

>[!NOTE]
>
>Wenn die Synchronisierung eines Primärgeräts aufgehoben wird, werden auch alle Verknüpfungen zu Client-Geräten, die mit diesem Primärgerät verbunden sind, aufgehoben.

Gehen Sie wie folgt vor, um die Synchronisierung vom primären Gerät zu entfernen:

1. Navigieren Sie zum **Geräte** und klicken Sie auf das Gerät.

1. Klicks **Synchronisieren von Geräten** , damit Sie die Synchronisierung des Clients mit dem primären Gerät aufheben können.

   ![image1](assets/command-sync/command-sync15-1.png)

1. Klicken Sie auf **Bestätigen**, um die Synchronisierung des ausgewählten Geräts mit dem Primärgerät aufzuheben.

   >[HINWEIS:]
   > Wenn Sie auf das primäre Gerät klicken und die Option zur Aufhebung der Synchronisierung verwenden, wird die Synchronisierung aller mit dem primären Gerät verbundenen Geräte in einem Schritt aufgehoben.
