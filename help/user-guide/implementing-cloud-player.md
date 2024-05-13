---
title: Implementieren des Cloud-Players
description: Erfahren Sie mehr über die Implementierung des Cloud-Players.
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 184168f5-6070-4c33-a2c5-5429061dac75
source-git-commit: 6720e20f5254e869bde814bd167730e426d0f8fe
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 74%

---

# Implementieren des Cloud-Players {#implementing-cloud-player}

Bisher hat AEM Screens separate native Player-Anwendungen für verschiedene Plattformen wie ChromeOS, Windows, Android und `Tizen` angeboten. Da sich die Bedürfnisse von Benutzenden jedoch ständig weiterentwickeln, hat Adobe eine innovative Lösung eingeführt: den AEM Screens-Cloud-Player.

Der Cloud-Player weicht deutlich von den vorherigen nativen Adobe-Anwendungen ab. Es handelt sich dabei um eine Progressive Web App (PWA), die auf einem Server gehostet wird. Dieser transformative Ansatz stellt Kundinnen und Kunden einen plattformunabhängigen Player zur Verfügung, der direkt in einem Webbrowser ausgeführt wird.

Der Zugriff auf den Cloud-Player erfolgt ganz einfach über `https://player.adobescreens.com`. Benutzende können ihn unabhängig von der Plattform auf ihrem Gerät installieren und sich über ein nahtloses Erlebnis für digitale Beschilderungen freuen. Die Kompatibilität des Cloud-Players hängt von der Verfügbarkeit eines modernen Browsers mit PWA-Unterstützung ab, um eine konsistente Leistung auf verschiedenen Geräten sicherzustellen. Manuelle Aktualisierungen haben ein Ende. Freuen Sie sich stattdessen über einen Player, der automatisch Fehlerbehebungen und Funktionen bereitstellt, sodass Sie stets über die neuesten Funktionen verfügen. Diese Umstellung auf einen PWA-basierten Cloud-Player stellt eine spannende Weiterentwicklung des Adobe-Angebots an Digital Signage dar, das dadurch leichter zugänglich, vielseitiger und benutzerfreundlicher als je zuvor wird.

In diesem Abschnitt wird die Implementierung des Cloud-Players beschrieben.

>[!NOTE]
>
>Die Kompatibilität des Cloud-Players erfordert einen modernen Browser mit PWA-Unterstützung, um eine konsistente Leistung auf verschiedenen Geräten sicherzustellen.

## Installieren des Cloud Players {#installing-cloud-player}

