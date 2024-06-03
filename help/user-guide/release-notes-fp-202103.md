---
title: Versionshinweise für Feature Pack 202103
description: Erfahren Sie mehr über AEM Screens Feature Pack 202103, das am 5. März 2021 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: a8741cc7-de4f-4e5a-b69e-852a43597123
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: ht
source-wordcount: '389'
ht-degree: 100%

---

# Versionshinweise für Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe empfiehlt, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. AEM Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 7 für AEM Screens wurde veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.7 steht auf dem [Software-Verteilungsportal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP7** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202103 ist der 5. März 2021.

### Neue Funktionen {#what-is-new}

* **AEM Screens – Automatische Registrierung von Playern**

  Eine manuelle Massenregistrierung von Tausenden von Playern ist mühsam und verursacht zusätzliche Zeitanforderungen und Kosten. Um diesen Vorgang zu vereinfachen, können Sie mit der Funktion zur automatischen Registrierung von Playern in AEM einen vorab freigegebenen Schlüssel angeben. Dieser Schlüssel kann entweder über eine Konfigurationsdatei oder eine Mobile Device Management (MDM)-Lösung für einen Player bereitgestellt werden.

  Weitere Informationen finden Sie unter [Automatische Registrierung von Playern](/help/user-guide/auto-registration-players.md).


* **Massenbereitstellung von Android™-Playern mit Enterprise Mobility Management**

  Bei der Massenbereitstellung von Android™-Playern ist es mühsam, jeden einzelnen Player manuell bei AEM zu registrieren. Es wird dringend empfohlen, eine EMM(Enterprise Mobility Management)-Lösung wie `VMWare Airwatch`, `MobileIron` oder `Samsung Knox` für die Remote-Bereitstellung und -Verwaltung Ihrer Bereitstellung zu verwenden. Der AEM Screens-Android™-Player unterstützt den Branchenstandard EMM AppConfig, um eine Remote-Bereitstellung zu ermöglichen.

  Weitere Informationen finden Sie unter [Massenbereitstellung von Android™-Playern mit Enterprise Mobility Management](/help/user-guide/implementing-android-player.md#implementation).


### Fehlerbehebungen {#bug-fixes}

* Verbesserte Leistung bei der Berechnung von `clientlib` und `asset hashes`.

* Die SmartSync-Migration würde den Player bei ausbleibender Cache-Invalidierung beschädigen.

* Offline-Caches wurden nicht erstellt, wenn die Zuweisung *OfflineConfig* enthielt.

* Aktualisierungen des `Tizen`-Players, die fehlschlugen, weil die Referrer-Richtlinie „strict-origin-when-cross-origin“ nicht unterstützt wird.

* Das Ändern des Felds *Wiederholungen* des Zeitplans des zugewiesenen Kanals führte zu Fehlern in der Benutzeroberfläche.

* Die Aktualisierung von Offline-Inhalten schlug mit Abfrageausnahmen fehl.

* Die Verzögerung zwischen Übergängen während der Interaktion in einem interaktiven Erlebnis wurde nun behoben.

* Eine fehlgeschlagene Konfigurationsaktualisierungsanfrage verursachte leere Bildschirme.

### Veröffentlichte AEM Screens-Player

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 7 verfügbar:

* Chrome OS
* Windows
* Linux®

#### AEM Screens-Player-Downloads

Navigieren Sie zur Seite **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neuesten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
