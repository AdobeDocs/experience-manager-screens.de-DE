---
title: Versionshinweise für Feature Pack 202109
description: Erfahren Sie mehr über das AEM Screens Feature Pack 202109, das am 23. September 2021 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: e1794013-59ce-4ddc-93c0-601668c75cd1
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 63%

---

# Versionshinweise für Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe empfiehlt ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM). AEM Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 9 für AEM Screens wurde veröffentlicht.

Sie können das neueste Feature Pack für AEM Screens 6.5.9 von der [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) die Verwendung Ihrer Adobe ID. Navigieren Sie zum **Adobe Experience Manager** Registerkarte und suchen Sie nach **Screens** , um das neueste Feature Pack mit dem Titel **AEM 6.5 Screens FP9**.

## Veröffentlichungsdatum {#release-date}

Das AEM Screens Feature Pack 202109 wurde am 23. September 2021 veröffentlicht.

### Neue Funktionen {#what-is-new}

* **Unterstützung von Miniaturansichten für Videos**

  AEM Screens unterstützt jetzt Miniaturansichten für Videos. Ein Inhaltsautor definiert eine Miniaturansicht für Videos, sodass das Bild als Platzhalter verwendet wird. Außerdem werden die Inhaltswiedergabe und das Targeting ordnungsgemäß getestet, während das entsprechende Team das eigentliche Video abschließt. Das Bild kann auch verwendet werden, wenn die Wiedergabe des Videos fehlschlägt.
Weitere Informationen finden Sie unter [Unterstützung von Miniaturansichten für Videos](/help/user-guide/thumbnail-support.md).

* **Einfache Wiedergabe-Überwachung**

  AEM Screens unterstützt jetzt einfache Wiedergabe-Überwachung. Der Player meldet jetzt bei jedem Ping (standardmäßig alle 30 Sekunden) verschiedene Wiedergabemetriken. Basierend auf diesen Metriken werden verschiedene Randfälle (Feststecken, leerer Bildschirm, Zeitplanprobleme usw.) erkannt. Mit dieser Funktion kann das Team remote überwachen, ob ein Player Inhalte ordnungsgemäß wiedergibt, und die Reaktionsrate auf leere Bildschirme oder fehlerhafte Erlebnisse im praktischen Einsatz verbessern. Außerdem sinkt so das Risiko, dass Endbenutzenden ein fehlerhaftes Erlebnis angezeigt wird.
