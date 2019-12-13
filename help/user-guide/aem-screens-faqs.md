---
title: Häufig gestellte Fragen zu AEM Screens
seo-title: Häufig gestellte Fragen zu AEM Screens
description: Auf dieser Seite erhalten Sie Antworten auf häufig gestellte Fragen zu einem AEM Screens-Projekt.
seo-description: Auf dieser Seite erhalten Sie Antworten auf häufig gestellte Fragen zu einem AEM Screens-Projekt.
uuid: 62e58f3b-0c0a-4006-b6d5-42d2090f47b5
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: f6ee043e41e46690e057758266f9adc5323001d2

---


# Häufig gestellte Fragen zu AEM Screens {#aem-screens-faqs}

Im folgenden Abschnitt finden Sie Antworten auf einige häufig gestellte Fragen zu einem AEM Screens-Projekt.

## Kanalverwaltung {#channel-management}

### 1.Was ist der Unterschied zwischen einem Online- und einem Offline-Kanal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

An ***Online Channel***, will show the updated content in the real time environment whereas an ***Offline Channel***, shows the cached content.

### 2.Wie mache ich einen Kanal online? {#how-do-i-make-a-channel-online}

Wählen Sie den Kanal aus und navigieren Sie in der Aktionsleiste zu den Kanaleigenschaften. Überprüfen Sie den **Entwicklermodus (zwingen Sie den Kanal, online zu sein)** unter der Registerkarte " **Kanal** ", um den Kanal online zu machen.

### 3.Welchen Nutzen hat das Feld Kanalrolle? {#what-is-the-use-of-the-channel-role-field}

Die Kanalrolle ist die Abstraktion des tatsächlichen Kanals, der ausgeführt wird, damit der Autor sich direkt auf das generische Erlebnis konzentrieren kann. Sie können sich das als eine Art Tag vorstellen, das den Kanal in seinem Kontext (Anzeige oder Zeitplan) eindeutig identifiziert.

### 4.Wie erfolgt die tatsächliche Kanalauflösung? {#how-does-actual-channel-resolution-happen}

Bei *statischen Verweisen* folgt die Auflösung nur dem angegebenen Pfad.

Bei *dynamischen Referenzen* erfolgt die Auflösung, sobald der Kanal der Anzeige zugewiesen wurde (nicht dem Zeitplan). Der Anzeigepfad wird zum Kontext des Kanals und die Auflösung erfolgt wie folgt (höchste bis niedrigste Priorität):

1. Die Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt
1. Die Anzeige verfügt über einen gleichrangigen Knoten, der dem Namen des referenzierten Kanals entspricht
1. Die übergeordnete Position der Anzeige hat einen untergeordneten Knoten, der dem Namen des referenzierten Kanals entspricht
1. Die übergeordnete Großposition der Anzeige hat einen untergeordneten Knoten, der mit dem Namen des referenzierten Kanals übereinstimmt

Und so weiter, bis Sie den Ordner "locations"erreichen und dort im Moment anhalten (sodass Sie nicht auf einen Kanal verweisen können, der sich beispielsweise im Ordner "Channels"befindet, sondern nur auf Kanäle in der Unterstruktur der Speicherorte).

## Geräteregistrierung {#device-registration}

### 1.Wenn ich Endpunkte wie z.B. Anfragen nach Geräten beim Einstieg und bei der Registrierung feststelle, kann ich eine große Anzahl von Geräten schreiben und diese Geräte registrieren. Ist es nicht möglich, diese Anforderungen zu sichern, sondern dies auch mit einer Zweigstelle zu sperren? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Derzeit ist die Registrierung nur auf der Autoreninstanz möglich. Obwohl der Registrierungsdienst nicht authentifiziert ist, erstellt er nur ein ausstehendes Gerät in AEM und registriert das Gerät nicht oder weist keine Anzeige zu.

Um ein Gerät zu registrieren (d. h. einen Benutzer für das Gerät in AEM zu erstellen), müssen Sie sich bei AEM authentifizieren und zur Zeit manuell auf den Registrierungsassistenten folgen, um die Registrierung abzuschließen. Theoretisch kann ein bösartiger Benutzer mehrere ausstehende Geräte erstellen, aber keine ohne AEM-Anmeldung registrieren.

### 2.Gibt es eine Möglichkeit, HTTP GET-Anforderungen mit einer Art Authentifizierung in HTTP POST umzuwandeln? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

