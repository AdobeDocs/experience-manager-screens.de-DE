---
title: Häufig gestellte Fragen zu AEM Screens
description: Lesen Sie Antworten auf häufig gestellte Fragen zu einem AEM Screens-Projekt.
feature: Digital Signage, Content
role: Developer
level: Intermediate
exl-id: 67204f04-5535-407c-bd4d-fabfbf850411
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '2118'
ht-degree: 55%

---

# Häufig gestellte Fragen zu AEM Screens {#aem-screens-faqs}

Dieses Thema enthält Antworten auf häufig gestellte Fragen zu einem AEM Screens-Projekt.

## Problem mit leerem Bildschirm {#blank-screen}

>[!NOTE]
>Die aufgelisteten obligatorischen Prüfungen, die vom primären Support oder vom kundenseitigen Support durchgeführt werden sollten, bevor ein Problem gemeldet wird.

### 1. Was sollten die Erste-Hilfe-Schritte zur Fehlerbehebung sein, wenn ein Kunde mit einem schwarzen Bildschirm oder nicht wiedergegebenen Inhalten konfrontiert wird? {#troubleshooting-blank-screen}

* Überprüfen Sie, ob die Kanalvorschau funktioniert.
* Überprüfen Sie, ob die Anzeigenvorschau funktioniert.
* Versuchen Sie, den Player als Browser-Erweiterung auf Ihrem System für dieselbe Anzeige zu registrieren und überprüfen Sie, ob dies funktioniert.
* Wenn der Player auf Ihrem System läuft, navigieren Sie zu `http://localhost:24502`. Überprüfen Sie, ob der gesamte Inhalt korrekt heruntergeladen wurde.
* Überprüfen Sie die Assets, damit Sie sicherstellen können, dass die entsprechenden Ausgabedarstellungen erstellt und die richtige Ausgabedarstellung wiedergegeben wird.
* Überprüfen Sie, ob es geplante Inhalte gibt und ob die Zeiten korrekt sind. Überprüfen Sie, ob die im Player eingestellte Zeit korrekt ist.
* Überprüfen Sie die Protokolle der Player-Konsole und überprüfen Sie sie auf Fehler. Klicken Sie mit der rechten Maustaste und überprüfen Sie die Konsolenprotokolle. Wenn Sie den Windows-Player verwenden, drücken Sie `CTRL + ALT +I` , um die Entwicklungskonsole aufzurufen und die Protokolle anzuzeigen.

### 2. Wie lässt sich das Problem mit grauen Bildschirmen in AEM Screens beim Erstellen eines Standardkanals oder -zeitplans beheben?

Um leere oder graue Bildschirme im Feld zu vermeiden, erstellen Sie einen standardmäßigen globalen Kanal oder Zeitplan, der jeder Anzeige mit der geringsten Priorität 1 zugewiesen wird. Falls etwas bei Inhaltsaktualisierungen fehlschlägt (aufgrund von Netzwerk, Player, Server oder Replikation), da die Player diesen Inhalt bereits auf dem Datenträger zwischengespeichert haben, der gut abgespielt werden sollte und die grauen Bildschirme vermieden werden sollten.

Alle anderen Inhalte wie Kanäle oder Zeitpläne haben eine Priorität größer als 1, sodass der andere Inhalt Priorität hat und der globale Kanal oder der Planinhalt (mit Priorität 1) nur als Fallback-Option wiedergegeben wird.

## Kanalverwaltung {#channel-management}

### 1. Was ist der Unterschied zwischen einem Online- und einem Offline-Kanal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

Ein ***Online-Kanal*** zeigt den aktualisierten Inhalt in der Echtzeit-Umgebung an, während eine ***Offline-Kanal*** zeigt den zwischengespeicherten Inhalt an.

### 2. Wie schalte ich einen Kanal online? {#how-do-i-make-a-channel-online}

Klicken Sie auf den Kanal und navigieren Sie in der Aktionsleiste zu den Kanaleigenschaften. Aktivieren Sie **Entwicklermodus (Kanal zwingen, online zu sein)** auf der Registerkarte **Kanal**, um den Kanal online zu schalten.

