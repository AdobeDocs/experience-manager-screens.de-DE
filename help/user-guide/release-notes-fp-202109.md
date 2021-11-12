---
title: Versionshinweise für Feature Pack 202109
description: Auf dieser Seite finden Sie Informationen zum AEM Screens Feature Pack 202109, das am 23. September 2021 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: e1794013-59ce-4ddc-93c0-601668c75cd1
source-git-commit: c49cce64fe34e0611f086de5ac1c363589e3dc14
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 94%

---

# Versionshinweise für Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 9 für AEM Screens wurde veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.9 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Gehen Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP9** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das AEM Screens Feature Pack 202109 wurde am 23. September 2021 veröffentlicht.

### Neue Funktionen {#what-is-new}

* **Unterstützung von Miniaturansichten für Videos**

   AEM Screens unterstützt jetzt Miniaturansichten für Videos. Ein Inhaltsautor kann eine Miniaturansicht für Videos definieren, sodass das Bild als Platzhalter verwendet und die Inhaltswiedergabe und das Targeting ordnungsgemäß getestet werden können, während das eigentliche Video vom entsprechenden Team fertiggestellt wird. Das Bild kann auch verwendet werden, wenn die Wiedergabe des Videos fehlschlägt.
Weitere Informationen finden Sie unter [Unterstützung von Miniaturansichten für Videos](/help/user-guide/thumbnail-support.md).

* **Einfache Wiedergabe-Überwachung**

   AEM Screens unterstützt jetzt einfache Wiedergabe-Überwachung. Der Player meldet jetzt bei jedem Ping (standardmäßig alle 30 Sekunden) verschiedene Wiedergabemetriken. Basierend auf den Metriken bietet dies die Möglichkeit, verschiedene Grenzfälle zu erkennen (z. B. steckengebliebenes Erlebnis, leerer Bildschirm, Zeitplanprobleme usw.). Diese Funktion ermöglicht es dem Team, aus der Ferne zu überwachen, ob ein Player die Inhalte ordnungsgemäß abspielt. Sie verbessert die Reaktionsfähigkeit auf leere Bildschirme oder fehlerhafte Erlebnisse im Feld und verringert das Risiko, dem Endbenutzer ein fehlerhaftes Erlebnis zu zeigen.
