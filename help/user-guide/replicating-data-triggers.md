---
title: Replizieren von Daten-Triggern auf Veröffentlichungs-Servern
description: Erfahren Sie, wie Sie Daten-Trigger auf dem Veröffentlichungs-Server für AEM Screens replizieren.
feature: Administering Screens, Data Trigger
role: Developer
level: Intermediate
exl-id: 6f90b864-eaa0-4b74-a47e-b0967a550552
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 100%

---

# Replizieren von Daten-Triggern auf Veröffentlichungs-Servern {#replicating-data-triggers}

Wenn Sie ContextHub und die AEM-Targeting-Engine verwenden, um Inhalte basierend auf Daten-Triggern in einer Autoren-/Veröffentlichungsinstanz anzupassen, werden die ContextHub- und personalisierungsbezogenen Konfigurationen im Falle einer Veröffentlichung nicht automatisch mit den Kanälen repliziert.

Auf dieser Seite lernen Sie die manuellen Schritte kennen, die erforderlich sind, um diese Konfigurationen separat zu veröffentlichen.

Dieser Vorgang läuft im Grunde auf das manuelle Veröffentlichen folgender Elemente hinaus:

1. Konfigurationen der ContextHub-Store- und UI-Module
1. Personalisierungszielgruppen
1. Personalisierungsaktivitäten

## Schritte zum Replizieren von Daten-Triggern auf Veröffentlichungs-Servern {#replicating-data-triggers-publish}

Gehen Sie wie folgt vor, um die Datenauslöser auf den Veröffentlichungs-Server zu replizieren.

### Schritt 1: Replizieren von ContextHub-Konfigurationen {#replicating-contexthub-configurations}

1. Navigieren Sie zu **Tools** > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent** und klicken Sie auf den Veröffentlichungsagenten, um Ihre Einstellungen zu konfigurieren.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!NOTE]
   >
   >Alternativ können Sie mit `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` direkt zum Bildschirm navigieren, um die Verbindung zu konfigurieren und zu testen.

1. Klicken Sie in der Aktionsleiste auf **Verbindung testen**, um die Kommunikation der Autoren- mit der Veröffentlichungsinstanz zu überprüfen, wie im Folgenden gezeigt:

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!NOTE]
   >
   >Wenn der Test fehlschlägt, korrigieren Sie die Konfiguration des Replikationsagenten zwischen der Autoreninstanz und der Veröffentlichungsinstanz. Weitere Informationen finden Sie unter [Fehlerbehebung bei der Testverbindung](/help/user-guide/replicating-data-triggers.md#troubleshoot-test).

1. Klicken Sie in der Struktur des Bildschirms **Verteilungsagent** auf **Hinzufügen** und klicken Sie auf den Konfigurationspfad für Ihr Projekt, zum Beispiel `/conf/screens/settings/cloudsettings/configuration`.

1. Klicken Sie auf **Absenden**.

### Replizieren der Zielgruppen {#replicating-audiences}

1. Navigieren Sie zu Ihrer AEM-Instanz > **Personalisierung** > **Zielgruppen** oder gehen Sie mit `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` direkt dorthin.

1. Führen Sie einen Drilldown in Ihren Projektordner aus, z. B. `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Klicken Sie in der Benutzeroberfläche auf alle Zielgruppen und Segmente.

1. Klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**.

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

### Replizieren der Aktivitäten {#replicating-activities}

1. Navigieren Sie zu Ihrer AEM-Instanz > **Personalisierung** > **Aktivitäten** oder gehen Sie mit `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` direkt dorthin.

1. Führen Sie einen Drilldown in Ihren Projektordner durch, also `/content/campaigns/screens/…`.

1. Klicken Sie in der Benutzeroberfläche auf alle Aktivitäten.

1. Klicken Sie in der Aktionsleiste auf **Veröffentlichung verwalten**.

1. Klicken Sie auf **Weiter** und **Veröffentlichen**.

>[!IMPORTANT]
>
>Die Replizierung von ContextHub-Konfigurationen und -Zielgruppen erfolgt im Zuge der Projekteinrichtung, während Aktivitäten repliziert werden. Dies ist bei jeder Targeting-Änderung innerhalb eines Kanals erforderlich.

#### Ergebnis {#result}

Wenn die Replikation erfolgreich ist, sollten Sie die folgende Struktur in der Veröffentlichungsinstanz (bzw. deren Entsprechung in Ihrem Projekt) sehen:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Fehlerbehebung bei der Testverbindung {#troubleshoot-test}

Wenn die Testverbindung beim Replizieren der ContextHub-Konfigurationen fehlschlägt, gehen Sie zur Fehlerbehebung so vor, wie im Abschnitt unten beschrieben:

1. Navigieren Sie zu **Tools** > **Bereitstellung** > **Verteilung** > **Veröffentlichungsagent**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten** und stellen Sie sicher, dass die Endpunkt-URL im Feld **Endpunkte des Importtools** auch auf die URL des Veröffentlichungs-Servers im Verteilungsagenten verweist.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Wenn Sie nicht die standardmäßigen Admin-Anmeldedaten verwenden, müssen Sie den Verteilungsagenten mit einem anderen Benutzernamen und einem anderen Kennwort konfigurieren.

   Führen Sie dazu folgende Schritte durch:

   1. Navigieren Sie zu „Tools“ > **Vorgänge** > **Web-Konsole** `http://localhost:4502/system/console/configMgr`, um den Bildschirm für die **Adobe Experience Manager-Web-Konsole** zu öffnen.
   1. Suchen Sie nach **`Apache Sling Distribution Transport Credentials - User Credentials based DistributionTransportSecretProvider`**.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Erstellen Sie eine Konfiguration, indem Sie einen **Namen** (z. B. *slingTransportSecretProvider*), einen **Benutzernamen** und ein **Kennwort** angeben.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Klicken Sie auf **Speichern**.
   1. Verwenden Sie `Cmd +F` zum Suchen nach **Apache Sling Distribution Agent - Forward Agents Factory**, um die Konfiguration zu öffnen. Gehen Sie dann zum Feld **Transport Secret Provider** (Secret-Provider für Transport).

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Aktualisieren Sie `(name=default)` mit `(name=slingTransportSecretProvider)`.
   1. Klicken Sie auf **Speichern** und führen Sie die Testverbindung über den Bildschirm **Verteilungsagent** noch einmal aus Ihrer AEM-Instanz aus.
