---
title: Geschlossenes Unternehmensnetzwerk
description: Geschlossenes Unternehmensnetzwerk
translation-type: tm+mt
source-git-commit: d12de8de2b7bb29d85ebb0e046f2d1fd5051e928
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 6%

---


# Vernetzte Unternehmensnetze (Drahtlos/Drahtlos) {#enclosed-corporate-networks}

Die Engeschlossene Unternehmensnetzwerkeinrichtung gilt für kleinere, größere und unternehmenseigene Unternehmen. Es kann theoretisch komplexer sein, und das logische Setup ist in der folgenden Abbildung dargestellt.

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


## Einrichten von geschlossenen Unternehmensnetzwerken {#requirements-enclosed-networks}

Die Einrichtung des Unternehmensnetzwerks &quot;Engeschlossene Unternehmensnetzwerke&quot;kann logisch in zwei Blöcke getrennt werden:

* WAN (Wide Area Network)
* Internes Local Area Network (LAN).

### Breites Netzwerk {#wan-connection}

Die Leistung der Internetverbindung ist neben der Netzwerkanbindung auch die Bereitstellung ausreichender Bandbreite für den reibungslosen Betrieb von AEM Screens.
*Eine ausreichende Bandbreite* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und von der Nutzung anderer Verbraucher im Netzwerk ab, z. B. Smartphones, Tablets, Kassierer, Computer oder WLAN-Gastnetzwerke.

>[!NOTE]
>Alle Geräte haben einen gleichzeitigen Zugriff auf die Internetverbindung und die Bandbreite verringert sich linear, wenn Sie mehr Benutzer oder Computer zum Netzwerk hinzufügen.

### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN) besteht neben der Netzwerkerreichbarkeit darin, ausreichend Bandbreite bereitzustellen, um AEM Screens reibungslos zu bedienen.

Das LAN-Netzwerk in Unternehmen ist in der Regel mindestens 1000 MBit/s Netzwerk, sodass es genügend Bandbreite gibt, um viele Geräte mit guter Leistung mit dem System zu verbinden. Bei Verwendung anderer aktiver Netzwerkkomponenten müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten die Netzwerkkomponenten mindestens dem Standard von 1000 Mbit/s entsprechen und der Bandbreite entsprechen, die in der Internet-Zugriffs-/Router-Spezifikation angegeben ist.

### Andere Spezifika von Unternehmensnetzwerken {#other-networks}

Unternehmensnetzwerke haben eine Reihe von Geräten angeschlossen, sind in verschiedene Subnetzwerke unterteilt und verfügen über redundante oder Multiplexing-Internetverbindungen, um eine ausreichende Leistung für viele tausend gleichzeitige Zugriffe zu bieten.
Dieses Schema ist vereinfacht und passt in den meisten Fällen zu den Umgebung, die für den Client verfügbar sind.

In case that a Wi-Fi solution is envisaged to connect Screens to the Internet Link it is recommended to use modern Wi-Fi standards like `IEEE 802.11g` as a minimum. Dieser Standard unterstützt Verbindungen mit bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n` Wenn ein Wi-Fi-Repeater erforderlich ist, empfehlen wir dringend Mesh Wi-Fi Access Point Technologien wie Google Nest Mesh Wi-Fi oder Ähnliches.
Andere Wi-Fi-Wiederholungstechnologien führen zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Der große Netzwerkverkehr tritt auf, wenn auf einer bestimmten Anzeige neue Inhalte angezeigt werden.

Bei normalen Vorgängen beispielsweise wird eine definierte Playlist, die im Laufe des Tages häufig aktualisiert wird, als Angebot ein netzwerkunabhängiger Vorgang ausgeführt, sobald alle Dateien im Player gespeichert wurden.

In Szenarien, in denen es mehr Interaktionen mit Sensoren oder Triggern und dynamischen Inhalten gibt, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar, um eine sofortige Bildschirmreaktion zu gewährleisten und eine bestmögliche Kundenerfahrung zu gewährleisten.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>Die Informationen ermöglichen es Ihnen, den Verbrauch der einzelnen Geräte im Netzwerk zu Ansichten, die eine Internetquelle anfordern und herunterladen. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/enclosed-network-download.png)