---
title: Häufig gestellte Fragen zu AEM Screens
description: Lesen Sie Antworten auf häufig gestellte Fragen zu einem AEM Screens-Projekt.
feature: Digital Signage, Content
role: Developer
level: Intermediate
exl-id: 67204f04-5535-407c-bd4d-fabfbf850411
source-git-commit: e82cfee5ecc6b639b7b2b65553d1635943b356ea
workflow-type: tm+mt
source-wordcount: '2135'
ht-degree: 68%

---

# Häufig gestellte Fragen zu AEM Screens {#aem-screens-faqs}

Dieses Thema enthält Antworten auf häufig gestellte Fragen zu einem AEM Screens-Projekt.

## Problem mit leerem Bildschirm {#blank-screen}

>[!NOTE]
>Die aufgelistete obligatorische überprüft, ob der primäre Support oder der kundenseitige Support versuchen sollte, bevor ein Problem gemeldet wird.

### 1. Was sollten die Erste-Hilfe-Schritte zur Fehlerbehebung sein, wenn ein Kunde mit einem schwarzen Bildschirm oder nicht wiedergegebenen Inhalten konfrontiert wird? {#troubleshooting-blank-screen}

* Überprüfen Sie, ob die Kanalvorschau funktioniert.
* Überprüfen Sie, ob die Anzeigenvorschau funktioniert.
* Versuchen Sie, den Player als Browser-Erweiterung auf Ihrem System für dieselbe Anzeige zu registrieren und überprüfen Sie, ob er funktioniert.
* Wenn der Player auf Ihrem System läuft, navigieren Sie zu `http://localhost:24502`. Überprüfen Sie, ob der gesamte Inhalt korrekt heruntergeladen wurde.
* Überprüfen Sie die Assets, um sicherzustellen, dass die entsprechenden Ausgabedarstellungen erstellt wurden und die richtige Ausgabedarstellung wiedergegeben wird.
* Überprüfen Sie, ob es geplante Inhalte gibt und ob die Zeiten korrekt sind. Überprüfen Sie, ob die im Player eingestellte Zeit korrekt ist.
* Überprüfen Sie die Protokolle der Player-Konsole und überprüfen Sie sie auf Fehler. Klicken Sie mit der rechten Maustaste und überprüfen Sie die Konsolenprotokolle. Wenn Sie den Windows Player verwenden, drücken Sie `CTRL + ALT +I` , um die Entwicklungskonsole aufzurufen und die Protokolle anzuzeigen.

### 2. Wie lässt sich das Problem der grauen Bildschirme in AEM Screens beim Erstellen eines Standardkanals oder -zeitplans beheben?

Um die leeren oder grauen Bildschirme im Feld zu vermeiden, erstellen Sie einen globalen Standardkanal oder -zeitplan, der jeder Anzeige mit der geringsten Priorität 1 zugewiesen ist. Falls etwas bei Inhaltsaktualisierungen fehlschlägt, weil die Player diesen Inhalt bereits auf der Festplatte zwischengespeichert haben. Es sollte gut abgespielt werden und die grauen Bildschirme sollten vermieden werden.

Alle anderen Inhalte, wie Kanäle oder Zeitpläne, haben eine Priorität größer als 1, sodass die anderen Inhalte Priorität haben und der globale Kanal- oder Zeitplaninhalt (mit Priorität 1) nur als Fallback-Option wiedergegeben wird.

## Kanalverwaltung {#channel-management}

### 1. Was ist der Unterschied zwischen einem Online- und einem Offline-Kanal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

Ein ***Online-Kanal*** zeigt den aktualisierten Inhalt in der Echtzeitumgebung, während ein ***Offline-Kanal*** den im Cache gespeicherten Inhalt zeigt.

### 2. Wie schalte ich einen Kanal online? {#how-do-i-make-a-channel-online}

Klicken Sie auf den Kanal und navigieren Sie in der Aktionsleiste zu den Kanaleigenschaften. Aktivieren Sie **Entwicklermodus (Kanal zwingen, online zu sein)** auf der Registerkarte **Kanal**, um den Kanal online zu schalten.

### 3. Was ermöglicht das Feld „Kanalrolle“? {#what-is-the-use-of-the-channel-role-field}