Weitere Informationen finden Sie unter [Einfache Wiedergabe-Überwachung](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/installing-screens-player.html?lang=de#playback-monitoring).

* **Aktualisierungen des Inhaltszuweisungsberichts**

   Der Inhaltszuweisungsbericht wurde jetzt mit verbesserter Benutzerfreundlichkeit optimiert. Der herunterladbare Bericht zeigt verbesserte Player-bezogene Entitäten wie Standorte, Anzeigen und Geräte auf einer Tabellenregisterkarte und die Content Provider-Informationen wie Kanäle und Assets auf einer anderen Registerkarte an.
Weitere Informationen finden Sie unter [Inhaltszuweisungsbericht](/help/user-guide/content-assignment-report.md).

* **Adaptive Ausgabedarstellungen**

   Adaptive Ausgabedarstellungen ermöglichen es den Geräten, basierend auf vom Kunden definierten Regeln automatisch die beste Ausgabedarstellung für ein Gerät auszuwählen.

   Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Weitere Informationen hierzu finden Sie in [Adaptive Ausgabedarstellungen: Überblick über die Architektur und Konfigurationen](/help/user-guide/adaptive-renditions.md).

   Darüber hinaus können Sie als AEM Screens-Inhaltsautor Ihre Assets so konfigurieren, dass sie adaptive Ausgabedarstellungen verwenden, und Ihre Geräte für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu nutzen. Weitere Informationen finden Sie unter [Verwenden adaptiver Ausgabedarstellungen in AEM Screens](/help/user-guide/using-adaptive-renditions.md).

* **Unterstützung für V3-Manifeste**

   Sie können jetzt den Dispatcher für Manifest Version 3 konfigurieren. Um das v3-Manifest zu aktivieren, müssen Sie Folgendes konfigurieren:

   * Dispatcher aktualisieren

   * Benutzerdefinierte Komponente aktualisieren

   * ContentSync deaktivieren in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag`

   * Aktivieren Sie SmartSync in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl`

   * Siehe [Konfigurieren des Dispatchers für die Manifestversion v3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=de#configuring-dispatcherv3) für weitere Details.
   * Wenn Sie benutzerdefinierte Komponenten als Teil von v3-Manifesten verwenden, lesen Sie [Vorlage für benutzerdefinierte Handler](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=de#custom-handlers).


### Fehlerbehebungen {#bug-fixes}

**Auf der Player-Seite**

* Fehlerkorrektur – Beim Zwischenspeichern von Dateien werden Assets nicht mehr durch Ausgabedarstellungen ersetzt.

* Die Player zeigen jetzt nur Asset-Ausgabedarstellungen an, wenn die Ausgabedarstellungszuordnung vorhanden ist.

* Verbesserter Ping zur erneuten Authentifizierung, wenn die Antwort kein gültiges JSON ist.

* Numerische Kanalnamen/-rollen führen nicht mehr zu einem leeren Bildschirm.

* Sie können optimierte Ausgabedarstellungen über SmartSync herunterladen.

* Die Zuordnung wurde in eine Liste von Ausgabedarstellungsschlüsseln umgewandelt.

* Der Zugriff auf `cmd.exe` und `reg.exe` im Windows-Player wurde entfernt.

* Ein Player muss das letzte erfolgreiche Wiedergabeereignis melden.

* Ein Player muss seinen Wiedergabestatus melden.

* Der Player lädt Assets nicht erneut herunter, wenn der `ALL`-Cache gelöscht wird.

* Als Player-Administrator können Sie jetzt einen Player-Namen auswählen.

* Das Entfernen der Kanalzuweisung aus der Anzeige wird nicht im Player angezeigt.

* Wenn der Player beim Herunterladen des Kanal-Updates neu geladen wird, ignoriert der Player das Update.

* Die eingebettete Seitenkomponente berücksichtigt jetzt das Touch-Ereignis.

* Die Remote-Bereitstellung des Tizen-Players wird jetzt unterstützt.

**Auf der Server-Seite**

* Das Ziel-Video wird nicht angezeigt
* Konkurrenzbedingung bei der Übertragung von Anzeigedaten an Teilsequenzen.

* Die Kanalvorschau funktioniert nicht für Kanäle, die Videos enthalten.

* Für den Splitscreen-Kanal wird der Vorschaumodus leer angezeigt.

* Videominiaturen werden bei aktivierten adaptiven Ausgabedarstellungen leer dargestellt.

* Das Kanalmanifest wird automatisch aktualisiert, wenn die referenzierte Seite veröffentlicht wird.

* Gelöschte Geräte blockieren jetzt nicht mehr die Screens-Replikationswarteschlange.

* Das Manifest enthielt weder ausgewählte Inhalte noch eingebettete Sites-Seiten. Dies wurde nun behoben.

* Dem Kanalmanifest wurde jetzt eine neue Kernbildkomponente hinzugefügt.

* Das Herunterladen optimierter Ausgabedarstellungen über SmartSync wird jetzt unterstützt.

* Für alle Assets werden optimierte Ausgabedarstellungen abgespielt.

* Unterstützung für mehrere Content-Provider-Typen wurde hinzugefügt

* Die Strategie zur Wiedergabe eingebetteter Sequenzen war beschädigt und dies wurde jetzt behoben.

* Das Offline-Manifest verwendete den Anforderungsparameter `wcmmode` für einen HTML-Eintrag, wodurch er nicht mehr erreichbar war.

* Eine leere dynamische eingebettete Sequenz verursachte manchmal einen leeren Bildschirm.

* Der Player meldet jetzt seinen Wiedergabestatus.

* Das Video wurde in `Tiny mode` wiedergegeben und nicht als Vollbildvideo auf dem Gerät abgespielt. Das Problem wurde jetzt behoben.

### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 9 verfügbar:

* ChromeOS
* Windows
* Tizen
* Android
* Linux

#### AEM Screens-Player-Downloads   {#aem-screens-player-downloads}

Gehen Sie zu **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neusten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
