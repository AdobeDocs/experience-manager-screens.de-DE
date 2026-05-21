---
title: Versionshinweise für Screens Feature Pack 20250327
description: Erfahren Sie mehr über das AEM Screens Feature Pack 20250327, das am Freitag, 27. März 2025 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: cadd83cd-fe64-436d-b3fd-6d72b9565885
TQID: https://experienceleague.adobe.com/q6KAClMHbAULOEumQlx5-FdaaVmAcMOCL8m6KWIB458
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 0b0bfcd803c3da9298122200a0a1715fc2d5e49c
workflow-type: tm+mt
source-wordcount: 270
ht-degree: 39%

---

# Versionshinweise für Feature Pack 20250327 {#release-notes-for-screens-feature-pack}

>[!CAUTION]
>Adobe empfiehlt, ein Upgrade auf die neueste Version (6.5) von Adobe Experience Manager (AEM 6.5) durchzuführen. Die neuesten Versionsinformationen finden sich [hier](https://experienceleague.adobe.com/de/docs/experience-manager-65/content/release-notes/release-notes).
>Adobe empfiehlt, FP11.6 mit SP(ServicePack) >= 21 zu verwenden.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 11,6 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.11.6 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) zum Download zur Verfügung. Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP11.6}**.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 20250327 ist der Freitag, 27. März 2025.

### Neue Funktionen {#what-is-new}

* Diese Version behebt den Paketkonflikt, dem Benutzer mit Service Pack 21 und höher ausgesetzt sind.

* Diese Version behebt das Problem mit Kartenansichten mit SP22 und höher.

* **Aktualisierung zu AEM Screens-Playern**
   * Der Linux-basierte AEM Screens-Player wird offiziell nicht mehr unterstützt. Benutzern wird empfohlen, zu einem anderen Betriebssystem zu migrieren, das von AEM Screens unterstützt wird.
   * Am Android-basierten AEM Screens-Player werden keine weiteren Aktualisierungen oder Verbesserungen vorgenommen. Benutzende werden ermutigt, auf ein alternatives Betriebssystem zu migrieren, das von AEM Screens unterstützt wird.

### Fehlerbehebungen {#bug-fixes}

* Paketkonflikt mit Service Pack 21 und Screens Feature Pack. (SCRNS-4638)

* Screens-Dashboard funktioniert nicht. (SCRNS-4749)

* XSS-Problem unter /libs/screens/dcc/components/dashboard/clientlibs/device-clear-cache.js (SCRNS-4761)
