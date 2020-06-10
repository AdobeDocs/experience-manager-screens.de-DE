---
title: Sicherheitscheckliste
seo-title: Sicherheitscheckliste
description: Die Seite beschreibt die Sicherheitscheckliste
seo-description: Die Seite beschreibt die Sicherheitscheckliste
translation-type: tm+mt
source-git-commit: 16361c016251a0ce0c86175eb6ef09ffb3150415
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 94%

---


# Sicherheitscheckliste für AEM Screens  {#security-checklist}

Die Seite „Sicherheitscheckliste für AEM Screens“ beschreibt die wichtigsten Sicherheitsbereiche und enthält eine Checkliste mit Fragen und Überlegungen.

## Checklisten-Tabelle {#checklist-table}

| **Sicherheitsbereich** | **Checkliste** | **Ja/Nein/k. A.** |
|---|---|---|
| **Updates für AEM und AEM Screens** | ***a.*** *Wurde das neueste Service Pack für Adobe Experience Manager (AEM) angewendet?* <br>***b.****Wurde das neueste Feature Pack für AEM Screens angewendet?*<br>***c.*** *Verwenden Sie die neueste verfügbare AEM Screens-Player-Software aus den[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/)?* |
| **Physische Sicherheit** | ***a.*** *Haben Sie alle unnötigen Anschlüsse deaktiviert?* <br>***b.****Haben Sie Kabel und Hardware gesichert?*<br>***c.*** *Verwenden Sie ggf. Container?* |
| **Netzwerksicherheit** | ***a.*** *Verwenden Sie ein isoliertes Subnetz für Ihre Signaturgeräte?* <br>***b.****Ermöglicht das isolierte Subnetz Zugriff auf die erforderlichen Endpunkte, einschließlich AEM, Adobe Analytics oder anderer erforderlicher Dienste?*<br>***c.*** *Haben Sie Ihr WLAN mithilfe der Best Practices für Unternehmen gesichert?* <br>***d.****Wenn Sie die synchronisierte Wiedergabe verwenden, ist TCP 24503 für WebSocket nur auf den Master-Geräten zugelassen?*<br>***e.*** *Haben Sie die IP-Bereiche der Player-Geräte freigegeben, damit nur autorisierte Geräte auf den Registrierungsdienst zugreifen können?* |
| **Betriebssystemsicherheit** | ***a.*** *Haben Sie auf die neueste Version des Betriebssystems aktualisiert und alle erforderlichen Sicherheits-Patches angewendet?* <br>***b.****Haben Sie alle unnötigen Dienste deaktiviert und unnötige Programme entfernt?*<br>***c.*** *Haben Sie das Gerät in die Geräteverwaltung eingeschrieben, um Unternehmensrichtlinien zu erzwingen?* <br>***d.****Haben Sie das Gerät auf einen einzelnen Anwendungs-Terminal (Player) beschränkt?*<br>***e.*** *Verfügen Sie über Standardarbeitsanweisungen, um über längere Zeit Betriebssystemsicherheits-Updates zu installieren?*<br>***f.****Haben Sie sich an die Best Practices für die Sicherheit des verwendeten Betriebssystems gehalten, wie z.B. Anti-Malware-Software, Nicht-Admin-Benutzer?* |
| **Anwendungssicherheit** | ***a.*** *Haben Sie die Admin-Benutzeroberfläche, den Kanalschalter und die Aktivitätsbenutzeroberfläche für die Produktion deaktiviert?* <br>***b.****Haben Sie die Protokollebene für die Produktion minimiert?*<br>***c.*** *Verwenden Sie HTTPS für die Verbindung mit AEM?* <br>***d.****Verwenden Sie ein CA-signiertes Zertifikat oder eine Unternehmens-PKI? (keine selbstsignierten Zertifikate)*<br>***e.**** Verwenden Sie TLS und nicht SSL v3?*<br>*** f.****Prüfen Sie das Registrierungs-Token auf dem Gerät und AEM bei der Registrierung?*<br> ***g.*** *Haben Sie die verwendeten Daten klassifiziert und sichergestellt, dass keine PII oder PHI auf dem Gerät vorhanden sind?*<br> ***h.*** *Haben Sie die verwendeten Daten klassifiziert und sichergestellt, dass keine persönlichen oder geschützten Gesundheitsinformationen (PII) oder Gesundheitsinformationen (PHI) auf dem Gerät vorhanden sind?*<br> ***i.*** *Haben Sie die Überwachung von E-Mails konfiguriert und haben Sie Standardarbeitsanweisungen für die Reaktion auf E-Mails und den Umgang mit Nicht-Ping-Geräten?* |
| **Zugriffssteuerung** | ***a.*** *Haben Sie eine rollenbasierte Zugriffskontrolle (RBAC) identifiziert und wird diese intern verwaltet?* <br>***b.****Haben Sie sich bei der Bereitstellung von Zugriff auf Autoren, Administratoren und Player mithilfe der von Adobe empfohlenen Verfahren an das Prinzip des geringsten Vertrauens gehalten?* |

### Herunterladen der Sicherheitscheckliste {#download-checklist}

Um die Sicherheitscheckliste für AEM Screens herunterzuladen, klicken Sie [hier](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).