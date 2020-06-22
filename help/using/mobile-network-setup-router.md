---
title: Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten
description: Auf der Seite werden Mobile Network mit Mobile Data Router und Active Network Components beschrieben.
translation-type: tm+mt
source-git-commit: 5460e384e96553d9f0478113368e31cf266479a4
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 0%

---


# Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten {#mobile-network-setup}

Adobe AEM Screens Player kann auch über mobile/zelluläre Netzwerke mit mindestens einem 3G-Netzwerk verbunden werden.
Innerhalb der AEM Screens wird der benötigte Inhalt physisch auf den Player-Controller/Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Dadurch wirkt sich die angegebene Bandbreite nur auf die anfänglichen Downloadzeiten aus und beeinflusst die Performance der Display-Systeme überhaupt nicht.
Anschluss von AEM Screens-Playern mit einer Mobilfunkverbindung 3/4/5G an Ihren Mobile Service-Datenanbieter. Der Vorteil dieses Setups besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. Dies wird in einer erhöhten und offenen Position mit so wenig umliegenden Beton- oder Metallkonstruktionen wie möglich verwendet.
Dieses Setup ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da keine Festnetzverbindung zum Verbinden von AEM Screens erforderlich ist.

![](/help/using/assets/mobile-network-1.png)

## Anschließen von AEM Screens Player an das Direct Mobile-Netzwerk {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine Verbindung mit AEM-Screen-Playern in dieser Konfiguration herzustellen:

Die Konfiguration beinhaltet einen Internetzugang eines AEM Screens Controllers über einen eigenen 3/4/5G Datenlink.
Die ordnungsgemäße Verbindung der AEM-Screen-Player in dieser Konfiguration ist einfach:

1. Stellen Sie sicher, dass der MobildatenRouter ordnungsgemäß mit dem zellulären Datennetzwerk verbunden ist, wie im Betriebssystem angegeben.
1. Stellen Sie sicher, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie im Systembrowser eine URL aufrufen.
   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit der Router-Einstellung übereinstimmt.
1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies kann in der Regel auch mit einer Signal-LED auf Standard Routern identifiziert werden. Sollte dies nicht in Ordnung sein, wenden Sie sich bitte an Ihren ISP-Dienst, um Ihren Router remote zu überprüfen.
iv. Wenn alle oben genannten Elemente korrekt konfiguriert sind und weiterhin eine Fehlermeldung angezeigt wird, überprüfen Sie Ihre aktiven Netzwerkkomponenten wie Switches oder zusätzliche Router, falls eine Port-Einschränkung vorliegt.
1. Falls der URL-Aufruf erfolgreich war, können Sie die AEM Screens weiter installieren und entsprechend registrieren. Beginn-AEM Screens

   >[!NOTE]
   >**Tipps zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und nicht den erwarteten Inhalt anzeigen:
   >
   >1. Prüfen Sie Ihre Internet Router Firewall, wenn es irgendwelche Einschränkungen in Bezug auf `TCP/IP Port 80/443`.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.



## Voraussetzungen für die Einrichtung des mobilen Netzwerks {#requirements-direct}

Das Netzwerk-Setup kann logisch in zwei Blöcke getrennt werden:

* Mobile Internetverbindung

* Local Area Network

### Mobile Internetverbindung {#mobile-internet-connection}

Die Leistung der Internetverbindung hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, ausreichend Bandwith zur Verfügung zu stellen, um AEM Screens angenehm und reibungslos zu bedienen. Im Einzelnen hängt &quot;ausreichend&quot;von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WLAN-Netze.
Denken Sie daran, dass alle Geräte einen gleichzeitigen Zugriff auf die Internetverbindung haben und Bandwith in der Regel linear abnimmt, während es mehr Benutzer/Computer zum Netzwerk hinzufügt.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Reichweite des mobilen Routers mindestens &quot;gut&quot; ist (siehe Handbuch für den mobilen Router). Auch der zugrunde liegende Monatsplan muss ausreichend Datenkapazität und ausreichend Bandbreite abdecken, um alle angeschlossenen Clients im angeschlossenen LAN zu bedienen.
Die Datennetzwerke bieten Standardbandwith mit ca. bis:
* 3Go 42Mbit/s ・ 4Go 150Mbit/s ・ 5Go 1000Mbit/sec-10000Mbit/secUnter Berücksichtigung, welches Data Network verwendet werden sollte, wird empfohlen, die folgenden Fragen zu beantworten:
・ Wie viele Clients sind mit dem Router verbunden?
・ Wie viele Inhaltsänderungen erwarte ich und wie hoch sind diese durchschnittlichen Dateigrößen?
Als Folgemaßnahme muss die erforderliche Datenpackage mindestens sein:
   `Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`
Stellen Sie sicher, dass genügend Puffer vorhanden ist.
Achtung: Beim ersten Hochladen von Mediendateien, z. B. bei der Integration neuer Player, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten, die sich in den obigen Annahmen widerspiegeln.


### Local Area Network {#lan-connection}

Die Leistung des LAN hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, ausreichend Bandwith zur Verfügung zu stellen, um AEM Screens angenehm und reibungslos zu bedienen. In diesen Tagen ist das LAN-Netzwerk in der Regel mindestens 100MBit/s Netzwerk, sodass es ausreichend Bandwith, um viele Geräte mit guter Leistung an das System angeschlossen werden sollte. Bei Verwendung einer anderen aktiven Netzwerkkomponente müssen alle diese mit den Anforderungen an den Netzwerkbandbreite übereinstimmen. Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100Mbit/s-Standard entsprechen und dem in der Internet Access/Router-Spezifikation angegebenen Bandwith entsprechen.
Falls eine WiFI-Lösung für die Verbindung des Bildschirms mit dem Internet-Link vorgesehen ist, wird empfohlen, als Minimum moderne WIFI-Standards wie IEEE 802.11g zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit. Alle &quot;neueren&quot; Standards wie 802.11h-n sind von besserer Qualität. Wenn ein Wifi-Repeater erforderlich ist, empfehlen wir dringend Mesh WiFi Accesspoint Technologie wie Google Nest Mesh Wifi oder Ähnliches.
Andere WiFi-Wiederholungstechnologien führen schließlich zu einem massiven Verlust von Bandwith im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bieten Digital Signage-Benutzern einen großen Vorteil. Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerk-Traffic, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Für den normalen Betrieb, z.B. wenn Sie eine Playlist definiert haben, die nicht sehr oft während des Tages geändert wird, wird hier ein Netzwerkunabhängiger Vorgang durchgeführt, sobald alle Angebote auf dem Player gespeichert wurden.
Für solche Anwendungsfälle, bei denen es mehr Interaktionen mit Sensoren oder anderen Triggern gibt und der Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar für eine sofortige Bildschirmreaktion, um ein bestmögliches Kundenerlebnis zu gewährleisten.
In den folgenden Tabellen finden Sie einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und mögliche Auslaufzeiten erforderlich sind.
Alle Informationen müssen als der Verbrauch jedes Geräts im Netzwerk gesehen werden, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen addiert sich also und verlängert die Downloadzeit.

![](/help/using/assets/mobile-router-download.png)



