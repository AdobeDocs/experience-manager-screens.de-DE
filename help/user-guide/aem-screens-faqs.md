---
title: Häufig gestellte Fragen zu AEM Screens
seo-title: AEM Screens FAQs
description: Auf dieser Seite erhalten Sie Antworten auf häufig gestellte Fragen zu AEM Screens-Projekten.
seo-description: Follow this page to get answers to FAQs related to an AEM Screens project.
feature: Digital Signage, Content
role: Developer
level: Intermediate
exl-id: 67204f04-5535-407c-bd4d-fabfbf850411
source-git-commit: 77ec3e6de6760bc5e31675399ed91bac4150ae69
workflow-type: tm+mt
source-wordcount: '2040'
ht-degree: 92%

---

# Häufig gestellte Fragen zu AEM Screens {#aem-screens-faqs}

Im folgenden Abschnitt finden Sie Antworten auf verschiedene häufig gestellte Fragen zu AEM Screens-Projekten.

## Problem mit leerem Bildschirm {#blank-screen}

>[!NOTE]
>Die aufgelisteten obligatorischen Prüfungen, die vom primären Support oder vom kundenseitigen Support durchgeführt werden sollten, bevor ein Problem gemeldet wird.

### 1. Was sollten die Erste-Hilfe-Schritte zur Fehlerbehebung sein, wenn ein Kunde mit einem schwarzen Bildschirm oder nicht wiedergegebenen Inhalten konfrontiert wird? {#troubleshooting-blank-screen}

* Überprüfen Sie, ob die Kanalvorschau funktioniert.
* Überprüfen Sie, ob die Anzeigenvorschau funktioniert.
* Versuchen Sie, den Player als Browser-Erweiterung auf Ihrem System für dieselbe Anzeige zu registrieren und überprüfen Sie, ob dies funktioniert.
* Wenn der Player auf Ihrem System läuft, navigieren Sie zu `http://localhost:24502`. Überprüfen Sie, ob der gesamte Inhalt korrekt heruntergeladen wurde.
* Überprüfen Sie, ob die entsprechenden Ausgabedarstellungen erstellt wurden und die richtige Ausgabedarstellung wiedergegeben wird.
* Überprüfen Sie, ob es geplante Inhalte gibt und ob die Zeiten korrekt sind. Überprüfen Sie, ob die im Player eingestellte Zeit korrekt ist.
* Überprüfen Sie die Protokolle der Player-Konsole und überprüfen Sie sie auf Fehler. Klicken Sie mit der rechten Maustaste und überprüfen Sie die Konsolenprotokolle. Wenn Sie den Windows-Player verwenden, drücken Sie `CTRL + ALT +I`, um die Entwicklungskonsole aufzurufen und die Protokolle anzuzeigen.

### 2. Wie lässt sich das Problem mit grauen Bildschirmen in AEM Screens beim Erstellen eines Standardkanals oder -zeitplans beheben?

Um die leeren oder grauen Bildschirme im Feld zu vermeiden, erstellen Sie einen globalen Standardkanal oder -zeitplan, der jeder Anzeige mit der geringsten Priorität 1 zugewiesen ist. Falls bei Inhaltsaktualisierungen ein Fehler auftritt (aufgrund von Netzwerk, Player, Server oder Replikation), sollte der Inhalt fehlerfrei und ohne graue Bildschirme wiedergegeben werden, da der Inhalt bereits auf der Festplatte des Players zwischengespeichert ist.

Alle anderen Inhalte, wie Kanäle oder Zeitpläne, haben eine Priorität größer als 1, sodass der andere Inhalt Priorität hat und der globale Kanal- oder Zeitplaninhalt (mit Priorität 1) nur als Fallback-Option wiedergegeben wird.

## Kanalverwaltung {#channel-management}

### 1. Was ist der Unterschied zwischen einem Online- und einem Offline-Kanal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

Ein ***Online-Kanal*** zeigt den aktualisierten Inhalt in der Echtzeitumgebung an, während ein ***Offline-Kanal*** den im Cache gespeicherten Inhalt wiedergibt.

