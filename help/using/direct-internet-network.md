---
title: Direkter Internet-Zugriff
description: Direkter Internet-Zugriff
exl-id: a393ce2f-b774-4cd5-9001-c5cc24d445ae
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 59%

---

# Netzwerk für direkten Internet-Zugriff (kabelgebunden/kabellos) {#direct-internet-access}

Das Netzwerk für direkten Internet-Zugriff beinhaltet einen Internet-Zugangspunkt, über den die Erreichbarkeit der AEM Cloud Services gewährleistet wird, mit denen AEM Screens eine Verbindung herstellen muss.

AEM Screens verwendet für die Kommunikation standardmäßig die folgenden Ports:

* `ssl-secured https (TCP Port 443)`
  <br> oder</br>

* `http (TCP Port 80)`, wenn Ihr bestimmter Anwendungsfall nicht diese Sicherheitsstufe erfordert.

Abhängig von der Konfiguration Ihrer dedizierten AEM-Konfiguration können die Ports variieren. In dieser Konfiguration sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der nachfolgenden Abbildung dargestellt.

![](/help/assets/direct-access-2.png)

Ferner beinhaltet die Konfiguration einen von einem Internet-Dienstanbieter (Internet Service Provider, ISP) bezogenen Internet-Zugang und die zugehörige Verbindung zum Internet. Die meisten ISPs bieten einen Internet-Router, der das Internet-Modem, den Netzwerk-Switch, den WLAN-Zugangspunkt, die Firewall und andere Netzwerkfunktionen umfasst (je nach Hersteller und Modell).

## Anbinden von AEM Screens-Playern für direkten Internet-Zugriff

Gehen Sie wie folgt vor, um eine ordnungsgemäße Anbindung der AEM Screens-Player in dieser Konfiguration sicherzustellen:

1. Stellen Sie sicher, dass alle AEM Screen Player mit dem Netzwerk des Routers verbunden sind.
1. Testen Sie die Internet-Verbindung, indem Sie in Ihrem System-Browser eine URL aufrufen.

   >[!NOTE]
   >Falls ein Fehler auftritt, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich gibt es zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration

1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit Ihren Router-Einstellungen übereinstimmt. Überprüfen Sie, ob die maximale Anzahl der in Ihrem Netzwerk verfügbaren IP-Adressen nicht erreicht ist.
1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide-Area-Netzwerk (Internet Link) des ISP verbunden ist. Sie kann auch über eine LED-Anzeige an Standard-Routern identifiziert werden.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Gehen Sie wie folgt vor, wenn bei AEM Screens Verbindungsprobleme auftreten und die erwarteten Inhalte nicht angezeigt werden:
   >
   >1. Überprüfen Sie, ob in der Firewall Ihres Internet-Routers Einschränkungen bezüglich `TCP/IP Port 80/443`.
   >1. Stellen Sie sicher, dass alle erforderlichen Ports zugelassen werden.

## Einrichten des Netzwerks für direkten Internet-Zugriff {#requirements-direct}

Das Netzwerk für direkten Zugriff ist logisch in zwei Blöcke unterteilt:

* WAN (Wide Area Network)

* LAN (Local Area Network)

### WAN (Wide Area Network) {#wan-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch der Betrieb von AEM Screens gewährleistet werden kann.

*Ausreichend* hängt von der Anzahl der verbundenen AEM Screens ab. Es hängt auch von der Nutzung anderer verbundener Netzwerknutzer wie Smartphones, Tablets, Kassensystemen, Computern oder Gast-WLANs ab.

>[!NOTE]
>
>Die oben genannten Geräte haben gleichzeitigen Zugriff auf die Internet-Verbindung und die Bandbreite nimmt linear ab, wenn Sie dem Netzwerk weitere Benutzer oder Computer hinzufügen.

### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch der Betrieb von AEM Screens gewährleistet werden kann.

LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 100 MBit/s und liefern daher auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite.
Sofern eine WLAN-Lösung für die Internet-Anbindung von AEM Screens vorgesehen ist, sollten moderne WLAN-Standards verwendet werden. Empfohlen wird hierfür mindestens `IEEE 802.11g`. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`.

>[!NOTE]
>
>Ist ein WLAN-Repeater erforderlich, empfiehlt Adobe, einen Mesh-WLAN-Zugangspunkt zu verwenden, z. B. Google Nest Mesh Wi-Fi oder vergleichbare Mesh-WLAN-Lösungen. Andere WLAN-Repeater-Technologien sind mit massiven Bandbreiteneinbußen im gesamten Netzwerk verbunden.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Digital-Signage-Anwendenden einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

So kann der Normalbetrieb, wenn sich z. B. eine definierte Wiedergabeliste häufig während des Tages aktualisiert, nahezu unabhängig vom Netzwerk ablaufen, nachdem alle Dateien auf dem Player gespeichert wurden.

In Szenarien, in denen es mehr Interaktionen mit Sensoren oder Triggern und dynamischen Inhalten gibt, ist eine schnelle und zuverlässige Netzwerkverbindung unerlässlich, um eine sofortige Reaktion auf den Bildschirm zu ermöglichen und so ein bestmögliches Kundenerlebnis zu gewährleisten.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>
>Mithilfe dieser Informationen können Sie den Verbrauch der einzelnen Geräte im Netzwerk anzeigen, indem Sie eine Internet-Quelle anfordern und herunterladen. Mit jeder weiteren solchen Anfrage summiert sich die Bandbreitennutzung, durch die sich wiederum die Download-Zeit verlängert.

![](/help/assets/download-times-direct.png)