Die Registrierungsanforderung ist eine POST-Anforderung.

Es wird empfohlen, die Geräte-ID aus der Sitzung abzurufen, anstatt als Parameter weitergegeben zu werden. Dadurch werden die Serverprotokolle, der Browser-Cache usw. bereinigt. Es handelt sich derzeit nicht um ein Sicherheitsproblem. Beachten Sie, dass Semantisch GET verwendet wird, wenn keine Statusänderung auf dem Server erfolgt und POST verwendet wird, wenn eine Statusänderung erfolgt.

### 3.Gibt es eine Möglichkeit, eine Geräteregistrierungsanforderung abzulehnen? {#is-there-a-way-to-decline-a-device-registration-request}

Sie können die Registrierungsanforderungen nicht ablehnen. Stattdessen sollten die Registrierungsanforderungen nach einem Timeout ablaufen, das in [Adobe Experience Manager Web Console](https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.registration.impl.RegistrationServiceImpl)konfiguriert wurde. Standardmäßig ist dieser Wert auf einen Tag festgelegt und wird in einem Arbeitsspeichercache gespeichert.

## Geräteüberwachung und Gesundheitsberichte {#device-monitoring-and-health-reports}

### 1.Wie kann ich eine Fehlerbehebung durchführen, wenn mein AEM Screens-Player einen leeren Bildschirm anzeigt? {#how-do-i-troubleshoot-if-my-aem-screens-player-shows-blank-screen}

Bitte prüfen Sie, ob folgende Möglichkeiten zur Fehlerbehebung bei einem leeren Bildschirmfehler bestehen:

* AEM kann Offline-Inhalte nicht per Push übertragen
* Kanal hat keinen Inhalt
* Keines der Assets soll zur aktuellen Zeit angezeigt werden

### 2.Was kann ich tun, wenn AEM Screens Player nicht registriert werden kann und der Status als "Fehler"angezeigt wird? {#what-do-i-do-if-aem-screens-player-cannot-register-and-its-state-is-displayed-as-failure}

Sie müssen den Apache Sling Referrer-Filter Leer zulassen aktivieren. Dies ist erforderlich, um eine optimale Funktionsweise des Steuerungsprotokolls zwischen AEM Screens Player und AEM Screens Server zu ermöglichen.

1. Navigate to **Adobe Experience Manager Web Console Configuration**
1. Check the **allow.empty** option.
1. Klicken Sie auf **Speichern**.

### 3.Wie kann eine Fehlerbehebung durchgeführt werden, wenn beim Registrieren eines AEM Screens-Players auf dem Gerät ein Fehler "FAILURE"angezeigt wird und in den Konsolenprotokollen der Fehler "ENAME_NOT_FOUND"angezeigt wird? {#how-to-troubleshoot-if-while-registering-an-aem-screens-player-device-shows-failure-and-the-console-logs-display-ename-not-found-error}

Dieses Problem kann auftreten, wenn der Player das AEM Screens Server-DNS nicht finden kann. Sie können versuchen, eine Verbindung über die IP-Adresse herzustellen. Um die IP des Servers abzurufen, verwenden Sie: *arp &lt;server_dns_name&gt;*.

### 4.Empfiehlt AMS die Implementierung eines Android-Watchdog auf allen Geräten? Ist das Watchdog-Plugin (Cordova) als Teil der APK enthalten? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Eine plattformübergreifende Android-Watchdog-App, die reine Android-APIs verwendet, ist bereits Teil der App. Es ist keine zusätzliche Software erforderlich, aber je nach verwendetem Gerät müssen Sie die APK zurücktreten, um Systemberechtigungen für einen vollständigen Betriebszyklus zu erhalten (Powermanager API). Wenn es nicht mit den Herstellerschlüsseln zurückgegeben wird, wird die Anwendung beendet und neu gestartet, nicht jedoch der Betriebszyklus.

Weitere Informationen zur Implementierung von Android Player finden Sie unter [**Implementierung von Android Player**](implementing-android-player.md).

### 5.Welche Remote-Überwachungs- und Warnungs-Tools (Software) von Drittanbietern werden von Adobe/AMS für die Überwachung der einzelnen Geräte empfohlen?  {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Je nachdem, was Sie aus der Überwachung und Warnhinweisen herausfordern, benachrichtigt der AEM Screens-Benachrichtigungsdienst Sie, wenn ein Gerät nicht in einer Weile gepingt wurde. Die Werkzeuge von Drittanbietern hängen von Ihrem Betriebssystem, seinen Fähigkeiten und den spezifischen Anforderungen des Kunden ab.

