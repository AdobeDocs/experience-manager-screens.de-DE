---
title: Implementieren des Cloud-Players
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
workflow-type: ht
source-wordcount: '455'
ht-degree: 100%

---

# Implementieren des Cloud-Players  {#implementing-cloud-player}

In diesem Abschnitt wird die Implementierung des Cloud-Players beschrieben.

>[!NOTE]
>
>Die Kompatibilität des Cloud-Players erfordert einen modernen Browser mit PWA-Unterstützung, um eine konsistente Leistung auf verschiedenen Geräten sicherzustellen.

## Installieren des Cloud Players {#installing-cloud-player}

Die Installation des Cloud-Players kann auf verschiedenen Plattformen variieren. Im Allgemeinen kann jede Plattform mit einem modernen Browser die Cloud Player-Anwendung ausführen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie den Browser und geben Sie die [Cloud-Player-URL](https://player.adobescreens.com) in die Adressleiste ein.
1. Der Browser prüft, ob der Cloud-Player installiert ist, und zeigt dann in der Adressleiste ein Installationssymbol an.

![Bild](/help/user-guide/assets/cloud-player-install.png)

1. Klicken Sie auf das Installationssymbol und anschließend auf die Schaltfläche „Installieren“ im Bestätigungsdialogfeld. Der Cloud-Player wird als eigenständige Anwendung auf Ihrem Gerät installiert und kann über ein Symbol gestartet werden.

### Cloud-Player-Installationsoption {#cloud-player-install-option}

1. Die Installationsoption für eine PWA wird auch als „Zum Startbildschirm hinzufügen“ oder A2HS-Funktion bezeichnet.  Die Unterstützung für die Installation von PWAs über das Internet variiert je nach Browser und Plattform.
1. Jeder Browser hat unterschiedliche Kriterien, um zu überprüfen, ob die PWA installiert ist oder nicht. Im Allgemeinen überprüft der Browser diese (weitere Details finden Sie hier):
   * Wenn die Anwendung über eine Manifest-JSON-Datei mit minimalen erforderlichen Schlüsseln für die Installation der Anwendung auf der Plattform verfügt, d. h. Name, Symbole, start_url, Anzeige.
   * Wenn die Anwendung über eine Service-Worker-Datei mit einem Ereignis-Listener zum Abrufen verfügt.
   * Die Anwendung muss über HTTPS bereitgestellt werden.
1. Die Installationsoption kann an verschiedenen Stellen in verschiedenen Browsern und Gerätetypen angezeigt werden. In einigen Browsern wird das Installationssymbol möglicherweise in der Menüleiste für Optionen ausgeblendet.

## Massenbereitstellung des Cloud-Players {#bulk-provisioning}

Massenbereitstellung des Cloud-Players auf mehreren Geräten:

1. Wählen Sie eine MDM-Lösung aus, die die Ausführung eines Browsers mit einer URL im Terminal-Modus unterstützt.
1. Sie können dieselben Konfigurationen auf alle Geräte anwenden, indem Sie die folgenden Schritte ausführen:
   1. Hosten Sie config.json auf einem Server, sodass sie zugänglich ist, z. B.: https://&lt;config_server_host>/config.json
   1. Um den Cloud-Player zu installieren und die gehosteten Konfigurationen anzuwenden, verwenden Sie eine Cloud-Player-URL wie z. B.: https://player.adobescreens.com?playerConfigAddress=https://&lt;config_server_host>
   1. Die Cloud Player-Anwendung sucht nach config.json im Stammverzeichnis von &lt;config_server_host>, analysiert die config.json, um die benutzerdefinierten Konfigurationen zu erhalten, und wendet diese Konfigurationen an.
   1. Diese Konfigurationen werden bei jedem Neuladen des Players angewendet.

## Massenbereitstellung unter Chrome OS {#bulk-provisioning-chrome}

Weitere Informationen zur Massenbereitstellung unter Chrome OS finden Sie unter: [Installieren des Cloud-Players unter Chrome OS](https://main--screens-franklin-documentation--hlxscreens.hlx.page/updates/cloud-player/guides/chromeos-install-cloud-player).

## Erforderliche Konfiguration für AEM-Instanzen {#bulk-provisioning-config-aem}

Wählen Sie je nach Typ der AEM-Instanz eines der folgenden Handbücher aus, um CORS zwischen AEM und Cloud-Player zu aktivieren:
* [AEM On-Premises/AMS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-onpremandams)
* [AEM Cloud Service](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-cs)

