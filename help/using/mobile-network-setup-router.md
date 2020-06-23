---
title: Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten
description: Auf der Seite werden Mobile Network mit Mobile Data Router und Active Network Components beschrieben.
translation-type: tm+mt
source-git-commit: 6d6637d5222e861fa9a83f555baf0699f56f150a
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 0%

---


# Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten {#mobile-network-setup}

Adobe AEM Screens Player kann auch über mobile/zelluläre Netzwerke mit mindestens einem 3G-Netzwerk verbunden werden.
Innerhalb der AEM Screens wird der benötigte Inhalt physisch auf den Player-Controller/Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Dadurch wirkt sich die angegebene Bandbreite nur auf die anfänglichen Downloadzeiten aus und beeinflusst die Performance der Display-Systeme überhaupt nicht.
Anschluss von AEM Screens-Playern mit einer Mobilfunkverbindung 3/4/5G an Ihren Mobile Service-Datenanbieter. Der Vorteil dieses Setups besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. Dies ist in der Regel in einer erhöhten und offenen Position mit so wenig umliegenden Beton- oder Metallkonstruktionen wie möglich.
Dieses Setup ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da keine Festnetzverbindung zum Verbinden von AEM Screens erforderlich ist.

![](/help/using/assets/mobile-network-1.png)

## AEM Screens Player mit Mobile Data Router und Active Network Components verbinden {#connecting-aem-screens-players}

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



## Voraussetzungen für die Einrichtung eines mobilen Netzwerks mit dem MobildatenRouter und aktiven Netzwerkkomponenten {#requirements-direct}

Das Netzwerk-Setup kann logisch in zwei Blöcke getrennt werden:

* Mobile Internetverbindung

* Local Area Network

### Mobile Internetverbindung {#mobile-internet-connection}

Die Leistung der Internetverbindung hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, eine ausreichende Bandbreite zur Verfügung gestellt, um AEM Screens angenehm und reibungslos zu bedienen. Im Einzelnen hängt &quot;ausreichend&quot;von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.
Denken Sie daran, dass alle Geräte einen gleichzeitigen Zugriff auf die Internetverbindung haben und dass die Bandbreite in der Regel linear sinkt, während dem Netzwerk mehr Benutzer/Computer hinzugefügt werden.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Reichweite des mobilen Routers mindestens &quot;gut&quot; ist (siehe Handbuch für den mobilen Router). Auch der zugrunde liegende Monatsplan muss genügend Datenkapazität und genügend Bandbreite für alle angeschlossenen Clients im angeschlossenen LAN abdecken.
Die Datennetze bieten Standardbandbreite mit:

**3G**
* 42 Mbit/s

**4G**
* 150 Mbit/s

**5G**
* 1000 Mbit/s - 10000 Mbit/s

Es wird empfohlen, die folgenden Fragen zu beantworten, während geprüft wird, welches Datennetzwerk verwendet werden sollte:

* Wie viele Clients sind mit dem Router verbunden?

* Wie viele Inhaltsänderungen werden erwartet und wie hoch sind diese durchschnittlichen Dateigrößen?

>[!NOTE]
>Die erforderliche Datenpackage muss mindestens sein:
`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>Beim ersten Hochladen von Mediendateien, bei dem neue Player integriert werden, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten, die sich in den obigen Annahmen widerspiegeln. Ein 4G-Netzwerk mit *guter* Abdeckung und unbegrenzten Daten sollte mit den gebräuchlichsten Installationen in dieser Netzwerkeinrichtung übereinstimmen.


### Local Area Network {#lan-connection}

Die Leistung des LAN hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, ausreichend Bandbreite zur Verfügung zu stellen, um AEM Screens angenehm und reibungslos zu bedienen. In diesen Tagen ist das LAN-Netzwerk in der Regel mindestens 100 Mbit/s Netzwerk, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Bei Verwendung einer anderen aktiven Netzwerkkomponente müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen. Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die in der Internet Access/Router-Spezifikation angegeben ist.
Falls eine WiFI-Lösung für die Verbindung des Bildschirms mit dem Internet-Link vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Alle &quot;neueren&quot; Standards wie 802.11h-n sind von besserer Qualität. Wenn ein WIFI-Repeater benötigt wird, empfehlen wir dringend Mesh WiFi Access-Point Technologien wie Google Nest Mesh WIFI oder Ähnliches.
Andere WiFi-Wiederholungstechnologien führen schließlich zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bieten Digital Signage-Benutzern einen großen Vorteil. Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerk-Traffic, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Für den normalen Betrieb, z.B. wenn Sie eine Playlist definiert haben, die nicht sehr oft während des Tages geändert wird, wird hier ein Netzwerkunabhängiger Vorgang durchgeführt, sobald alle Angebote auf dem Player gespeichert wurden.
Für solche Anwendungsfälle, bei denen es mehr Interaktionen mit Sensoren oder anderen Triggern gibt und der Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar für eine sofortige Bildschirmreaktion, um ein bestmögliches Kundenerlebnis zu gewährleisten.
Die folgenden Tabellen bieten einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und für potenzielle Wartezeiten erforderlich sind.

>[!NOTE]
>Alle Informationen beziehen sich auf den Verbrauch jedes Geräts im Netzwerk, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/mobile-router-download.png)



