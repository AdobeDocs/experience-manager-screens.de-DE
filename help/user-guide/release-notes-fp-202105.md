---
title: Versionshinweise für Feature Pack 202105
description: Erfahren Sie mehr über AEM Screens Feature Pack 202105, das am 4. Juni 2021 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: fc210d9d-5fac-4147-849d-182ffbaf0a5e
source-git-commit: 4102c2b2291c92823a36f87f07d5b5ca87cfa48f
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 66%

---

# Versionshinweise für Feature Pack 202105 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. AEM Screens bietet Wartungs-Support für AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 8 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.8 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP8** herunterzuladen.

>[!IMPORTANT]
>Installieren Sie die Mindestversion von AEM 6.5 Feature Pack 8 für den AMS-Connector, um nach der Installation der Pakete zu funktionieren. `screens-cloud-ams-pkg-0.0.20`, `screens-cloud-ams-pkg-0.0.16`und die `screens core bundles`.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202105 ist der 4. Juni 2021.

### Neue Funktionen {#what-is-new}

* **Sperren von Seiten in einem AEM Screens-Kanal**

  AEM Screens unterstützt jetzt *Sperren einer Seite*, wie bereits in AEM Sites implementiert. Mit Adobe Experience Manager (AEM) können Sie eine Seite sperren, sodass niemand außer Ihnen den Inhalt ändern kann. Dies ist nützlich, wenn Sie zahlreiche Änderungen an einer bestimmten Seite vornehmen oder eine Seite für kurze Zeit einfrieren möchten.

* **Benennen des AEM Screens Player-Geräts**

  Die AEM Screens-Player bieten jetzt die Möglichkeit, einen Gerätenamen an Adobe Experience Manager (AEM) zu senden.
Standardmäßig wird bei der Massenregistrierung eines Geräts ein systemgenerierter Benutzername in das Titelfeld eingegeben. Alternativ kann ein Kunde ein Asset-Tag oder einen anderen benutzerfreundlichen Namen verwenden, damit es in AEM sichtbar ist und damit es einfacher ist, geeignete Inhalte zuzuweisen.

  Informationen zum Konfigurieren des Namens in den einzelnen unterstützten Betriebssystemen finden Sie in der folgenden Dokumentation:

   * [Android](/help/user-guide/implementing-android-player.md#name-android)
   * [Windows](/help/user-guide/implementing-windows-player.md#name-windows)
   * [Tizen](/help/user-guide/tizen-player.md#name-tizen)
   * [Chrome OS](/help/user-guide/implementing-chrome-os-player.md#name-chrome)

* **Manifestgenerierung**

  Schnellere Generierung von Kanalmanifest mit verbesserter Leistung, z. B. der Zuweisung von weniger Ressourcen auf dem Server.

### Fehlerbehebungen {#bug-fixes}

* Wenn der Player auf einen Kanal mit einer dynamischen eingebetteten Sequenz umschaltet, wird kein schwarzer Bildschirm mehr angezeigt.
* Die Screens-Player blockieren jetzt den Wechsel zu einem fehlerhaften Kanal, wodurch der 404-Fehler oder eine Seite mit einer Fehlermeldung vermieden wird.

### Veröffentlichte AEM Screens-Player

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 8 verfügbar:

* ChromeOS
* Windows
* Tizen
* Android™
* Linux®

#### AEM Screens-Player-Downloads 

Informationen zum Herunterladen des neuesten AEM Screens-Players und zu weiteren Fehlerbehebungen finden Sie unter **[AEM Screens Player-Downloads](https://download.macromedia.com/screens/index.html)**.
