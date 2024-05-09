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
ht-degree: 33%

---

# Implementieren des Cloud-Players {#implementing-cloud-player}

AEM Screens bietet seit jeher verschiedene native Player-Anwendungen für verschiedene Plattformen wie ChromeOS, Windows, Android™ und `Tizen`. Aufgrund der sich wandelnden Bedürfnisse von Anwendern führte Adobe jedoch eine innovative Lösung ein - den AEM Screens Cloud Player.

Die Cloud stellt einen signifikanten Unterschied zu früheren nativen Adobe-Programmen dar. Es handelt sich um eine Progressive Web App (PWA), die auf einem Server gehostet wird. Dieser transformative Ansatz ermöglicht Kunden einen plattformunabhängigen Player, der direkt in einem Webbrowser ausgeführt wird.

Der Zugriff auf den Cloud Player ist so einfach wie der Besuch `https://player.adobescreens.com`. Benutzende können ihn unabhängig von der Plattform auf ihrem Gerät installieren und ein nahtloses Erlebnis für digitale Beschilderungen erhalten. Die Kompatibilität des Cloud-Players hängt von der Verfügbarkeit eines modernen Browsers mit PWA-Unterstützung ab, um eine konsistente Leistung auf verschiedenen Geräten sicherzustellen. Manuelle Aktualisierungen haben ein Ende. Freuen Sie sich stattdessen über einen Player, der automatisch Fehlerbehebungen und Funktionen bereitstellt, sodass Sie stets über die neuesten Funktionen verfügen. Dieser Wechsel zu einer PWA-basierten Cloud-Player stellt eine aufregende Weiterentwicklung im Hinblick auf Adobe-Digital-Signage-Angebote dar und macht sie leichter zugänglich, vielseitiger und benutzerfreundlicher als je zuvor.

In diesem Abschnitt wird die Implementierung des Cloud-Players beschrieben.

>[!NOTE]
>
>Die Kompatibilität des Cloud-Players erfordert einen modernen Browser mit PWA-Unterstützung, um eine konsistente Leistung auf verschiedenen Geräten sicherzustellen.

## Installieren des Cloud Players {#installing-cloud-player}

