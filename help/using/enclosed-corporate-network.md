---
title: Geschlossenes Unternehmensnetzwerk
description: Geschlossenes Unternehmensnetzwerk
translation-type: tm+mt
source-git-commit: 31a6b202cae200e43e87db1df4e60f6f9d75c1bf
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 1%

---


# Geschlossene Unternehmensnetzwerke {#enclosed-corporate-networks}

Das Engeschlossene Unternehmensnetzwerk-SetUp ist für kleinere, größere und unternehmensinterne Unternehmen geeignet. Es kann theoretisch komplexer sein, aber die logische Einrichtung ist immer wie unten in einem vereinfachten Beispiel dargestellt.

## Anforderungen für die Einrichtung von geschlossenen Unternehmensnetzwerken {#requirements-enclosed-networks}

Die Einrichtung des Unternehmensnetzwerks kann logisch in zwei Blöcke getrennt werden. Der WAN/Outer World/Internet Connection Block und das interne LAN/Local Area Network.

### WAN/Internetverbindung {#wan-connection}

Die Leistung der Internetverbindung hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, eine ausreichende Bandbreite zur Verfügung gestellt, um AEM Screens angenehm und reibungslos zu bedienen.
Im Einzelnen hängt &quot;ausreichend&quot;von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.
Denken Sie daran, dass alle Geräte über einen gleichzeitigen Zugriff auf die Internetverbindung verfügen und dass die Bandbreite in der Regel linear sinkt, während Sie dem Netzwerk mehr Benutzer/Computer hinzufügen.

### LAN-Verbindung {#lan-connection}

Die Leistung des LAN hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, ausreichend Bandbreite zur Verfügung zu stellen, um AEM Screens angenehm und reibungslos zu bedienen. In diesen Tagen ist das LAN-Netzwerk in Unternehmen in der Regel mindestens 1000 MBit/s Netzwerk, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Bei Verwendung einer anderen aktiven Netzwerkkomponente müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen. Beispielsweise sollten die Netzwerkkomponenten mindestens dem 1000Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.

### Sonstige Unternehmensnetzspezifikationen {#other-networks}

In der Regel haben Unternehmensnetzwerke eine Vielzahl von Geräten angeschlossen, könnten in verschiedene Teilnetzwerke aufgeteilt werden und haben redundante oder Multiplexing-Internetverbindungen, um eine ausreichende Leistung für viele tausend gleichzeitige Zugriffe zu bieten.
Das obige Schema ist vereinfacht und passt in den meisten Fällen zu der Umgebung, die für den Kunden zur Verfügung steht.
Falls eine WiFI-Lösung für die Verbindung des Bildschirms mit dem Internet-Link vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit. Alle &quot;neueren&quot; Standards wie 802.11h-n sind von besserer Qualität. Wenn ein WIFI-Repeater benötigt wird, empfehlen wir dringend Mesh WIFI Accesspoint Technologie wie Google Nest Mesh WIFI oder Ähnliches.
Andere WiFi-Wiederholungstechnologien führen schließlich zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bieten Digital Signage-Benutzern einen großen Vorteil. Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerk-Traffic, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Für den normalen Betrieb, z.B. wenn Sie eine Playlist definiert haben, die nicht sehr oft während des Tages geändert wird, wird hier ein Netzwerkunabhängiger Vorgang durchgeführt, sobald alle Angebote auf dem Player gespeichert wurden. Für solche Anwendungsfälle, bei denen es mehr Interaktionen mit Sensoren oder anderen Triggern gibt und der Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar für eine sofortige Bildschirmreaktion, um ein bestmögliches Kundenerlebnis zu gewährleisten.

In den folgenden Tabellen finden Sie einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und mögliche Auslaufzeiten erforderlich sind.

Alle Informationen müssen als der Verbrauch jedes Geräts im Netzwerk gesehen werden, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen addiert sich also und verlängert die Downloadzeit.