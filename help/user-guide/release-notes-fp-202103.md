---
title: Versionshinweise für Feature Pack 202103
description: Auf der Seite finden Sie die Versionshinweise für Feature Pack 202103.
translation-type: ht
source-git-commit: dfbf904c1f23f7e41a9d65a270c5ca667ddcdb31
workflow-type: ht
source-wordcount: '389'
ht-degree: 100%

---


# Versionshinweise für Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 7 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.7 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP7** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202103 ist der 5. März 2021.

### Neue Funktionen {#what-is-new}

* **AEM Screens – Automatische Registrierung von Playern**

   Die manuelle Massenregistrierung von Tausenden von Playern ist sehr mühsam und verursacht zusätzliche Zeitanforderungen und Kosten. Um diesen Prozess zu vereinfachen, können Sie mit der automatischen Registrierung von Playern einen vorinstallierten Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

   Weitere Informationen finden Sie unter [Automatische Registrierung von Playern](/help/user-guide/auto-registration-players.md).


* **Massenbereitstellung von Android-Playern mit Enterprise Mobility Management**

   Bei der Massenbereitstellung von Android-Playern ist es mühsam, jeden einzelnen Player manuell bei AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) wie VMWare Airwatch, MobileIron oder Samsung Knox für die Remote-Bereitstellung und -Verwaltung Ihrer Bereitstellung zu verwenden. Der AEM Screens-Android-Player unterstützt den Branchenstandard EMM AppConfig, um eine Remote-Bereitstellung zu ermöglichen.

   Weitere Informationen finden Sie unter [Massenbereitstellung von Android-Playern mit Enterprise Mobility Management](/help/user-guide/using-emm-bulkprovision-android-player.md).


### Fehlerbehebungen {#bug-fixes}

* Verbesserte Leistung bei der Berechnung von `clientlib` und `asset hashes`.

* Die SmartSync-Migration würde den Player beschädigen, wenn der Cache nicht ungültig gemacht würde.

* Offline-Caches wurden nicht erstellt, wenn die Zuweisung *OfflineConfig* enthielt.

* Aktualisierungen des Tizen-Players, die fehlschlugen, weil die Referrer-Richtlinie „strict-origin-when-cross-origin“ nicht unterstützt wird.

* Das Ändern des Feldes *Wiederholungen* des Zeitplans des zugewiesenen Kanals führte zu Fehlern in der Benutzeroberfläche.

* Die Aktualisierung von Offline-Inhalten schlug mit Abfrageausnahmen fehl.

* Die Zeitverzögerung zwischen Übergängen während der Interaktion im interaktiven Erlebnis wurde jetzt behoben.

* Eine fehlgeschlagene Anfrage zur Aktualisierung der Konfiguration führte zu einem leeren Bildschirm.

### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 7 verfügbar:

* Chrome OS
* Windows
* Linux

#### AEM Screens-Player-Downloads {#aem-screens-player-downloads}

Navigieren Sie zu **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neusten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
