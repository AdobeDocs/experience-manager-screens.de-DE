---
title: Versionshinweise für Feature Pack 202103
description: Erfahren Sie mehr über AEM Screens Feature Pack 202103, das am 5. März 2021 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: a8741cc7-de4f-4e5a-b69e-852a43597123
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 24%

---

# Versionshinweise für Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe empfiehlt ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM). AEM Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 7 wurde für AEM Screens veröffentlicht.

Sie können das neueste Feature Pack für AEM Screens 6.5.7 von der [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) die Verwendung Ihrer Adobe ID. Navigieren Sie zum **Adobe Experience Manager** Registerkarte und suchen Sie nach **Screens** , um das neueste Feature Pack mit dem Titel **AEM 6.5 Screens FP7**.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202103 ist der 5. März 2021.

### Neue Funktionen {#what-is-new}

* **AEM Screens – Automatische Registrierung von Playern**

  Das manuelle Registrieren von Tausenden von Playern mit Massenregistrierung ist umständlich und bringt Zeit und Kosten. Um diesen Vorgang zu vereinfachen, können Sie mit der Funktion Automatische Registrierung von Playern in AEM einen vorab freigegebenen Schlüssel angeben. Dieser Schlüssel kann entweder über eine Konfigurationsdatei oder eine Mobile Device Management (MDM)-Lösung in einen Player bereitgestellt werden.

  Siehe [Automatische Registrierung von Playern](/help/user-guide/auto-registration-players.md) für weitere Details.


* **Massenbereitstellung von Android™-Player mithilfe von Enterprise Mobility Management**

  Bei der Massenbereitstellung des Android™-Players wird es mühsam, jeden Player manuell bei AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) zu verwenden, z. B. `VMWare Airwatch`, `MobileIron`oder `Samsung Knox` , um Ihre Implementierung remote bereitzustellen und zu verwalten. Der AEM Screens Android™ Player unterstützt die standardmäßige EMM AppConfig-Lösung, die die Remote-Bereitstellung ermöglicht.

  Siehe [Massenbereitstellung von Android™-Player mithilfe von Enterprise Mobility Management](/help/user-guide/implementing-android-player.md#implementation) für weitere Details.


### Fehlerbehebungen {#bug-fixes}

* Verbesserte Leistung bei der Berechnung von `clientlib` und `asset hashes`.

* Die Migration von SmartSync würde den Player beschädigen, wenn der Cache nicht invalidiert wurde.

* Offline-Caches wurden nicht erstellt, wenn die Zuweisung *OfflineConfig* enthielt.

* Aktualisierungen für `Tizen` Player, der fehlschlug, weil die Richtlinie &quot;referrer&quot;strikt auf den Ursprung ausgerichtet ist, wenn der Ursprung zwischen verschiedenen Elementen nicht unterstützt wird.

* Zeitplan des zugewiesenen Kanals ändern *Wiederholungen* -Feld die Benutzeroberfläche beschädigte.

* Die Aktualisierung von Offline-Inhalten schlug mit Abfrageausnahmen fehl.

* Die zeitliche Verzögerung zwischen Transitionen während der Interaktion in einem interaktiven Erlebnis wurde jetzt behoben.

* Eine fehlgeschlagene Konfigurationsaktualisierungsanfrage verursachte leere Bildschirme.

### Veröffentlichte AEM Screens-Player

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 7 verfügbar:

* Chrome OS
* Windows
* Linux®

#### AEM Screens-Player-Downloads 

Informationen zum Herunterladen des neuesten AEM Screens-Players und zu weiteren Fehlerbehebungen finden Sie unter **[AEM Screens Player-Downloads](https://download.macromedia.com/screens/index.html)**.
