---
title: Implementieren von Cloud Player
seo-title: Implementing Cloud Player
description: Auf dieser Seite erfahren Sie mehr über die Implementierung des Cloud-Players.
seo-description: Follow  this page to learn about the implementation of the Cloud Player.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
feature: Administering Screens
role: Admin
level: Intermediate
source-git-commit: 718ef76b620accd7096be2e4b7ac53658cb7fce7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# Implementieren von Cloud Player  {#implementing-cloud-player}

In diesem Abschnitt wird die Implementierung des Cloud-Players beschrieben.

>[!NOTE]
>
>Die Kompatibilität des Cloud-Players erfordert einen modernen Browser mit PWA-Unterstützung, um eine konsistente Leistung auf verschiedenen Geräten sicherzustellen.

## Installieren von Cloud Player {#installing-cloud-player}

Die Installation des Cloud-Players kann auf verschiedenen Plattformen variieren. Im Allgemeinen kann jede Plattform mit einem modernen Browser die Cloud Player-Anwendung ausführen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie den Browser und geben Sie die [Cloud Player-URL](https://player.adobescreens.com) in der Adressleiste.
1. Der Browser prüft, ob der Cloud Player installiert ist, und zeigt dann in der Adressleiste ein Installationssymbol an.

![Bild](/help/user-guide/assets/cloud-player-install.png)

1. Klicken Sie auf das Installationssymbol und installieren Sie die Schaltfläche im Bestätigungsdialogfeld. Cloud Player wird als eigenständige Anwendung auf Ihrem Gerät installiert und kann über ein Symbol gestartet werden.

### Cloud Player-Installationsoption {#cloud-player-install-option}

1. Die Installationsoption für eine PWA wird auch als &quot;Zum Startbildschirm hinzufügen&quot;oder &quot;A2HS-Funktion&quot;bezeichnet.  Die Unterstützung für die Installation von PWA über das Internet variiert je nach Browser und Plattform.
1. Jeder Browser hat unterschiedliche Kriterien, um zu überprüfen, ob die PWA-App installiert ist oder nicht. Im Allgemeinen überprüft der Browser diese (weitere Details finden Sie hier):
   * Wenn die Anwendung über eine Manifest-JSON-Datei mit minimalen erforderlichen Schlüsseln für die Installation der App auf der Plattform verfügt, d. h. Name, Symbole, start_url, Anzeige
   * Wenn die Anwendung über eine Service Worker-Datei mit einem Ereignis-Listener zum Abrufen verfügt.
   * App muss über HTTPS bereitgestellt werden.
1. Die Installationsoption kann an verschiedenen Stellen in verschiedenen Browsern und Gerätetypen angezeigt werden. In einigen Browsern wird das Installationssymbol möglicherweise in der Menüleiste &quot;Optionen&quot;ausgeblendet.

## Massenbereitstellung Cloud Player {#bulk-provisioning}

Massenbereitstellung von Cloud Player auf mehreren Geräten:

1. Wählen Sie eine MDM-Lösung aus, die die Ausführung eines Browsers mit einer URL im Kiosk-Modus unterstützt.
1. Sie können dieselben Konfigurationen auf alle Geräte anwenden, indem Sie die folgenden Schritte ausführen:
   1. Hosten Sie config.json auf einem Server so, dass er zugänglich ist, z. B.: https://&lt;config_server_host>/config.json
   1. Um den Cloud Player zu installieren und die gehosteten Konfigurationen anzuwenden, verwenden Sie die Cloud-Player-URL wie: https://player.adobescreens.com?playerConfigAddress=https://&lt;config_server_host>
   1. Die Cloud Player-Anwendung sucht im Stammverzeichnis von nach config.json &lt;config_server_host>, analysieren Sie config.json , um die benutzerdefinierten Konfigurationen abzurufen und diese Konfigurationen anzuwenden.
   1. Diese Konfigurationen werden bei jeder Neuladung des Players angewendet.

## Massenbereitstellung unter Chrome OS {#bulk-provisioning-chrome}

Weitere Informationen zur Massenbereitstellung unter Chrome OS finden Sie unter: [Installieren des Cloud-Players unter Chrome OS](https://main--screens-franklin-documentation--hlxscreens.hlx.page/updates/cloud-player/guides/chromeos-install-cloud-player).

## Konfiguration erforderlich für AEM Instanzen {#bulk-provisioning-config-aem}

Wählen Sie je nach Typ der AEM-Instanz eines der folgenden Handbücher aus, um CORS b/w AEM und Cloud-Player zu aktivieren:
* [AEM On-Premises/AMS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-onpremandams)
* [AEM Cloud Service](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-cs)

