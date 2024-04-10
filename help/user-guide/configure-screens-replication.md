---
title: Konfigurieren von Screens-Replikationsagenten
description: Erfahren Sie, wie Sie Screens-Replikationsagenten konfigurieren.
role: Developer
level: Intermediate
exl-id: 40877547-5027-41eb-8d66-d4a2d7b9af70
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 35%

---

# Konfigurieren von Screens-Replikationsagenten {#configuring-screens-replication-agent}

Auf dieser Seite wird beschrieben, wie Sie Screens-Replikationsagenten konfigurieren.

## Ziel {#objective}

Der Screens-Replikationsagent ist für die Bereitstellung von Befehlsdaten von Veröffentlichung an Autor verantwortlich, z. B. *user*, *password*, *rebootSchedule*, *maxNumberOfLogFilesToKeep* und viele mehr. Dies muss unbedingt konfiguriert werden, damit der Autor den Geräte-Ping anzeigen kann.

>[!NOTE]
>Weitere Informationen zu Screens-Replikationsagenten finden Sie unter [Screens-Replikationsagenten und -Befehle](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview#screens-replication-agents-and-commands).

Führen Sie beide Abschnitte aus, wenn Sie die Konfiguration für den Screens-Replikationsagenten abschließen möchten:

1. [Aktivieren von Benutzern und Aktualisieren des Passworts](#enable-users)
1. [Aktualisieren der Einstellungen für den Screens-Replikationsagenten](#replicate-agent)

## Aktivieren von Benutzern und Aktualisieren des Passworts {#enable-users}

Gehen Sie wie folgt vor, um Benutzer zu aktivieren und das Kennwort für `screens-receiver-user`:

>[!NOTE]
>Aus Sicherheitsgründen wird empfohlen, die Verwendung des Administratorkennworts für `screens-receiver-user`.

1. Navigieren Sie zu Ihrer AEM-Autoreninstanz.

1. Klicken Sie auf Tools > **Sicherheit** > **Benutzer**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Suchen Sie nach **`screens-receiver-user`**.

1. Wählen Sie die **`screens-receiver-user`** und klicken **Aktivieren** in der Aktionsleiste aus.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Klicken Sie zur Bestätigung auf **OK**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Sobald Sie den Benutzer aktiviert haben, sehen Sie die **`screens-receiver-user`** as **Aktiviert** unter **Status** -Feld.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Wählen Sie die **`screens-receiver-user`** und klicken **Eigenschaften** in der Aktionsleiste aus.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Klicks **Kennwort ändern** under **Kontoeinstellungen** aus dem **Details** wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Geben Sie im **Kennwort ändern** und klicken Sie auf **Speichern**.

   >[!NOTE]
   >Geben Sie das vorhandene Administratorkennwort in **Ihr Passwort** -Feld.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Klicken Sie auf **Speichern und schließen**.

1. Wählen Sie die **`screens-receiver-user`** und klicken **Aktivieren** in der Aktionsleiste aus.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Klicken Sie zur Bestätigung auf **OK**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Wählen Sie die **`screens-receiver-user`** und klicken **Deaktivieren** in der Aktionsleiste aus.

   >[!IMPORTANT]
   > Deaktivieren **`screens-receiver-user`** Deaktiviert nur diesen Benutzer aus der Authoring-Instanz und alle Benutzer in der Veröffentlichungsinstanz bleiben aktiv. Nicht klicken **Deaktivieren** über die Aktionsleiste aus, da die Deaktivierung den Benutzer auch aus den Veröffentlichungsinstanzen entfernt.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Klicken Sie zur Bestätigung auf **OK**.

## Aktualisieren der Einstellungen für den Screens-Replikationsagenten {#replicate-agent}

Gehen Sie wie folgt vor, um die Einstellungen im AEM Screens-Replikationsagenten zu aktualisieren:

>[!IMPORTANT]
>Führen Sie die folgenden Schritte für ALLE vorhandenen AEM Screens-Replikationsagenten aus.

1. Navigieren Sie zu Ihrer AEM-Instanz.
1. Klicken Sie auf Tools > **Implementierung** > **Replikation**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klicks **Agenten für Autor**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Suchen Sie nach allen AEM Screens-Replikationsagenten auf der Autoreninstanz und klicken Sie auf den Link, wie in der folgenden Abbildung dargestellt.

   >[!NOTE]
   >Suchen Sie nach allen AEM Screens-Replikationsagenten. Der Name des Screens-Replikationsagenten enthält den Brief **S** im Titel.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klicken Sie auf **Bearbeiten**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Aktivieren Sie **Aktiviert** auf der Registerkarte **Einstellungen**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigieren Sie zu **Verkehr** Registerkarte aus **Agenteneinstellungen** und aktualisieren Sie die **Benutzer** nach **`screens-receiver-user`** und geben Sie dasselbe Kennwort ein, das Sie zuvor in Schritt (8) von [Aktivieren von Benutzern und Aktualisieren des Kennworts](#enable-users).

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Klicken Sie auf **OK**.

1. Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie auf **Verbindung testen** , um die Verbindung zu überprüfen.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Wenn die Verbindungsprüfung erfolgreich war, ist die Konfiguration des Screens-Replikationsagenten abgeschlossen.
