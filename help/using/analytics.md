---
title: Analyse mit AEM Screens
description: Erfahren Sie mehr über Adobe Analytics mit Adobe Experience Manager Screens.
exl-id: cfb47e94-9f65-43f3-b197-07222f3f6424
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 100%

---

# Analyse mit AEM Screens {#analytics-screens}

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind Marketing-/Geschäftsstrateginnen und -strategen.

AEM Screens kann alle verfolgbaren Ereignisse, die einzelne Player-Geräte ausführen, lokal erfassen. Diese Daten werden lokal gespeichert, bis sie zur Verarbeitung in die Cloud hochgeladen werden können. Zusätzlich zu allen Ereignisdaten werden eine Geräte-ID und ein Zeitstempel hinzugefügt. Diese Funktion stellt sicher, dass Daten eines Players von denen eines anderen Players unterschieden werden können. Daten, die zu unterschiedlichen Tageszeiten ausgeführt werden, können bei Bedarf separat ausgewertet werden.

Es gibt zwei wesentliche Gründe für die Erfassung dieser Daten.

Der erste umfasst **Feedbackschleifen und maschinelles Lernen**, während der zweite die **Erstellung von Diagrammen, Dashboards und Berichten** beinhaltet, die für den menschlichen Gebrauch bestimmt sind.

Im Nutzungsszenario „Feedbackschleife“ geht es nicht um visuelle Berichte oder Dashboards, sondern um eine Definition von Regeln, die AEM zur Inhaltsänderung ausführen kann. Durch Nutzung und Verarbeitung aller Screens-Player-Ereignisdaten aus einem bestimmten Zeitraum können Sie eine Regel definieren, die die Effektivität von image1 im Vergleich zu image2 bewertet. Durch Kombination von Verkaufsdaten mit Wiedergabedaten kann AEM ermitteln, dass image1 einen größeren Einfluss auf den Umsatz hat, und alle Player automatisch anweisen, image1 zu verwenden.

Der zweite Anwendungsfall für Analysen bezieht sich auf die Verarbeitung von Wiedergabeereignissen und Nutzungsdaten für den menschlichen Gebrauch (in Form von Berichten und Dashboards).
Mit diesen Daten können Sie für ein interaktives Erlebnis eine Heatmap erstellen, um mithilfe der Anwendung die bevorzugte Journey Map zu bestimmen.  Außerdem können Sie ein Dashboard einrichten, das eine grafische Interpretation der Anzahl der Interaktionen von Verbraucherinnen und Verbrauchern mit der Anwendung erlaubt.
