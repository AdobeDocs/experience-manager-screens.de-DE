---
title: Konfigurieren von Screens-Replikationsagenten
description: Erfahren Sie, wie Sie Screens-Replikationsagenten konfigurieren.
role: Developer
level: Intermediate
exl-id: 40877547-5027-41eb-8d66-d4a2d7b9af70
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 78%

---

# Konfigurieren von Screens-Replikationsagenten {#configuring-screens-replication-agent}

Auf dieser Seite wird beschrieben, wie Sie Screens-Replikationsagenten konfigurieren.

## Ziel {#objective}

Der Screens-Replikationsagent ist für das Abrufen von Befehlsdaten wie *Benutzer*, *password*, *rebootSchedule*, *maxNumberOfLogFilesToKeep* und viele weitere solcher Werte vom Veröffentlichungs- zum Autorenmodus. Dieser Agent muss unbedingt konfiguriert werden, damit der Autor den Geräte-Ping anzeigen kann.

>[!NOTE]
>Weitere Informationen zu Screens-Replikationsagenten finden Sie unter [Screens-Replikationsagenten und -Befehle](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview#screens-replication-agents-and-commands).

Führen Sie die Schritte in den beiden folgenden Abschnitten aus, um die Konfiguration für den Screens-Replikationsagenten abzuschließen:

1. [Aktivieren von Benutzern und Aktualisieren des Passworts](#enable-users)
1. [Aktualisieren der Einstellungen für den Screens-Replikationsagenten](#replicate-agent)

## Aktivieren von Benutzern und Aktualisieren des Passworts {#enable-users}

Gehen Sie wie folgt vor, um Benutzende zu aktivieren und das Kennwort für `screens-receiver-user` zu aktualisieren:

>[!NOTE]
>Aus Sicherheitsgründen wird empfohlen, für `screens-receiver-user` nicht das Administratorkennwort zu verwenden.

1. Navigieren Sie zu Ihrer Instanz AEM -Autors.

1. Klicken Sie auf „Tools“ > **Sicherheit** > **Benutzer**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Suchen Sie nach **`screens-receiver-user`**.

1. Klicken Sie auf **`screens-receiver-user`** und dann in der Aktionsleiste auf **Aktivieren**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Klicken Sie zur Bestätigung auf **OK**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Wenn Sie das Benutzerprofil aktiviert haben, wird **`screens-receiver-user`** im Feld **Status** als **Aktiviert** aufgeführt.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Klicken Sie auf **`screens-receiver-user`** und dann in der Aktionsleiste auf **Eigenschaften**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Klicken Sie auf der Registerkarte **Details** unter **Kontoeinstellungen** auf **Kennwort ändern**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Geben Sie im Dialogfeld **Kennwort ändern** ein neues Kennwort ein und klicken Sie auf **Speichern**.

   >[!NOTE]
   >Geben Sie das vorhandene Administratorkennwort in das Feld **Ihr Kennwort** ein.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Klicken Sie auf **Speichern und schließen**.

1. Klicken Sie auf **`screens-receiver-user`** und dann in der Aktionsleiste auf **Aktivieren**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Klicken Sie zur Bestätigung auf **OK**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Klicken Sie auf **`screens-receiver-user`** und dann in der Aktionsleiste auf **Deaktivieren**.

   >[!IMPORTANT]
   > Durch Deaktivieren von **`screens-receiver-user`** wird nur dieses Benutzerprofil in der Autoreninstanz deaktiviert. Alle Benutzenden in der Veröffentlichungsinstanz bleiben weiterhin aktiv. Klicken Sie in der Aktionsleiste nicht auf **Deaktivieren**, da dadurch das Benutzerprofil auch aus den Veröffentlichungsinstanzen entfernt wird.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Klicken Sie zur Bestätigung auf **OK**.

## Aktualisieren der Einstellungen für den Screens-Replikationsagenten {#replicate-agent}

Gehen Sie zum Aktualisieren der Einstellungen für den AEM Screens-Replikationsagenten wie folgt vor:

>[!IMPORTANT]
>Führen Sie die folgenden Schritte für ALLE vorhandenen AEM Screens-Replikationsagenten aus.

1. Navigieren Sie zu Ihrer AEM-Instanz.
1. Klicken Sie auf „Tools“ > **Bereitstellung** > **Replikation**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klicken Sie auf **Agenten für Autor**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Suchen Sie nach allen AEM Screens-Replikationsagenten auf der Autoreninstanz und klicken Sie auf den Link, wie in der folgenden Abbildung dargestellt.

   >[!NOTE]
   >Suchen Sie nach allen AEM Screens-Replikationsagenten. Der Name des Screens-Replikationsagenten enthält den Buchstaben **S** im Titel.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klicken Sie auf **Bearbeiten**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Aktivieren Sie **Aktiviert** auf der Registerkarte **Einstellungen**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigieren Sie im Dialogfeld **Agenteneinstellungen** zur Registerkarte **Transport** und ändern Sie die Einstellung unter **Benutzer** in **`screens-receiver-user`**. Geben Sie dasselbe Kennwort ein, das Sie zuvor in Schritt (8) im Abschnitt [Aktivieren von Benutzenden und Aktualisieren des Passworts](#enable-users) festgelegt haben.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Klicken Sie auf **OK**.

1. Nachdem Sie alle vorherigen Schritte ausgeführt haben, klicken Sie auf **Verbindung testen**, um die Verbindung zu überprüfen.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Wenn die Verbindungsprüfung erfolgreich war, haben Sie die Konfiguration des Screens-Replikationsagenten abgeschlossen.
