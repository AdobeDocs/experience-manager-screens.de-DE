---
title: Sicherheitscheckliste
description: Erfahren Sie mehr über die wichtigsten Sicherheitsbereiche von AEM Screens anhand einer Checkliste mit Fragen und Überlegungen.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3d2835c8-d844-46fd-b35a-30feaced9dd8
TQID: https://experienceleague.adobe.com/ES-ciW55PF5Zzh9zqRYGu-kWbOym8XkLInXmmqga524
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 536
ht-degree: 16%

---

# Sicherheitscheckliste für AEM Screens {#security-checklist}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Die Seite „Sicherheitscheckliste für AEM Screens“ beschreibt die wichtigsten Sicherheitsbereiche und enthält eine Checkliste mit Fragen und Überlegungen.

## Checklisten-Tabelle {#checklist-table}

| **Sicherheitsbereich** | **Checkliste** | **Ja/Nein/k. A.** |
|---|---|---|
| **Updates für AEM und AEM Screens** | **a.** *Wurde das neueste Adobe Experience Manager (AEM) Service Pack angewendet?* <br>**b.** *Wurde das neueste AEM Screens Feature Pack angewendet?* <br>**c.** *Verwenden Sie die neueste verfügbare AEM Screens Player-Software von [AEM Screens Player-Downloads](https://download.macromedia.com/screens/)?* | |
| **Physische Sicherheit** | **a.** *Haben Sie alle unnötigen Ports deaktiviert?* <br>**b.** *Haben Sie Kabel und Hardware gesichert?* <br>**c.** *Verwenden Sie ggf. Container?* | |
| **Netzwerksicherheit** | **a.** *Verwenden Sie ein isoliertes Subnetz für Ihre Signage-Geräte?* <br>**b.** *Ermöglicht das isolierte Subnetz Zugriff auf die erforderlichen Endpunkte, einschließlich AEM, Adobe Analytics oder anderer erforderlicher Services?* <br>**c.** *Haben Sie Ihr WLAN mithilfe von Best Practices für Unternehmen gesichert?* <br>**d.** *Haben Sie bei synchronisierter Wiedergabe TCP-24503 für WebSocket nur auf den Primärgeräten zugelassen?* <br>**E.** *Haben Sie den IP-Adressbereich der Player-Geräte entsperrt, um sicherzustellen, dass nur autorisierte Geräte auf den Registrierungs-Service der Autoreninstanz zugreifen können?* | |
| **Betriebssystemsicherheit** | **a.** *Haben Sie ein Upgrade auf die neueste Version des Betriebssystems durchgeführt und alle erforderlichen Sicherheits-Patches angewendet?* <br>**b.** *Haben Sie alle unnötigen Services deaktiviert und unnötige Programme entfernt?* <br>**c.** *Haben Sie das Gerät bei der Geräteverwaltung registriert, um Unternehmensrichtlinien durchzusetzen?* <br>**d.** *Haben Sie das Gerät auf einen einzelnen Anwendungs-Kiosk (Player) gesperrt?* <br>**E.** *Verfügen Sie über ein SOP (Standard Operating Procedures) für die Installation von Betriebssystemsicherheitsaktualisierungen im Laufe der Zeit?*<br>**f.***Haben Sie die Best Practices für die Sicherheit des verwendeten Betriebssystems befolgt, z. B. Anti-Malware-Software, Benutzer ohne Administratorrechte?* | |
| **Anwendungssicherheit** | **a.** *Haben Sie die Admin-Benutzeroberfläche, den Kanalumschalter und die Aktivitäts-Benutzeroberfläche für die Produktion deaktiviert?* <br>**b.** *Haben Sie die Protokollebene für die Produktion minimiert?* <br>**c.** *Verwenden Sie HTTPS für die Verbindung mit AEM?* <br>**d.** *Verwenden Sie ein von der Zertifizierungsstelle signiertes Zertifikat oder eine Unternehmens-PKI? (Keine selbstsignierten Zertifikate)*<br>**z.***Benutzen Sie TLS und nicht SSL v3?*<br>**f.** *Validieren Sie bei der Registrierung das Registrierungs-Token auf dem Gerät und in AEM?*<br> **g.** *Haben Sie die verwendeten Daten klassifiziert und keine PII oder PHI auf dem Gerät vorhanden?*<br> **h.** *Haben Sie die verwendeten Daten als vertraulich eingestuft und festgestellt, dass auf dem Gerät keine personenbezogenen oder geschützten Gesundheitsinformationen (PHI) vorhanden sind?*<br> **i.** *Haben Sie die Überwachung von E-Mails konfiguriert? Verfügen Sie über ein SOP für die Reaktion auf die Überwachungs-E-Mails und den Umgang mit Geräten, die nicht pingen?* | |
| **Zugriffssteuerung** | **a.** *Verfügen Sie über eine rollenbasierte Zugriffssteuerung (RBAC), die intern identifiziert und verwaltet wird?* <br>**b.** *Haben Sie das Prinzip der geringsten Rechte befolgt, indem Sie Autoren, Administratoren und Playern Zugriff gewährt haben, indem Sie die Best Practices von Adobe verwendet haben?* | |

### Sicherheitscheckliste herunterladen {#download-checklist}

Um die Sicherheitscheckliste für AEM Screens herunterzuladen, klicken Sie [hier](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).

