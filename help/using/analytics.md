---
title: Analytics mit AEM Screens
seo-title: Analytics mit AEM Screens
description: Die Seite beschreibt Analytics mit AEM Screens
seo-description: Die Seite beschreibt die Analysen mit AEM Screens
translation-type: tm+mt
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 87%

---


# Analytics mit AEM Screens {#analytics-screens}

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind Marketing-/Geschäftsstrategen.

AEM Screens bietet die Möglichkeit, alle verfolgbaren Ereignisse, die einzelne Player-Geräte ausführen, lokal zu erfassen. Diese Daten werden lokal gespeichert, bis sie zur Verarbeitung in die Cloud hochgeladen werden können. Zusätzlich zu allen Ereignisdaten werden eine Geräte-ID und ein Zeitstempel hinzugefügt. So lassen sich Daten eines Players von den Daten eines anderen Players unterscheiden und Daten, die zu unterschiedlichen Tageszeiten ausgeführt werden, bei Bedarf separat auswerten.

Es gibt zwei wesentliche Gründe für die Erfassung dieser Daten.

Der erste umfasst **Feedbackschleifen und maschinelles Lernen**, während der zweite die **Erstellung von Diagrammen, Dashboards und Berichten** beinhaltet, die für den menschlichen Gebrauch bestimmt sind.

Im Nutzungsszenario Feedbackschleife geht es nicht um visuelle Berichte oder Dashboards, sondern um eine Definition von Regeln, die AEM zur Inhaltsänderung ausführen kann. Durch Nutzung und Verarbeitung aller Screens-Player-Ereignisdaten aus einem bestimmten Zeitraum können wir eine Regel definieren, die die Effektivität von image1 im Vergleich zu image2 bewertet. Durch Kombination von Verkaufsdaten mit Wiedergabedaten kann AEM ermitteln, dass image1 einen wesentlich größeren Einfluss auf den Umsatz hat, und alle Player automatisch anweisen, image1 zu verwenden.

Das zweite Nutzungsszenario bei Verwendung von Analytics besteht in der Verarbeitung von Wiedergabeereignissen und Nutzungsdaten für den menschlichen Gebrauch (in Form von Berichten und Dashboards).
Wir können diese Daten verwenden, um eine Heatmap eines interaktiven Erlebnisses zu erstellen, um die bevorzugte Reisekarte durch unsere Anwendung zu bestimmen. Außerdem können wir ein Dashboard einrichten, das eine grafische Interpretation der Anzahl der Interaktionen von Verbrauchern mit unserer Anwendung erlaubt.