Die Installation des Cloud-Players kann auf verschiedenen Plattformen variieren. Im Allgemeinen kann jede Plattform mit einem modernen Browser die Cloud Player-Anwendung ausführen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie den Browser und geben Sie die [Cloud-Player-URL](https://player.adobescreens.com/content/dam/universal-player/firmware.html) in die Adressleiste ein.
1. Der Browser prüft, ob der Cloud Player installiert ist, und zeigt dann in der Adressleiste ein Installationssymbol an.

   ![Bild](/help/user-guide/assets/cloud-player-install.png)

1. Klicken Sie im Bestätigungsdialogfeld auf das Installationssymbol und die Schaltfläche &quot;Installieren&quot;. Cloud Player wird als eigenständige Anwendung auf Ihrem Gerät installiert und kann über ein Symbol gestartet werden.

>[!NOTE]
>
>### Cloud-Player-Installationsoption {#cloud-player-install-option}
>
1. Die Installationsoption für eine PWA wird auch als &quot;Zum Startbildschirm hinzufügen&quot;oder &quot;A2HS-Funktion&quot;bezeichnet. Die Unterstützung für die Installation von PWA über das Internet variiert je nach Browser und Plattform.
1. Jeder Browser hat unterschiedliche Kriterien, um zu überprüfen, ob die PWA installiert ist oder nicht. Im Allgemeinen kann der Browser Folgendes überprüfen (weitere Details finden Sie hier):
>
* Wenn die Anwendung über eine JSON-Manifestdatei mit minimalen erforderlichen Schlüsseln für die Installation der App auf der Plattform verfügt, d. h. Name, Symbole, start_url, Anzeige
* Wenn die Anwendung über eine Service Worker-Datei mit einem Ereignis-Listener zum Abrufen verfügt
* Die App muss über HTTPS bereitgestellt werden
>
1. Die Installationsoption kann an verschiedenen Stellen in verschiedenen Browsern und Gerätetypen angezeigt werden. In einigen Browsern wird das Installationssymbol möglicherweise in der Menüleiste &quot;Optionen&quot;ausgeblendet.

## Massenbereitstellung des Cloud-Players {#bulk-provisioning}

Massenbereitstellung des Cloud-Players auf mehreren Geräten:

1. Wählen Sie eine MDM-Lösung aus, die die Ausführung eines Browsers mit einer URL im Kiosk-Modus unterstützt.
1. Sie können dieselben Konfigurationen auf alle Geräte anwenden, indem Sie die folgenden Schritte ausführen:

   1. Hosten Sie config.json auf einem Server so, dass er zugänglich ist, z. B.: `https://<config_server_host>/config.json`
   1. Um den Cloud Player zu installieren und die gehosteten Konfigurationen anzuwenden, verwenden Sie die Cloud-Player-URL wie: `https://player.adobescreens.com?playerConfigAddress=https://<config_server_host>`
   1. Die Cloud Player-Anwendung sucht im Stammverzeichnis von nach config.json &lt;config_server_host>, analysiert dann die Datei &quot;config.json&quot;, um die benutzerdefinierten Konfigurationen abzurufen und diese Konfigurationen anzuwenden.
   1. Diese Konfigurationen werden bei jeder Neuladung des Players angewendet.

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
Google arbeitet aktiv an der Einstellung von Chrome-Apps und stellt stattdessen auf PWA-Apps um, wobei die Migration bis Januar 2025 geplant ist. Daher funktioniert die AEM Screens Player-App unter Chrome OS nicht mehr auf der Grundlage der freigegebenen Timeline. Adobe fordert Benutzer, die derzeit den Chrome-Player in Produktion verwenden, auf, die Umstellung auf den Screens Cloud-Player zu planen.
>
1. Chrome Extension Player unter Mac, Windows und Linux®:
>
Aufgrund des Einstellungsprozesses von Google wird der Screens-Player für Chrome-Erweiterungen ab Google Chrome Version 114 nicht mehr unterstützt. Adobe rät Ihnen, für alle Entwicklungs- und Testanforderungen zum Screens Cloud Player zu wechseln.

## Offline-Unterstützung für Abruf von externen Inhalten {#offline-support}

In verschiedenen Nutzungsszenarien erfordern Kanäle möglicherweise das Abrufen von Inhalten aus einer externen Quelle (z. B. Wetter-Widgets oder Commerce-integrierte Einzelseiten-Apps), die von Natur aus keine Offline-Unterstützung bieten können. Um Offline-Funktionen für diese spezifischen Anwendungsfälle zu aktivieren, bietet der Cloud-Player Unterstützung für benutzerdefinierte Kopfzeilen.

Cloud Player verwendet eine Strategie für den ersten Netzwerkcache. Das bedeutet, dass versucht wird, Inhalte aus dem Netzwerk abzurufen (und dann den Cache mit der neuesten Version zu aktualisieren) und auf zwischengespeicherte Inhalte zurückzukehren, sofern verfügbar. Um die Offline-Unterstützung für ein solches Abrufen von Inhalten zu implementieren, muss die benutzerdefinierte Kopfzeile in die Anfrage aufgenommen werden. Anschließend wird die Anfrage mit dem benutzerdefinierten Header auf dem Player zwischengespeichert, was den Offline-Zugriff auf den Inhalt erleichtert und gleichzeitig die Strategie für den ersten Cache im Netzwerk verwaltet.

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

Adobe wertet Ihr Feedback aus. Teilen Sie Ihre Gedanken mit uns durch [Formular](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4TFE0b_GjstOj6I1uGs9vLpURVdWWklQQTZZRTFVNEhRVlBWWldMWlJXOC4u).
