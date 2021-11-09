---
title: Konfigurieren von Screens-Replikationsagenten
description: Auf dieser Seite erhalten Sie Informationen zum Konfigurieren von Screens-Replikationsagenten.
role: Developer
level: Intermediate
source-git-commit: 46b466d5d05700def4b2c290fa164fbdabae268a
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 5%

---


# Konfigurieren von Screens-Replikationsagenten {#configuring-screens-replication-agent}

Auf dieser Seite wird beschrieben, wie Sie Screens-Replikationsagenten konfigurieren.

## Ziel {#objective}

Der Screens-Replikationsagent ist für das Abrufen von Ping-Daten verantwortlich, z. B.: *Benutzer*, *password*, *rebootSchedule*, *maxNumberOfLogFilesToKeep*, und viele weitere solcher Werte von der Veröffentlichung bis zur Autoreninstanz. Dies muss unbedingt konfiguriert werden, damit der Autor den Geräte-Ping anzeigen kann.

>[!NOTE]
>Weitere Informationen zu Screens-Replikationsagenten finden Sie unter [Screens-Replikationsagenten und -Befehle](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview.html?lang=en#screens-replication-agents-and-commands).

Sie müssen beide Abschnitte ausführen, um die Konfiguration für den Screens-Replikationsagenten abzuschließen:

1. [Aktivieren von Benutzern und Aktualisieren des Kennworts](#enable-users)
1. [Aktualisieren der Einstellungen für den Screens-Replikationsagenten](#replicate-agent)

## Aktivieren von Benutzern und Aktualisieren des Kennworts {#enable-users}

Gehen Sie wie folgt vor, um Benutzer zu aktivieren und das Kennwort für screens-empfänger-user zu aktualisieren:

>[!NOTE]
>Aus Sicherheitsgründen wird empfohlen, die Verwendung des Administratorkennworts für screens-empfänger-user zu vermeiden.

1. Navigieren Sie zu Ihrer AEM-Autoreninstanz.

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
   >Sie sollten das vorhandene Administratorkennwort in **Ihr Passwort** -Feld.

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

>[!IMPORTANT]
>Sie müssen die folgenden Schritte für ALLE vorhandenen Screens-Replikationsagenten ausführen.

1. Navigieren Sie zu Ihrer AEM-Instanz.

1. Klicken Sie auf Tools > **Implementierung** —> **Replikation**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klicken Sie auf **Agenten für Autor**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Suchen Sie nach allen Screens-Replikationsagenten auf der Autoreninstanz und klicken Sie auf den Link, wie in der folgenden Abbildung dargestellt.

   >[!NOTE]
   >Suchen Sie nach allen Screens-Replikationsagenten. Der Name des Screens-Replikationsagenten enthält einen Brief **S** im Titel.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klicken Sie auf **Bearbeiten**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Überprüfen **Aktiviert** von **Einstellungen** Registerkarte.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigieren Sie zu **Verkehr** Registerkarte aus **Agenteneinstellungen** und aktualisieren Sie die **Benutzer** nach **screens-empfänger-user** und geben Sie dasselbe Kennwort ein, das Sie zuvor in Schritt (8) von [Aktivieren von Benutzern und Aktualisieren des Kennworts](#enable-users).

   ![image](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Klicken Sie auf **OK**.

1. Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie auf **Verbindung testen** , um die Verbindung zu überprüfen.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Wenn die Verbindungsprüfung erfolgreich war, haben Sie die Konfiguration des Screens-Replikationsagenten abgeschlossen.