---
title: Umgebungen für [!UICONTROL AEM Screens]
description: Erfahren Sie mehr über die Umgebungen für ein AEM Screens-Projekt.
source-git-commit: f7653d8b386c02f510eb7a770cf3cdc22c41a5fb
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 100%

---


# Umgebungen {#environments}

Ermitteln Sie im Voraus, über welche AEM-Umgebungen die Kundin oder der Kunde verfügt und von Ihnen erwartet, sowohl für die *Entwicklung* als auch für die *Bereitstellung*.

>[!NOTE]
>
>AEM Screens setzt für funktionierende Projekte verschiedene Pakete voraus. In allen Umgebungen sollte dieselbe Version von Adobe Experience Manager ausgeführt werden.

Beachten Sie folgende Richtlinien zur Einrichtung der Umgebung für Ihr AEM Screens-Projekt:

1. Führen Sie die neuesten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager aus:

   * **AEM Service Pack**
   * **Screens Feature Pack**
   * **AEM Cumulative Fix Pack**

1. Ermitteln Sie alle erforderlichen Entwicklungspakete (z. B. zentrale WCM-Komponenten) oder Toolkits von Drittanbietern (z. B. SAP Hybris).

1. Installieren Sie die gleichen Software-Pakete in Ihrer lokalen Entwicklungsumgebung.

1. Weisen Sie Ihren Client an, dieselbe Konfiguration auf allen QA-, Staging- und Produktions-Servern zu verwenden. Nicht übereinstimmende Server-Konfigurationen verursachen Probleme bei Bereitstellung und Tests.
