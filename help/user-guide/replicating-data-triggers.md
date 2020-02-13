---
title: Replizieren von Datenauslösern in Veröffentlichungsserver
seo-title: Replizieren von Datenauslösern zum Veröffentlichungsserver
description: Replizieren Sie Datenauslöser auf den Veröffentlichungsserver.
seo-description: Replizieren Sie Datenauslöser auf den Veröffentlichungsserver.
translation-type: tm+mt
source-git-commit: 47e0204ea734a1348385ddd3c7108038c88d1933

---


# Replizieren von Datenauslösern auf den Veröffentlichungsserver {#replicating-data-triggers}

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
   >Alternativ können Sie über den [Link](http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish) direkt zum Bildschirm navigieren, um die Verbindung zu konfigurieren und zu testen.

1. Klicken Sie in der Aktionsleiste auf **Verbindung** testen, um die Kommunikation des Autors mit der Veröffentlichungsinstanz zu überprüfen, wie in der folgenden Abbildung dargestellt.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!Note]
   >Wenn der Test fehlschlägt, müssen Sie die Konfiguration des Replizierungsagenten zwischen der Autoreninstanz und der Veröffentlichungsinstanz beheben. Weitere Informationen finden Sie unter [Fehlerbehebung bei Test Connection](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) .

1. Klicken Sie oben im Bildschirm auf **Bearbeiten** und stellen Sie sicher, dass die Endpunkt-URL im Feld **Importer-Endpunkte** auch auf die URL des Servers im Distributionsagent verweist.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers3.png)

1. Wählen Sie **Hinzufügen** aus der **Verteilungsagenten** -Bildschirmstruktur und wählen Sie den Konfigurationspfad für Ihr Projekt, das heißt, `/conf/screens/settings/cloudsettings/configuration)`.

1. Klicken Sie auf **Übermitteln**

### Replizieren der Zielgruppen {#replicating-audiences}

1. Navigieren Sie zu **Tools** > **Personalisierung** > **Zielgruppen** oder verwenden Sie den [Link](http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html) , um direkt zu navigieren.

1. Führen Sie einen Drilldown in Ihren Projektordner durch, das heißt, `/conf/screens/`Sie können

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers5.png)

1. Wählen Sie alle Zielgruppen und Segmente in der Benutzeroberfläche aus.

1. Klicken Sie in der Aktionsleiste auf Veröffentlichung **verwalten** .

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

### Replizieren der Aktivitäten {#replicating-activities}

1. Navigieren Sie zu **Tools** > **Personalisierung** > **Aktivitäten** oder verwenden Sie den [Link](http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html) , um direkt zu navigieren.

1. Führen Sie einen Drilldown in Ihren Projektordner durch, das heißt, `/content/campaigns/screens/…`Sie können

1. Wählen Sie alle Aktivitäten in der Benutzeroberfläche aus.

1. Klicken Sie in der Aktionsleiste auf Veröffentlichung **verwalten** .

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

   > [!Note]
   >Die Replizierung von ContextHub-Konfigurationen und -Zielgruppen erfolgt während der Projekteinrichtung, während Aktivitäten repliziert werden. Dies ist bei jeder Änderung des Targeting innerhalb eines Kanals erforderlich.

#### Ergebnis {#result}

Wenn die Replikation erfolgreich ist, sollten Sie die folgende Struktur in der Veröffentlichungsinstanz (oder ähnlich für Ihr Projekt) anzeigen:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Fehlerbehebung bei Testverbindung {#troubleshoot-test}

Wenn die Testverbindung beim Replizieren der ContextHub-Konfigurationen fehlschlägt, befolgen Sie den folgenden Abschnitt zur Fehlerbehebung:

1. Navigieren Sie zum Feld &quot; **Importer-Endpunkte** &quot;und stellen Sie sicher, dass die Endpunkt-URL auf die URL des Veröffentlichungsservers im Distribution Agent verweist.

1. Wenn Sie nicht die Standardanmeldeinformationen verwenden, müssen Sie den Verteilungsagenten mit einem anderen Administratorkennwort konfigurieren.
Führen Sie dazu folgende Schritte durch:

   1. Navigieren Sie zu &quot;Extras&quot;> &quot; **Vorgänge** &quot;> &quot;Web-Konsole&quot;**, `http://localhost:4502/system/console/configMgr`um den **Adobe Experience Manager Web-Konsolenbildschirm** zu öffnen.

   1. Search for **Apache Sling Distribution Transport Credentials - User Credentials based DistributionTransportSecretProvider**

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Erstellen Sie eine Konfiguration, indem Sie **Name**, **Benutzername** und **Kennwort** füllen, z. B. *slingTransportSecretProvider*. .
   1. Klicken Sie auf **Speichern**.

   1. Suchen Sie nach dem Namen Ihres Verteilungsagenten, der `Cmd +F`.

   1. Klicken Sie auf , um den Verteilungsagenten osgi config zu öffnen.

   1. Suchen Sie nach Transport Secret Provider in osgi config und aktualisieren Sie es mit `"(name=slingTransportSecretProvider)"`.

   1. Klicken Sie auf **Speichern** und führen Sie die Testverbindung aus.

