---
title: Replizieren von Daten-Triggern auf Veröffentlichungs-Servern
description: Erfahren Sie, wie Sie Daten-Trigger auf dem Publishing-Server für AEM Screens replizieren.
feature: Administering Screens, Data Trigger
role: Developer
level: Intermediate
exl-id: 6f90b864-eaa0-4b74-a47e-b0967a550552
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 37%

---

# Replizieren von Datenauslösern auf Veröffentlichungs-Servern {#replicating-data-triggers}

Wenn Sie ContextHub und die AEM-Targeting-Engine verwenden, um Content basierend auf Datenauslösern in einem Autor-/Veröffentlichungsinstanz anzupassen, werden die ContextHub- und Personalisierung-bezogenen Konfigurationen nicht automatisch in den Kanälen repliziert, wenn sie veröffentlicht werden.

Auf dieser Seite erfahren Sie mehr über die manuellen Schritte, die erforderlich sind, um diese Konfigurationen separat zu veröffentlichen.

Dies betrifft im Wesentlichen die manuelle Veröffentlichung:

1. Konfigurationen der ContextHub-Store- und UI-Module
1. Personalisierungszielgruppen
1. Personalisierungsaktivitäten

## Schritte zum Replizieren von Daten-Triggern auf den Veröffentlichungs-Server {#replicating-data-triggers-publish}

Gehen Sie wie folgt vor, um die Datenauslöser auf den Veröffentlichungs-Server zu replizieren.

### Schritt 1: Replikation von ContextHub-Konfigurationen {#replicating-contexthub-configurations}

1. Navigieren Sie zu **Instrumente** > **Implementierung** > **Distribution** > **Veröffentlichungsagent** und wählen Sie den Veröffentlichungsagenten aus, damit Sie Ihre Einstellungen konfigurieren können.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!NOTE]
   >
   >Alternativ können Sie mit `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` direkt zum Bildschirm navigieren, um die Verbindung zu konfigurieren und zu testen.

1. Auswählen **Verbindung testen** in der Aktionsleiste, damit Sie die Kommunikation des Autors mit der Veröffentlichungsinstanz überprüfen können, wie im Folgenden gezeigt:

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!NOTE]
   >
   >Wenn der Test fehlschlägt, beheben Sie die Konfiguration des Replikationsagenten zwischen der Autoren- und der Veröffentlichungsinstanz. Siehe [Fehlerbehebung bei der Testverbindung](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) für weitere Details.

1. Wählen Sie in der Struktur des Bildschirms **Verteilungsagent** die Option **Hinzufügen** aus und wählen Sie den Konfigurationspfad für Ihr Projekt aus, z. B. `/conf/screens/settings/cloudsettings/configuration`.

1. Wählen Sie **Absenden**.

### Replizieren der Zielgruppen {#replicating-audiences}

1. Navigieren Sie zu Ihrer AEM > **Personalisierung** > **Zielgruppen** oder Verwendung `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` um direkt zu navigieren.

1. Führen Sie einen Drilldown in Ihren Projektordner aus, z. B. `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Wählen Sie in der Benutzeroberfläche alle Zielgruppen und Segmente aus.

1. Auswählen **Veröffentlichung verwalten** in der Aktionsleiste aus.

1. Auswählen **Nächste** und **Veröffentlichen**.

### Replizieren der Aktivitäten  {#replicating-activities}

1. Navigieren Sie zu Ihrer AEM > **Personalisierung** > **Tätigkeiten** oder Verwendung `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` um direkt zu navigieren.

1. Führen Sie einen Drilldown in Ihren Projektordner durch, also `/content/campaigns/screens/…`.

1. Wählen Sie alle Aktivitäten in der Benutzeroberfläche aus.

1. Auswählen **Veröffentlichung verwalten** in der Aktionsleiste aus.

1. Auswählen **Nächste** und **Veröffentlichen**.

>[!IMPORTANT]
>
>Die Replizierung von ContextHub-Konfigurationen und -Zielgruppen erfolgt während der Projekteinrichtung bei der Replikation von Aktivitäten und ist jedes Mal erforderlich, wenn das Targeting innerhalb eines Kanals geändert wird.

#### Ergebnis {#result}

Wenn die Replikation erfolgreich ist, sollten Sie die folgende Struktur in der Veröffentlichungsinstanz (bzw. der Entsprechung in Ihrem Projekt) sehen:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Fehlerbehebung bei der Testverbindung {#troubleshoot-test}

Wenn die Testverbindung beim Replizieren der ContextHub-Konfigurationen fehlschlägt, gehen Sie zur Fehlerbehebung wie im Abschnitt unten beschrieben vor:

1. Navigieren Sie zu Werkzeuge > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent**.

1. Auswählen **Bearbeiten** in der Aktionsleiste aus und stellen Sie sicher, dass die Endpunkt-URL in **Importer Endpoints** -Feld verweist auch auf die URL des Veröffentlichungsservers im Verteilungsagenten.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Wenn Sie nicht die standardmäßigen Administratorberechtigungen verwenden, müssen Sie den Verteilungsagenten mit einem anderen Benutzernamen und Kennwort konfigurieren.

   Führen Sie dazu folgende Schritte durch:

   1. Navigieren Sie zu Tools > **Aktivitäten** > **Web-Konsole** `http://localhost:4502/system/console/configMgr`Sie können die **Bildschirm &quot;Adobe Experience Manager Web Console&quot;**.
   1. Suchen Sie nach **Apache Sling Distribution Transport Credentials – User Credentials based DistributionTransportSecretProvider**.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Erstellen Sie eine Konfiguration, indem Sie **Name**, **Benutzername**, und **password**, beispielsweise *slingTransportSecretProvider*.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Wählen Sie **Speichern** aus
   1. Verwendung `Cmd +F` zum Suchen nach **Apache Sling Distribution Agent - Forward Agents Factory** , um die Konfigurationen zu öffnen und nach **Transport Secret Provider**.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Aktualisieren Sie `(name=default)` mit `(name=slingTransportSecretProvider)`.
   1. Auswählen **Speichern** und führen Sie die Testverbindung über die **Verteilungsagent** von Ihrer AEM-Instanz erneut angezeigt.
