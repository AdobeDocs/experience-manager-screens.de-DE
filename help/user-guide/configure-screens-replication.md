---
title: Konfigurieren des Screens-Replikationsagenten
description: Auf dieser Seite erhalten Sie Informationen zum Konfigurieren des Screens-Replikationsagenten.
role: Developer
level: Intermediate
source-git-commit: 9f0beddf87d9f5473fdedc292d3c24e96b85cdd4
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---


# Konfigurieren des Screens-Replikationsagenten {#configuring-screens-replication-agent}

In diesem Abschnitt wird die Konfiguration des Screens-Replikationsagenten beschrieben.

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

## Aktualisieren des Screens-Replikationsagenten {#replicate-agent}

Gehen Sie wie folgt vor, um die Einstellungen im Screens-Replikationsagenten zu aktualisieren:

1. Navigieren Sie zu Ihrer AEM-Instanz.

1. Klicken Sie auf Tools > **Implementierung** —> **Replikation**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1a.png)
