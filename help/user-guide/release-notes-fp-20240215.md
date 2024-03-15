---
title: Versionshinweise für Screens Feature Pack 20240215
description: Auf dieser Seite finden Sie Informationen zum AEM Screens Feature Pack 20240215, das am 15. Februar 2024 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
source-git-commit: d5b94814df33f00e23fcd22e85e50d6f02947d45
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---

# Versionshinweise für Feature Pack 20240215 {#release-notes-for-screens-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version (6.5) von Adobe Experience Manager (AEM 6.5) durchzuführen. Die neuesten Versionsinformationen finden sich [hier](https://experienceleague.adobe.com/docs/experience-manager-65/content/release-notes/release-notes.html?lang=de)

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 11,3 für AEM Screens wurde veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.11.3 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Gehen Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP11.3** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für das AEM Screens Feature Pack 20240215 ist der 15. Februar 2024.

### Neue Funktionen {#what-is-new}

Diese Version beinhaltet nur Sicherheits-Fehlerbehebungen.

### Fehlerbehebungen {#bug-fixes}

* Die Überprüfung beim Umschalter wurde aus dem zuvor in FP11.1 für XSS bereitgestellten Fix unter `libs/screens/dcc/components/clientlibs/actions/cq.screens.dcc.openLink.js` entfernt. (SCRNS-3459)

* XSS-Problem in `libs/screens/dcc/components/clientlibs/columnviewnavigatorshim.js`. (SCRNS-3973)
