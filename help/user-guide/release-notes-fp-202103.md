---
title: Versionshinweise für Feature Pack 202103
description: Auf der Seite werden die Versionshinweise für das Feature Pack 202103 hervorgehoben.
translation-type: tm+mt
source-git-commit: 3701c6f72ceadb5b61cd608503a95af11d631c49
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 36%

---


# Versionshinweise für Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 7 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.7 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP7** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Release Date for AEM Screens Feature Pack 202103 ist der 05. März 2021.

### Neue Funktionen {#what-is-new}

* **AEM Screens Automatische Registrierung von Spielern**

   Massen Registrieren Tausende von Spielern manuell ist sehr schwerfällig und erhöht Zeit und Kosten. Um diesen Vorgang zu vereinfachen, können Sie mit der Funktion zur automatischen Registrierung von Playern einen vorab freigegebenen Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

   Weitere Informationen finden Sie unter [Automatische Registrierung von Spielern](/help/user-guide/auto-registration-players.md).


* **Massenbereitstellung von Android Player mit Enterprise Mobility Management**

   Bei der Massenbereitstellung des Android-Players wird es mühsam, jeden einzelnen Player manuell mit AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) wie VMWare Airwatch, MobileIron oder Samsung Knox zu verwenden, um Ihre Bereitstellung remote bereitzustellen und zu verwalten. AEM Screens Android Player unterstützt den Branchenstandard EMM AppConfig, um die Bereitstellung per Remote-Zugriff zu ermöglichen.

   Weitere Informationen finden Sie unter [Massenbereitstellung von Android Player mit Enterprise Mobility Management](/help/user-guide/using-emm-bulkprovision-android-player.md).


### Fehlerbehebungen {#bug-fixes}

* Verbesserte Leistung für die Berechnung von `clientlib` und `asset hashes`.

* Die Migration von SmartSync würde den Player beschädigen, wenn der Cache nicht ungültig wäre.

* Offline-Caches wurden nicht erstellt, wenn die Zuweisung *OfflineConfig* enthielt.

* Updates des Zehn-Players, die fehlschlugen, weil die strikte Herkunft-wenn-Cross-Herkunft von Werbern nicht unterstützt wird.

* Durch das Ändern des Zeitplans des zugewiesenen Kanals *Wiederholungen* wurde die Benutzeroberfläche beschädigt.

* Das Aktualisieren von Offlineinhalten schlug mit Ausnahme der Abfrage fehl.

* Die Zeitverzögerung zwischen Transitionen während der Interaktion im interaktiven Erlebnis wurde jetzt behoben.

* Fehler bei der Aktualisierungsanforderung der Konfiguration verursachte den leeren Bildschirm.

### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 7 verfügbar:

* Chrome OS
* Windows
* Tizen
* Linux

#### AEM Screens-Player-Downloads {#aem-screens-player-downloads}

Navigieren Sie zu **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neusten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