### 3. Was ermöglicht das Feld „Kanalrolle“? {#what-is-the-use-of-the-channel-role-field}

Die Kanalrolle ist die Abstraktion des tatsächlichen Kanals, der ausgeführt wird, damit sich der Autor direkt auf das generische Erlebnis konzentrieren kann. Sie können sich die Rolle als eine Art Tag vorstellen, das den Kanal in seinem Kontext (Anzeige oder Zeitplan) eindeutig identifiziert.

### 4. Wie erfolgt die tatsächliche Kanalauflösung? {#how-does-actual-channel-resolution-happen}

Bei *statischen Verweisen* folgt die Auflösung einfach dem angegebenen Pfad.

Bei *dynamischen Verweisen* erfolgt die Auflösung, sobald der Kanal der Anzeige zugewiesen wird (nicht dem Zeitplan). Der Anzeigepfad wird zum Kontext des Kanals und die Auflösung wird wie folgt durchgeführt (höchste zu niedrigster Priorität):

1. Die Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Die Anzeige verfügt über einen gleichrangigen Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Der übergeordnete Standort der Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Der über-übergeordnete Standort der Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt

Und so weiter, bis Sie den Ordner &quot;Speicherorte&quot;erreichen und dort stoppen (sodass Sie nicht auf einen Kanal verweisen können, der sich beispielsweise im Ordner &quot;Kanäle&quot;befindet, sondern nur auf Kanäle in der Unterstruktur &quot;Speicherorte&quot;).

### 5. Wie richten Sie die benutzerdefinierte clientlib-Offline-Konfiguration im AEM Screens-Kanal ein?

Bei Verwendung eines erstellten benutzerdefinierten clientseitigen Codes `clientlib` in einem AEM Screens-Kanal sind die folgenden Schritte erforderlich, um sicherzustellen, dass die `clientlib` -Dateien erfolgreich im Kanal geladen werden (`manifest.json`) und enthält den Pfad der `clientlib`.

Gehen Sie im Kanaleditor wie folgt vor:

1. Klicken Sie auf einen Kanal und dann auf **Bearbeiten** in der Aktionsleiste aus.
1. Klicken Sie auf die Komponente, der Sie die benutzerdefinierte `clientlib`.
1. Klicken Sie auf die Schaltfläche &quot;Konfigurieren&quot;(Schraubenschlüsselsymbol).
1. Gehen Sie zur Registerkarte **Offline-Konfiguration** und fügen Sie den Pfad zu Ihrer benutzerdefinierten clientlib unter **Client-seitige Bibliotheken** hinzu.

## Geräteregistrierung {#device-registration}

### 1. Wenn ich Endpunkte wie Anfragen zum Onboarding und Registrieren von Geräten entdecke, kann ich viele Geräte Skripten erstellen und diese Geräte registrieren. Ist es möglich, diese Anfragen zu schützen und fest mit dem WLAN einer Zweigstelle zu verknüpfen? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Derzeit ist eine Registrierung nur in der Autoreninstanz möglich. Obwohl der Registrierungsdienst nicht authentifiziert ist, erstellt er nur ein ausstehendes Gerät in AEM und registriert das Gerät nicht oder weist keine Anzeige zu.

Um ein Gerät zu registrieren (in AEM Benutzer für das Gerät zu erstellen), authentifizieren Sie sich bei AEM und folgen Sie derzeit manuell dem Registrierungsassistenten, um die Registrierung abzuschließen. Theoretisch kann ein böswilliger Benutzer mehrere ausstehende Geräte erstellen, ohne Anmeldung in AEM jedoch keines von ihnen registrieren.

### 2. Ist es möglich, mit einer bestimmten Form von Authentifizierung HTTP GET-Anfragen in HTTP POST umzuwandeln? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

Die Registrierungsanfrage ist eine POST-Anfrage.

Es wird empfohlen, die Geräte-ID aus der Sitzung abzurufen, anstatt sie als Parameter zu übernehmen. Dadurch werden die Server-Protokolle, der Browsercache usw. bereinigt. Das ist keine Sicherheitsfrage. Semantisch. GET wird verwendet, wenn keine Statusänderung auf dem Server erfolgt und die POST verwendet wird, wenn eine Statusänderung erfolgt.

