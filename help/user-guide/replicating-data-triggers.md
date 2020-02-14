---
title: Replizieren von Datenauslösern in Veröffentlichungsserver
seo-title: Replizieren von Datenauslösern zum Veröffentlichungsserver
description: Replizieren Sie Datenauslöser auf den Veröffentlichungsserver.
seo-description: Replizieren Sie Datenauslöser auf den Veröffentlichungsserver.
translation-type: tm+mt
source-git-commit: 4e86ed7c3050209b3baa67087fc149afae8340b6

---


# Replizieren von Datenauslösern auf Veröffentlichungsserver {#replicating-data-triggers}

Wenn Sie ContextHub und die AEM-Targeting-Engine verwenden, um Inhalte basierend auf Datenauslösern in einem Autor-/Veröffentlichungssetup anzupassen, werden alle ContextHub- und Personalisierungsbezogenen Konfigurationen nicht automatisch mit den Kanälen repliziert, wenn sie veröffentlicht werden.

Folgen Sie dieser Seite, um die Schritte für die Handbücher zu erfahren, die erforderlich sind, um diese Konfigurationen separat zu veröffentlichen.

Das liegt im Wesentlichen in der manuellen Veröffentlichung:

1. Konfigurationen der ContextHub Store- und UI-Module
1. Personalisierungszielgruppen
1. Personalisierungstätigkeiten

## Schritte zum Replizieren von Datenauslösern auf den Publish-Server {#replicating-data-triggers-publish}

Gehen Sie wie folgt vor, um die Datenauslöser auf den Veröffentlichungsserver zu replizieren.

### Schritt 1:Replizieren von ContextHub-Konfigurationen {#replicating-contexthub-configurations}

1. Navigieren Sie zu **Werkzeuge** > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent** und klicken Sie auf den Veröffentlichungsagenten, um Ihre Einstellungen zu konfigurieren.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!Note]
   >Alternativ dazu können Sie mit der `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` Methode direkt zum Bildschirm navigieren, um die Verbindung zu konfigurieren und zu testen.

1. Klicken Sie in der Aktionsleiste auf **Verbindung** testen, um die Kommunikation des Autors mit der Veröffentlichungsinstanz zu überprüfen, wie in der folgenden Abbildung dargestellt.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!Note]
   >Wenn der Test fehlschlägt, müssen Sie die Konfiguration des Replizierungsagenten zwischen der Autoreninstanz und der Veröffentlichungsinstanz beheben. Weitere Informationen finden Sie unter [Fehlerbehebung bei Test Connection](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) .

1. Wählen Sie **Hinzufügen** aus der **Verteilungsagenten** -Bildschirmstruktur und wählen Sie den Konfigurationspfad für Ihr Projekt aus, z. B. `/conf/screens/settings/cloudsettings/configuration`.

1. Klicken Sie auf **Übermitteln**

### Replizieren der Zielgruppen {#replicating-audiences}

1. Navigieren Sie zu Ihrer AEM-Instanz > **Personalisierung** > **Zielgruppen** oder verwenden Sie `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` die direkte Navigation.

1. Führen Sie einen Drilldown in Ihren Projektordner aus, z. B. `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Wählen Sie alle Zielgruppen und Segmente in der Benutzeroberfläche aus.

1. Klicken Sie in der Aktionsleiste auf Veröffentlichung **verwalten** .

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

### Replizieren der Aktivitäten {#replicating-activities}

1. Navigieren Sie zu Ihrer AEM-Instanz > **Personalisierung** > **Aktivitäten** oder verwenden Sie `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` die direkte Navigation.

1. Führen Sie einen Drilldown in Ihren Projektordner durch, das heißt, `/content/campaigns/screens/…`Sie können

1. Wählen Sie alle Aktivitäten in der Benutzeroberfläche aus.

1. Klicken Sie in der Aktionsleiste auf Veröffentlichung **verwalten** .

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

> [!Note]
> **Wichtig **:>Die Replizierung von ContextHub-Konfigurationen und -Zielgruppen erfolgt während der Projekteinrichtung, während Aktivitäten repliziert werden. Dies ist bei jeder Änderung des Targeting innerhalb eines Kanals erforderlich.

#### Ergebnis {#result}

Wenn die Replikation erfolgreich ist, sollten Sie die folgende Struktur in der Veröffentlichungsinstanz (oder ähnlich für Ihr Projekt) anzeigen:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Fehlerbehebung bei Testverbindung {#troubleshoot-test}

Wenn die Testverbindung beim Replizieren der ContextHub-Konfigurationen fehlschlägt, befolgen Sie den folgenden Abschnitt zur Fehlerbehebung:

1. Navigieren Sie zu Werkzeuge > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent**.

1. Klicken Sie in der Aktionsleiste auf &quot; **Bearbeiten** &quot;und stellen Sie sicher, dass die Endpunkt-URL im Feld &quot; **Importer-Endpunkte** &quot;auch auf die URL des Servers im Distributionsagent verweist.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Wenn Sie nicht die standardmäßigen Administratorberechtigungen verwenden, müssen Sie den Verteilungsagenten mit einem anderen Benutzernamen und einem anderen Kennwort konfigurieren.
Führen Sie dazu folgende Schritte durch:

   1. Navigieren Sie zu Tools > **Vorgänge** > **Web-Konsole** , `http://localhost:4502/system/console/configMgr`um den Bildschirm **&quot;** Adobe Experience Manager Web-Konsole&quot;zu öffnen.

   1. Search for **Apache Sling Distribution Transport Credentials - User Credentials based DistributionTransportSecretProvider**

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Erstellen Sie eine Konfiguration, indem Sie **Name**, **Benutzername** und **Kennwort** füllen, z. B. *slingTransportSecretProvider*.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Klicken Sie auf **Speichern**.

   1. Verwenden Sie `Cmd +F` die Suche nach **Apache Sling Distribution Agent - Forward Agents Factory** , um die Konfigurationen zu öffnen und nach **Transport Secret Provider** zu suchen.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Aktualisieren Sie den `(name=default)` mit `(name=slingTransportSecretProvider)`.

   1. Klicken Sie auf **Speichern** und führen Sie die Testverbindung erneut über den Bildschirm **Distribution Agent** aus Ihrer AEM-Instanz aus.
