---
title: Konfigurieren des Screens-Replikationsagenten
description: Auf dieser Seite erhalten Sie Informationen zum Konfigurieren des Screens-Replikationsagenten.
role: Developer
level: Intermediate
source-git-commit: 6f44bc9d28ed7fa3a9c8afef7ab7ecab64d53d36
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 8%

---


# Konfigurieren von Screens-Replikationsagenten {#configuring-screens-replication-agent}

Auf dieser Seite wird beschrieben, wie Sie Screens-Replikationsagenten konfigurieren.

>[!NOTE]
>Weitere Informationen zu Screens-Replikationsagenten finden Sie unter [Screens-Replikationsagenten und -Befehle](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview.html?lang=en#screens-replication-agents-and-commands).

Sie müssen beide Abschnitte ausführen, um die Konfiguration für den Screens-Replikationsagenten abzuschließen:

1. [Aktivieren von Benutzern und Aktualisieren des Kennworts](#enable-users)
1. [Aktualisieren der Einstellungen für den Screens-Replikationsagenten](#replicate-agent)

## Aktivieren von Benutzern und Aktualisieren des Kennworts {#enable-users}

Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zu Ihrer AEM-Instanz.

1. Klicken Sie auf Tools > **Sicherheit** —> **Benutzer**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Suchen Sie nach **screens-empfänger-user**.

1. Wählen Sie die **screens-empfänger-user** und klicken Sie auf **Aktivieren** in der Aktionsleiste aus.

   ![image](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Klicken Sie auf **OK** zur Bestätigung.

   ![image](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Sobald Sie den Benutzer aktiviert haben, sehen Sie die **screens-empfänger-user** as **Aktiviert** unter **Status** -Feld.

   ![image](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Wählen Sie die **screens-empfänger-user** und klicken Sie auf **Eigenschaften** in der Aktionsleiste aus.

   ![image](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Klicken Sie auf **Kennwort ändern** under **Kontoeinstellungen** von **Details** wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Geben Sie im **Kennwort ändern** und klicken Sie auf **Speichern**.

   >[!NOTE]
   >Sie sollten **admin** in **Ihr Passwort** -Feld.

   ![image](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Klicken Sie auf **Speichern und schließen**.

1. Wählen Sie die **screens-empfänger-user** und klicken Sie auf **Aktivieren** in der Aktionsleiste aus.

   ![image](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Klicken Sie auf **OK** zur Bestätigung.

   ![image](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Wählen Sie die **screens-empfänger-user** und klicken Sie auf **Deaktivieren** in der Aktionsleiste aus.

   >[!IMPORTANT]
   > Deaktivieren **screens-empfänger-user** deaktiviert nur diesen Benutzer von der Autoreninstanz und alle Benutzer in der Veröffentlichungsinstanz bleiben weiterhin aktiv. Klicken Sie nicht auf **Deaktivieren** in der Aktionsleiste aus, da durch Deaktivieren der Benutzer auch aus den Veröffentlichungsinstanzen entfernt wird.

   ![image](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Klicken Sie auf **OK** zur Bestätigung.

## Aktualisieren der Einstellungen für den Screens-Replikationsagenten {#replicate-agent}

Gehen Sie wie folgt vor, um die Einstellungen im Screens-Replikationsagenten zu aktualisieren:

1. Navigieren Sie zu Ihrer AEM-Instanz.

1. Klicken Sie auf Tools > **Implementierung** —> **Replikation**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klicken Sie auf **Agenten für Autor**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Suchen Sie nach dem Screens-Replikationsagenten auf der Autoreninstanz und klicken Sie auf den Link, wie in der folgenden Abbildung dargestellt.

   >[!NOTE]
   >Suchen Sie mit dem Brief nach dem Screens-Replikationsagenten. **S** im Namen des Autors enthalten ist.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klicken Sie auf **Bearbeiten**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Überprüfen **Aktiviert** von **Einstellungen** Registerkarte.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigieren Sie zu **Verkehr** Registerkarte aus **Agenteneinstellungen** und geben Sie dasselbe Kennwort ein, das Sie zuvor in Schritt 8 von festgelegt haben. [Aktivieren von Benutzern und Aktualisieren des Kennworts](#enable-users). Klicken Sie auf **OK**.

   ![Bild](/help/user-guide/assets/screens-replication/screens-replication1f.png)

1. Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie auf **Verbindung testen** , um die Verbindung zu überprüfen.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Wenn die Verbindungsprüfung erfolgreich war, haben Sie die Konfiguration des Screens-Replikationsagenten abgeschlossen.