---
title: Geschlossenes Unternehmensnetzwerk
description: Geschlossenes Unternehmensnetzwerk
translation-type: tm+mt
source-git-commit: 8e62b3fc4ce324e02aaec6fca9df79b1aaf94d72
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 44%

---


# Vernetzte Unternehmensnetze (Drahtlos/Drahtlos) {#enclosed-corporate-networks}

Die Konfiguration für geschlossene Unternehmensnetzwerke ist in kleineren, mittleren und großen Unternehmen gleichermaßen anwendbar. Es kann theoretisch komplexer sein, aber das logische Setup ist in der folgenden Abbildung dargestellt.

![](/help/using/assets/enclosed-network-1.png)

## Voraussetzungen für die Einrichtung von geschlossenen Unternehmensnetzwerken {#requirements-enclosed-networks}

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

Aktuelle in Unternehmen eingesetzte LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 1000 MBit/s und sollten daher auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite liefern. Bei Verwendung anderer aktiver Netzwerkkomponenten müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten die Netzwerkkomponenten mindestens dem 1000-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.

### Andere Spezifika von Unternehmensnetzwerken {#other-networks}

In der Regel haben Unternehmensnetzwerke eine Vielzahl von Geräten angeschlossen, könnten in verschiedene Subnetzwerke aufgeteilt werden und über redundante oder Multiplexing-Internetverbindungen verfügen, um eine ausreichende Leistung für viele tausend gleichzeitige Zugriffe zu bieten.
Dieses Schema ist vereinfacht und passt in den meisten Fällen zu der Umgebung, die für den Client verfügbar ist.

In case that an WIFI solution is envisaged to connect screen to the internet Link it is recommended to use modern WIFI standards like `IEEE 802.11g` as a minimum. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n` Ist ein WLAN-Repeater erforderlich, wird für die Zugangspunkte dringend der Einsatz von Mesh-WLAN-Technologie empfohlen, z. B. Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen.
Andere WLAN-Repeater-Technologien sind mit massiven Bandbreiteneinbußen verbunden.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Durch dieses Konzept ist der Großteil des Netzwerk-Traffics auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.
So kann der Normalbetrieb, also beispielsweise Fälle, in denen bei einer Wiedergabeliste für den Tagesverlauf nur wenige Änderungen definiert sind, nahezu unabhängig vom Netzwerk ablaufen, sobald alle Dateien auf dem Player gespeichert wurden. Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Die folgenden Tabellen bieten einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und für potenzielle Wartezeiten erforderlich sind.

>[!NOTE]
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/enclosed-network-download.png)