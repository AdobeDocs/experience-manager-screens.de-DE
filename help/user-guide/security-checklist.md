---
title: Sicherheitscheckliste
seo-title: Sicherheitscheckliste
description: Die Seite beschreibt die Sicherheitscheckliste
seo-description: Die Seite beschreibt die Sicherheitscheckliste
translation-type: tm+mt
source-git-commit: aade9071cebddf147dfad51d7319fb6f0e1c22bf
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 2%

---


# Checkliste für die Sicherheit von AEM Screens  {#security-checklist}

Auf der Seite &quot;AEM Screens Security Checklist&quot;werden die wichtigsten Sicherheitsbereiche mit einer Checkliste mit Fragen und Überlegungen beschrieben.

## Checkliste {#checklist-table}

| **Sicherheitsbereich** | **Checkliste** | **Ja/Nein/NA** |
|---|---|---|
| **Updates der AEM- und Screensoftware** | ***a.*** *Wurde das neueste Adobe Experience Manager (AEM) Service Pack angewendet?* <br>***b.****Wird das neueste AEM Screens Feature Pack angewendet?*<br>***c.*** *Verwenden Sie die neueste verfügbare AEM Screens Player-Software aus den[AEM Screens Player-Downloads](https://download.macromedia.com/screens/)?* |
| **Physische Sicherheit** | ***a.*** *Haben Sie alle unnötigen Anschlüsse deaktiviert?* <br>***b.****Haben Sie Kabel und Hardware gesichert?*<br>***c.*** *Verwenden Sie ggf. Container?* |
| **Netzwerksicherheit** | ***a.*** *Verwenden Sie ein isoliertes Subnetz für Ihre Signaturgeräte?* <br>***b.****Ermöglicht das isolierte Subnetz Zugriff auf die erforderlichen Endpunkte, einschließlich AEM, Adobe Analytics oder anderen erforderlichen Diensten?*<br>***c.*** *Haben Sie Ihr Wi-Fi mithilfe der Best Practices des Unternehmens gesichert?* <br>***d.****Wenn Sie die synchronisierte Wiedergabe verwenden, ist TCP 24503 für WebSocket nur auf dem/den Master-Geräten zulässig?*<br>***e.*** *Haben Sie die IP-Bereiche der Player-Geräte auf die Positivliste gesetzt, damit nur autorisierte Geräte auf den Registrierungsdienst zugreifen können?* |
| **Betriebssystemsicherheit** | ***a.*** *Haben Sie auf die neueste Version des Betriebssystems aktualisiert und alle erforderlichen Sicherheits-Patches angewendet?* <br>***b.****Haben Sie alle unnötigen Dienste deaktiviert und unnötige Anwendungen entfernt?*<br>***c.*** *Haben Sie das Gerät in die Geräteverwaltung eingeschrieben, um Unternehmensrichtlinien durchzusetzen?* <br>***d.****Haben Sie das Gerät auf einen einzelnen Anwendungskiosk (Player) gesperrt?*<br>***e.*** *Verfügen Sie über Standardarbeitsanweisungen (Standard Operating Procedures, SOP), um über längere Zeit Betriebssystemsicherheitsaktualisierungen zu installieren?*<br>***f.****Haben Sie sich an die Best Practices für die Sicherheit des verwendeten Betriebssystems gehalten, wie z.B. Anti-Malware-Software, Nicht-Verwaltungsbenutzer?* |
| **Anwendungssicherheit** | ***a.*** *Haben Sie die Benutzeroberfläche &quot;Admin-Benutzeroberfläche&quot;, &quot;Kanal-Switch&quot;und &quot;Aktivität&quot;für die Produktion deaktiviert?* <br>***b.****Haben Sie die Protokollebene für die Produktion minimiert?*<br>***c.*** *Verwenden Sie HTTPS für die Verbindung mit AEM?* <br>***d.****Verwenden Sie ein CA-signiertes Zertifikat oder eine Enterprise PKI? (keine selbstsignierten Zertifikate)*<br>***e.**** Verwenden Sie TLS und nicht SSL v3?*<br>*** f.****Prüfen Sie das Registrierungstoken auf dem Gerät und AEM bei der Registrierung?*<br> ***g.*** *Haben Sie die verwendeten Daten klassifiziert und kein PII oder PHI auf dem Gerät vorhanden?*<br> ***h.*** *Haben Sie die verwendeten Daten klassifiziert und sind keine persönlichen oder geschützten Gesundheitsinformationen (PII) oder Gesundheitsinformationen (PHI) auf dem Gerät vorhanden?*<br> ***i.*** *Haben Sie die Überwachung von E-Mails konfiguriert, und haben Sie einen SOP für die Reaktion auf E-Mails und den Umgang mit Nicht-Ping-Geräten?* |
| **Zugriffssteuerung** | ***a.*** *Haben Sie eine Rollenbasierte Zugriffskontrolle (RBAC) identifiziert und intern verwaltet?* <br>***b.****Haben Sie sich bei der Bereitstellung von Zugriff auf Autoren, Administratoren und Player mithilfe der von Adobe empfohlenen Verfahren an das Prinzip des geringsten Vertrauens gehalten?* |

### Herunterladen der Sicherheits-Checkliste {#download-checklist}

Um die AEM Screens Security Checkliste herunterzuladen, klicken Sie [hier](/help/user-guide/assets/Screens-Security-Checklist.pdf).



