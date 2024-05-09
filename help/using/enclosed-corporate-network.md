---
title: Geschlossenes Unternehmensnetzwerk
description: Geschlossenes Unternehmensnetzwerk
exl-id: b8c52e72-86da-4089-ba02-0c643862419f
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 46%

---

# Geschlossenes Unternehmensnetzwerk (kabelgebunden/kabellos) {#enclosed-corporate-networks}

Die Konfiguration für geschlossene Unternehmensnetzwerke gilt für kleinere, größere und Unternehmen. Aus logischer Sicht ist diese Konfiguration so aufgebaut, wie in der nachfolgenden Abbildung dargestellt. Theoretisch kann sie aber auch komplexer ausfallen.

![](/help/using/assets/enclosed-network-1.png)


## Verbinden des AEM Screens-Players mit dem direkten Internetzugang

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

1. Stellen Sie sicher, dass alle AEM Screens-Player mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL im Browser Ihres Systems aufrufen.

   >[!NOTE]
   >Falls ein Fehler auftritt, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich gibt es zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration

1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit den Einstellungen des Routers übereinstimmt, und überprüfen Sie, ob die maximale Anzahl der in Ihrem Netzwerk verfügbaren IP-Adressen nicht erreicht ist.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide-Area-Netzwerk (Internet Link) des ISP verbunden ist. Diese Verbindung kann auch über eine Signal-LED auf Standard-Routern identifiziert werden.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Gehen Sie wie folgt vor, wenn bei AEM Screens Verbindungsprobleme auftreten und die erwarteten Inhalte nicht angezeigt werden:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.
   >1. Stellen Sie sicher, dass alle erforderlichen Ports zugelassen werden.

## Einrichten von geschlossenen Unternehmensnetzwerken {#requirements-enclosed-networks}

Die Konfiguration für geschlossene Unternehmensnetzwerke kann logisch in zwei Blöcke unterteilt werden:

* WAN (Wide Area Network)
* Internes LAN (Local Area Network)

### WAN (Wide Area Network) {#wan-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch reibungslose Aktualisierungen von AEM Screens-Inhalten gewährleistet werden können.
*Ausreichende Bandbreite* hängt von der Anzahl der verbundenen AEM Screens ab. Es hängt auch von der Nutzung anderer verbundener Netzwerknutzer wie Smartphones, Tablets, Kassensystemen, Computern oder Gast-WLANs ab.

>[!NOTE]
>
>Alle Geräte haben gleichzeitigen Zugriff auf die Internet-Verbindung und die Bandbreite nimmt linear ab, wenn Sie dem Netzwerk weitere Benutzer oder Computer hinzufügen.

### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch eine reibungslose Aktualisierung von AEM Screens-Inhalten gewährleistet werden kann.

In Unternehmen eingesetzte LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 1000 MBit/s, was auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite liefert. Bei Verwendung anderer aktiver Netzwerkkomponenten müssen diese alle den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten die Netzwerkkomponenten mindestens mit dem 100 MBit/s-Standard übereinstimmen und mit der Bandbreite übereinstimmen, die von der Internet-Zugriffs-/Routerspezifikation bereitgestellt wird.

### Andere Spezifika von Unternehmensnetzwerken {#other-networks}

Unternehmensnetzwerke verfügen über mehrere miteinander verbundene Geräte, sind in verschiedene Subnetze unterteilt und verfügen über redundante oder durch Multiplexing gestützte Internet-Verbindungen, die eine ausreichende Leistung für viele Tausende gleichzeitiger Zugriffe ermöglichen.
Dieses Schema ist vereinfacht und in den meisten Fällen auf die dem Client zur Verfügung stehenden Umgebungen anwendbar.

Sofern eine WLAN-Lösung für die Internet-Anbindung von AEM Screens vorgesehen ist, sollten moderne WLAN-Standards verwendet werden. Empfohlen wird hierfür mindestens `IEEE 802.11g`. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`. Wenn ein WLAN-Repeater erforderlich ist, empfiehlt Adobe Mesh-WLAN-Zugangspunkttechnologien wie Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen.
Andere WLAN-Repeater-Technologien sind mit massiven Bandbreiteneinbußen verbunden.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen erheblichen Vorteil. dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

Bei normalen Vorgängen, z. B. einer definierten Wiedergabeliste, die im Laufe des Tages häufig aktualisiert wird, ist ein nahezu netzwerkunabhängiger Vorgang verfügbar, nachdem alle Dateien auf dem Player gespeichert wurden.

In Szenarien, in denen es mehr Interaktionen mit Sensoren oder Triggern und dynamischen Inhalten gibt, ist eine schnelle und zuverlässige Netzwerkverbindung unerlässlich, um eine sofortige Reaktion auf den Bildschirm zu ermöglichen und so ein bestmögliches Kundenerlebnis zu gewährleisten.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>Mithilfe dieser Informationen können Sie den Verbrauch der einzelnen Geräte im Netzwerk anzeigen, indem Sie eine Internet-Quelle anfordern und herunterladen. Mit jeder dieser Anforderungen wird die Download-Zeit addiert und verlängert.

![](/help/using/assets/enclosed-network-download.png)
