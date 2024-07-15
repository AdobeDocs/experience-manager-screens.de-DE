---
title: Versionshinweise für Screens Feature Pack 202401
description: Erfahren Sie mehr über das AEM Screens Feature Pack 202401, das am 2. Januar 2024 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: 9879f339-e70f-446d-acd3-380016269f27
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 100%

---

# Versionshinweise für Feature Pack 202401 {#release-notes-for-screens-feature-pack}

>[!CAUTION]
>Adobe empfiehlt, ein Upgrade auf die neueste Version (6.5) von Adobe Experience Manager (AEM 6.5) durchzuführen. Die neuesten Versionsinformationen finden Sie [hier](https://experienceleague.adobe.com/de/docs/experience-manager-65/content/release-notes/release-notes).

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 11,1 für AEM Screens wurde veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.11.1 steht im [Software-Verteilungsportal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit der Bezeichnung **AEM 6.5 Screens FP11.1** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202204 ist der 2. Januar 2024.

### Neue Funktionen {#what-is-new}

Diese Version beinhaltet nur Sicherheits-Fehlerbehebungen.

### Fehlerbehebungen {#bug-fixes}

* XSS-Problem im Feld „Text für Leerlauf“ des AEM Screens-Geräts. (SCRNS-2614)

* XSS-Problem in `screens/dashboard/device.html` über das Aktionsdialogfeld `Clear cache`. (SCRNS-2632)

* XSS-Problem in der Screens-Player-Konfiguration in `libs/screens/player/browser/firmware.html`. (SCRNS-2652)

* Gespeichertes XSS im Gerätetitel wird ausgelöst, wenn ein Gerät gelöscht wird. (SCRNS-2653)

* XSS-Problem in `/libs/screens/core/components/device/info.json.html`. (SCRNS-2659)

* Reflektiertes XSS mit dem Parameter `item` in `/screens/register-device-wizard.html`. (SCRNS-2670)

* Reflektiertes XSS in `screens/dashboard/device.html` über den Parameter `returnPage`. (SCRNS-3056)

* Offene Umleitung auf assign-device-wizard.html. (SCRNS-3444)

* Offene Umleitung auf das Geräte-Dashboard. (SCRNS-3443)

* XSS-Problem in `libs/screens/dcc/components/clientlibs/actions/cq.screens.dcc.openLink.js`. (SCRNS-3459)

* Behoben: Fehlende Schaltflächen für „Wiederholungszeitplan“ und „Zeitplan hinzufügen“: Ein Problem in der Kanalplanung wurde entdeckt. (SCRNS-2739)