Die Kanalrolle ist eine Abstraktion des tatsächlichen Kanals, die ausgeführt wird, damit sich die Autorin bzw. der Autor direkt auf das generische Erlebnis konzentrieren kann. Sie können sich die Rolle als eine Art Tag vorstellen, das den Kanal in seinem Kontext (Anzeige oder Zeitplan) eindeutig identifiziert.

### 4. Wie erfolgt die tatsächliche Kanalauflösung? {#how-does-actual-channel-resolution-happen}

Bei *statischen Verweisen* folgt die Auflösung einfach dem angegebenen Pfad.

Bei *dynamischen Verweisen* erfolgt die Auflösung, sobald der Kanal der Anzeige zugewiesen wird (nicht dem Zeitplan). Der Anzeigepfad wird zum Kontext des Kanals und die Auflösung wird wie folgt durchgeführt (höchste zu niedrigster Priorität):

1. Die Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Die Anzeige verfügt über einen gleichrangigen Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Der übergeordnete Standort der Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Der über-übergeordnete Standort der Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt

Und so weiter, bis Sie den Ordner &quot;Speicherorte&quot;erreichen. Beenden Sie den Vorgang im Moment (Sie können also nicht auf einen Kanal verweisen, der sich beispielsweise im Ordner Kanäle befindet, sondern nur auf Kanäle im Unterbaum Ort).

### 5. Wie wird die benutzerdefinierte clientlib-Offline-Konfiguration im AEM Screens-Kanal eingerichtet?

Bei Verwendung eines erstellten benutzerdefinierten clientseitigen Codes `clientlib` in einem AEM Screens-Kanal sind die folgenden Schritte erforderlich. Die Schritte stellen sicher, dass die `clientlib` -Dateien erfolgreich im Kanal geladen werden (`manifest.json`) und enthält den Pfad der `clientlib`.

Gehen Sie im Kanaleditor wie folgt vor:

1. Klicken Sie auf einen Kanal und dann auf **Bearbeiten** in der Aktionsleiste aus.
1. Klicken Sie auf die Komponente, der Sie die benutzerdefinierte `clientlib`.
1. Klicken Sie auf die Schaltfläche &quot;Konfigurieren&quot;(Schraubenschlüsselsymbol).
1. Gehen Sie zur Registerkarte **Offline-Konfiguration** und fügen Sie den Pfad zu Ihrer benutzerdefinierten clientlib unter **Client-seitige Bibliotheken** hinzu.

## Geräteregistrierung {#device-registration}

### 1. Bei der Ermittlung von Endpunkten (z. B. Anfragen zum Onboarding und Registrieren von Geräten) kann ich Skripte für eine große Zahl von Geräten verfassen, um die Geräte zu registrieren. Ist es möglich, diese Anfragen zu schützen und sie nicht nur an eine Zweigstelle mit Wi-Fi zu binden? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Derzeit ist eine Registrierung nur in der Autoreninstanz möglich. Obwohl der Registrierungsdienst nicht authentifiziert ist, erstellt er in AEM nur ein ausstehendes Gerät, das jedoch weder registriert noch einer Anzeige zugewiesen wird.

Um ein Gerät zu registrieren (in AEM Benutzer für das Gerät zu erstellen), authentifizieren Sie sich bei AEM und befolgen Sie den Registrierungsassistenten manuell, um die Registrierung abzuschließen. Theoretisch kann ein böswilliger Benutzer mehrere ausstehende Geräte erstellen, aber keine registrieren, wenn er keine AEM Anmeldung hat.

### 2. Ist es möglich, mit einer bestimmten Form von Authentifizierung HTTP GET-Anfragen in HTTP POST umzuwandeln? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

Die Registrierungsanfrage ist eine POST-Anfrage.

Es wird empfohlen, die Geräte-ID aus der Sitzung abzurufen, anstatt sie als Parameter zu übergeben. Dies würde die Serverprotokolle, den Browsercache usw. bereinigen. Es handelt sich dabei nicht um ein Sicherheitsproblem. Semantisch. wird GET verwendet, wenn keine Statusänderung auf dem Server erfolgt; POST kommt zum Einsatz, wenn eine Statusänderung vorhanden ist.

### 3. Ist es möglich, eine Anfrage zur Geräteregistrierung abzulehnen? {#is-there-a-way-to-decline-a-device-registration-request}

Sie können Registrierungsanfragen nicht ablehnen. Stattdessen sollten Registrierungsanfragen nach einem Timeout ablaufen, das in konfiguriert ist. `Adobe Experience Manager Web Console`. Standardmäßig ist dieser Wert auf einen Tag festgelegt und wird in einem Arbeitsspeicher-Cache gespeichert.

