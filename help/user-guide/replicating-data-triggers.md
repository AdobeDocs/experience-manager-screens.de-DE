---
title: Replizieren von Datenauslösern auf Veröffentlichungsservern
seo-title: Replizieren von Datenauslösern auf Veröffentlichungsserver
description: Replizieren von Datenauslösern auf Veröffentlichungsserver.
seo-description: Replizieren von Datenauslösern auf Veröffentlichungsserver.
translation-type: tm+mt
source-git-commit: 081db31efda17ac12cdc88f79ed2f4e1fbfc7edf
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 100%

---


# Replizieren von Datenauslösern auf Veröffentlichungsservern {#replicating-data-triggers}

Wenn Sie ContextHub und die AEM-Targeting-Engine verwenden, um Content basierend auf Datenauslösern in einem Autor-/Veröffentlichungsinstanz anzupassen, werden die ContextHub- und Personalisierung-bezogenen Konfigurationen nicht automatisch in den Kanälen repliziert, wenn sie veröffentlicht werden.

Auf dieser Seite lernen Sie die manuellen Schritte kennen, die erforderlich sind, um diese Konfigurationen separat zu veröffentlichen.

Das läuft im Wesentlichen auf das manuelle Veröffentlichen folgender Elemente hinaus:

1. Konfigurationen der ContextHub-Store- und UI-Module
1. Personalisierungszielgruppen
1. Personalisierungsaktivitäten

## Schritte zum Replizieren von Datenauslösern auf den Veröffentlichungsserver {#replicating-data-triggers-publish}

Gehen Sie wie folgt vor, um die Datenauslöser auf den Veröffentlichungsserver zu replizieren.

### Schritt 1: Replizieren von ContextHub-Konfigurationen {#replicating-contexthub-configurations}

1. Navigieren Sie zu **Werkzeuge** > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent** und klicken Sie auf den Veröffentlichungsagenten, um Ihre Einstellungen zu konfigurieren.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!NOTE]
   >
   >Alternativ können Sie mit `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` direkt zum Bildschirm navigieren, um die Verbindung zu konfigurieren und zu testen.

1. Klicken Sie in der Aktionsleiste auf **Verbindung testen**, um die Kommunikation des Autors mit der Veröffentlichungsinstanz zu überprüfen, wie in der folgenden Abbildung dargestellt.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!NOTE]
   >
   >Wenn der Test fehlschlägt, müssen Sie die Konfiguration des Replikationsagenten zwischen der Autoreninstanz und der Veröffentlichungsinstanz korrigieren. Weitere Informationen finden Sie unter [Fehlerbehebung bei der Testverbindung](/help/user-guide/replicating-data-triggers.md#troubleshoot-test).

1. Wählen Sie in der Struktur des Bildschirms **Verteilungsagent** die Option **Hinzufügen** aus und wählen Sie den Konfigurationspfad für Ihr Projekt aus, z. B. `/conf/screens/settings/cloudsettings/configuration`.

1. Klicken Sie auf **Übermitteln**.

### Replizieren der Zielgruppen {#replicating-audiences}

1. Navigieren Sie zu Ihrer AEM-Instanz > **Personalisierung** > **Zielgruppen** oder verwenden Sie `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` zum direkten Navigieren.

1. Führen Sie einen Drilldown in Ihren Projektordner aus, z. B. `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Wählen Sie in der Benutzeroberfläche alle Zielgruppen und Segmente aus.

1. Klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**.

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

### Replizieren der Aktivitäten {#replicating-activities}

1. Navigieren Sie zu Ihrer AEM-Instanz > **Personalisierung** > **Aktivitäten** oder verwenden Sie `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` zum direkten Navigieren.

1. Führen Sie einen Drilldown in Ihren Projektordner durch, also `/content/campaigns/screens/…`.

1. Wählen Sie alle Aktivitäten in der Benutzeroberfläche aus.

1. Klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**.

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

>[!IMPORTANT]
>
>Die Replizierung von ContextHub-Konfigurationen und -Zielgruppen erfolgt im Zuge der Projekteinrichtung, während Aktivitäten repliziert werden. Dies ist bei jeder Änderung des Targeting innerhalb eines Kanals erforderlich.

#### Ergebnis {#result}

Wenn die Replikation erfolgreich ist, sollten Sie die folgende Struktur in der Veröffentlichungsinstanz (bzw. der Entsprechung in Ihrem Projekt) sehen:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Fehlerbehebung bei der Testverbindung {#troubleshoot-test}

Wenn die Testverbindung beim Replizieren der ContextHub-Konfigurationen fehlschlägt, gehen Sie zur Fehlerbehebung wie im Abschnitt unten beschrieben vor:

1. Navigieren Sie zu Werkzeuge > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten** und stellen Sie sicher, dass die Endpunkt-URL im Feld **Importer Endpoints** auch auf die URL des Veröffentlichungsservers im Verteilungsagenten verweist.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Wenn Sie nicht die standardmäßigen Administratorberechtigungen verwenden, müssen Sie den Verteilungsagenten mit einem anderen Benutzernamen und einem anderen Kennwort konfigurieren.

   Führen Sie dazu folgende Schritte durch:

   1. Navigieren Sie zu Werkzeuge > **Vorgänge** > **Web-Konsole** `http://localhost:4502/system/console/configMgr` zum Öffnen des Bildschirms **Adobe Experience Manager Web Console**.
   1. Suchen Sie nach **Apache Sling Distribution Transport Credentials – User Credentials based DistributionTransportSecretProvider**.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Erstellen Sie eine Konfiguration, indem Sie **Name**, **Benutzername** und **Kennwort** ausfüllen, z. B. *slingTransportSecretProvider*.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Klicken Sie auf **Speichern**.
   1. Verwenden Sie `Cmd +F` zum Suchen nach **Apache Sling Distribution Agent - Forward Agents Factory**, um die Konfigurationen zu öffnen und nach **Transport Secret Provider** zu suchen.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Aktualisieren Sie `(name=default)` mit `(name=slingTransportSecretProvider)`.
   1. Klicken Sie auf **Speichern** und führen Sie die Testverbindung über den Bildschirm **Verteilungsagent** noch einmal aus Ihrer AEM-Instanz aus.