### 2. Wie schalte ich einen Kanal online? {#how-do-i-make-a-channel-online}

Wählen Sie den Kanal aus und navigieren Sie in der Aktionsleiste zu den Kanaleigenschaften. Aktivieren Sie **Entwicklermodus (Kanal zwingen, online zu sein)** auf der Registerkarte **Kanal**, um den Kanal online zu schalten.

### 3. Was ermöglicht das Feld „Kanalrolle“?  {#what-is-the-use-of-the-channel-role-field}

Die Kanalrolle ist eine Abstraktion des tatsächlichen Kanals, die ausgeführt wird, damit sich der Autor direkt auf das generische Erlebnis konzentrieren kann. Sie können sich die Rolle als eine Art Tag vorstellen, das den Kanal in seinem Kontext (Anzeige oder Zeitplan) eindeutig identifiziert.

### 4. Wie erfolgt die tatsächliche Kanalauflösung? {#how-does-actual-channel-resolution-happen}

Bei *statischen Verweisen* folgt die Auflösung einfach dem angegebenen Pfad.

Bei *dynamischen Verweisen* erfolgt die Auflösung, sobald der Kanal der Anzeige zugewiesen wird (nicht dem Zeitplan). Der Anzeigepfad wird zum Kontext des Kanals und die Auflösung wird wie folgt durchgeführt (höchste zu niedrigster Priorität):

1. Die Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Die Anzeige verfügt über einen gleichrangigen Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Der übergeordnete Standort der Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Der über-übergeordnete Standort der Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt

Und so weiter, bis Sie den Standortordner erreichen und dort anhalten (Sie können also nicht auf einen Kanal verweisen, der sich zum Beispiel im Kanalordner befindet, sondern nur auf Kanäle in der Unterstruktur der Standorte)

### 5. Wie wird die benutzerdefinierte clientlib-Offline-Konfiguration im AEM Screens-Kanal eingerichtet?

Bei Verwendung eines erstellten benutzerdefinierten clientseitigen Codes `clientlib` in einem AEM Screens-Kanal sind die folgenden Schritte erforderlich, um sicherzustellen, dass die `clientlib` -Dateien erfolgreich im Kanal geladen werden (`manifest.json`) und enthält den Pfad der `clientlib`.

Gehen Sie im Kanaleditor wie folgt vor:

1. Wählen Sie einen Kanal aus und klicken Sie auf **Bearbeiten** in der Aktionsleiste, um den Kanaleditor zu öffnen.
1. Wählen Sie die Komponente aus, der Sie die benutzerdefinierte `clientlib`.
1. Klicken Sie auf die Schaltfläche &quot;Konfigurieren&quot;(das Schraubenschlüsselsymbol).
1. Navigieren Sie zum **Offline-Konfiguration** und fügen Sie den Pfad zu Ihrer benutzerdefinierten Client-Bibliothek in **Client-seitige Bibliotheken**.

## Geräteregistrierung {#device-registration}

### 1. Bei der Ermittlung von Endpunkten (z. B. Anfragen zum Onboarding und Registrieren von Geräten) kann ich Skripte für eine große Zahl von Geräten verfassen, um die Geräte zu registrieren. Ist es möglich, diese Anfragen zu schützen und fest mit dem WLAN einer Zweigstelle zu verknüpfen? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Derzeit ist eine Registrierung nur in der Autoreninstanz möglich. Obwohl der Registrierungsdienst nicht authentifiziert ist, erstellt er in AEM nur ein ausstehendes Gerät, das jedoch weder registriert noch einer Anzeige zugewiesen wird.

Um ein Gerät zu registrieren (d. h. in AEM einen Benutzer für das Gerät zu erstellen), müssen Sie sich bei AEM authentifizieren und derzeit manuell den Registrierungsassistenten nutzen, um die Registrierung abzuschließen. Theoretisch kann ein böswilliger Benutzer mehrere ausstehende Geräte erstellen, ohne Anmeldung in AEM jedoch keines von ihnen registrieren.

### 2. Ist es möglich, mit einer bestimmten Form von Authentifizierung HTTP GET-Anfragen in HTTP POST umzuwandeln? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

