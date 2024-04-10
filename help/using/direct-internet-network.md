---
title: Direkter Internet-Zugriff
description: Direkter Internet-Zugriff
exl-id: a393ce2f-b774-4cd5-9001-c5cc24d445ae
source-git-commit: 1e8beb9dfaf579250138d4a41eeec88cc81f2d39
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 51%

---

# Netzwerk für direkten Internet-Zugriff (kabelgebunden/kabellos) {#direct-internet-access}

Das Netzwerk für direkten Internet-Zugriff enthält einen Zugangspunkt für den Internetzugang, um die AEM Cloud Service zu erreichen, mit denen AEM Screens eine Verbindung herstellen muss.

AEM Screens verwendet für die Kommunikation standardmäßig die folgenden Ports:

* `ssl-secured https (TCP Port 443)`
  <br> oder</br>

* `http (TCP Port 80)`, wenn Ihr bestimmter Anwendungsfall nicht diese Sicherheitsstufe erfordert.

Abhängig von der Konfiguration Ihrer dedizierten AEM-Konfiguration können die Ports variieren. In dieser Konfiguration sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der nachfolgenden Abbildung dargestellt.

![](/help/assets/direct-access-2.png)

Die Konfiguration umfasst auch einen Internet-Zugriff durch einen beliebigen Internet Service Provider (ISP) und dessen Internet-Anschluss. Die meisten ISPs bieten einen Internet-Router, der das Internet-Modem, den Netzwerk-Switch, den WLAN-Zugangspunkt, die Firewall und andere Netzwerkfunktionen umfasst (je nach Hersteller und Modell).

## Verbinden des AEM Screens-Players mit dem direkten Internetzugang

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

1. Stellen Sie sicher, dass alle AEM Screens-Player mit dem Netzwerk des Routers verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL im Browser Ihres Systems aufrufen.

   >[!NOTE]
   >Wenn ein Fehler auftritt, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich gibt es zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration

1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit den Einstellungen des Routers übereinstimmt. Stellen Sie sicher, dass die maximale Anzahl der in Ihrem Netzwerk verfügbaren IP-Adressen nicht erreicht ist.
1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide-Area-Netzwerk (Internet Link) des ISP verbunden ist. Auf Standard-Routern signalisiert dies in der Regel auch eine LED.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Gehen Sie wie folgt vor, wenn bei AEM Screens Verbindungsprobleme auftreten und die erwarteten Inhalte nicht angezeigt werden:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.
   >1. Stellen Sie sicher, dass alle erforderlichen Ports zugelassen werden.

## Einrichten eines direkten Internet-Netzwerks {#requirements-direct}

Das Netzwerk für direkten Zugriff ist logisch in zwei Blöcke unterteilt:

* WAN (Wide Area Network)

* LAN (Local Area Network)

### WAN (Wide Area Network) {#wan-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch der Betrieb von AEM Screens gewährleistet werden kann.

*Ausreichend* hängt von der Anzahl der an AEM angebundenen Bildschirme sowie vom Bandbreitenbedarf anderer verbundener Netzwerknutzer wie Smartphones, Tablets, Kassensystemen, Computern oder Gast-WLANs ab.

>[!NOTE]
>
>Die oben genannten Geräte haben einen gleichzeitigen Zugriff auf die Internet-Verbindung und die Bandbreite nimmt linear ab, wenn Sie dem Netzwerk weitere Benutzer oder Computer hinzufügen.

### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung stellt ausreichend Bandbreite zur Verfügung, um neben der Erreichbarkeit des Netzwerks auch den Betrieb von AEM Screens zu gewährleisten.

LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 100 MBit/s, sodass ausreichend Bandbreite zur Verfügung steht, damit viele Geräte mit guter Leistung an das System angeschlossen werden können.
Sofern eine WLAN-Lösung für die Internet-Anbindung von AEM Screens vorgesehen ist, sollten moderne WLAN-Standards verwendet werden. Empfohlen wird hierfür mindestens `IEEE 802.11g`. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`.

>[!NOTE]
>
>Wenn ein WLAN-Repeater erforderlich ist, empfiehlt Adobe einen Mesh-WLAN-Zugangspunkt wie Google Nest Wifi oder Ähnliches. Andere WLAN-Repeater-Technologien sind mit massiven Bandbreiteneinbußen verbunden.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen erheblichen Vorteil. dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

Bei normalen Vorgängen, z. B. einer definierten Wiedergabeliste, die im Laufe des Tages häufig aktualisiert wird, ist ein nahezu netzwerkunabhängiger Vorgang verfügbar, nachdem alle Dateien auf dem Player gespeichert wurden.

Szenarien, in denen umfangreicher mit Sensoren oder Auslösern sowie dynamischen Inhalten interagiert wird, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>
>Anhand dieser Informationen können Sie die Nutzung der einzelnen Geräte im Netzwerk anzeigen, die eine Internet-Quelle anfordern und herunterladen. Mit jeder dieser Anforderungen wird die Download-Zeit addiert und verlängert.

![](/help/assets/download-times-direct.png)
