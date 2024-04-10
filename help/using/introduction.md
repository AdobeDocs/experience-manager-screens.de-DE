---
title: Einführung in [!UICONTROL AEM Screens]
description: Diese Seite enthält einen Einführungsabschnitt zu AEM Screens.
exl-id: 11781e0b-0aca-4d08-aaad-87a7aaf28c24
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 66%

---

# Einführung in AEM Screens {#introduction}

**AEM (Adobe Experience Manager) Screens** ist eine Digital Signage-Lösung, mit der Sie dynamische und interaktive digitale Erlebnisse erstellen, veröffentlichen und wiedergeben können. Es umfasst verschiedene Arten von lokalen Anzeigebildschirmen in Abstimmung mit einer umfassenden kanalübergreifenden digitalen Marketingstrategie.

Mit AEM Screens können Sie Folgendes erstellen:

* **dedizierte digitale Menüboards**
* **Produktempfehlungen**
* **Lifestyle-Hintergrundbilder**

Screens bietet außerdem viele einzigartige Anwendungen für Kunden und Mitarbeiter, die auf der Domäne basieren, in der sie bereitgestellt werden, z. B.:

* **Interaktive Displays**
* **Wegweiser**
* **Branding**
* **Zusätzliches Ambiente für Ihre Umgebung**

Das Einrichten und Verwalten eines Digital-Signage-Netzwerks mit AEM Screens ist einfach und intuitiv. Eine Player-Anwendung hostet Inhaltskanäle, die von Kunden oder Implementierungspartnern für AEM Screens erstellt wurden. *Standorte* eine vordefinierte Standorthierarchie verwalten und Anzeigen enthalten. Jedes *Display* verfügt über ein Dashboard, in dem unterschiedliche angeschlossene Geräte und Bildschirme angezeigt werden. Inhalte für AEM Screens werden in *Kanälen* verwaltet. Mit dem *AEM Screens Player* lassen sich in Kanälen vorhandene Inhalte auf Displays darstellen.



>[!NOTE]
>
>Ausführliche Informationen zu den verschiedenen Funktionen bei der Entwicklung und Verwaltung von AEM Screens-Projekten finden Sie unter **[AEM Screens-Benutzerhandbuch](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/aem-screens-introduction)**.

## AEM Sites versus AEM Screens {#aem-sites-screens}

>[!NOTE]
>
>Wenn Ihr Implementierungsteam Erfahrung mit AEM Sites-Anwendungen hat, ist es wichtig, dass es den Unterschied zwischen AEM Sites und AEM Screens kennt.

AEM Screens ist eine einheitliche Authoring-/Wiedergabeplattform für die Bereitstellung von Inhalten auf Digital-Signage-Geräten in öffentlichen Räumen. Der Autor des Erlebnisses sollte zwar um Konsistenz im Web und an lokalen Standorten bemüht sein. Darüber hinaus gibt es aber Unterschiede, die beachtet werden sollten.

* **Verweilzeit**: In der Regel dienen Webseiten dazu, eine Vielzahl von Informationen bereitzustellen, die über einen relativ langen Zeitraum konsumiert werden können. Im Gegensatz dazu sollten digitale Vor-Ort-Erlebnisse die Bedürfnisse des Betrachters vorwegnehmen sowie klare und präzise Anweisungen geben, wie und warum der Benutzer interagieren sollte. Dies führt zu zielgerichteteren, kuratierten und kontextbezogenen Erlebnissen.

* **Betrachtungsabstand**: Betrachtungsabstände sind länger oder weiter entfernt als der typische Abstand, den Benutzer mit einer Website erleben. Daher sollte die Textgröße meist größer ausfallen; zudem sollte der Abstand zwischen Text, Bildern und anderen ergänzenden Inhalten mit Blick auf die erwartete Bildschirmgröße und Platzierung im physischen Raum getestet werden.

* **Persistenz**: Der Verbindungsstatus des Player-Geräts sollte niemals Einfluss darauf haben, ob dem Benutzer digitale Erlebnisse bereitgestellt werden. Der Player muss so konzipiert sein, dass stets ein oder mehrere Erlebnisse vorhanden sind und unabhängig vom Verbindungsstatus des Player-Geräts bereitgestellt werden können.

* **Segmentierung von Medienschleifen**: Durch die Konfiguration jedes Player-Geräts für ein eigenes Schleifensegment wird sichergestellt, dass lokalisierte Inhalte innerhalb des gesamten digitalen Erlebnisses einfach erstellt, veröffentlicht und wiedergegeben werden können. Medien-Assets, die in integrierten Sequenzkanälen enthalten sind, werden dem vorherigen Schleifensegment hinzugefügt und bieten die Möglichkeit, für jede Standortgruppe ein Medienschleifensegment als Ziel festzulegen.

* **Interaktive Erlebnisse**: Eine Touch-optimierte Kiosk-Anwendung kann in einem Screens-Kanal mit AEM und dem SPA-Editor erstellt und bereitgestellt werden. Empfohlen wird die Anwendung konsistenter Omni-Channel-Design-Eigenschaften, eines Inaktivitäts-Timers zum Zurücksetzen des Erlebnisses und eines klaren Handlungsaufrufs dazu, welche Aufgaben die Anwendung ausführen kann. Die Landingpage sollte aus zentralen digitalen Elementen bestehen, die dazu dienen, Wert zu vermitteln sowie Benutzer an den Bildschirm zu locken und zur Interaktion einzuladen.

AEM Screens bietet ein Framework zum Bereitstellen von Inhalten auf physischen Geräten. Inhalte werden in Screens Kanälen zugewiesen, die Medieninhalte oder Touchscreen-Anwendungen enthalten können. In diesem Framework kann eine AEM Sites-Anwendung als Inhalt über einen Kanal bereitgestellt werden.

Bevor eine AEM Site in Screens in einem Kanal abgelegt werden kann, muss sie für die Abmessungen des Anzeigegeräts formatiert werden.

>[!NOTE]
>Viele Komponenten von AEM Sites sind nicht mit AEM Screens kompatibel. AEM Screens ist mit vielen vordefinierten Komponenten ausgestattet, sodass Sie digitale Erlebnisse auch ohne Anpassungen kreieren können. Wenn es die Projektanforderungen zulassen, sollten Sie nach Möglichkeit integrierte AEM Screens-Funktionen verwenden.
