---
title: Versionshinweise für Feature Pack 202103
description: Auf der Seite werden die Versionshinweise für das Feature Pack 202103 hervorgehoben.
translation-type: tm+mt
source-git-commit: 5f8938bfd092197391aefcd2d730d47fa06c214d
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 44%

---


# Versionshinweise für Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 7 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.7 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP7** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Release Date for AEM Screens Feature Pack 202103 ist der 08. März 2021.

### Neue Funktionen {#what-is-new}

* **AEM Screens Massenregistrierung und -zuweisung**

   Massen Registrieren Tausende von Spielern manuell ist sehr schwerfällig und erhöht Zeit und Kosten. Um diesen Vorgang zu vereinfachen, können Sie mit der Massenregistrierungsfunktion einen vorab freigegebenen Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

* **Massenbereitstellung von Android Player mit Enterprise Mobility Management**

   Bei der Massenbereitstellung des Android-Players wird es mühsam, jeden einzelnen Player manuell mit AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) wie VMWare Airwatch, MobileIron oder Samsung Knox zu verwenden, um Ihre Bereitstellung remote bereitzustellen und zu verwalten. AEM Screens Android Player unterstützt den Industriestandard EMM Appconfig, um eine Remote-Bereitstellung zu ermöglichen.

* **Seite in einem AEM Screens-Kanal sperren**

   AEM Screens unterstützt jetzt *Sperren einer Seite*, wie bereits in AEM Sites implementiert. Mit Adobe Experience Manager (AEM) können Sie eine Seite sperren, sodass niemand anders den Inhalt ändern kann. Dies ist hilfreich, wenn Sie eine Vielzahl von Bearbeitungen an einer bestimmten Seite vornehmen oder wenn Sie eine Seite für eine kurze Zeit einfrieren möchten.

### Fehlerbehebungen {#bug-fixes}

* Verbesserte Leistung für die Berechnung von `clientlib` und `asset hashes`.

* Die Migration von SmartSync würde den Player beschädigen, wenn der Cache nicht ungültig wäre.

* Offline-Caches wurden nicht erstellt, wenn die Zuweisung *OfflineConfig* enthielt.

### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 7 verfügbar:

* Chrome OS
* Windows
* Android
* Tizen
* Linux

#### AEM Screens-Player-Downloads {#aem-screens-player-downloads}

Navigieren Sie zu **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neusten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