### 3. Ist es möglich, eine Anfrage zur Geräteregistrierung abzulehnen? {#is-there-a-way-to-decline-a-device-registration-request}

Sie können Registrierungsanfragen nicht ablehnen. Stattdessen sollten Registrierungsanfragen nach einer Zeitüberschreitung ablaufen, die in `Adobe Experience Manager Web Console` konfiguriert ist. Standardmäßig ist dieser Wert auf einen Tag festgelegt und wird in einem Arbeitsspeicher-Cache gespeichert.

## Geräteüberwachung und Statusberichte {#device-monitoring-and-health-reports}

### 1. Wie kann ich eine Fehlerbehebung vornehmen, wenn der AEM Screens-Player einen leeren Bildschirm anzeigt?

Überprüfen Sie, ob folgende Möglichkeiten zur Fehlerbehebung für das Problem mit dem leeren Bildschirm verfügbar sind:

* AEM kann die Offline-Inhalte nicht im Push-Verfahren übertragen
* Der Kanal weist keinen Inhalt auf
* Keines der Assets soll gerade angezeigt werden

### 2. Was kann ich tun, wenn der AEM Screens-Player nicht registriert werden kann und den Status „Failure“ aufweist?

Aktivieren Sie den Apache Sling Referrer-Filter &quot;Allow Empty&quot;. Dies ist erforderlich, um eine optimale Funktionsweise des Steuerungsprotokolls zwischen dem AEM Screens-Player und dem AEM Screens-Server zu ermöglichen.

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**.
1. Aktivieren Sie die Option **allow.empty**.
1. Klicken Sie auf **Speichern**.

### 3. Wie lässt sich ein Problem beheben, wenn beim Registrieren eines AEM Screens-Players auf dem Gerät „FAILURE“ und in den Protokollen der Konsole der Fehler „ENAME_NOT_FOUND“ angezeigt wird?

Das Problem kann auftreten, wenn der Player das DNS des AEM Screens-Servers nicht finden kann. Sie können versuchen, eine Verbindung über die IP-Adresse herzustellen. Um die IP des Servers abzurufen, verwenden Sie *arp &lt;Server-DNS-Name>*.

### 4. Empfiehlt AMS die Implementierung eines Android™ Watchdog auf allen Geräten? Ist das Watchdog-Plug-in (Cordova) Teil des APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Ein plattformübergreifender Android™-Watchdog, der reine Android™-APIs verwendet, ist bereits Teil der APK. Es ist keine zusätzliche Software erforderlich. Je nach dem von Ihnen verwendeten Gerät können Sie die APK jedoch zurücksetzen, um Systemberechtigungen für einen vollständigen Leistungszyklus zu erhalten (`Powermanager` api), falls erforderlich. Wenn es nicht mithilfe der Herstellerschlüssel zurückgegeben wird, wird die Anwendung beendet und neu gestartet, es wird jedoch kein Betriebszyklus durchgeführt.

Weitere Informationen zur Implementierung des Android™-Players finden Sie unter [**Implementieren von Android™ Player**](implementing-android-player.md).

### 5. Welche Remote-Überwachungs- und Warnmeldungs-Tools (Software) von Drittanbietern empfiehlt Adobe/AMS zur Überwachung einzelner Geräte? {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Je nachdem, welches Ergebnis Sie von der Überwachung und den Warnmeldungen wünschen, benachrichtigt Sie der AEM Screens-Benachrichtigungsdienst, wenn ein Gerät länger nicht mehr gepingt hat. Die Tools von Drittanbietern hängen von Ihrem Betriebssystem (Betriebssystem), dessen Funktionen und den spezifischen Anforderungen des Kunden ab.

Weitere Informationen darüber, wo Sie Geräteaktivität überwachen können, finden Sie unter [**AEM Screens ns-Benachrichtigungsdienst**](screens-notifications-service.md).

## AEM Screens-Player

### 1. Wie installiere ich den Chrome OS-Player als Chrome-Browser-Plug-in? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

