---
title: Versionshinweise für Feature Pack 202109
description: Auf dieser Seite finden Sie Informationen zum AEM Screens Feature Pack 202109, das am Mittwoch, 23. September 2021 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: e1794013-59ce-4ddc-93c0-601668c75cd1
source-git-commit: 6d9dab9fd59289aafdb688682fea47589d3ec873
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 45%

---

# Versionshinweise für Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 9 für AEM Screens wurde veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.9 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Gehen Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP9** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202109 ist der 23. September 2021.

### Neue Funktionen {#what-is-new}

* **Unterstützung von Miniaturansichten für Videos**

   AEM Screens unterstützt jetzt Miniaturansichten für Videos. Ein Inhaltsautor kann eine Miniaturansicht für Videos definieren, sodass das Bild als Platzhalter verwendet und die Inhaltswiedergabe und das Targeting ordnungsgemäß getestet werden können, während das eigentliche Video vom entsprechenden Team fertiggestellt wird. Das Bild kann auch verwendet werden, wenn die Wiedergabe des Videos fehlschlägt.
Weitere Informationen finden Sie unter [Unterstützung für Miniaturansichten für Videos](/help/user-guide/thumbnail-support.md) .

* **Einfache Wiedergabe-Überwachung**

   AEM Screens unterstützt jetzt einfache Wiedergabe-Überwachung. Der Player meldet jetzt bei jedem Ping (standardmäßig alle 30 Sekunden) verschiedene Wiedergabemetriken. Basierend auf den Metriken bietet dies die Möglichkeit, verschiedene Grenzfälle zu erkennen (z. B. steckengebliebenes Erlebnis, leerer Bildschirm, Zeitplanprobleme usw.). Diese Funktion ermöglicht es dem Team, aus der Ferne zu überwachen, ob ein Player die Inhalte ordnungsgemäß abspielt. Sie verbessert die Reaktionsfähigkeit auf leere Bildschirme oder fehlerhafte Erlebnisse im Feld und verringert das Risiko, dem Endbenutzer ein fehlerhaftes Erlebnis zu zeigen.
Weitere Informationen finden Sie unter [Grundlegende Wiedergabe-Überwachung](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/installing-screens-player.html?lang=en#playback-monitoring) .

* **Aktualisierungen des Inhaltszuweisungsberichts**

   Der Inhaltszuweisungsbericht wurde jetzt mit verbesserter Benutzerfreundlichkeit optimiert und verbessert. Der herunterladbare Bericht zeigt verbesserte Player-bezogene Entitäten wie Standorte, Anzeigen und Geräte auf einer Tabellenregisterkarte und die Content Provider-Informationen wie Kanäle und Assets auf einer anderen Registerkarte an.
Weitere Informationen finden Sie unter [Inhaltszuweisungsbericht](/help/user-guide/content-assignment-report.md) .

* **Adaptive Ausgabedarstellungen**

   Adaptive Ausgabedarstellungen ermöglichen es den Geräten, basierend auf vom Kunden definierten Regeln automatisch die beste Ausgabedarstellung für ein Gerät auszuwählen.

   Als AEM Screens-Entwickler können Sie jetzt gerätespezifische Asset-Ausgabedarstellungen so konfigurieren, dass sie automatisch heruntergeladen und wiedergegeben werden, ohne dass alle Inhaltsvarianten manuell erstellt werden müssen. Siehe [Adaptive Ausgabeformate: Architektonischer Überblick und Konfigurationen](/help/user-guide/adaptive-renditions.md) für weitere Details.

   Darüber hinaus können Sie als AEM Screens Content Author Ihre Assets so konfigurieren, dass sie adaptive Ausgabedarstellungen verwenden, und Ihre Geräte für große Netzwerke migrieren, um diese Funktion in Ihren AEM Screens-Kanälen zu nutzen. Weitere Informationen finden Sie unter [Verwenden adaptiver Ausgabeformate in AEM Screens](/help/user-guide/using-adaptive-renditions.md) .

* **Unterstützung für V3-Manifeste**

   Sie können jetzt den Dispatcher für Manifest Version 3 konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren des Dispatchers für Manifest Version 3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=de#configuring-dispatcherv3).
Wenn Sie außerdem benutzerdefinierte Komponenten als Teil von Manifesten Version 3 verwenden, finden Sie weitere Informationen unter [Vorlage für benutzerdefinierte Handler](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=de#custom-handlers).


### Fehlerbehebungen {#bug-fixes}

**Player-Seite**

* Es wurden Fehler beim Zwischenspeichern von Dateien behoben, indem Assets durch Ausgabedarstellungen ersetzt wurden.

* Die Player zeigen jetzt nur Asset-Ausgabedarstellungen an, wenn die Ausgabedarstellungszuordnung vorhanden ist.

* Verbesserter Ping zur erneuten Authentifizierung, wenn die Antwort keine gültige JSON ist.

* Numerische Kanalnamen/-rollen führten zu einem leeren Bildschirm.

* Laden Sie optimierte Ausgabedarstellungen über SmartSync herunter.

* Die Zuordnung wurde in eine Liste von Ausgabedarstellungsschlüsseln umgewandelt.

* Der Zugriff auf `cmd.exe` und `reg.exe` im Windows-Player wurde entfernt.

* Ein Player muss das letzte erfolgreiche Wiedergabeereignis melden.

* Ein Player muss seinen Wiedergabestatus melden.

* Der Player lädt Assets nicht erneut herunter, wenn der Cache `ALL` gelöscht wird.

* Als Player-Administrator können Sie jetzt einen Player-Namen auswählen.

* Das Entfernen der Kanalzuweisung aus der Anzeige wird nicht im Player angezeigt.

* Wenn der Player beim Herunterladen der Kanalaktualisierung neu geladen wird, ignoriert der Player die Aktualisierung.

* Die eingebettete Seitenkomponente berücksichtigt jetzt das Touch-Ereignis.

* Die Remote-Bereitstellung des Tizen-Players wird jetzt unterstützt.

**Server Side**

* Target-Video wird nicht angezeigt
* Wettlaufsituationen bei der Übertragung von Anzeigedaten in die Folgezeiten.

* Die Kanalvorschau funktioniert nicht für Kanäle, die Videos enthalten.

* Vorschaumodus wird für den Splitscreen-Kanal leer angezeigt.

* Videominiaturen werden bei aktivierten adaptiven Ausgabeformaten leer dargestellt.

* Kanalmanifest automatisch aktualisieren, wenn referenzierte Seite veröffentlicht wird.

* Gelöschte Geräte blockieren jetzt nicht die Screens-Replikationswarteschlange.

* Das Manifest enthielt weder zielgerichtete Inhalte noch eingebettete Sites-Seiten. Dieser Fehler wurde nun behoben.

* Dem Kanalmanifest wurde jetzt eine neue Kernbildkomponente hinzugefügt.

* Das Herunterladen optimierter Ausgabedarstellungen über SmartSync wird jetzt unterstützt.

* Optimierte Ausgabedarstellung für alle Assets abspielen.

* Unterstützung für mehrere Content-Provider-Typen hinzugefügt

* Die Strategie zur Wiedergabe eingebetteter Sequenzen wurde beschädigt und jetzt wurde dies behoben.

* Offline-Manifest mit dem Anforderungsparameter `wcmmode` für HTML-Eintrag, wodurch es nicht mehr erreichbar ist.

* Leere dynamische eingebettete Sequenz verursachte manchmal einen leeren Bildschirm.

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
