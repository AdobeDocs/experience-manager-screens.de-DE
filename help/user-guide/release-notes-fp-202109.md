---
title: Versionshinweise für Feature Pack 202109
description: Auf dieser Seite erhalten Sie Informationen zu AEM Screens Feature Pack 202105, das am 23. September 2021 veröffentlicht wurde.
feature: Feature Pack
role: Developer
level: Intermediate
index: false
source-git-commit: 060ab6a906597ab8e8789fab6932cec310cc06f5
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 19%

---

# Versionshinweise für Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 9 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.9 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack mit dem Namen **AEM 6.5 Screens FP9** herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202109 ist der 23. September 2021.

### Neue Funktionen {#what-is-new}

* **Unterstützung von Miniaturansichten für Videos**

   Unterstützung von Miniaturbildern für Videos in wird jetzt in AEM Screens unterstützt. Ein Inhaltsautor kann eine Miniaturansicht für Videos definieren, sodass das Bild als Platzhalter verwendet und die Inhaltswiedergabe und das Targeting ordnungsgemäß getestet werden kann, während das eigentliche Video vom entsprechenden Team fertig gestellt wird. Das Bild kann auch verwendet werden, falls die Wiedergabe des Videos fehlschlägt.
Weitere Informationen finden Sie unter Unterstützung für Miniaturansichten für Videos .

* **Grundlegende Wiedergabe-Überwachung**

   AEM Screens unterstützt jetzt die grundlegende Wiedergabe-Überwachung. Der Player meldet jetzt bei jedem Ping verschiedene Wiedergabemetriken (standardmäßig 30 Sekunden). Basierend auf den Metriken bietet es die Möglichkeit, verschiedene Edge-Fälle zu erkennen (festes Erlebnis, leerer Bildschirm, Planungsproblem usw.). Mit dieser Funktion kann das Team remote überwachen, ob ein Player Inhalte ordnungsgemäß wiedergibt, die Reaktionsrate auf leere Bildschirme oder fehlerhafte Erlebnisse im Feld verbessert und das Risiko verringert, dem Endbenutzer ein defektes Erlebnis anzuzeigen.
Weitere Informationen finden Sie unter Grundlegende Wiedergabe-Überwachung .

* **Aktualisierungen des Inhaltszuweisungsberichts**

* **Unterstützung für V3-Manifeste**

   Sie können jetzt den Dispatcher für Manifest Version 3 konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren des Dispatchers für die Manifestversion v3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=en#configuring-dispatcherv3) .
Wenn Sie außerdem benutzerdefinierte Komponenten als Teil von v3-Manifesten verwenden, finden Sie weitere Informationen unter [Vorlage für benutzerdefinierte Handler](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=en#custom-handlers).


### Fehlerbehebungen {#bug-fixes}

**Player-Seite**

* Es wurden Fehler beim Zwischenspeichern von Dateien behoben, indem Assets durch Ausgabedarstellungen ersetzt wurden.

* Die Player zeigen jetzt nur Asset-Ausgabedarstellungen an, wenn die Ausgabedarstellungszuordnung vorhanden ist.

* Sie können jetzt Slack-Warnhinweise basierend auf Splunk-Protokollen einrichten.

* Verbessern Sie den Ping, um sich erneut zu authentifizieren, wenn die Antwort keine gültige JSON ist.

* Numerische Kanalnamen/-rollen führten zu einem leeren Bildschirm.

* Laden Sie optimierte Ausgabedarstellungen über SmartSync herunter.

* Wandeln Sie die Zuordnung in eine Liste von Ausgabedarstellungsschlüsseln um.

* Entfernen Sie den Zugriff auf cmd.exe und reg.exe im Windows-Player.

* Beschränken Sie CSRF-Token-Aufrufe.

* Ein Player muss das letzte erfolgreiche Wiedergabeereignis melden.

* Ein Player muss seinen Wiedergabestatus melden.

* Der Player lädt Assets nicht erneut herunter, wenn der Cache `ALL` gelöscht wird.

* Als Player-Admin können Sie jetzt einen Player-Namen auswählen.

* Das Entfernen der Kanalzuweisung aus der Anzeige wird nicht im Player angezeigt.

* Wenn der Player beim Herunterladen der Kanalaktualisierung neu geladen wird, ignoriert der Player die Aktualisierung.

* Die eingebettete Seitenkomponente berücksichtigt kein Touchereignis.

* Die Remote-Bereitstellung des Tizen-Players wird jetzt unterstützt.

**Server Side**

* Target-Video wird nicht angezeigt
* Wettlaufsituationen bei der Übertragung von Anzeigedaten in die Folgezeiten.

* Die Kanalvorschau funktioniert nicht für Kanäle, die Videos enthalten.

* Vorschaumodus wird für den Splitscreen-Kanal leer angezeigt.

* Videominiaturen werden bei aktivierten adaptiven Ausgabeformaten leer dargestellt.

* Kanalmanifest automatisch aktualisieren, wenn referenzierte Seite veröffentlicht wird.

* Kanal JSON enthält keine benutzerdefinierten Kanäle (#942)

* Gelöschte Geräte blockieren jetzt nicht die Screens-Replikationswarteschlange.

* Das Manifest enthält weder zielgerichtete Inhalte noch eingebettete Sites-Seiten.

* Neue Kernbildkomponente wurde dem Kanalmanifest nicht hinzugefügt.

* Das Herunterladen optimierter Ausgabedarstellungen über SmartSync wird jetzt unterstützt.

* Optimierte Ausgabedarstellung für alle Assets abspielen.

* Unterstützung für mehrere Content-Provider-Typen hinzugefügt

* Die Strategie zur Wiedergabe eingebetteter Sequenzen wurde beschädigt und jetzt wurde dies behoben.

* Offline-Manifest mit dem Anforderungsparameter `wcmmode` für HTML-Eintrag, wodurch es nicht mehr erreichbar ist.

* Leere dynamische eingebettete Sequenz verursacht manchmal einen leeren Bildschirm.

* Ein Player muss seinen Wiedergabestatus melden.

* Das Video wird in `Tiny mode` wiedergegeben und nicht als Vollbildvideo auf dem Gerät.

* OSGi-Kennwörter sind als Klartext sichtbar.


### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM 6.5 Feature Pack 9 verfügbar:

* ChromeOS
* Windows
* Tizen
* Android
* Linux

#### AEM Screens-Player-Downloads   {#aem-screens-player-downloads}

Navigieren Sie zu **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neusten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
