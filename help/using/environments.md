---
title: Umgebungen für [!UICONTROL AEM Screens]
description: Erfahren Sie mehr über die Umgebungen für ein AEM Screens-Projekt.
source-git-commit: 3c4b37b3b9f268b500562fa4ce3782b7be1e7d74
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 61%

---


# Umgebungen {#environments}

Ermitteln Sie im Voraus, welche AEM Umgebungen der Client hat und von Ihnen erwartet, beide für *development* und *Implementierung*.

>[!NOTE]
>
>AEM Screens benötigt mehrere Pakete, damit Projekte funktionieren. In allen Umgebungen sollte dieselbe Version von Adobe Experience Manager ausgeführt werden.

Beachten Sie folgende Richtlinien zur Einrichtung der Umgebung für Ihr AEM Screens-Projekt:

1. Führen Sie die neuesten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager aus:

   * **AEM Service Pack**
   * **Screens Feature Pack**
   * **AEM Cumulative Fix Pack**

1. Ermitteln Sie alle erforderlichen Entwicklungspakete (z. B. zentrale WCM-Komponenten) oder Toolkits von Drittanbietern (z. B. SAP Hybris).

1. Installieren Sie dieselben Softwarepakete in Ihrer lokalen Entwicklungsumgebung.

1. Weisen Sie Ihren Klienten an, dieselbe Konfiguration auf allen QA-, Staging- und Produktionsservern zu verwenden. Nicht übereinstimmende Serverkonfigurationen verursachen Probleme bei der Bereitstellung und beim Testen.
