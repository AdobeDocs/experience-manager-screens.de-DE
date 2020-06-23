---
title: Geschlossenes Unternehmensnetzwerk
description: Geschlossenes Unternehmensnetzwerk
translation-type: tm+mt
source-git-commit: 6d6637d5222e861fa9a83f555baf0699f56f150a
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 1%

---


# Geschlossene Unternehmensnetzwerke {#enclosed-corporate-networks}

Das Engeschlossene Unternehmensnetzwerk-SetUp ist für kleinere, größere und unternehmensinterne Unternehmen geeignet. Es kann theoretisch komplexer sein, aber das logische Setup ist in der folgenden Abbildung dargestellt.

![](/help/using/assets/enclosed-network-1.png)

## Anforderungen für die Einrichtung von geschlossenen Unternehmensnetzwerken {#requirements-enclosed-networks}

Die Einrichtung des Unternehmensnetzwerks &quot;Engeschlossene Unternehmensnetzwerke&quot;kann logisch in zwei Blöcke getrennt werden:

* WAN (Wide Area Network)
* Internes Local Area Network (LAN).

### Breites Netzwerk {#wan-connection}

Die Leistung der Internetverbindung ist nicht nur die Reichweite des Netzwerks, sondern auch die Bereitstellung ausreichender Bandbreite, um die AEM Screens angenehm und reibungslos zu bedienen.
*Eine ausreichende Bandbreite* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und von der Nutzung anderer Verbraucher im Netzwerk ab, z. B. Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.

>[!NOTE]
>Alle Geräte haben einen gleichzeitigen Zugriff auf die Internetverbindung und die Bandbreite wird normalerweise linear verringert, wenn Sie mehr Benutzer oder Computer zum Netzwerk hinzufügen.

### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN) ist neben der Netzwerkerreichbarkeit auch die Bereitstellung ausreichender Bandbreite für den reibungslosen Betrieb von AEM Screens.

In diesen Tagen ist das LAN-Netzwerk innerhalb der Unternehmen in der Regel mindestens 1000 MBit/s Netzwerk, sodass es ausreichend Bandbreite, um viele Geräte mit guter Leistung mit dem System verbinden. Bei Verwendung anderer aktiver Netzwerkkomponenten müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten die Netzwerkkomponenten mindestens dem 1000-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.

### Sonstige Unternehmensnetzspezifikationen {#other-networks}

In der Regel haben Unternehmensnetzwerke eine Vielzahl von Geräten angeschlossen, könnten in verschiedene Teilnetzwerke aufgeteilt werden und haben redundante oder Multiplexing-Internetverbindungen, um eine ausreichende Leistung für viele tausend gleichzeitige Zugriffe zu bieten.
Das obige Schema ist vereinfacht und passt in den meisten Fällen zu der Umgebung, die für den Kunden zur Verfügung steht.
Falls eine WiFI-Lösung für die Verbindung des Bildschirms mit dem Internet-Link vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Alle &quot;neueren&quot; Standards wie 802.11h-n sind von besserer Qualität. Wenn ein WIFI-Repeater benötigt wird, empfehlen wir dringend Mesh WIFI Access-Point Technologien wie Google Nest Mesh WIFI oder Ähnliches.
Andere WiFi-Wiederholungstechnologien führen schließlich zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bieten Digital Signage-Benutzern einen großen Vorteil. Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerk-Traffic, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Für den normalen Betrieb, z.B. wenn Sie eine Playlist definiert haben, die nicht sehr oft während des Tages geändert wird, wird hier ein Netzwerkunabhängiger Vorgang durchgeführt, sobald alle Angebote auf dem Player gespeichert wurden. Für solche Anwendungsfälle, bei denen es mehr Interaktionen mit Sensoren oder anderen Triggern gibt und der Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar für eine sofortige Bildschirmreaktion, um ein bestmögliches Kundenerlebnis zu gewährleisten.

Die folgenden Tabellen bieten einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und für potenzielle Wartezeiten erforderlich sind.

Alle Informationen müssen als der Verbrauch jedes Geräts im Netzwerk gesehen werden, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen addiert sich also und verlängert die Downloadzeit.

![](/help/using/assets/enclosed-network-download.png)