Die Installation des Cloud-Players kann auf verschiedenen Plattformen variieren. Im Allgemeinen kann jede Plattform mit einem modernen Browser die Cloud Player-Anwendung ausführen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie den Browser und geben Sie die [Cloud-Player-URL](https://player.adobescreens.com/content/dam/universal-player/firmware.html) in die Adressleiste ein.
1. Der Browser prüft, ob der Cloud Player installiert ist, und zeigt dann in der Adressleiste ein Installationssymbol an.

   ![Bild](/help/user-guide/assets/cloud-player-install.png)

1. Klicken Sie im Bestätigungsdialogfeld auf das Installationssymbol und die Schaltfläche &quot;Installieren&quot;. Der Cloud-Player wird als eigenständige Anwendung auf Ihrem Gerät installiert und kann über ein Symbol gestartet werden.

>[!NOTE]
>
>### Cloud-Player-Installationsoption {#cloud-player-install-option}
>
1. Die Installationsoption für eine PWA wird auch als A2HS-Funktion („Add to Home Screen = Zum Startbildschirm hinzufügen“) bezeichnet.  Die Unterstützung für die Installation von PWA über das Internet variiert je nach Browser und Plattform.
1. Jeder Browser hat unterschiedliche Kriterien, um zu überprüfen, ob die PWA installiert ist oder nicht. Im Allgemeinen kann der Browser Folgendes überprüfen (weitere Details finden Sie hier):
>
* Wenn die Anwendung über eine JSON-Manifestdatei mit minimalen erforderlichen Schlüsseln für die Installation der App auf der Plattform verfügt, d. h. Name, Symbole, start_url, Anzeige
* Ob die Anwendung über eine Service-Worker-Datei mit einem Ereignis-Listener zum Abrufen verfügt.
* Die App muss über HTTPS bereitgestellt werden
>
1. Die Installationsoption kann an verschiedenen Stellen in verschiedenen Browsern und Gerätetypen angezeigt werden. In einigen Browsern wird das Installationssymbol möglicherweise in der Menüleiste &quot;Optionen&quot;ausgeblendet.

## Massenbereitstellung des Cloud-Players {#bulk-provisioning}

Massenbereitstellung des Cloud-Players auf mehreren Geräten:

1. Wählen Sie eine MDM-Lösung aus, die die Ausführung eines Browsers mit einer URL im Terminal-Modus unterstützt.
1. Sie können dieselben Konfigurationen auf alle Geräte anwenden, indem Sie die folgenden Schritte ausführen:

   1. Hosten Sie config.json auf einem Server, sodass sie zugänglich ist, z. B.: `https://<config_server_host>/config.json`
   1. Um den Cloud-Player zu installieren und die gehosteten Konfigurationen anzuwenden, verwenden Sie eine Cloud-Player-URL wie z. B. `https://player.adobescreens.com?playerConfigAddress=https://<config_server_host>`
   1. Die Cloud Player-Anwendung sucht im Stammverzeichnis von nach config.json &lt;config_server_host>, analysiert dann die Datei &quot;config.json&quot;, um die benutzerdefinierten Konfigurationen abzurufen und diese Konfigurationen anzuwenden.
   1. Diese Konfigurationen werden bei jedem Neuladen des Players angewendet.

## Massenbereitstellung unter Chrome OS {#bulk-provisioning-chrome}

Erfahren Sie mehr über die Massenbereitstellung unter Chrome OS. Siehe [Installieren des Cloud-Players unter Chrome OS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/chromeos-install-cloud-player). &lt;!-- `https://www.adobe.com/go/aem_screens_cloud_player_en` >

## Erforderliche Konfiguration für AEM-Instanzen {#bulk-provisioning-config-aem}

Klicken Sie je nach Typ der AEM-Instanz auf eine der folgenden Handbücher, um CORS b/w AEM und Cloud Player zu aktivieren:

* [AEM On-Premises/AMS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-onpremandams) <!-- `https://www.adobe.com/go/aem_screens_cors_ams_en` -->

* [AEM Cloud Service](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-cs) <!-- `https://www.adobe.com/go/aem_screens_cors_aemaacs_en` -->


>[!NOTE]
>
## Einstellung von Chrome-Apps durch Google
>
1. Chrome-Apps auf Chrome OS-Hardware:
>
Google arbeitet aktiv an der Einstellung von Chrome-Apps und stellt stattdessen auf PWA-Apps um, wobei die Migration bis Januar 2025 geplant ist. Daher funktioniert die AEM Screens Player-App unter Chrome OS nicht mehr auf der Grundlage der freigegebenen Timeline. Adobe fordert Benutzende, die derzeit den Chrome-Player in der Produktion verwenden, dazu auf, die Umstellung auf den Screens Cloud-Player zu planen.
>
1. Player für Chrome-Erweiterungen unter Mac, Windows und Linux®:
>
Aufgrund des Einstellungsprozesses von Google wird der Screens-Player für Chrome-Erweiterungen ab Google Chrome Version 114 nicht mehr unterstützt. Adobe empfiehlt dringend, für alle Entwicklungs- und Testanforderungen zu seinem Screens-Cloud-Player zu wechseln.

## Offline-Unterstützung für Abruf von externen Inhalten {#offline-support}

In verschiedenen Nutzungsszenarien erfordern Kanäle möglicherweise das Abrufen von Inhalten aus einer externen Quelle (z. B. Wetter-Widgets oder Commerce-integrierte Single Page Applications), die grundsätzlich keine Offline-Unterstützung bieten können.  Um Offline-Funktionen für diese spezifischen Anwendungsfälle zu aktivieren, bietet der Cloud-Player Unterstützung für benutzerdefinierte Kopfzeilen.

Cloud Player verwendet eine Strategie für den ersten Netzwerkcache. Das bedeutet, dass versucht wird, Inhalte aus dem Netzwerk abzurufen (und dann den Cache mit der neuesten Version zu aktualisieren) und auf zwischengespeicherte Inhalte zurückzukehren, sofern verfügbar. Um die Offline-Unterstützung für ein solches Abrufen von Inhalten zu implementieren, muss die benutzerdefinierte Kopfzeile in die Anfrage aufgenommen werden. Anschließend wird die Anfrage mit der benutzerdefinierten Kopfzeile auf dem Player zwischengespeichert, was den Offline-Zugriff auf den Inhalt erleichtert und gleichzeitig die Network First-Cache-Strategie aufrechterhält.

```
// Sample fetch request with the 'X-Cache-Strategy' header
fetch(externalUrl, {
  headers: {
    'X-Cache-Strategy': 'external-cache'
  }
})
  .then(response => {
    // Handle the response, which may be from the network or cache.
    // Your logic here.
  })
  .catch(error => {
    // Handle any errors that may occur during the fetch operation.
    // Your error handling logic here.
  }); 
```

## Feedback

Ihr Feedback ist für Adobe wichtig. Teilen Sie uns über dieses [Formular](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4TFE0b_GjstOj6I1uGs9vLpURVdWWklQQTZZRTFVNEhRVlBWWldMWlJXOC4u) Ihre Gedanken mit.
