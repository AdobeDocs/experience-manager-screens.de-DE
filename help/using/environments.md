---
title: Umgebungen für [!UICONTROL AEM Screens]
seo-title: Umgebungen für [!UICONTROL AEM Screens]
description: Auf dieser Seite werden die Umgebungen für ein AEM Screens-Projekt beschrieben.
seo-description: Auf dieser Seite werden die Umgebungen für ein AEM Screens-Projekt erläutert.
translation-type: ht
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: ht
source-wordcount: '170'
ht-degree: 100%

---


# Umgebungen {#environments}

Ermitteln Sie im Voraus, welche AEM-Umgebungen der Klient aufweist und voraussichtlich nutzen wird, sowohl für *Entwicklung* als auch *Implementierung*.

>[!NOTE]
>
>AEM Screens erfordert für funktionierende Projekte verschiedene Pakete. In allen Umgebungen sollte dieselbe Version von Adobe Experience Manager ausgeführt werden.

Beachten Sie folgende Richtlinien zur Einrichtung der Umgebung für Ihr AEM Screens-Projekt:

1. Führen Sie die neuesten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager aus:

   * **AEM Service Pack**
   * **Screens Feature Pack**
   * **AEM Cumulative Fix Pack**

1. Ermitteln Sie alle erforderlichen Entwicklungspakete (z. B. zentrale WCM-Komponenten) oder Toolkits von Drittanbietern (z. B. SAP Hybris).

1. Installieren Sie dieselben Softwarepakete in Ihren lokalen Entwicklungsumgebungen.

1. Weisen Sie Ihren Klienten an, dieselbe Konfiguration auf allen QA-, Staging- und Produktionsservern zu verwenden. Nicht übereinstimmende Serverkonfigurationen verursachen Probleme bei Bereitstellung und Tests.