Die Registrierungsanfrage ist eine POST-Anfrage.

Es wird empfohlen, die Geräte-ID aus der Sitzung abzurufen, anstatt sie als Parameter zu übernehmen. Dadurch werden die Server-Protokolle, der Browsercache usw. bereinigt. Es handelt sich dabei derzeit nicht um ein Sicherheitsproblem. Beachten Sie, dass GET semantisch verwendet wird, wenn keine Statusänderung auf dem Server erfolgt, und POST zum Einsatz kommt, wenn eine Statusänderung erfolgt.

### 3. Ist es möglich, eine Anfrage zur Geräteregistrierung abzulehnen? {#is-there-a-way-to-decline-a-device-registration-request}

Sie können Registrierungsanfragen nicht ablehnen. Stattdessen sollten Registrierungsanfragen nach einer Zeitüberschreitung ablaufen, die in `Adobe Experience Manager Web Console` konfiguriert ist. Standardmäßig ist dieser Wert auf einen Tag festgelegt und wird in einem Arbeitsspeicher-Cache gespeichert.

## Geräteüberwachung und Statusberichte {#device-monitoring-and-health-reports}

### 1. Wie kann ich eine Fehlerbehebung vornehmen, wenn der AEM Screens-Player einen leeren Bildschirm anzeigt? {#how-do-i-troubleshoot-if-my-aem-screens-player-shows-blank-screen}

Prüfen Sie folgende Möglichkeiten, um Probleme mit einem leeren Bildschirm zu beheben:

* AEM kann die Offline-Inhalte nicht im Push-Verfahren übertragen
* Der Kanal weist keinen Inhalt auf
* Keines der Assets soll gerade angezeigt werden

### 2. Was kann ich tun, wenn der AEM Screens-Player nicht registriert werden kann und den Status „Failure“ aufweist? {#what-do-i-do-if-aem-screens-player-cannot-register-and-its-state-is-displayed-as-failure}

Sie müssen die Option „Apache Sling Referrer Filter Allow Empty“ aktivieren. Dies ist erforderlich, um eine optimale Funktionsweise des Steuerungsprotokolls zwischen dem AEM Screens-Player und dem AEM Screens-Server zu ermöglichen.

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**.
1. Aktivieren Sie die Option **allow.empty**.
1. Klicken Sie auf **Speichern**.

### 3. Wie lässt sich ein Problem beheben, wenn beim Registrieren eines AEM Screens-Players auf dem Gerät „FAILURE“ und in den Protokollen der Konsole der Fehler „ENAME_NOT_FOUND“ angezeigt wird? {#how-to-troubleshoot-if-while-registering-an-aem-screens-player-device-shows-failure-and-the-console-logs-display-ename-not-found-error}

Das Problem kann auftreten, wenn der Player das DNS des AEM Screens-Servers nicht finden kann. Sie können versuchen, eine Verbindung über die IP-Adresse herzustellen. Um die IP des Servers abzurufen, verwenden Sie *arp &lt;Server-DNS-Name>*.

### 4. Empfiehlt AMS die Implementierung eines Android-Watchdog auf allen Geräten? Ist das Watchdog-Plug-in (Cordova) Teil des APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Ein plattformübergreifender Android-Watchdog, der reine Android-APIs nutzt, ist bereits Bestandteil des APK. Es ist keine zusätzliche Software erforderlich, aber je nach verwendetem Gerät müssen Sie das APK neu signieren, um Systemberechtigungen für einen vollständigen Betriebszyklus zu erhalten (Powermanager-API). Falls es nicht mit den Herstellerschlüsseln neu signiert wird, wird das APK beendet und die Anwendung neu gestartet, jedoch ohne Betriebszyklus.

Weitere Informationen zur Implementierung des Android-Players finden Sie unter [**Implementieren des Android-Players**](implementing-android-player.md).