Im Entwicklermodus kann der Chrome OS-Player als Chrome-Browser-Plug-in installiert werden, ohne dass ein echtes Chrome-Player-Gerät erforderlich ist. Gehen Sie zur Installation wie folgt vor:

1. Klicken Sie [hier](https://download.macromedia.com/screens/), um den neuesten Chrome-Player herunterzuladen.
1. Entpacken Sie die Datei und speichern Sie sie auf der Festplatte.
1. Öffnen Sie den Chrome-Browser und klicken Sie auf **Erweiterungen** aus dem Menü oder direkt zu ***chrome://extensions***.
1. Schalten Sie die **Entwicklermodus** oben rechts.
1. Klicks **Entpacktes Laden** oben links und laden Sie den entpackten Chrome-Player.
1. Wenn in der Liste der Erweiterungen verfügbar, überprüfen Sie **AEM Screens Chrome-Player** Plug-in.
1. Öffnen Sie eine neue Registerkarte und klicken Sie auf **Apps** Symbol oben links oder navigieren Sie direkt zu ***chrome://apps***.
1. Klicken Sie auf **AEM Screens** Plug-in. Standardmäßig wird der Player im Vollbildmodus gestartet. Presse **Esc** , um den Vollbildmodus zu beenden.

### 2. Wie kann eine Fehlerbehebung durchgeführt werden, wenn der Screens-Player nicht über die Veröffentlichungsinstanz mit dem benutzerdefinierten Fehler-Handler authentifiziert werden kann?

Wenn der AEM Screens-Player beim Starten einen 404-Fehler erhält, stellt er eine Anfrage an ***/content/screens/svc.ping.json***. Der Player initiiert eine Authentifizierungsanfrage, um sich bei der Veröffentlichungsinstanz zu authentifizieren. Wenn es in der Veröffentlichungsinstanz einen benutzerdefinierten Fehler-Handler gibt, stellen Sie sicher, dass Sie den 404-Status-Code für einen anonymen Benutzer bei ***/content/screens/svc.ping.json***.

### 3. Wie lässt sich der Gerätebildschirm in einem Android™-Player einschalten? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Gehen Sie wie folgt vor, um Stay Awake in einem beliebigen Android™-Player zu aktivieren:

1. Navigieren Sie zu den Einstellungen des Android™-Players > **Info**.
1. Tippen Sie siebenmal auf die Build-Nummer, damit Sie **Entwickleroptionen** in **Einstellungen**.
1. Navigieren Sie zu **Entwickleroptionen**.
1. Aktivieren **Stay Awake**.

### 4. Wie wird der Fenstermodus für den Windows-Player aktiviert? {#enable-player}

Der Windows-Player verfügt über keinen Fenstermodus. Der Vollbildmodus ist immer aktiviert.

### 5. Wie kann eine Fehlerbehebung durchgeführt werden, wenn ein AEM Screens-Player ständig Login-Anfragen sendet? 

Gehen Sie wie folgt vor, um eine Fehlerbehebung bei einem AEM Screens-Player durchzuführen, der fortlaufend Anfragen an `/content/screens/svc.json` und `/libs/granite/core/content/login.validate/j_security_check` sendet:

1. Wenn der AEM Screens-Player gestartet wird, sendet er eine Anfrage an `/content/screens/svc.json`. Wenn der Player in der Antwort einen 404-Status-Code erhält, startet er eine Authentifizierungsanfrage durch Verwendung von `/libs/granite/core/content/login.validate/j_security_check` gegen *publish* -Instanz. Wenn es in der *Veröffentlichungsinstanz* einen benutzerdefinierten Fehler-Handler gibt, stellen Sie sicher, dass Sie in `/content/screens/svc.json` bzw. `/content/screens/svc.ping.json` den 404-Status-Code für einen anonymen Benutzer zurückgeben.

1. Überprüfen Sie, ob diese Anforderungen in Ihrer Dispatcher-Konfiguration im `/filters`.

   Weitere Informationen finden Sie unter [Konfigurieren von Screens-Filtern](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#step-configure-screens-filters).

1. Überprüfen Sie, ob Ihre Dispatcher-Neuschreibungsregeln einen der Bildschirmpfade in einen anderen Pfad umschreiben.

1. Überprüfen Sie, ob Sie `/etc/map`-Regeln in der *Autoren*- oder *Veröffentlichungsinstanz* verwenden und ob die Bildschirmpfade mit `sling:match` übereinstimmen und interen zu einem anderen Pfad umgeleitet werden. Die Auflösung der exakten URL in `/system/console/jcrresolver` hilft dabei herauszufinden, ob die *Veröffentlichungsinstanz* diese URLs in einen anderen Pfad umschreibt.

1. Überprüfen Sie, ob die Apache Sling Resource Resolver Factory-Konfiguration interne Neuschreibungen verursacht.

### 6. Wie können Details zu Anzeige und Gerät von der Player-API abgerufen werden?

Die Details zu Anzeige und Gerät erhalten Sie über:

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

Deaktivieren Sie Livefyre, um Protokollfehler zu vermeiden, indem Sie Folgendes ausführen.

1. ***Livefyre-Bundle deaktivieren:***

   * Navigieren Sie zu `https://<host>:<port>/system/console/bundles`.
   * Suchen Sie nach dem AEM Livefyre-Bundle: `com.adobe.cq.social.cq-social-livefyre`.
   * Klicks **Anhalten**.

1. ***Livefyre-Poller deaktivieren:***

   * Navigieren Sie unter CRXDE Lite zu `/etc/importers/polling/livefyre-poller/jcr:content`.
   * Hinzufügen einer Eigenschaft *enabled* type *Boolesch*.
   * Satz **enabled-Eigenschaft** nach **false**.

### 2. Wie fügt man Oak-Index-Informationen hinzu? {#add-oak-index-info}

AEM Screens erstellt Indexdefinitionen für die vom Produkt verwendeten Abfragen.
Wenn es im `error.log` *abfrageübergreifende Warnhinweise (WARN)* gibt, erstellen Sie einen benutzerdefinierten Index für Ihre Abfrage. Siehe [Konfigurieren der Indizes](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#configuring-the-indexes) für weitere Details.

Sie können auch eine zusätzliche Ressource in [Oak-Dokumentation](https://jackrabbit.apache.org/oak/docs/query/lucene.html).


### 3. Was ist erforderlich, um V3-Manifeste zu konfigurieren? {#configure-v3}

Gehen Sie wie folgt vor, um das v3-Manifest zu aktivieren:

* Dispatcher aktualisieren.
Weitere Informationen finden Sie unter [Konfigurieren des Dispatchers für Manifest Version 3](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3).

* Benutzerdefinierte Komponente aktualisieren.
Weitere Informationen finden Sie unter [Vorlage für benutzerdefinierte Handler](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers).

* ContentSync in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` deaktivieren.

* SmartSync in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl` aktivieren.

* `channel/experience fragment/page components` bearbeiten.

* Navigieren Sie zur Registerkarte **Offline-Konfiguration**.

* Eingabe `clientlibs `und Ordner für statische Dateien, die zum Manifest hinzugefügt werden müssen.

### 4. Was sollten Sie tun, wenn nach dem Paket „screens-cloud-ams-pkg-0.0.20“ „screens-cloud-ams-pkg-0.0.16“ und die Screens-Core-Bundles installiert, aber nicht aktiv sind?

Installieren Sie eine Mindestversion von AEM 6.5 Feature Pack 8 , damit der AMS-Connector funktioniert. Siehe [Verfügbarkeit](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202105#availability) sodass Sie die Mindestversion des AEM Screens Feature Packs erhalten.

### 5. Wie konfiguriere ich den CQ Link Externalizer-Dienst in Screens?

Der Service wird verwendet, um den öffentlichen Host-Namen für die Autoren- und Veröffentlichungsinstanz zu definieren. Die Werte werden dann zum Aktualisieren der Geräte-Server-URLs und auch für das ContextHub-Targeting verwendet.

Der CQ Link Externalizer-Service in Screens kann wie folgt konfiguriert werden:

1. Navigieren Sie zu `http://localhost:4502/system/console/configMgr`
1. Day CQ Link Externalizer 
1. Ändern Sie den Host-Namen für die `author/publish`-Einträge nach Bedarf