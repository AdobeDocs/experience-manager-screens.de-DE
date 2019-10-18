---
title: Umgebungen für [!UICONTROL AEM-Bildschirme]
seo-title: Umgebungen für [!UICONTROL AEM-Bildschirme]
description: Auf dieser Seite werden die Umgebungen für ein AEM Screens-Projekt beschrieben.
seo-description: Auf dieser Seite werden die Umgebungen für ein AEM Screens-Projekt hervorgehoben.
translation-type: tm+mt
source-git-commit: 0d91aa653508969cf1f4ccfba23a570e22e6414c

---


# Umgebungen {#environments}

Legen Sie im Voraus fest, welche AEM-Umgebungen der Client besitzt und welche Sie voraussichtlich verwenden werden, sowohl für die *Entwicklung* als auch für die *Bereitstellung*.

>[!NOTE]
>
>AEM Screens erfordert mehrere Pakete, damit Projekte funktionieren. In allen Umgebungen sollte dieselbe Version von Adobe Experience Manager ausgeführt werden.

Beachten Sie die folgenden Richtlinien, um die Umgebung für Ihr AEM Screens-Projekt einzurichten:

1. Führen Sie die neuesten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager aus:

   * **AEM Service Pack **
   * **Screens Feature Pack**
   * **AEM  Cumulative Fix Pack **

1. Identifizieren Sie alle erforderlichen Entwicklungspakete (z. B. WCM-Kernkomponenten) oder Drittanbieter-Toolkits (z. B. SAP Hybris).

1. Installieren Sie dieselben Softwarepakete auf Ihren lokalen Entwicklungsumgebungen.

1. Weisen Sie Ihren Client an, dieselbe Konfiguration auf allen QA-, Stage- und Production-Servern zu verwenden. Nicht übereinstimmende Serverkonfigurationen verursachen Probleme bei der Bereitstellung und beim Testen.
