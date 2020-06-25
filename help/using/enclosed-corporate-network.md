---
title: Geschlossenes Unternehmensnetzwerk
description: Geschlossenes Unternehmensnetzwerk
translation-type: tm+mt
source-git-commit: ed683a86b7e8c6ec06309577bd0a8690a9cc4684
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 29%

---


# Vernetzte Unternehmensnetze (Drahtlos/Drahtlos) {#enclosed-corporate-networks}

Die Konfiguration für geschlossene Unternehmensnetzwerke ist in kleineren, mittleren und großen Unternehmen gleichermaßen anwendbar. Es kann theoretisch komplexer sein, aber das logische Setup ist in der folgenden Abbildung dargestellt.

![](/help/using/assets/enclosed-network-1.png)


## Anschließen des AEM Screens Player an den direkten Internetzugang {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine ordnungsgemäße Verbindung der AEM-Bildschirmplayer in dieser Konfiguration sicherzustellen:

1. Vergewissern Sie sich, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn Sie einen Fehler erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit den Router-Einstellungen übereinstimmt, und überprüfen Sie, ob die maximale Anzahl an IP-Adressen in Ihrem Netzwerk nicht erreicht wird.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies lässt sich auch mit einer Signal-LED auf Standard Routern identifizieren.
1. Falls der URL-Aufruf erfolgreich ist, können Sie die Installation der AEM Screens fortsetzen und sich registrieren. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und der erwartete Inhalt nicht angezeigt wird:
   >
   >1. Check in your Internet Router firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.


## Voraussetzungen für die Einrichtung von geschlossenen Unternehmensnetzwerken {#requirements-enclosed-networks}

Die Einrichtung des Unternehmensnetzwerks &quot;Engeschlossene Unternehmensnetzwerke&quot;kann logisch in zwei Blöcke getrennt werden:

* WAN (Wide Area Network)
* Internes Local Area Network (LAN).

### Breites Netzwerk {#wan-connection}

Die Leistung der Internetverbindung ist nicht nur die Reichweite des Netzwerks, sondern auch die Bereitstellung ausreichender Bandbreite, um die AEM Screens angenehm und reibungslos zu bedienen.
*Eine ausreichende Bandbreite* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und von der Nutzung anderer Verbraucher im Netzwerk ab, z. B. Smartphones, Tablets, Kassierer, Computer oder Guest-Wi-Fi-Netzwerke.

>[!NOTE]
>Alle Geräte haben einen gleichzeitigen Zugriff auf die Internetverbindung und die Bandbreite wird normalerweise linear verringert, wenn Sie mehr Benutzer oder Computer zum Netzwerk hinzufügen.

### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN) ist neben der Netzwerkerreichbarkeit auch die Bereitstellung ausreichender Bandbreite für den reibungslosen Betrieb von AEM Screens.

Aktuelle in Unternehmen eingesetzte LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 1000 MBit/s und sollten daher auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite liefern. Bei Verwendung anderer aktiver Netzwerkkomponenten müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten die Netzwerkkomponenten mindestens dem 1000-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.

### Andere Spezifika von Unternehmensnetzwerken {#other-networks}

In der Regel haben Unternehmensnetzwerke eine Vielzahl von Geräten angeschlossen, könnten in verschiedene Subnetzwerke aufgeteilt werden und über redundante oder Multiplexing-Internetverbindungen verfügen, um eine ausreichende Leistung für viele tausend gleichzeitige Zugriffe zu bieten.
Dieses Schema ist vereinfacht und passt in den meisten Fällen zu der Umgebung, die für den Client verfügbar ist.

In case that an Wi-Fi solution is envisaged to connect screen to the internet Link it is recommended to use modern Wi-Fi standards like `IEEE 802.11g` as a minimum. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n` Wenn ein Wi-Fi-Repeater erforderlich ist, empfehlen wir dringend Mesh Wi-Fi Access-Point Technologien wie Google Nest Mesh Wi-Fi oder Ähnliches.
Andere Wi-Fi-Wiederholungstechnologien führen schließlich zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Durch dieses Konzept ist der Großteil des Netzwerk-Traffics auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.
So kann der Normalbetrieb, also beispielsweise Fälle, in denen bei einer Wiedergabeliste für den Tagesverlauf nur wenige Änderungen definiert sind, nahezu unabhängig vom Netzwerk ablaufen, sobald alle Dateien auf dem Player gespeichert wurden. Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Die folgenden Tabellen bieten einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und für potenzielle Wartezeiten erforderlich sind.

>[!NOTE]
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/enclosed-network-download.png)