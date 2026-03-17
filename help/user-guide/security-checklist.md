---
title: Sicherheitscheckliste
description: Erfahren Sie mehr über die wichtigsten Sicherheitsbereiche von AEM Screens anhand einer Checkliste mit Fragen und Überlegungen.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3d2835c8-d844-46fd-b35a-30feaced9dd8
source-git-commit: ad8509deaff9f90df5f6b50947f587a74e420661
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 18%

---

# Sicherheitscheckliste für AEM Screens {#security-checklist}

Die Seite „Sicherheitscheckliste für AEM Screens“ beschreibt die wichtigsten Sicherheitsbereiche und enthält eine Checkliste mit Fragen und Überlegungen.

## Checklisten-Tabelle {#checklist-table}

| **Sicherheitsbereich** | **Checkliste** | **Ja/Nein/k. A.** |
|---|---|---|
| **Updates für AEM und AEM Screens** | **a.** *Wurde das neueste Adobe Experience Manager (AEM) Service Pack angewendet?* <br>**B.** *Wurde das neueste AEM Screens Feature Pack angewendet?* <br>**C.** *Verwenden Sie die neueste verfügbare AEM Screens Player-Software von [AEM Screens Player-Downloads](https://download.macromedia.com/screens/)?* | |
| **Physische Sicherheit** | **a.** *Haben Sie alle unnötigen Ports deaktiviert?* <br>**B.** *Haben Sie Kabel und Hardware gesichert?* <br>**C.** *Verwenden Sie Container, falls zutreffend?* | |
| **Netzwerksicherheit** | **a.** *Verwenden Sie ein isoliertes Subnetz für Ihre Signage-Geräte?* <br>**B.** *Ermöglicht das isolierte Subnetz Zugriff auf die erforderlichen Endpunkte, einschließlich AEM, Adobe Analytics oder anderer erforderlicher Services?* <br>**C.** *Haben Sie Ihr WLAN mithilfe von Best Practices für Unternehmen gesichert?* <br>**D.** *Wenn Sie die synchronisierte Wiedergabe verwenden, haben Sie TCP-24503 für WebSocket nur auf den Primärgeräten zugelassen?* <br>**E.** *Haben Sie den IP-Adressbereich der Player-Geräte entsperrt, um sicherzustellen, dass nur autorisierte Geräte auf den Registrierungs-Service der Autoreninstanz zugreifen können?* | |
| **Betriebssystemsicherheit** | **a.** *Haben Sie ein Upgrade auf die neueste Version des Betriebssystems durchgeführt und alle erforderlichen Sicherheits-Patches angewendet?* <br>**B.** *Haben Sie alle unnötigen Services deaktiviert und unnötige Programme entfernt?* <br>**C.** *Haben Sie das Gerät bei der Geräteverwaltung registriert, um Unternehmensrichtlinien durchzusetzen?* <br>**D.** *Haben Sie das Gerät auf einen einzelnen Anwendungs-Kiosk (Player) gesperrt?* <br>**E.** *Verfügen Sie über ein SOP (Standard Operating Procedures) für die Installation von Betriebssystemsicherheitsaktualisierungen im Laufe der Zeit?*<br>**f.***Haben Sie die Best Practices für die Sicherheit des verwendeten Betriebssystems befolgt, z. B. Anti-Malware-Software, Benutzer ohne Administratorrechte?* | |
| **Anwendungssicherheit** | **a.** *Haben Sie die Admin-Benutzeroberfläche, den Kanalumschalter und die Aktivitäts-Benutzeroberfläche für die Produktion deaktiviert?* <br>**B.** *Haben Sie die Protokollebene für die Produktion minimiert?* <br>**C.** *Verwenden Sie HTTPS für die Verbindung mit AEM?* <br>**D.** *Verwenden Sie ein von der Zertifizierungsstelle signiertes Zertifikat oder eine Unternehmens-PKI? (Keine selbstsignierten Zertifikate)*<br>**z.***Verwenden Sie TLS und nicht SSL v3?*<br>**f.** *Validieren Sie bei der Registrierung das Registrierungs-Token auf dem Gerät und in AEM?*<br> **g.** *Haben Sie die verwendeten Daten klassifiziert und keine PII oder PHI auf dem Gerät vorhanden?*<br> **h.** *Haben Sie die verwendeten Daten als vertraulich eingestuft und festgestellt, dass auf dem Gerät keine personenbezogenen oder geschützten Gesundheitsinformationen (PHI) vorhanden sind?*<br> **i.** *Haben Sie die Überwachung von E-Mails konfiguriert? Verfügen Sie über ein SOP für die Reaktion auf die Überwachungs-E-Mails und den Umgang mit Geräten, die nicht pingen?* | |
| **Zugriffssteuerung** | **a.** *Verfügen Sie über eine intern identifizierte und verwaltete rollenbasierte Zugriffssteuerung (RBAC)* <br>**B.** *Haben Sie das Prinzip der geringsten Rechte befolgt, indem Sie Autoren, Administratoren und Playern Zugriff gewährt haben, indem Sie die Best Practices von Adobe verwendet haben?* | |

### Sicherheitscheckliste herunterladen {#download-checklist}

Um die Sicherheitscheckliste für AEM Screens herunterzuladen, klicken Sie [hier](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).
