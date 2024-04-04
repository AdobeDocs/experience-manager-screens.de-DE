---
title: Konfigurieren von Screens-Replikationsagenten
description: Auf dieser Seite erhalten Sie Informationen zum Konfigurieren von Screens-Replikationsagenten.
role: Developer
level: Intermediate
exl-id: 40877547-5027-41eb-8d66-d4a2d7b9af70
source-git-commit: d1adadbab2cb13626dd8ce70deacced9f55aa4c9
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 97%

---

# Konfigurieren von Screens-Replikationsagenten {#configuring-screens-replication-agent}

Auf dieser Seite wird beschrieben, wie Sie Screens-Replikationsagenten konfigurieren.

## Ziel {#objective}

Der Screens-Replikationsagent ist für die Bereitstellung von Befehlsdaten von Veröffentlichung an Autor verantwortlich, z. B. *user*, *password*, *rebootSchedule*, *maxNumberOfLogFilesToKeep* und viele mehr. Dies muss unbedingt konfiguriert werden, damit der Autor den Geräte-Ping anzeigen kann.

>[!NOTE]
>Weitere Informationen zu Screens-Replikationsagenten finden Sie unter [Screens-Replikationsagenten und -Befehle](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview.html?lang=de#screens-replication-agents-and-commands).

Sie müssen beide Abschnitte abschließen, um den Screens-Replikationsagenten vollständig zu konfigurieren:

1. [Aktivieren von Benutzern und Aktualisieren des Passworts](#enable-users)
1. [Aktualisieren der Einstellungen für den Screens-Replikationsagenten](#replicate-agent)

## Aktivieren von Benutzern und Aktualisieren des Passworts {#enable-users}

Gehen Sie zum Aktivieren von Benutzern und Aktualisieren des Passworts für „screens-receiver-user“ wie folgt vor:

>[!NOTE]
>Aus Sicherheitsgründen wird empfohlen, für „screens-receiver-user“ nicht das Administratorpasswort zu verwenden.

1. Navigieren Sie zu Ihrer AEM-Autoreninstanz.

1. Klicken Sie auf Tools > **Sicherheit** > **Benutzer**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Suchen Sie nach **screens-receiver-user**.

1. Wählen Sie **screens-receiver-user** aus und klicken Sie in der Aktionsleiste auf **Aktivieren**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Klicken Sie zum Bestätigen auf **OK**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Nachdem Sie den Benutzer aktiviert haben, wird **screens-receiver-user** als **Aktiviert** im Feld **Status** aufgeführt.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Wählen Sie **screens-receiver-user** aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Klicken Sie auf der Registerkarte **Details** unter **Kontoeinstellungen** auf **Kennwort ändern**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Geben Sie im Dialogfeld **Kennwort ändern** ein neues Passwort ein und klicken Sie auf **Speichern**.

   >[!NOTE]
   >Sie sollten im Feld **Ihr Passwort** das vorhandene Administratorpasswort eingeben.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Klicken Sie auf **Speichern und schließen**.

1. Wählen Sie **screens-receiver-user** aus und klicken Sie in der Aktionsleiste auf **Aktivieren**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Klicken Sie zum Bestätigen auf **OK**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Wählen Sie **screens-receiver-user** aus und klicken Sie in der Aktionsleiste auf **Deaktivieren**.

   >[!IMPORTANT]
   > Durch Deaktivieren von **screens-receiver-user** wird nur dieser Benutzer in der Autoreninstanz deaktiviert. Alle Benutzer in der Veröffentlichungsinstanz bleiben weiterhin aktiv. Klicken Sie nicht auf **Deaktivieren** in der Aktionsleiste, da durch Deaktivieren der Benutzer auch aus den Veröffentlichungsinstanzen entfernt wird.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Klicken Sie zum Bestätigen auf **OK**.

## Aktualisieren der Einstellungen für den Screens-Replikationsagenten {#replicate-agent}

Gehen Sie zum Aktualisieren der Einstellungen für den Screens-Replikationsagenten wie folgt vor:

>[!IMPORTANT]
>Sie müssen die folgenden Schritte für ALLE vorhandenen Screens-Replikationsagenten ausführen.

1. Navigieren Sie zu Ihrer AEM-Instanz.

1. Klicken Sie auf Tools > **Implementierung** > **Replikation**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klicken Sie auf **Agenten für Autor**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Suchen Sie nach allen Screens-Replikationsagenten in der Autoreninstanz und klicken Sie auf den Link, wie in der folgenden Abbildung dargestellt.

   >[!NOTE]
   >Suchen Sie nach allen Screens-Replikationsagenten. Der Name des Screens-Replikationsagenten enthält den Buchstaben **S** im Titel.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klicken Sie auf **Bearbeiten**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Aktivieren Sie **Aktiviert** auf der Registerkarte **Einstellungen**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigieren Sie im Dialogfeld **Agenteneinstellungen** zur Registerkarte **Transport** und aktualisieren Sie die Einstellung für **Benutzer** in **screens-receiver-user**. Geben Sie dasselbe Passwort ein, das Sie zuvor in Schritt (8) von [Aktivieren von Benutzern und Aktualisieren des Passworts](#enable-users) festgelegt haben.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Klicken Sie auf **OK**.

1. Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie auf **Verbindung testen** klicken, um die Verbindung zu überprüfen.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Wenn die Verbindungsprüfung erfolgreich war, ist die Konfiguration des Screens-Replikationsagenten abgeschlossen.
