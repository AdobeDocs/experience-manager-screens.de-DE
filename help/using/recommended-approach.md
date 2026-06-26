---
title: Empfohlener Ansatz
description: Erfahren Sie mehr über den empfohlenen Ansatz in einem AEM Screens-Projekt.
exl-id: 28aacffa-e9c9-4ccb-8038-720bb3e02a3f
TQID: https://experienceleague.adobe.com/r0WE0DQZx3dtGGlNaX9DUX3ckvu2ZdseJLy8-sDJZXQ
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ae478996-b206-4712-9b0c-dc78a2644453
  - id: f18e6c98-d21a-4444-b84b-f327ce464de4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: fc314d1d-7cb9-4a38-8dbd-8f9b6478f40d
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 482
ht-degree: 47%

---

# Empfohlener Ansatz {#recommended-approach}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Die Best Practice ist, alle AEM Screens-Projekte auf Unternehmensebene als langfristige Projekte zu betrachten. Eine Projektdauer von einem oder mehreren Jahren ist wahrscheinlich, insbesondere wenn die Lösung komplexe Benutzerinteraktionen ermöglicht oder auf verschiedenen Geräten und Standorten bereitgestellt wird.

## Leitlinien für die Entwicklung einer Digital Signage-Strategie {#signage-strategy}

Beachten Sie die folgenden Empfehlungen, bevor Sie ein Digital-Signage-Projekt entwickeln und bereitstellen:

* **Kontrolle des**:
Wenn die gewünschte Lösung ehrgeizig ist, wird empfohlen, die Ergebnisse in separate Phasen zu unterteilen, um den Umfang des Projekts zu steuern.

* **Definierte Anwendungsfälle**:
Die Projektphasen sollten klar definierte Anwendungsfälle mit eindeutig identifizierten Erfolgskriterien liefern.

* **Inkrementelle Ergebnisse**:
Konzentration auf die schrittweise Bereitstellung von Funktionen.

* **Schätzen des gewünschten**:
Beginnen Sie mit den vordefinierten AEM Screens-Funktionen, bevor Sie benutzerdefinierte Komponenten und Integrationen erstellen. Führen Sie stets ein Brainstorming durch, um zu ermitteln, ob das gewünschte Ergebnis mit den standardmäßigen Komponenten und Funktionen von AEM Screens erreichbar ist.

* **Definieren von Pilotprogrammen, Rollouts und POCs**:
Entwickeln Sie einen Machbarkeitsnachweis (Proof of Concept, POCs) und passen Sie ihn durch einen Pilotversuch und einen Rollout nach Bedarf an.

* **Vordefinieren der Inhaltsstrategie**:
eine Inhaltsstrategie festlegen, einschließlich kurz- und langfristiger Ziele. Richten Sie zudem Markenziele/KPIs auf Funktionsverbesserungen aus.

  >[!NOTE]
  >
  > Die Vorlaufkosten für ein AEM Screens-Projekt sind häufig höher, da in Hardware, Geräte und Sitedesigns investiert werden muss. Daher können Inhaltslösungen, die zunächst einfach gehalten werden, dazu beitragen, den Budgeterwartungen gerecht zu werden.

* **Schätzen umfangreicher Ergebnisse**:
Wenn die Lösung in großem Umfang bereitgestellt wird, führen Sie die Komponenten der Anwendung an sorgfältig ausgewählten Pilotstandorten zur Testverwendung aus. Stellen Sie die Anwendung an neuen Standorten und auf neuen Geräten bereit, sobald sie die Validierung bestanden hat.

  >[!NOTE]
  >
  > Beginnen Sie in der Pilotphase mit der Erfassung von Analysen. So können Sie Businessteams dabei helfen, anhand der spezifischen Metriken, die erreicht werden sollen, den Erfolg der Lösung zu überprüfen. Die Ergebnisse aus dem Pilotprojekt helfen Businessteams dabei, zu ermitteln, welche Verbesserungen vorgenommen werden müssen.

* **Aufspaltung der Ergebnisse in messbare Aufgaben**:
Die Aufteilung der Bereitstellung von Funktionen in messbare Aufgaben ermöglicht Feedback, bietet erreichbarere Ziele und reduziert die allgemeinen Projektrisiken.

* **Entwicklung einer Roadmap**:
Wenn Ihr Kunde ein funktionsreiches Produkt wünscht, stellen Sie einen Teil der geplanten Funktionen schon früh im Projekt bereit und planen Sie andere Funktionen für zukünftige Phasen. Eine funktionsreiche erste Lieferung birgt ein höheres Risiko und erschwert die Validierung auf Kundenseite.

* **Den Umfang benutzerdefinierter Integrationen**:
Interaktive Komponenten mit Touchscreen-Interaktion, Bewegungssensor oder RFID erfordern eine signifikante benutzerdefinierte Entwicklung der Implementierungsmethode. Bildschirmpräsentationen, Videowerbung oder statische Menüs können in einem Screens-Kanal als grafische Inhalte oder HTML bereitgestellt werden.

