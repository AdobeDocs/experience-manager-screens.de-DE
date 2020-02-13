---
title: Replizieren von Datenauslösern in Veröffentlichungsserver
seo-title: Replizieren von Datenauslösern zum Veröffentlichungsserver
description: Replizieren Sie Datenauslöser auf den Veröffentlichungsserver.
seo-description: Replizieren Sie Datenauslöser auf den Veröffentlichungsserver.
translation-type: tm+mt
source-git-commit: a8ded0c15e0e3cbaf0999da796789991b20d24cb

---


# Replizieren von Datenauslösern auf den Veröffentlichungsserver {#replicating-data-triggers}

Wenn Sie ContextHub und die AEM-Targeting-Engine verwenden, um Inhalte basierend auf Datenauslösern in einem Autor-/Veröffentlichungssetup anzupassen, werden alle ContextHub- und Personalisierungsbezogenen Konfigurationen nicht automatisch mit den Kanälen repliziert, wenn sie veröffentlicht werden.

Folgen Sie dieser Seite, um die Schritte für die Handbücher zu erfahren, die erforderlich sind, um diese Konfigurationen separat zu veröffentlichen.

Das liegt im Wesentlichen in der manuellen Veröffentlichung:

1. Konfigurationen der ContextHub Store- und UI-Module
1. Personalisierungszielgruppen
1. Personalisierungstätigkeiten

## Schritte zum Replizieren von Datenauslösern auf den Publish-Server {#replicating-data-triggers-publish}

Gehen Sie wie folgt vor, um die Datenauslöser auf den Veröffentlichungsserver zu replizieren:

### Replizieren von ContextHub-Konfigurationen {#replicating-contexthub-configurations}

1. Navigieren Sie zu **Werkzeuge** > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent** http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish
1. Klicken Sie auf die Schaltfläche Verbindung testen, um zu überprüfen, ob der Autor ordnungsgemäß mit der Veröffentlichungsinstanz kommunizieren kann.
1. Wenn der Test fehlschlägt, müssen Sie die Replizierungsagenten-Konfiguration zwischen Autor und Veröffentlichung beheben
1. Vergewissern Sie sich, dass die Endpunkt-URL auch auf die URL des Veröffentlichungsservers im Distributionsagenten verweist
1. Bearbeiten > Importer-Endpunkte
1. Klicken Sie auf die Registerkarte Verteilen
1. Optionsfeld &quot;Struktur hinzufügen&quot;
1. Wählen Sie im Pfadbrowser den Konfigurationspfad für Ihr Projekt aus (d.h. /conf/screens/settings/cloudsettings/configuration)
1. Klicken Sie auf Übermitteln

### Replizieren der Zielgruppen {#replicating-audiences}

1. Navigieren Sie zu Tools > Personalisierung > Zielgruppenhttp://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html
1. Führen Sie einen Drilldown in Ihren Projektordner durch (d.h. /conf/screens/)
1. Auswählen aller Zielgruppen/Segmente in der Benutzeroberfläche
1. Klicken Sie auf Veröffentlichung verwalten
1. Klicken Sie auf Weiter
1. Klicken Sie auf Veröffentlichen

### Replizieren der Aktivitäten {#replicating-activities}

1. Navigieren Sie zu Tools > Personalisierung > Aktivitätenhttp://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html
1. Führen Sie einen Drilldown in Ihren Projektordner durch (d.h. /content/campaigns/screens/...)
1. Wählen Sie alle Aktivitäten in der Benutzeroberfläche
1. Klicken Sie auf Veröffentlichung verwalten
1. Klicken Sie auf Weiter
1. Klicken Sie auf Veröffentlichen

> [!Note]
>Die Replizierung von ContextHub-Konfigurationen und -Zielgruppen erfolgt während der Projekteinrichtung, während Aktivitäten repliziert werden. Dies ist bei jeder Änderung des Targeting innerhalb eines Kanals erforderlich.

#### Ergebnis {#result}

Wenn die Replikation erfolgreich ist, sollten Sie die folgende Struktur in der Veröffentlichungsinstanz (oder ähnlich für Ihr Projekt) anzeigen:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`