---
cloud: Experience Cloud
product: experience manager
audience: end-user
user-guide-title: Adobe Experience Manager Screens-Hilfe
breadcrumb-title: AEM Screens-Anleitung
user-guide-description: Erfahren Sie, wie Sie mit einer Digital-Signage-Lösung dynamische und interaktive digitale Erlebnisse und Interaktionen veröffentlichen können.
feature-set: Experience Manager Screens
feature: Content
role: User
source-git-commit: 1bd79ed3a0a610efb12f9ff1030a33978ccccf1e
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---


# AEM Screens-Benutzerhandbuch {#user-guide}

+ [Einführung in Screens](aem-screens-introduction.md)
+ Übersicht und Schnellstartanleitung {#overview}
   + [Schnellstartanleitung](kickstart-for-aem-screens.md)
   + [Leitfaden zu Best Practices für Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/using/about-guide)
   + [Schlüsselbegriffe](screens-glossary.md)
+ Netzwerkgrundlagen für Digital Signage {#digital-signage-network}
   + [Teil 1: Projektrollen und Zuständigkeiten](project-roles-responsibilities.md)
   + [Teil 2: Überlegungen zum Projektumfang](project-considerations.md)
   + [Teil 3: Tests, POCs, Pilotprogramme und Rollouts](testing-pocs-pilots-rollouts.md)
   + [Teil 4: Projekt-Management und Bereitstellung](project-management-and-deployment.md)
   + [Teil 5: Überlegungen zum Support](support-considerations.md)
+ Konfiguration und Verwaltung {#administering}
   + [Konfigurieren des Screens-Servers](configuring-screens-introduction.md)
   + [Einrichten von Dispatcher-Konfigurationen](dispatcher-configurations-aem-screens.md)
   + [Installieren des Screens-Players](installing-screens-player.md)
   + [Verbinden des Screens-Players](working-with-screens-player.md)
   + [Geräteregistrierung](device-registration.md)
   + [Einrichten von ACLs](setting-up-acls.md)
   + [Sicherheitscheckliste für AEM Screens](security-checklist.md)
   + [Umstellung von ContentSync auf SmartSync](smartsync.md)
   + [Importer für neue Projekte aus einer Datei](project-importer.md)
   + [Replizieren von Daten-Triggern auf Veröffentlichungs-Servern](replicating-data-triggers.md)
   + [Konfigurieren von Replikationsagenten in Screens](configure-screens-replication.md)
   + Kundenspezifische Aspekte {#installing-client}
      + [Chrome OS-Player](implementing-chrome-os-player.md)
      + [Verwenden von Chrome-Player als Erweiterung zur Problembehebung](using-chrome-player-as-an-extension.md)
      + [Android](implementing-android-player.md)
      + [Windows-Player](implementing-windows-player.md)
      + [Tizen-Player](tizen-player.md)
      + [Cloud-Player](implementing-cloud-player.md)
      + [Automatische Registrierung von Playern](auto-registration-players.md)
      + [Verwenden der Fernbedienungs-Steuerung](implementing-remote-control.md)
   + Autoren- und Veröffentlichungsinstanz {#author-publish}
      + [Architektonischer Überblick zur Autoren- und Veröffentlichungsinstanz](author-publish-architecture-overview.md)
      + [Konfigurieren von Autoren- und Veröffentlichungsinstanz](author-and-publish.md)
   + Analytics-Integration mit AEM Screens {#analytics-integration}
      + [Adobe Analytics-Integration](adobe-analytics-integration-aem-screens.md)
      + [Konfigurieren von Adobe Analytics mit AEM Screens](configuring-adobe-analytics-aem-screens.md)
+ Authoring und Anwendungsbeispiele {#authoring}
   + Einrichten von Screens-Projekten {#setting-up-projects}
      + [Erstellen und Verwalten von Projekten](creating-a-screens-project.md)
      + [Erstellen und Verwalten von Kanälen](managing-channels.md)
      + [Erstellen und Verwalten von Anzeigen](managing-displays.md)
      + [Erstellen und Verwalten von Standorten](managing-locations.md)
      + [Erstellen und Verwalten von Zeitplänen](managing-schedules.md)
      + [Verwalten von Geräten](managing-devices.md)
      + Zuweisen von Kanälen {#assigning-channels}
         + [Kanalzuweisung](channel-assignment-latest-fp.md)
         + [Kanalzuweisung: Ältere AEM Screens Feature Packs](channel-assignment.md)
   + Verwenden der wichtigsten Produktfunktionen {#product-features}
      + [Textüberlagerung](text-overlay.md)
      + [Massen-Offline-Update](bulk-offline-update.md)
      + [AEM Screens-Benachrichtigungsdienst](screens-notifications-service.md)
      + [Verwenden von Experience Fragments](experience-fragments-in-screens.md)
      + [Aktivierung auf Asset-Ebene](asset-level-scheduling.md)
      + [Aktivierung auf Kanalebene](channel-level-activation.md)
      + [Erstellen und Verwalten einer Live Copy](managing-livecopy.md)
      + [Erstellen eines Workflows für Video-Padding](creating-a-video-padding-workflow.md)
      + [Hinzufügen von Komponenten zu Kanälen](adding-components-to-a-channel.md)
      + [Eingebettete Sequenzen](embedded-sequences.md)
      + [Mehrzonen-Layout](multi-zone-layout-aem-screens.md)
      + [Videoausgabedarstellungen](generating-renditions.md)
      + [Dynamische eingebettete Sequenz](dynamic-embedded-sequences.md)
      + [Dauer der Massenwiedergabe von Bildern auf Kanalebene](channel-level-image-playback.md)
      + [Befehlssynchronisierung](using-command-sync.md)
      + [Inhaltserstellung mit Datenauslösern](authoring-data-triggers.md)
      + [Verwenden von Tags](tagging.md)
      + [Spracherkennung](voice-recognition.md)
      + [Inhaltszuweisungsbericht](content-assignment-report.md)
      + [Unterstützung von Miniaturansichten für Videos](thumbnail-support.md)
      + [Verwenden adaptiver Ausgabedarstellungen in AEM Screens](using-adaptive-renditions.md)
   + Verwalten von Inhaltsaktualisierungen {#content-updates}
      + [On-Demand-Inhaltsaktualisierung](on-demand-content.md)
      + [Aktualisierungen von Content-as-a-Service](content-update-as-a-service.md)
      + [Inhaltsaktualisierung mit Screens Launch](launches.md)
   + Anwendungsbeispiele {#use-case-examples}
      + [Notfallkanäle](emergency-channel.md)
      + [Temperaturaktivierung für ein Reiseangebot](local-temperature-activation.md)
      + [Aktivierung der Reservierung im Gastgewerbe](hospitality-reservation-activation.md)
      + [Zielgerichtete Aktivierung des Lagerbestands im Einzelhandel](retail-inventory-activation.md)
      + [Anwenden von Übergängen](applying-transitions.md)
      + [Übergang von mehreren zu einzelnen Zonen](multizone-to-singlezone.md)
      + [Übernahmekanal für die einmalige Verwendung](single-use-takeover-channel.md)
      + [Übernahmekanal für die unbefristete Verwendung](perpetual-takeover-channel.md)
+ Entwickler- und API-Ressourcen {#developing}
   + [REST-APIs](rest-api.md)
   + [Entwickeln einer benutzerdefinierten Komponente für AEM Screens](developing-custom-component-tutorial-develop.md)
   + [Offline-Kanäle](offline-channels.md)
   + [Erweitern einer AEM Screens-Komponente](extending-component-tutorial-develop.md)
   + [Erstellen von Komponenten](creating-components.md)
   + [Einbetten einer REACT-Anwendung mit AEM SPA Editor und Integration mit AEM Screens Analytics](embedding-react-app.md)
   + [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md)
   + [Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts](creating-custom-templates-multizone-layouts.md)
   + [Anwenden von benutzerdefiniertem Branding und Styling für Textüberlagerungen](custom-branding-text-overlays.md)
   + [Adaptive Ausgabedarstellungen: Überblick über die Architektur und Konfigurationen](/help/user-guide/adaptive-renditions.md)
+ Problembehebung und häufig gestellte Fragen {#troubleshooting}
   + [Häufig gestellte Fragen zu AEM Screens](aem-screens-faqs.md)
   + [Fehlerbehebung über das Geräte-Kontrollzentrum](monitoring-screens.md)
   + [Konfiguration der Videowiedergabe](troubleshoot-videos.md)
+ Versionshinweise {#release-notes}
   + [Versionshinweise für Feature Pack 202401](release-notes-fp-202401.md)
   + [Versionshinweise für Feature Pack 20240116](release-notes-fp-20240116.md)
   + [Versionshinweise für Feature Pack 20240215](release-notes-fp-20240215.md)
   + [Versionshinweise für Feature Pack 202204](release-notes-fp-202204.md)
   + [Versionshinweise für Feature Pack 202203](release-notes-fp-202203.md)
   + [Versionshinweise für Feature Pack 202112](release-notes-fp-202112.md)
   + [Versionshinweise für Feature Pack 202109](release-notes-fp-202109.md)
   + [Versionshinweise für Feature Pack 202105](release-notes-fp-202105.md)
   + [Versionshinweise für Feature Pack 202103](release-notes-fp-202103.md)
   + [Versionshinweise für Feature Pack 202011](release-notes-fp-202011.md)
   + [Versionshinweise für Feature Pack 202008](release-notes-fp-202008.md)
   + [Versionshinweise für Feature Pack 202004](release-notes-fp-202004.md)
   + [Versionshinweise für Feature Pack 202001](release-notes-fp-202001.md)
   + [Versionshinweise für Feature Pack 201909](release-notes-fp-201909.md)
   + [Versionshinweise für Feature Pack 201907](release-notes-fp-201907.md)
   + [Versionshinweise für Feature Pack 201905](screens-release-notes-fp-201905.md)
   + [Versionshinweise für Feature Pack 201812](release-notes-fp-201812.md)
   + [Versionshinweise für Feature Pack 201809](screens-release-notes.md)
