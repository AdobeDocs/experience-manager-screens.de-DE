---
title: Analyse mit AEM Screens
description: Erfahren Sie mehr über Adobe Analytics mit Adobe Experience Manager Screens.
exl-id: cfb47e94-9f65-43f3-b197-07222f3f6424
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 20%

---

# Analyse mit AEM Screens {#analytics-screens}

>[!NOTE]
>
>Typische Stakeholder für diese Aktivität sind Marketing-/Geschäftsstrategen.

AEM Screens bietet die Möglichkeit, alle verfolgbaren Ereignisse, die einzelne Player-Geräte ausführen, lokal zu erfassen. Diese Daten werden lokal gespeichert, bis sie zur Verarbeitung in die Cloud hochgeladen werden können. Zusätzlich zu allen Ereignisdaten werden eine Geräte-ID und ein Zeitstempel hinzugefügt. Dadurch wird sichergestellt, dass Daten aus einem Player von einem anderen Player unterschieden werden können und Daten, die zu unterschiedlichen Tageszeiten ausgeführt werden, bei Bedarf separat ausgewertet werden können.

Es gibt zwei wesentliche Gründe, warum Sie diese Daten erfassen möchten.

Der erste betrifft **Feedback-Schleifen und maschinelles Lernen** während das zweite die **Erstellung von Diagrammen, Dashboards und Berichten** die für den menschlichen Verzehr bestimmt sind.

Im Anwendungsfall der Feedback-Schleife müssen Sie sich nicht mit visuellen Berichten oder Dashboards befassen, sondern Regeln definieren, die AEM zur Inhaltsänderung ausführen können. Durch Nutzung und Verarbeitung aller Screens-Player-Ereignisdaten aus einem bestimmten Zeitraum können Sie eine Regel definieren, die die Effektivität von image1 im Vergleich zu image2 bewertet. Durch Kombination von Verkaufsdaten mit Wiedergabedaten kann AEM feststellen, dass image1 einen größeren Einfluss auf den Umsatz hat, und alle Player automatisch anweisen, image1 zu verwenden.

Das zweite Nutzungsszenario bei Verwendung von Analytics besteht in der Verarbeitung von Wiedergabeereignissen und Nutzungsdaten für den menschlichen Gebrauch (in Form von Berichten und Dashboards).
Sie können diese Daten verwenden, um eine Heatmap eines interaktiven Erlebnisses zu erstellen und die bevorzugte Journey-Zuordnung über die Anwendung zu bestimmen. Sie können auch ein Dashboard erstellen, das eine grafische Interpretation der Anzahl der Interaktionen von Verbrauchern mit der Anwendung ermöglicht.
