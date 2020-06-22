---
title: Mobilnetzwerk-Einrichtung
description: Die Seite beschreibt die Einrichtung des Mobilnetzwerks
translation-type: tm+mt
source-git-commit: 88ba9ab26c4ecc3f829f53244117041a9a1fd2b3
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 1%

---


# Mobilnetzwerk-Einrichtung {#mobile-network-setup}

Adobe AEM Screens Player kann auch über mobile/zelluläre Netzwerke mit mindestens einem 3G-Netzwerk verbunden werden.
Innerhalb der AEM Screens wird der benötigte Inhalt physisch auf den Player-Controller/Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Dadurch wirkt sich die angegebene Bandbreite nur auf die anfänglichen Downloadzeiten aus und beeinflusst die Performance der Display-Systeme überhaupt nicht.
Anschluss von AEM Screens-Playern mit einer Mobilfunkverbindung 3/4/5G an Ihren Mobile Service-Datenanbieter. Der Vorteil dieses Setups besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. Dies ist in der Regel in einer erhöhten und offenen Position mit so wenig umliegenden Beton- oder Metallkonstruktionen wie möglich.
Dieses Setup ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da keine Festnetzverbindung zum Verbinden von AEM Screens erforderlich ist.


![](/help/using/assets/mobile-network-1.png)

>[!NOTE]
>**Tipps zur Fehlerbehebung **>Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und nicht den erwarteten Inhalt anzeigen:
>
>1. Prüfen Sie Ihre Internet Router Firewall, wenn es irgendwelche Einschränkungen in Bezug auf `TCP/IP Port 80/443`.
>1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind, und versuchen Sie es erneut.




## Voraussetzungen für die Einrichtung des mobilen Netzwerks {#requirements-direct}

Das Netzwerk-Setup, wie unter 5.5 beschrieben, kann logisch in drei Blöcke getrennt werden. Der WAN/Outer World/Internet Connection Block (hier mobile Datenverbindung), das interne LAN/Local Area Network und optionale Unterabschnitte des LAN durch Active Network Components getrennt.
Um eine bestmögliche Leistung zu gewährleisten, muss sichergestellt werden, dass beide Abschnitte den empfohlenen Mindeststandards entsprechen.
Was bedeutet &quot;gute Leistung&quot;in der Umgebung &quot;AEM Screens&quot;?
AEM Screens bieten Digital Signage-Benutzern einen großen Vorteil. Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerk-Traffic, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Für den normalen Betrieb, z.B. wenn Sie eine Playlist definiert haben, die nicht sehr oft während des Tages geändert wird, wird hier ein Netzwerkunabhängiger Vorgang durchgeführt, sobald alle Angebote auf dem Player gespeichert wurden.
Für solche Anwendungsfälle, bei denen es mehr Interaktionen mit Sensoren oder anderen Triggern gibt und der Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar für eine sofortige Bildschirmreaktion, um ein bestmögliches Kundenerlebnis zu gewährleisten.
In den folgenden Tabellen finden Sie einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und mögliche Auslaufzeiten erforderlich sind.
Alle Informationen müssen als der Verbrauch jedes Geräts im Netzwerk gesehen werden, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen addiert sich also und verlängert die Downloadzeit.


### WAN/Internetverbindung {#wan-connection}

Die Leistung der Internetverbindung hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, eine ausreichende Bandbreite zur Verfügung gestellt, um AEM Screens angenehm und reibungslos zu bedienen. Im Einzelnen hängt &quot;ausreichend&quot;von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WLAN-Netze.
Denken Sie daran, dass alle Geräte über einen gleichzeitigen Zugriff auf die Internetverbindung verfügen und dass die Bandbreite in der Regel linear sinkt, während Sie dem Netzwerk mehr Benutzer/Computer hinzufügen.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Reichweite des mobilen Routers mindestens &quot;gut&quot; ist (siehe Handbuch für den mobilen Router). Auch der zugrunde liegende Monatsplan muss genügend Datenkapazität und genügend Bandbreite für alle angeschlossenen Clients im angeschlossenen LAN abdecken.
Die Data-Netzwerke bieten Standardbandbreite von ca. bis:
・ 3Go 42Mbit/s ・ 4Go 150Mbit/s ・ 5Go 1000Mbit/sec-10000Mbit/secUnter Berücksichtigung, welches Data Network verwendet werden sollte, wird empfohlen, die folgenden Fragen zu beantworten:
・ Wie viele Clients sind mit dem Router verbunden?
・ Wie viele Inhaltsänderungen erwarte ich und wie hoch sind diese durchschnittlichen Dateigrößen?
Als Folgemaßnahme muss die erforderliche Datenpackage mindestens sein:
Datenpackage Capacity = Anzahl der Clients * (# der Inhaltsdateien * Durchschnittliche Dateigröße) Bitte stellen Sie sicher, dass genügend Puffer vorhanden ist.
Achtung: Beim ersten Hochladen von Mediendateien, z. B. bei der Integration neuer Player, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten, die sich in den obigen Annahmen widerspiegeln.
Als Thumb-Regel sollte ein 4G-Netzwerk mit &quot;guter&quot;Abdeckung und unbegrenzten Daten mit den gebräuchlichsten Installationen in diesem Netzwerk-Setup übereinstimmen.


### LAN-Verbindung {#lan-connection}

Die Leistung des LAN hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, ausreichend Bandbreite zur Verfügung zu stellen, um AEM Screens angenehm und reibungslos zu bedienen. In diesen Tagen ist das LAN-Netzwerk in der Regel mindestens 100 MBit/s Netzwerk, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Bei Verwendung einer anderen aktiven Netzwerkkomponente müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen. Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die in der Internet Access/Router-Spezifikation angegeben ist.
Falls eine WiFI-Lösung für die Verbindung des Bildschirms mit dem Internet-Link vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit. Alle &quot;neueren&quot; Standards wie 802.11h-n sind von besserer Qualität. Wenn ein Wifi-Repeater benötigt wird, empfehlen wir dringend Mesh WiFi Access-Point Technologien wie Google Nest Mesh Wifi oder Ähnliches.
Andere WiFi-Wiederholungstechnologien führen schließlich zu einem massiven Bandbreitenverlust im gesamten Netzwerk.
