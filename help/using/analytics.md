---
title: Analyse mit AEM Screens
seo-title: Analyse mit AEM Screens
description: Die Seite beschreibt Analytics mit AEM Screens
seo-description: Die Seite beschreibt die Analyse mit AEM Screens
translation-type: tm+mt
source-git-commit: f01b69b860a3862e2b46f11b2d9b95dede742d9c

---


# Analytics mit AEM Screens {#analytics-screens}

>[!NOTE]
>
>Typische Interessenvertreter für diese Aktivität sind Marketing-/Geschäftsstratege.

AEM Screens bietet die Möglichkeit, jedes verfolgte Ereignis, das jedes Player-Gerät ausführt, lokal zu erfassen. Diese Daten werden lokal gespeichert, bis sie zur Verarbeitung in die Cloud hochgeladen werden können. Zusätzlich zu allen Ereignisdaten werden eine deviceID und ein timestamp hinzugefügt. Dadurch wird sichergestellt, dass Daten von einem Player von einem anderen Player unterschieden werden können und Daten, die zu unterschiedlichen Tageszeiten ausgeführt werden, bei Bedarf separat ausgewertet werden können.

Es gibt zwei wesentliche Gründe, warum wir diese Daten erfassen möchten.

Die erste umfasst **Feedback-Schleifen und maschinelles Lernen** , während die zweite die **Erstellung von Diagrammen, Dashboards und Berichten** umfasst, die für den menschlichen Gebrauch bestimmt sind.

Im Anwendungsfall der Feedback-Schleife geht es nicht um visuelle Berichte oder Dashboards, sondern es sollten Regeln definiert werden, auf denen AEM zur Inhaltsänderung ausgeführt werden kann. Indem wir alle Screens Player-Ereignisdaten aus einem bestimmten Zeitraum nutzen und verarbeiten, können wir eine Regel definieren, die die Effektivität von image1 im Vergleich zu image2 bewertet. Durch die Kombination von Verkaufsdaten mit Wiedergabedaten kann AEM feststellen, dass image1 einen wesentlich größeren Einfluss auf den Umsatz hat, und weist alle Player automatisch an, image1 zu verwenden.

Der zweite Anwendungsfall bei der Verwendung von Analytics besteht in der Verarbeitung von Wiedergabeereignissen und Nutzungsdaten für den menschlichen Verbrauch über Berichte und Dashboards.
Wir können diese Daten verwenden, um eine Heatmap eines interaktiven Erlebnisses zu erstellen, um die bevorzugte Reisekarte durch unsere Anwendung zu bestimmen. Wir können auch ein Dashboard erstellen, das eine grafische Interpretation der Anzahl der Interaktionen von Verbrauchern mit unserer Anwendung bietet.