Weitere Informationen darüber, wo Sie die Geräteaktivität überwachen können, finden Sie im [**AEM Screens-Benachrichtigungsdienst**](screens-notifications-service.md).

## AEM Screens-Player {#aem-screens-player}

### 1.Wie installiere ich den ChromeOS Player als Chrome Browser Plugin? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

Der ChromeOS-Player kann als Chrome-Browser-Plugin im Entwicklermodus installiert werden, ohne dass ein richtiges Chrome-Player-Gerät erforderlich ist. Gehen Sie bei der Installation wie folgt vor:

1. Klicken Sie [hier](https://download.macromedia.com/screens/) , um den neuesten Chrome Player herunterzuladen.
1. Dekomprimieren Sie die Datei und speichern Sie sie auf der Festplatte.
1. Öffnen Sie den Chrome-Browser und klicken Sie auf das Menü mit 3 Punkten und wählen Sie **Mehr Werkzeuge** —&gt; **Erweiterungen** oben rechts oder navigieren Sie direkt zu ***chrome://extensions***.
1. Schalten Sie den **Entwicklermodus** von oben rechts ein.
1. Klicken Sie auf **Entpackte **aus der oberen linken Ecke laden und laden Sie den entpackten Chrome Player.
1. Überprüfen Sie, ob das **AEM Screens Chrome Player** -Plugin in der Liste der Erweiterungen verfügbar ist.
1. Öffnen Sie eine neue Registerkarte und klicken Sie auf das Symbol **Apps** oben links oder navigieren Sie direkt zu ***chrome://apps***.
1. Klicken Sie auf **AEM Screens** Plugin, um Chrome Player zu starten. Standardmäßig wird der Player im Vollbildmodus gestartet. Drücken Sie **esc** , um den Vollbildmodus zu beenden.

### 2.Wie kann eine Fehlerbehebung durchgeführt werden, wenn der Screens-Player nicht über die Veröffentlichungsinstanz mit dem benutzerdefinierten Fehlerhandler authentifiziert werden kann? {#how-to-troubleshoot-if-screens-player-is-unable-to-authenticate-through-publish-instance-with-custom-error-handler}

Beim Start des AEM Screens-Players wird eine Anforderung an ***/content/screens/svc.ping.json*** gesendet, wenn der Player den Fehler 404 erhält. Der Player initiiert eine Authentifizierungsanforderung, um sich für die Veröffentlichungsinstanz zu authentifizieren. Wenn in der Veröffentlichungsinstanz ein benutzerdefinierter Fehler-Handler vorhanden ist, stellen Sie sicher, dass Sie den 404-Statuscode für einen anonymen Benutzer unter ***/content/screens/svc.ping.json*** zurückgeben.

### 3.Wie kann der Gerätebildschirm in einem Android Player aktiviert bleiben? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Führen Sie die folgenden Schritte aus, um "Awak" bei jedem Android-Player zu aktivieren:

1. Navigieren Sie zu den Einstellungen des Android-Players —&gt; **Info**
1. Tippen Sie auf 7 Mal auf die Buildnummer, um **Entwickleroptionen** in **Einstellungen zu aktivieren.**
1. Navigieren Sie zu den **Entwickleroptionen.**
1. Aktivieren Sie **Awake**

## Allgemeine Tipps zur Problembehebung {#general-troubleshooting-tips}

### 1.Wie kann ich Livefyre deaktivieren, um Fehler bei A/P-Bildschirmen zu vermeiden? {#how-to-disable-livefyre-to-avoid-a-p-screens-error}

Zur Deaktivierung von Livefyre zur Vermeidung von Protokollfehlern:

1. ***Livefyre-Bundle deaktivieren:***

   * Navigieren Sie zu `https://&lt;host&gt;:&lt;port&gt;/system/console/bundles`
   * Suchen Sie nach dem AEM Livefyre-Bundle: `com.adobe.cq.social.cq-social-livefyre`
   * Klicken Sie auf **Stopp**

1. ***Livefyre-Poller deaktivieren:***

   * Navigieren Sie in CRXDE Lite zu `/etc/importers/polling/livefyre-poller/jcr:content`
   * Neue *aktivierte* Eigenschaft *Boolescher Typ hinzufügen*
   * Die **Eigenschaft** enabled auf **false setzen**