## Geräteüberwachung und Statusberichte {#device-monitoring-and-health-reports}

### 1. Wie kann ich eine Fehlerbehebung vornehmen, wenn mein AEM Screens-Player einen leeren Bildschirm anzeigt?

Prüfen Sie folgende Möglichkeiten, um Probleme mit einem leeren Bildschirm zu beheben:

* AEM kann die Offline-Inhalte nicht im Push-Verfahren übertragen
* Der Kanal enthält keinen Inhalt
* Keines der Assets soll zur aktuellen Zeit angezeigt werden

### 2. Was kann ich tun, wenn der AEM Screens-Player nicht registriert werden kann und sein Status als &quot;Fehlgeschlagen&quot;angezeigt wird?

Aktivieren Sie im Dialogfeld für den Apache Sling Referrer-Filter die Option „Allow Empty“ (Leeres Feld zulassen). Erforderlich für eine optimale Funktionsweise des Steuerungsprotokolls zwischen AEM Screens Player und AEM Screens-Server.

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**.
1. Aktivieren Sie die Option **allow.empty**.
1. Klicken Sie auf **Speichern**.

### 3. Wie kann eine Fehlerbehebung durchgeführt werden, wenn beim Registrieren eines AEM Screens-Players auf dem Gerät &quot;FAILURE&quot;angezeigt wird und in den Konsolenprotokollen der Fehler &quot;ENAME_NOT_FOUND&quot;angezeigt wird?

Das Problem kann auftreten, wenn der Player das DNS des AEM Screens-Servers nicht finden kann. Sie können versuchen, eine Verbindung über die IP-Adresse herzustellen. Um die IP des Servers abzurufen, verwenden Sie: *arp &lt;server_dns_name>*.

### 4. Empfiehlt AMS, Android™ Watchdog auf allen Geräten zu implementieren? Ist das Watchdog-Plug-in (Cordova) Teil des APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Ein plattformübergreifender Android™-Watchdog, der reine Android™-APIs nutzt, ist bereits Bestandteil des APK. Es ist keine zusätzliche Software erforderlich. Je nach dem von Ihnen verwendeten Gerät können Sie das APK jedoch zurücksetzen, um ggf. Systemberechtigungen für einen vollständigen Aus- und Einschaltvorgang des Geräts zu erhalten (`Powermanager`-API). Falls es nicht mit den Herstellerschlüsseln neu signiert wird, wird das APK beendet und die Anwendung neu gestartet, aber nicht das Gerät aus- und wieder eingeschaltet.

Weitere Informationen zur Implementierung des Android™-Players finden Sie unter [**Implementieren des Android™-Players**](implementing-android-player.md).

### 5. Welche Remote-Überwachungs- und Warnmeldungs-Tools (Software) von Drittanbietern empfiehlt Adobe/AMS zur Überwachung einzelner Geräte? {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Je nachdem, welches Ergebnis Sie von der Überwachung und den Warnmeldungen wünschen, benachrichtigt Sie der AEM Screens-Benachrichtigungsdienst, wenn ein Gerät länger nicht mehr gepingt hat. Geeignete Tools von Drittanbietern hängen vom jeweiligen Betriebssystem, seinen Funktionen und den spezifischen Anforderungen der Kundinnen und Kunden ab.

Weitere Informationen dazu, wie Sie die Geräteaktivität überwachen können, finden Sie unter [**AEM Screens-Benachrichtigungsdienst**](screens-notifications-service.md).

## AEM Screens-Player

### 1. Wie installiere ich den Chrome OS-Player als Chrome-Browser-Plugin? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

Der ChromeOS-Player kann im Entwicklermodus als Chrome-Browser-Plug-in installiert werden, ohne dass ein aktuelles Chrome-Player-Gerät erforderlich ist. Gehen Sie zur Installation wie folgt vor:

