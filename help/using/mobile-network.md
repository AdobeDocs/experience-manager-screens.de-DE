---
title: Direktes Mobilfunknetz
description: Auf der Seite wird die Einrichtung des Direct Mobile-Netzwerks beschrieben.
translation-type: tm+mt
source-git-commit: d12de8de2b7bb29d85ebb0e046f2d1fd5051e928
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 3%

---


# Direktes Mobilfunknetz {#mobile-network-setup}

AEM Screens Player können auch über mobile oder zelluläre Netzwerke verbunden werden, die mindestens auf einem 3G-Netzwerk laufen.

Innerhalb der AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Downloadzeiten aus und beeinflusst nicht die Leistung von Displays.

Der Vorteil des Anschlusses von AEM Screens Players mit einer Mobilfunkverbindung 3/4/5G mit Ihrem Mobile Service Data Provider besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine optimale Netzabdeckung zu gewährleisten. Dies ist in der Regel in einer erhöhten und offenen Position mit einer möglichst optimalen Umgebung aus Beton oder Metall.

Dieses Setup ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da keine Festnetzverbindung erforderlich ist, um eine Verbindung zu AEM Screens herzustellen.

Das folgende Diagramm zeigt die Einrichtung des Direct Mobile-Netzwerks und besteht aus einem einzigen Segment der Netzwerkverbindung und der Verbindung jedes Players mit dem mobilen oder zellulären Datennetzwerk.

![](/help/using/assets/direct-mobile-1.png)

## Anschließen von AEM Screens Player an das Direct Mobile-Netzwerk {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine ordnungsgemäße Verbindung der AEM-Bildschirmplayer in dieser Konfiguration sicherzustellen:

1. Vergewissern Sie sich, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.

1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie die Netzwerkeinstellungen und überprüfen Sie, ob ein ausreichender Netzwerklink vorhanden ist und die Betriebssystem-Firewall so konfiguriert ist, dass der Netzwerkzugriff über die konfigurierten AEM Screens-Kommunikationsanschlüsse ermöglicht wird.

1. Falls der URL-Aufruf erfolgreich ist, können Sie die Installation der AEM Screens fortsetzen und sich registrieren. Beginn-AEM Screens.

## Einrichten des Direct Mobile-Netzwerks {#requirements-direct}

Das Netzwerk-Setup kann logisch in zwei Blöcke getrennt werden:

* Mobile Internetverbindung

* Local Area Network

### Mobile Internetverbindung {#mobile-internet-connection}

Die Leistung der Internetverbindung bietet neben der Reichweite des Netzwerks genügend Bandbreite, um AEM Screens reibungslos zu bedienen.

In Direct Mobile Network ist jeder Player mit einer einzigen mobilen Datenkarte mit dem Datennetzwerk des Anbieters verbunden.

In der folgenden Tabelle sind die Datennetzwerke mit ihrer Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 Mbit/s |
| 4G | 150 Mbit/s |
| 5G | 1000 - 10000 Mbit/s |

Es wird empfohlen, die folgenden Fragen zu beantworten, während geprüft wird, welches Datennetzwerk verwendet werden sollte:

Die verfügbare Netzwerkgeschwindigkeit hängt vom jeweiligen Mobildatenanbieter-Plan ab und von der verfügbaren Reichweite, die am Standort des AEM Screens-Controllers erreicht wird.
Bei dieser Einrichtung ist zu berücksichtigen, dass neben der verfügbaren Bandbreite einige mobile Datenanbieterpläne die verfügbare Datenmenge, die über die Verbindung kommt, innerhalb eines bestimmten Zeitraums einschränken. Es muss sichergestellt werden, dass genügend Datenmenge und Bandbreite vorhanden sind.
Als Folgemaßnahme muss die erforderliche Datenpackage mindestens sein:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>Beim ersten Hochladen von Mediendateien, z. B. bei der Integration neuer Player, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten und in den obigen Annahmen widerzuspiegeln.Ein 4G-Netzwerk mit *guter* Abdeckung und *unbegrenzten* Daten sollte mit den gebräuchlichsten Installationen in diesem Netzwerk-Setup übereinstimmen.

>[!NOTE]
>Ein 3G-Mindestplan mit guter Netzabdeckung sollte zu einer akzeptablen Downloadleistung für einen AEM Screens-Player führen. Wenn nur eine angemessene Abdeckung an einem bestimmten Ort zur Verfügung steht, ist zu berücksichtigen, dass die gesamte Netzwerkeinrichtung mit [Mobile Data Router und Active Network Components](/help/using/mobile-network-router.md)auf Mobile Network umgestellt wird.


### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN) ist nicht nur die Netzwerkerreichbarkeit, sondern auch die Bereitstellung ausreichender Bandbreite für einen reibungslosen Betrieb von AEM Screens. Das LAN-Netzwerk ist in der Regel mit einem 100 Mbit/s Netzwerk kompatibel, sodass genügend Bandbreite vorhanden ist, um viele Geräte mit guter Leistung mit dem System zu verbinden.

Bei Verwendung anderer aktiver Netzwerkkomponenten müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen. Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet-Zugriffs- oder Router-Spezifikation bereitgestellt wird.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Der große Netzwerkverkehr tritt auf, wenn auf einer bestimmten Anzeige neue Inhalte angezeigt werden.

Bei normalen Vorgängen beispielsweise wird eine definierte Playlist, die im Laufe des Tages häufig aktualisiert wird, als Angebot ein netzwerkunabhängiger Vorgang ausgeführt, sobald alle Dateien im Player gespeichert wurden.

In Szenarien, in denen es mehr Interaktionen mit Sensoren oder Triggern und dynamischen Inhalten gibt, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar, um eine sofortige Bildschirmreaktion zu gewährleisten und eine bestmögliche Kundenerfahrung zu gewährleisten.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>Alle Informationen beziehen sich auf den Verbrauch jedes Geräts im Netzwerk, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/download-times-mobile.png)



