---
title: Analyse mit AEM Screens
description: Erfahren Sie mehr über Adobe Analytics mit Adobe Experience Manager Screens.
exl-id: cfb47e94-9f65-43f3-b197-07222f3f6424
TQID: https://experienceleague.adobe.com/i7B7E5Kyno2U-ZTxEOPfhrr9W7fqYTWTV5vvcteRicY
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: d4664dd5678eaccabe656398c437dca264d4675e
workflow-type: tm+mt
source-wordcount: 289
ht-degree: 76%

---

# Analyse mit AEM Screens {#analytics-screens}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind Marketing-/Geschäftsstrateginnen und -strategen.

AEM Screens kann alle verfolgbaren Ereignisse, die einzelne Player-Geräte ausführen, lokal erfassen. Diese Daten werden lokal gespeichert, bis sie zur Verarbeitung in die Cloud hochgeladen werden können. Zusätzlich zu allen Ereignisdaten werden eine Geräte-ID und ein Zeitstempel hinzugefügt. Diese Funktion stellt sicher, dass Daten eines Players von denen eines anderen Players unterschieden werden können. Daten, die zu unterschiedlichen Tageszeiten ausgeführt werden, können bei Bedarf separat ausgewertet werden.

Es gibt zwei wesentliche Gründe für die Erfassung dieser Daten.

Der erste umfasst **Feedbackschleifen und maschinelles Lernen**, während der zweite die **Erstellung von Diagrammen, Dashboards und Berichten** beinhaltet, die für den menschlichen Gebrauch bestimmt sind.

Im Nutzungsszenario „Feedbackschleife“ geht es nicht um visuelle Berichte oder Dashboards, sondern um eine Definition von Regeln, die AEM zur Inhaltsänderung ausführen kann. Durch Nutzung und Verarbeitung aller Screens-Player-Ereignisdaten aus einem bestimmten Zeitraum können Sie eine Regel definieren, die die Effektivität von image1 im Vergleich zu image2 bewertet. Durch Kombination von Verkaufsdaten mit Wiedergabedaten kann AEM ermitteln, dass image1 einen größeren Einfluss auf den Umsatz hat, und alle Player automatisch anweisen, image1 zu verwenden.

Der zweite Anwendungsfall, bei dem Analytics verwendet wird, besteht darin, Wiedergabeereignisse und Nutzungsdaten für den menschlichen Gebrauch über Berichte und Dashboards zu verarbeiten.
Sie können diese Daten verwenden, um eine Heatmap eines interaktiven Erlebnisses zu erstellen und über die Anwendung die bevorzugte Journey-Map zu bestimmen. Sie können auch ein Dashboard erstellen, das eine grafische Interpretation der Interaktion von Nutzern mit dem Programm bietet.