### 5. Welche Remote-Überwachungs- und Warnmeldungs-Tools (Software) von Drittanbietern empfiehlt Adobe/AMS zur Überwachung einzelner Geräte?   {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Je nachdem, welches Ergebnis Sie von der Überwachung und den Warnmeldungen wünschen, benachrichtigt Sie der AEM Screens-Benachrichtigungsdienst, wenn ein Gerät länger nicht mehr gepingt hat. Geeignete Tools von Drittanbietern hängen vom jeweiligen Betriebssystem, seinen Funktionen und den spezifischen Anforderungen des Kunden ab.

Wenn Sie weitere Informationen dazu benötigen, wie Sie Geräteaktivität überwachen können, konsultieren Sie [**AEM Screens-Benachrichtigungsdienst**](screens-notifications-service.md).

## AEM Screens-Player {#aem-screens-player}

### 1. Wie installiere ich den Chrome OS-Player als Chrome-Browser-Plug-in? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

Im Entwicklermodus kann der Chrome OS-Player als Chrome-Browser-Plug-in installiert werden, ohne dass ein echtes Chrome-Player-Gerät erforderlich ist. Gehen Sie zur Installation wie folgt vor:

1. Klicken Sie [hier](https://download.macromedia.com/screens/), um den neuesten Chrome-Player herunterzuladen.
1. Entpacken Sie die Datei und speichern Sie sie auf der Festplatte.
1. Öffnen Sie den Chrome-Browser und wählen Sie im Menü die Option **Erweiterungen** oder navigieren Sie direkt zu ***chrome://extensions***.
1. Aktivieren Sie oben rechts den **Entwicklermodus**.
1. Klicken Sie oben links auf **Entpackte Erweiterung laden** und laden Sie den entpackten Chrome-Player.
1. Überprüfen Sie, ob in der Liste der Erweiterungen das Plug-in **AEM Screens Chrome Player** aufgeführt wird.
1. Öffnen Sie eine neue Registerkarte und klicken Sie oben links auf das Symbol **Apps** oder navigieren Sie direkt zu ***chrome://apps***.
1. Klicken Sie auf das Plug-in **AEM Screens**, um den Chrome-Player zu starten. Standardmäßig wird der Player im Vollbildmodus gestartet. Drücken Sie **Esc**, um den Vollbildmodus zu beenden.

### 2. Wie kann ich ein Problem beheben, wenn der Screens-Player bei einer Veröffentlichungsinstanz, die einen benutzerdefinierten Fehler-Handler aufweist, nicht authentifiziert werden kann? {#how-to-troubleshoot-if-screens-player-is-unable-to-authenticate-through-publish-instance-with-custom-error-handler}

Wenn der AEM Screens-Player beim Starten einen 404-Fehler erhält, stellt er eine Anfrage an ***/content/screens/svc.ping.json***. Der Player initiiert eine Authentifizierungsanforderung, um sich bei der Veröffentlichungsinstanz zu authentifizieren. Wenn es in der Veröffentlichungsinstanz einen benutzerdefinierten Fehler-Handler gibt, sorgen Sie dafür, dass Sie in ***/content/screens/svc.ping.json*** den 404-Status-Code für einen anonymen Benutzer zurückgeben.

### 3. Wie lässt sich der Gerätebildschirm in einem Android-Player dauerhaft einschalten? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Führen Sie folgende Schritte durch, um „Stay Awake“ in einem beliebigen Android-Player zu aktivieren:

1. Navigieren Sie zu den Einstellungen des Android-Players > **Über**.
1. Tippen Sie 7-mal auf die Build-Nummer, um **Entwickleroptionen** in den **Einstellungen** zu aktivieren.
1. Navigieren Sie zu den **Entwickleroptionen**.
1. Aktivieren Sie **Stay Awake**.

### 4. Wie wird der Fenstermodus für den Windows-Player aktiviert?{#enable-player}

Der Windows-Player verfügt über keinen Fenstermodus. Der Vollbildmodus ist immer aktiviert.

### 5. Wie kann eine Fehlerbehebung durchgeführt werden, wenn ein AEM Screens-Player ständig Login-Anfragen sendet? {#requests-login}

Gehen Sie wie folgt vor, um eine Fehlerbehebung bei einem AEM Screens-Player durchzuführen, der fortlaufend Anfragen an `/content/screens/svc.json` und `/libs/granite/core/content/login.validate/j_security_check` sendet:

1. Wenn der AEM Screens-Player gestartet wird, sendet er eine Anfrage an `/content/screens/svc.json`. Wenn der Player daraufhin eine Antwort mit einem 404-Status-Code erhält, startet er eine Authentifizierungsanfrage mit `/libs/granite/core/content/login.validate/j_security_check` bei der *Veröffentlichungsinstanz*. Wenn es in der *Veröffentlichungsinstanz* einen benutzerdefinierten Fehler-Handler gibt, stellen Sie sicher, dass Sie in `/content/screens/svc.json` bzw. `/content/screens/svc.ping.json` den 404-Status-Code für einen anonymen Benutzer zurückgeben.

1. Überprüfen Sie, ob Ihre Dispatcher-Konfiguration diese Anfragen in `/filters` zulässt.

   Weitere Informationen finden Sie unter [Konfigurieren von Screens-Filtern](https://docs.adobe.com/content/help/de-DE/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html#step-configuring-screens-filters).

1. Überprüfen Sie, ob die Umschreibungsregeln des Dispatchers einen Bildschirmpfad in einen anderen Pfad umschreiben.

1. Überprüfen Sie, ob Sie `/etc/map`-Regeln in der *Autoren*- oder *Veröffentlichungsinstanz* verwenden und ob die Bildschirmpfade mit `sling:match` übereinstimmen und interen zu einem anderen Pfad umgeleitet werden. Die Auflösung der exakten URL in `/system/console/jcrresolver` hilft dabei herauszufinden, ob die *Veröffentlichungsinstanz* diese URLs in einen anderen Pfad umschreibt.

1. Überprüfen Sie, ob die Apache Sling Resource Resolver Factory-Konfiguration interne Umschreibungen verursacht.

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

### 1. Wie kann ich Livefyre deaktivieren, um A/P-Screens-Fehler zu vermeiden? {#how-to-disable-livefyre-to-avoid-a-p-screens-error}

So deaktivieren Sie Livefyre, um Protokollfehler zu vermeiden:

1. ***Livefyre-Bundle deaktivieren:***

   * Navigieren Sie zu `https://&lt;host&gt;:&lt;port&gt;/system/console/bundles`
   * Suchen Sie nach dem AEM Livefyre-Bundle: `com.adobe.cq.social.cq-social-livefyre`
   * Klicken Sie auf **Anhalten**

1. ***Livefyre-Poller deaktivieren:***

   * Navigieren Sie in CRXDE Lite zu `/etc/importers/polling/livefyre-poller/jcr:content`
   * Fügen Sie eine neue *aktivierte* Eigenschaft vom Typ *Boolesch* hinzu
   * Setzen Sie die **aktivierte Eigenschaft** auf **false**

### 2. Wie fügt man Oak-Index-Informationen hinzu? {#add-oak-index-info}

AEM Screens erstellt Indexdefinitionen für die vom Produkt verwendeten Abfragen.
Wenn es im `error.log` *abfrageübergreifende Warnhinweise (WARN)* gibt, erstellen Sie einen benutzerdefinierten Index für Ihre Abfrage. Weitere Informationen finden Sie unter [Konfigurieren der Indizes](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=de#configuring-the-indexes).

Sie können auch auf eine zusätzliche Ressource in der [Oak-Dokumentation](https://jackrabbit.apache.org/oak/docs/query/lucene.html) zurückgreifen.


### 3. Was ist erforderlich, um v3-Manifeste zu konfigurieren? {#configure-v3}

Um das v3-Manifest zu aktivieren, müssen Sie:

* Aktualisieren Sie den Dispatcher.
Siehe [Konfigurieren des Dispatchers für die Manifestversion v3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=de#configuring-dispatcherv3) für weitere Details.

* Benutzerdefinierte Komponente aktualisieren
Siehe [Vorlage für benutzerdefinierte Handler](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=de#custom-handlers) für weitere Details.

* ContentSync deaktivieren in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag`.

* Aktivieren Sie SmartSync in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl`.
