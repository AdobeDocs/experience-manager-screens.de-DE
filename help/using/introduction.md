---
title: Einführung in [!UICONTROL AEM-Bildschirme]
seo-title: Best Practices für [!UICONTROL AEM Screens] -Projekte
description: Diese Seite ist ein Einführungsabschnitt zu AEM Screens
seo-description: Diese Seite bietet eine Einführung in AEM Screens
translation-type: tm+mt
source-git-commit: 55999ae9ead7ab8986f4dcb69b0bbaa46933c9ec

---


# Einführung in AEM Screens {#introduction}

**AEM (Adobe Experience Manager) Screens** ist eine Digital Signage-Lösung, mit der Sie dynamische und interaktive digitale Erlebnisse erstellen, veröffentlichen und abspielen können, die verschiedene Arten von lokalen Anzeigebildschirmen in Abstimmung mit einer umfassenden digitalen Marketingstrategie für Omniannel beinhalten.

Mit AEM Screens können Sie Folgendes erstellen:

* **dedizierte Menüs**
* **Produktempfehlungen**
* **Hintergrundbilder für Lifestyle**

Darüber hinaus bieten Screens eine Vielzahl einzigartiger Anwendungen für Kunden und Mitarbeiter, die auf der jeweiligen Domäne basieren, in der diese bereitgestellt werden, z. B.:

* **interaktive Displays**
* **Wegsuchen**
* **Branding**
* **Ambiente in Ihrer Umgebung hinzufügen**

Das Erstellen und Verwalten eines digitalen Signaturnetzwerks mit AEM Screens ist einfach und intuitiv. Eine Player-Anwendung hostet Inhaltskanäle, die von Kunden oder Implementierungspartnern für AEM Screens erstellt wurden. *Positionen* verwalten eine vordefinierte Positionshierarchie und enthalten Anzeigen. Each *display* has a dashboard that shows different devices and screens attached. Der Inhalt für AEM Screens wird in *Kanälen* verwaltet. *Mit dem AEM Screens Player wird der auf Kanälen vorhandene Inhalt auf Displays dargestellt.*



>[!NOTE]
>
>Detaillierte Informationen zu den verschiedenen Funktionen in der Entwicklung und Verwaltung von AEM Screens-Projekten finden Sie im **[AEM Screens-Benutzerhandbuch](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html)**.

## AEM Sites versus AEM Screens {#aem-sites-screens}

> [!NOTE]
>
> Wenn Ihr Implementierungsteam Erfahrung mit der Arbeit mit AEM-Sites-Anwendungen hat, ist es wichtig, den Unterschied zwischen AEM-Sites und AEM-Bildschirmen zu verstehen.

AEM Screens bietet eine einheitliche Authoring-/Wiedergabe-Plattform für die Bereitstellung von Inhalten auf Geräten mit digitaler Signatur in öffentlichen Räumen. Während der Erlebnisautor sich bemühen sollte, die Konsistenz über das Web und die Kanäle zu gewährleisten, gibt es einige Unterschiede, die beachtet werden sollten.

* **Verweilzeit**: In der Regel werden Webseiten so gestaltet, dass sie eine Vielzahl von Informationen bereitstellen, die über einen relativ längeren Zeitraum genutzt werden können. Im Gegensatz dazu sollten digitale Erlebnisse am Verkaufsort die Bedürfnisse des Viewers vorwegnehmen und klare und präzise Anweisungen dazu geben, wie und warum der Benutzer eingreifen sollte. Dies führt zu zielgerichteteren, kuratierten und kontextbezogenen Erlebnissen.

* **Anzeigeabstand**: Die Anzeige von Entfernungen ist in der Regel länger oder weiter entfernt als die typische Entfernung, die Benutzer mit einer Website erleben. Daher sollte die Textgröße normalerweise größer sein, und der Abstand zwischen Text, Bildern und anderen ergänzenden Inhalten sollte anhand der erwarteten Bildschirmgröße und Platzierung im physischen Raum getestet werden.

* **Persistenz**: Der vernetzte Zustand des Player-Geräts sollte nie Einfluss darauf haben, ob dem Benutzer digitale Erlebnisse bereitgestellt werden. Der Player muss so konzipiert sein, dass ein oder mehrere Erlebnisse immer bestehen bleiben und unabhängig vom Status des Player-Geräts bereitgestellt werden können.

* **Medienschleifensegmentierung**: Durch die Konfiguration der einzelnen Player-Geräte mit einem eigenen Loopsegment wird sichergestellt, dass lokalisierte Inhalte innerhalb des gesamten digitalen Erlebnisses einfach erstellt, veröffentlicht und wiedergegeben werden können. Medienelemente, die in eingebetteten Sequenzkanälen enthalten sind, werden dem vorherigen Schleifensegment hinzugefügt und bieten die Möglichkeit, ein Medienschleifensegment für jede Ortsgruppierung als Ziel festzulegen.

* **Interaktive Erlebnisse**: Eine Touch-fähige Kiosk-Anwendung kann mit AEM und dem SPA-Editor in einem Bildschirmkanal erstellt und bereitgestellt werden. Es empfiehlt sich, konsistente omnichannel-Designeigenschaften anzuwenden, einen Inaktivitätszeitgeber zum Zurücksetzen des Erlebnisses und einen klaren Aktionsaufruf für die Aufgaben, die die Anwendung ausführen kann. Die Einstiegsseite sollte aus wichtigen digitalen Elementen bestehen, die dazu bestimmt sind, einen Wert zu vermitteln, den Benutzer zum Bildschirm anzuziehen und den Benutzer zur Interaktion aufzufordern.

AEM Screens bietet ein Framework zum Bereitstellen von Inhalten auf physischen Geräten. Inhalte werden Kanälen in Bildschirmen zugewiesen, die Medieninhalte oder Touchscreen-Anwendungen enthalten können. Innerhalb dieses Rahmens kann eine AEM-Site-Anwendung als Inhalt über einen Kanal bereitgestellt werden.

Bevor eine AEM-Site in einem Kanal in Bildschirmen abgelegt wird, muss sie für die verwendeten Abmessungen des Anzeigegeräts formatiert werden.

> [!NOTE]
>
> Viele AEM-Sites-Komponenten sind nicht mit AEM-Bildschirmen kompatibel. AEM Screens enthält viele eigene vordefinierte Komponenten, mit denen Sie digitale Erlebnisse erstellen können, ohne dass eine Anpassung erforderlich ist. Wenn die Projektanforderungen dies zulassen, verwenden Sie nach Möglichkeit die integrierte AEM Screens-Funktion.
