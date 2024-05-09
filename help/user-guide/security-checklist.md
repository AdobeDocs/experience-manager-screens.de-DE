---
title: Sicherheitscheckliste
description: Erfahren Sie mehr über die wichtigsten Sicherheitsbereiche von AEM Screens mit einer Checkliste mit Fragen und Überlegungen.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3d2835c8-d844-46fd-b35a-30feaced9dd8
source-git-commit: 2a51258ffe7b969962378dcd0558bd001b616ba1
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 36%

---

# Sicherheitscheckliste für AEM Screens {#security-checklist}

Auf der AEM Screens-Sicherheitschecklistenseite werden die wichtigsten Sicherheitsbereiche mit einer Checkliste mit Fragen und Überlegungen beschrieben.

## Checklisten-Tabelle {#checklist-table}

| **Sicherheitsbereich** | **Checkliste** | **Ja/Nein/k. A.** |
|---|---|---|
| **Updates für AEM und AEM Screens** | **a.** *Wurde das neueste Service Pack für Adobe Experience Manager (AEM) angewendet?* <br>**b.** *Wurde das neueste AEM Screens Feature Pack angewendet?* <br>**c.** *Verwenden Sie die neueste verfügbare AEM Screens-Player-Software aus den [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/)?* |
| **Physische Sicherheit** | **a.** *Haben Sie alle unnötigen Anschlüsse deaktiviert?* <br>**b.** *Haben Sie Kabel und Hardware gesichert?* <br>**c.** *Verwenden Sie ggf. Container?* |
| **Netzwerksicherheit** | **a.** *Verwenden Sie ein isoliertes Subnetz für Ihre Signaturgeräte?* <br>**b.** *Ermöglicht das isolierte Subnetz Zugriff auf die erforderlichen Endpunkte, einschließlich AEM, Adobe Analytics oder anderer erforderlicher Dienste?* <br>**c.** *Haben Sie Ihr WLAN mithilfe der Best Practices für Unternehmen gesichert?* <br>**d.** *Wenn Sie die synchronisierte Wiedergabe verwenden, haben Sie TCP 24503 für WebSocket nur auf den primären Geräten zugelassen?* <br>**e.** *Haben Sie den IP-Adressbereich der Player-Geräte entsperrt, sodass nur autorisierte Geräte auf den Registrierungsdienst in der Authoring-Instanz zugreifen können?* |
| **Betriebssystemsicherheit** | **a.** *Haben Sie auf die neueste Version des Betriebssystems aktualisiert und alle erforderlichen Sicherheits-Patches angewendet?* <br>**b.** *Haben Sie alle unnötigen Services deaktiviert und unnötige Programme entfernt?* <br>**c.** *Haben Sie das Gerät in die Geräteverwaltung eingeschrieben, um Unternehmensrichtlinien zu erzwingen?* <br>**d.** *Haben Sie das Gerät auf einen einzigen Anwendungs-Terminal (Player) beschränkt?* <br>**e.** *Verfügen Sie über Standardarbeitsanweisungen, um über längere Zeit Betriebssystemsicherheits-Updates zu installieren?*<br>**f.***Haben Sie die Best Practices für die Sicherheit des verwendeten Betriebssystems befolgt, wie z. B. Anti-Malware-Software, Benutzer ohne Administratorrechte?* |
| **Anwendungssicherheit** | **a.** *Haben Sie die Admin-Benutzeroberfläche, den Kanalschalter und die Aktivitäts-Benutzeroberfläche für die Produktion deaktiviert?* <br>**b.** *Haben Sie die Protokollebene für die Produktion minimiert?* <br>**c.** *Verwenden Sie HTTPS für die Verbindung mit AEM?* <br>**d.** *Verwenden Sie ein CA-signiertes Zertifikat oder eine Unternehmens-PKI? (keine selbstsignierten Zertifikate)*<br>**e.***Verwenden Sie TLS und nicht SSL v3?*<br>**f.** *Überprüfen Sie das Registrierungstoken auf dem Gerät und AEM bei der Registrierung?*<br> **g.** *Haben Sie die verwendeten Daten klassifiziert und sichergestellt, dass auf dem Gerät keine PII oder PHI vorhanden sind?*<br> **h.** *Haben Sie die verwendeten Daten klassifiziert und sichergestellt, dass keine personenbezogenen oder geschützten Gesundheitsinformationen (PII) oder Gesundheitsinformationen (PHI) auf dem Gerät vorhanden sind?*<br> **i.** *Haben Sie die Überwachung von E-Mails konfiguriert? Verfügen Sie über ein SOP für die Reaktion auf Monitoring-E-Mails und den Umgang mit Nicht-Ping-Geräten?* |
| **Zugriffssteuerung** | **a.** *Haben Sie eine rollenbasierte Zugriffskontrolle (RBAC) identifiziert und intern verwaltet?* <br>**b.** *Haben Sie sich bei der Bereitstellung des Zugriffs für Autoren, Administratoren und Player mithilfe von Best Practices von Adobe an das Prinzip der geringsten Berechtigung gehalten?* |

### Herunterladen der Sicherheitscheckliste {#download-checklist}

Um die Sicherheitscheckliste für AEM Screens herunterzuladen, klicken Sie auf [here](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).