Weitere Informationen finden Sie unter [Einfache Wiedergabe-Überwachung](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/installing-screens-player#playback-monitoring).

* **Aktualisierungen des Inhaltszuweisungsberichts**

  Der Inhaltszuweisungsbericht wurde jetzt optimiert und mit einem verbesserten Benutzererlebnis verbessert. Der herunterladbare Bericht zeigt verbesserte Player-bezogene Entitäten an. Zu diesen Entitäten gehören Standorte, Anzeigen und Geräte in einer Tabelle. Sie enthält auch die Informationen des Inhaltsanbieters wie Kanäle und Assets auf einer anderen Registerkarte.
Weitere Informationen finden Sie unter [Inhaltszuweisungsbericht](/help/user-guide/content-assignment-report.md).

* **Adaptive Ausgabedarstellungen**

  Mit adaptiven Ausgabedarstellungen kann das Gerät basierend auf kundendefinierten Regeln automatisch auf die beste Ausgabedarstellung für ein Gerät klicken.

  Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Weitere Informationen hierzu finden Sie in [Adaptive Ausgabedarstellungen: Überblick über die Architektur und Konfigurationen](/help/user-guide/adaptive-renditions.md).

  Als AEM Screens-Inhaltsautorin oder -Inhaltsautor können Sie Ihre Assets für adaptive Ausgabedarstellungen konfigurieren. Sie können Ihre Geräte auch für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu verwenden. Weitere Informationen finden Sie unter [Verwenden adaptiver Ausgabedarstellungen in AEM Screens](/help/user-guide/using-adaptive-renditions.md).

* **Unterstützung für V3-Manifeste**

  Sie können jetzt den Dispatcher für Manifest Version 3 konfigurieren. Gehen Sie wie folgt vor, um das v3-Manifest zu aktivieren:

   * Löschen Sie alle ausstehenden Offline-Inhaltsaufträge sowohl in der Autoren- als auch in der Veröffentlichungsinstanz.

      * Navigieren Sie in der Autoren- und der Veröffentlichungsinstanz zu CRXDE Lite.

      * Klicken Sie auf „Tools“ > „Abfrage“

      * Verwenden Sie in der Abfrage `/jcr:root/var/eventing/jobs/assgined//element(*,slingevent:Job)[\@event.job.topic='screens/offline_content_update']`.

      * Dadurch werden alle Offline-Inhaltsaufträge aufgelistet, die derzeit ausgeführt werden oder noch in der Warteschlange ausstehen.

      * Warten Sie, bis keine weiteren Offline-Inhaltsaufträge mehr von der Abfrage zurückgegeben werden.

   * ContentSync in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` deaktivieren.

   * SmartSync in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl` aktivieren.

   * Führen Sie eine Dispatcher-Aktualisierung durch.

   * Aktualisieren Sie die benutzerdefinierte Komponente.


   * Weitere Informationen finden Sie unter [Konfigurieren des Dispatchers für Manifest Version 3](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3).
   * Wenn Sie außerdem benutzerdefinierte Komponenten als Teil von Manifesten der Version 3 verwenden, finden Sie weitere Informationen unter [Vorlage für benutzerdefinierte Handler](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers).


### Fehlerbehebungen {#bug-fixes}

**Auf der Player-Seite**

* Fehlerkorrektur – Beim Zwischenspeichern von Dateien werden Assets nicht mehr durch Ausgabedarstellungen ersetzt.

* Die Player zeigen jetzt nur Asset-Ausgabedarstellungen an, wenn die Ausgabedarstellungszuordnung vorhanden ist.

* Verbesserter Ping zur erneuten Authentifizierung, wenn die Antwort keine gültige JSON ist.

* Numerische Kanalnamen/-rollen führen nicht mehr zu einem leeren Bildschirm.

* Laden Sie optimierte Ausgabedarstellungen über SmartSync herunter.

* Die Zuordnung wurde in eine Liste von Ausgabedarstellungsschlüsseln umgewandelt.

* Der Zugriff auf `cmd.exe` und `reg.exe` im Windows-Player.

* Ein Player muss sein letztes erfolgreiches Wiedergabeereignis melden.

* Ein Player muss seinen Wiedergabestatus melden.

* Der Player lädt Assets nicht erneut herunter, wenn der `ALL`-Cache gelöscht wird.

* Als Player-Administrator können Sie jetzt einen Player-Namen auswählen.

* Das Entfernen der Kanalzuweisung aus der Anzeige wird nicht im Player angezeigt.

* Wenn der Player beim Herunterladen der Kanalaktualisierung neu geladen wird, ignoriert der Player die Aktualisierung.

* Die eingebettete Seitenkomponente berücksichtigt jetzt das Touch-Ereignis.

* Die Remote-Bereitstellung des Tizen-Players wird jetzt unterstützt.

**Auf der Server-Seite**

* Das Ziel-Video wird nicht angezeigt.
* Konkurrenzbedingungen bei der Übertragung von Anzeigedaten an Teilsequenzen.

* Die Kanalvorschau funktioniert nicht für Kanäle, die Videos enthalten.

* Für den Splitscreen-Kanal wird der Vorschaumodus leer angezeigt.

* Videominiaturen werden bei aktivierten adaptiven Ausgabeformaten leer dargestellt.

* Aktualisieren Sie das Kanalmanifest automatisch, wenn die referenzierte Seite veröffentlicht wird.

* Gelöschte Geräte blockieren jetzt nicht mehr die Screens-Replikationswarteschlange.

* Das Manifest enthielt keine zielgerichteten Inhalte oder eingebetteten Sites-Seiten. Dieser Fehler wurde behoben.

* Dem Kanalmanifest wird jetzt eine neue Kernbildkomponente hinzugefügt.

* Das Herunterladen optimierter Ausgabedarstellungen über SmartSync wird jetzt unterstützt.

* Für alle Assets werden optimierte Ausgabedarstellungen abgespielt.

* Unterstützung für mehrere Content-Provider-Typen wurde hinzugefügt

* Die Strategie zur Wiedergabe eingebetteter Sequenzen wurde beschädigt und dieser Fehler wurde jetzt behoben.

* Das Offline-Manifest verwendete den Anforderungsparameter `wcmmode` für einen HTML-Eintrag, wodurch er nicht mehr erreichbar war.

* Eine leere dynamische eingebettete Sequenz verursachte manchmal einen leeren Bildschirm.

* Der Player meldet jetzt seinen Wiedergabestatus.

* Das Video wurde in `Tiny mode` wiedergegeben und nicht als Vollbildvideo auf dem Gerät abgespielt. Das Problem wurde jetzt behoben.

### Veröffentlichte AEM Screens-Player

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 9 verfügbar:

* ChromeOS
* Windows
* Tizen
* Android™
* Linux®

#### AEM Screens-Player-Downloads

Informationen zum Herunterladen des neuesten AEM Screens-Players und zu weiteren Fehlerbehebungen finden Sie unter **[AEM Screens Player-Downloads](https://download.macromedia.com/screens/index.html)**.