1. Klicken Sie [hier](https://download.macromedia.com/screens/), um den neuesten Chrome-Player herunterzuladen.
1. Entpacken Sie die Datei und speichern Sie sie auf der Festplatte.
1. Öffnen Sie den Chrome-Browser und klicken Sie auf **Erweiterungen** aus dem Menü oder direkt zu ***chrome://extensions***.
1. Schalten Sie die **Entwicklermodus** oben rechts.
1. Klicks **Entpacktes Laden** oben links und laden Sie den entpackten Chrome-Player.
1. Wenn in der Liste der Erweiterungen verfügbar, überprüfen Sie die **AEM Screens Chrome-Player** Plug-in.
1. Öffnen Sie eine neue Registerkarte und klicken Sie oben links auf das Symbol **Apps** oder navigieren Sie direkt zu ***chrome://apps***.
1. Klicken Sie auf **AEM Screens** Plug-in. Standardmäßig wird der Player im Vollbildmodus gestartet. Drücken Sie **Esc**, um den Vollbildmodus zu beenden.

### 2. Wie kann eine Fehlerbehebung durchgeführt werden, wenn der Screens-Player nicht durch eine Veröffentlichungsinstanz mit einem benutzerdefinierten Fehler-Handler authentifiziert werden kann?

Wenn der AEM Screens-Player gestartet wird, sendet er eine Anfrage an ***/content/screens/svc.ping.json***, wenn der Player einen 404-Fehler erhält. Der Player initiiert eine Authentifizierungsanforderung, um sich bei der Veröffentlichungsinstanz zu authentifizieren. Wenn es in der Veröffentlichungsinstanz einen benutzerdefinierten Fehler-Handler gibt, stellen Sie sicher, dass Sie den 404-Status-Code für einen anonymen Benutzer bei ***/content/screens/svc.ping.json***.

### 3. Wie lässt sich der Gerätebildschirm in einem Android™-Player dauerhaft einschalten? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Führen Sie folgende Schritte durch, um „Stay Awake“ in einem beliebigen Android™-Player zu aktivieren:

1. Navigieren Sie zu den Einstellungen des Android™-Players > **Über**.
1. Tippen Sie siebenmal auf die Build-Nummer, um die **Entwickleroptionen** in den **Einstellungen** zu aktivieren.
1. Navigieren Sie zu den **Entwickleroptionen**.
1. Aktivieren Sie **Stay Awake**.

### 4. Wie wird der Fenstermodus für den Windows Player aktiviert?{#enable-player}

Es gibt keinen Fenstermodus im Windows Player. Sie befindet sich immer im Vollbildmodus.

### 5. Wie kann eine Fehlerbehebung durchgeführt werden, wenn ein AEM Screens-Player ständig Login-Anfragen sendet?

Führen Sie die folgenden Schritte aus, um eine Fehlerbehebung bei einem AEM Screens-Player durchzuführen, der fortlaufend Anfragen an sendet `/content/screens/svc.json` und `/libs/granite/core/content/login.validate/j_security_check`:

1. Beim Starten des AEM Screens-Players wird an `/content/screens/svc.json`. Wenn der Player daraufhin eine Antwort mit einem 404-Status-Code erhält, startet er eine Authentifizierungsanfrage mit `/libs/granite/core/content/login.validate/j_security_check` bei der *Veröffentlichungsinstanz*. Wenn es in der *Veröffentlichungsinstanz* einen benutzerdefinierten Fehler-Handler gibt, stellen Sie sicher, dass Sie in `/content/screens/svc.json` bzw. `/content/screens/svc.ping.json` den 404-Status-Code für eine anonyme Benutzerin oder einen anonymen Benutzer zurückgeben.

1. Überprüfen Sie, ob Ihre Dispatcher-Konfiguration diese Anfragen in `/filters` zulässt.

   Weitere Informationen finden Sie unter [Konfigurieren von Screens-Filtern](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#step-configure-screens-filters).

1. Überprüfen Sie, ob die Umschreibungsregeln des Dispatchers einen Bildschirmpfad in einen anderen Pfad umschreiben.

1. Überprüfen Sie, ob Sie `/etc/map`-Regeln in der *Autoren*- oder *Veröffentlichungsinstanz* verwenden und ob die Bildschirmpfade mit `sling:match` übereinstimmen und intern zu einem anderen Pfad umgeleitet werden. Die Auflösung der exakten URL in `/system/console/jcrresolver` hilft dabei herauszufinden, ob die *Veröffentlichungsinstanz* diese URLs in einen anderen Pfad umschreibt.

1. Überprüfen Sie, ob die Apache Sling Resource Resolver Factory-Konfiguration interne Neuschreibungen verursacht.

### 6. Wie können Details zu Anzeige und Gerät von der Player-API abgerufen werden?

Die Details der Anzeige und des Geräts erhalten Sie über:

* **eine interne JS-API**
* **einen ContextHub-Store**: Drei ContextHub-Stores sind in `/libs/screens/clientlibs/contexthub` definiert, um Informationen zu Kanal, Geräte und Anzeige anzuzeigen.

  Gehen Sie wie folgt vor, um diese ContentHub-Speicherwerte zu verwenden:

   * Bearbeiten Sie die Eigenschaften des Kanals und legen Sie auf der Registerkarte „Personalisierung“ den ContextHub-Pfad auf den Wert fest (wie oben erläutert)
   * Im Kanal-JS können Sie Folgendes verwenden:

     ```shell
        ContextHub.getStore('screens-device');
        ContextHub.getStore('screens-display');
        ContextHub.getStore('screens-channels');
     ```

## Allgemeine Tipps zur Problembehebung {#general-troubleshooting-tips}

### 1. Wie kann ich Livefyre deaktivieren, um A/P-Screens-Fehler zu vermeiden?

Deaktivieren Sie Livefyre, um Protokollfehler zu vermeiden, indem Sie wie folgt vorgehen.

1. ***Livefyre-Bundle deaktivieren:***

   * Navigieren Sie zu `https://<host>:<port>/system/console/bundles`.
   * Suchen Sie nach dem AEM Livefyre-Bundle: `com.adobe.cq.social.cq-social-livefyre`.
   * Klicks **Anhalten**.

1. ***So deaktivieren Sie den Livefyre-Poller:***

   * Navigieren Sie in CRXDE Lite zu `/etc/importers/polling/livefyre-poller/jcr:content`.
   * Fügen Sie eine *aktivierte* Eigenschaft vom Typ *Boolesch* hinzu
   * Satz **Aktivierte Eigenschaft** zu **false**.

### 2. Wie fügt man Oak-Index-Informationen hinzu? {#add-oak-index-info}

AEM Screens erstellt Indexdefinitionen für die vom Produkt verwendeten Abfragen.
Wenn es im `error.log` *abfrageübergreifende Warnhinweise (WARN)* gibt, erstellen Sie einen benutzerdefinierten Index für Ihre Abfrage. Weitere Informationen finden Sie unter [Konfigurieren der Indizes](https://experienceleague.adobe.com/de/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#configuring-the-indexes).

Eine zusätzliche Ressource finden Sie in der [Oak-Dokumentation](https://jackrabbit.apache.org/oak/docs/query/lucene.html).


### 3. Was ist erforderlich, um V3-Manifeste zu konfigurieren? {#configure-v3}

Gehen Sie wie folgt vor, um das v3-Manifest zu aktivieren:

* Dispatcher aktualisieren.
Weitere Informationen finden Sie unter [Konfigurieren des Dispatchers für Manifest Version 3](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3).

* Benutzerdefinierte Komponente aktualisieren.
Weitere Informationen finden Sie unter [Vorlage für benutzerdefinierte Handler](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers).

* ContentSync in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` deaktivieren.

* SmartSync in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl` aktivieren.

* `channel/experience fragment/page components` bearbeiten.

* Navigieren Sie zur Registerkarte **Offline-Konfiguration**.

* Geben Sie `clientlibs ` und die Ordner für statische Dateien ein, die zum Manifest hinzugefügt werden müssen.

### 4. Was sollten Sie tun, wenn nach dem Paket „screens-cloud-ams-pkg-0.0.20“ zwar „screens-cloud-ams-pkg-0.0.16“ und die Screens-Core-Bundles installiert, aber nicht aktiv sind?

Sie müssen mindestens die Version AEM 6.5 Feature Pack 8 installieren, damit der AMS-Connector funktioniert. Siehe [Verfügbarkeit](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202105#availability) damit Sie die Mindestversion von AEM Screens Feature Pack erhalten.

### 5. Wie wird der CQ Link Externalizer-Service in Screens konfiguriert?

Der Service wird verwendet, um den öffentlichen Host-Namen für die Autoren- und Veröffentlichungsinstanz zu definieren. Die Werte werden dann zum Aktualisieren der Geräte-Server-URLs und auch für das ContextHub-Targeting verwendet.

Der CQ Link Externalizer-Dienst in Screens kann wie folgt konfiguriert werden:

1. Navigieren Sie zu `http://localhost:4502/system/console/configMgr`
1. Day CQ Link Externalizer 
1. Ändern Sie den Host-Namen für die `author/publish`-Einträge nach Bedarf