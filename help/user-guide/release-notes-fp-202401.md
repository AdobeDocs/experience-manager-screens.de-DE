---
title: Versionshinweise für Screens Feature Pack 202401
description: Auf dieser Seite erhalten Sie Informationen zu AEM Screens Feature Pack 202401, das am 2. Januar 2024 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
source-git-commit: e172d2a4a3d2c1f3b555edc8f8ea41b663fc0a30
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 7%

---

# Versionshinweise für Feature Pack 202401 {#release-notes-for-screens-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von 6.5 Adobe Experience Manager (AEM 6.5) durchzuführen. Wir erhalten die neuesten Versionsinformationen von [here](https://experienceleague.adobe.com/docs/experience-manager-65/content/release-notes/release-notes.html?lang=en)

## Verfügbarkeit {#availability}

AEM Screens hat AEM 6.5 Feature Pack 11.1 veröffentlicht.

Sie können das neueste Feature Pack für AEM Screens 6.5.11.1 von der [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) die Verwendung Ihrer Adobe ID. Navigieren Sie zu **Adobe Experience Manager** Registerkarte und suchen Sie nach **Screens** , um das neueste Feature Pack mit dem Titel **AEM 6.5 Screens FP11.1**.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202204 ist der 2. Januar 2024.

### Neue Funktionen {#what-is-new}

Diese Version umfasst nur Sicherheitskorrekturen.

### Fehlerbehebungen {#bug-fixes}

* XSS-Problem auf dem AEM Screens-Gerät &quot;Idle text&quot;-Feld. (SCRNS-2614)

* XSS-Problem bei `screens/dashboard/device.html` über die `Clear cache` Dialogfeld &quot;Aktion&quot;. (SCRNS-2632)

* XSS-Problem in der Screens-Player-Konfiguration unter `libs/screens/player/browser/firmware.html`. (SCRNS-2652)

* Gespeichertes XSS in Triggern mit Gerätetitel, wenn ein Gerät gelöscht wird. (SCRNS-2653)

* XSS-Problem bei `/libs/screens/core/components/device/info.json.html`. (SCRNS-2659)

* Reflektiertes XSS mit dem Parameter `item` at `/screens/register-device-wizard.html`. (SCRNS-2670)

* Reflektierte XSS in `screens/dashboard/device.html` über die `returnPage` -Parameter. (SCRNS-3056)

* Öffnen Sie die Umleitung auf assign-device-wizard.html. (SCRNS-3444)

* Öffnen Sie die Umleitung im Geräte-Dashboard. (SCRNS-3443)

* XSS-Problem bei `libs/screens/dcc/components/clientlibs/actions/cq.screens.dcc.openLink.js`. (SCRNS-3459)

* Behebung eines Fehlers für die Schaltflächen Intervallzeitplan und Zeitplan hinzufügen: Ein Problem wurde unter Kanalzeitplanung entdeckt. (SCRNS-2739)

#### AEM Screens-Player-Downloads   {#aem-screens-player-downloads}

Informationen zum Herunterladen des neuesten AEM Screens-Players finden Sie unter **[AEM Screens Player-Downloads](https://download.macromedia.com/screens/index.html)**.
