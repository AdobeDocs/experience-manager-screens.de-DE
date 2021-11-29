---
title: Versionshinweise für Feature Pack 202105
description: „Auf dieser Seite finden Sie Informationen zum AEM Screens Feature Pack 202105, das am 4. Juni 2021 veröffentlicht wurde.“
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: fc210d9d-5fac-4147-849d-182ffbaf0a5e
source-git-commit: 02bc399d61f5666918caad9fce3d69d63f0782d7
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 94%

---

# Versionshinweise für Feature Pack 202105 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 8 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.8 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP8** herunterzuladen.

>[!IMPORTANT]
>Sie müssen eine Mindestversion von AEM 6.5 Feature Pack 8 installieren, damit der AMS-Connector funktioniert, sobald Sie die Pakete installiert haben `screens-cloud-ams-pkg-0.0.20`, `screens-cloud-ams-pkg-0.0.16` und `screens core bundles`.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202105 ist der 4. Juni 2021.

### Neue Funktionen {#what-is-new}

* **Sperren von Seiten in einem AEM Screens-Kanal**

   AEM Screens unterstützt jetzt *Sperren einer Seite*, wie bereits in AEM Sites implementiert. Adobe Experience Manager (AEM) bietet Ihnen die Möglichkeit, eine Seite zu sperren, sodass niemand außer Ihnen den Inhalt bearbeiten kann. Dies ist hilfreich, wenn Sie eine Vielzahl von Bearbeitungen an einer bestimmten Seite vornehmen oder wenn Sie eine Seite für eine kurze Zeit einfrieren möchten.

* **Benennen des AEM Screens Player-Geräts**

   Die AEM Screens-Player bieten jetzt die Möglichkeit, einen Gerätenamen an Adobe Experience Manager (AEM) zu senden.
Standardmäßig wird bei der Massenregistrierung eines Geräts ein vom System generierter Benutzername in das Titelfeld eingegeben. Alternativ kann ein Kunde ein Asset-Tag oder einen anderen benutzerfreundlichen Namen verwenden, damit es in AEM sichtbar ist und damit es einfacher ist, geeignete Inhalte zuzuweisen.

   In der folgenden Dokumentation erfahren Sie, wie Sie den Namen in jedem unterstützten Betriebssystem konfigurieren:

   * [Android](/help/user-guide/implementing-android-player.md#name-android)
   * [Windows](/help/user-guide/implementing-windows-player.md#name-windows)
   * [Tizen](/help/user-guide/tizen-player.md#name-tizen)
   * [Chrome OS](/help/user-guide/implementing-chrome-os-player.md#name-chrome)

* **Manifestgenerierung**

   Schnellere Generierung eines Kanalmanifests mit verbesserter Leistung, z. B. weniger Ressourcen auf dem Server zuzuweisen.

### Fehlerbehebungen {#bug-fixes}

* Wenn der Player auf einen Kanal mit einer dynamischen eingebetteten Sequenz umschaltet, wird kein schwarzer Bildschirm mehr angezeigt.
* Die Screens-Player blockieren jetzt den Wechsel zu einem fehlerhaften Kanal, wodurch der 404-Fehler oder eine Seite mit einer Fehlermeldung vermieden wird.

### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 8 verfügbar:

* ChromeOS
* Windows
* Tizen
* Android
* Linux

#### AEM Screens-Player-Downloads  {#aem-screens-player-downloads}

Gehen Sie zu **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neusten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
