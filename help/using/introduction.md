---
title: Einführung in AEM Screens
description: Erfahren Sie mehr über AEM Screens und was es für Sie tun kann.
exl-id: 11781e0b-0aca-4d08-aaad-87a7aaf28c24
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 82%

---

# Einführung in AEM Screens {#introduction}

**AEM Screens** ist eine Digital Signage-Lösung, mit der Sie dynamische und interaktive digitale Erlebnisse erstellen, veröffentlichen und wiedergeben können. Dies umfasst verschiedene Arten von lokalen Anzeigebildschirmen in Abstimmung mit einer umfassenden kanalübergreifenden digitalen Marketing-Strategie.

Mit AEM Screens können Sie Folgendes erstellen:

* **dedizierte digitale Menüboards**
* **Produktempfehlungen**
* **Lifestyle-Hintergrundbilder**

Screens bietet außerdem viele einzigartige Anwendungen für Kunden und Mitarbeiter, die auf der Domäne basieren, in der die Anwendungen bereitgestellt werden, z. B.:

* **Interaktive Displays**
* **Wegweiser**
* **Branding**
* **Zusätzliches Ambiente für Ihre Umgebung**

Das Einrichten und Verwalten eines Digital-Signage-Netzwerks mit AEM Screens ist einfach und intuitiv. Eine Player-Anwendung hostet Inhaltskanäle, die von Kunden oder Implementierungspartnern für AEM Screens erstellt wurden. *Standorte* verwalten eine vordefinierte Standorthierarchie und beinhalten Anzeigen. Jedes *Display* verfügt über ein Dashboard, in dem unterschiedliche angeschlossene Geräte und Bildschirme angezeigt werden. Inhalte für AEM Screens werden in *Kanälen* verwaltet. Mit dem *AEM Screens Player* lassen sich in Kanälen vorhandene Inhalte auf Displays darstellen.

>[!NOTE]
>
>Ausführliche Informationen zu den verschiedenen Funktionen bei der Entwicklung und Verwaltung von AEM Screens-Projekten finden Sie in der **[AEM Screens-Benutzerhandbuch](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/aem-screens-introduction)**.

## AEM Sites und AEM Screens {#aem-sites-screens}

>[!NOTE]
>
>Wenn Ihr Implementierungsteam Erfahrung mit AEM Sites-Anwendungen hat, ist es wichtig, dass es den Unterschied zwischen AEM Sites und AEM Screens kennt.

AEM Screens ist eine einheitliche Authoring-/Wiedergabeplattform für die Bereitstellung von Inhalten auf Digital-Signage-Geräten in öffentlichen Räumen. Der Autor des Erlebnisses sollte zwar um Konsistenz im Web und an lokalen Standorten bemüht sein. Darüber hinaus gibt es aber Unterschiede, die beachtet werden sollten.

* **Verweildauer**: In der Regel werden Web-Seiten so gestaltet, dass sie eine Vielzahl von Informationen bereitstellen, die sich über einen relativ langen Zeitraum nutzen lassen. Im Gegensatz dazu sollten digitale Vor-Ort-Erlebnisse die Bedürfnisse der Person, die sie betrachtet, vorwegnehmen sowie klare und präzise Anweisungen geben, wie und warum sie interagieren sollte. Diese Aufmerksamkeit führt zu zielgerichteteren, kuratierten und kontextbezogenen Erlebnissen.

* **Betrachtungsabstand**: Betrachtungsabstände sind größer oder weiter als der typische Abstand, den Benutzende bei einer Website erleben. Daher sollte die Textgröße meist größer ausfallen; zudem sollte der Abstand zwischen Text, Bildern und anderen ergänzenden Inhalten mit Blick auf die erwartete Bildschirmgröße und Platzierung im physischen Raum getestet werden.

* **Persistenz**: Der Verbindungsstatus des Player-Geräts sollte niemals Einfluss darauf haben, ob den Benutzenden digitale Erlebnisse bereitgestellt werden oder nicht. Der Player muss so konzipiert sein, dass stets ein oder mehrere Erlebnisse vorhanden sind und unabhängig vom Verbindungsstatus des Player-Geräts bereitgestellt werden können.

* **Segmentierung von Medienschleifen**: Durch Konfiguration einzelner Player-Geräte mit eigenen Schleifensegmenten wird sichergestellt, dass lokalisierte Inhalte innerhalb des übergeordneten digitalen Erlebnisses einfach erstellt, veröffentlicht und wiedergegeben werden können. Medien-Assets, die in integrierten Sequenzkanälen enthalten sind, werden dem vorherigen Schleifensegment hinzugefügt und bieten die Möglichkeit, für jede Standortgruppe ein Medienschleifensegment als Ziel festzulegen.

* **Interaktive Erlebnisse**: Mit AEM und dem SPA-Editor kann in einem Screens-Kanal eine Touch-fähige Kiosk-Anwendung erzeugt und bereitgestellt werden. Empfohlen wird die Anwendung konsistenter Omni-Channel-Design-Eigenschaften, eines Inaktivitäts-Timers zum Zurücksetzen des Erlebnisses und eines klaren Handlungsaufrufs dazu, welche Aufgaben die Anwendung ausführen kann. Die Landingpage sollte aus zentralen digitalen Elementen bestehen, die dazu dienen, Wert zu vermitteln sowie Benutzer an den Bildschirm zu locken und zur Interaktion einzuladen.

AEM Screens bietet ein Framework zum Bereitstellen von Inhalten auf physischen Geräten. Inhalte werden in Screens Kanälen zugewiesen, die Medieninhalte oder Touchscreen-Anwendungen enthalten können. In diesem Framework kann eine AEM Sites-Anwendung als Inhalt über einen Kanal bereitgestellt werden.

Eine AEM Site muss für die Verwendung mit den Abmessungen des Anzeigegeräts formatiert sein. Dies sollte vor dem Ablegen in einem Kanal in Screens durchgeführt werden.

>[!NOTE]
>Viele Komponenten von AEM Sites sind nicht mit AEM Screens kompatibel. AEM Screens ist mit vielen vordefinierten Komponenten ausgestattet, sodass Sie digitale Erlebnisse auch ohne Anpassungen kreieren können. Wenn es die Projektanforderungen zulassen, sollten Sie nach Möglichkeit integrierte AEM Screens-Funktionen verwenden.
