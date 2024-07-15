---
title: Direkter Internet-Zugriff
description: Direkter Internet-Zugriff
exl-id: a393ce2f-b774-4cd5-9001-c5cc24d445ae
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 100%

---

# Netzwerk für direkten Internet-Zugriff (kabelgebunden/kabellos) {#direct-internet-access}

Das Netzwerk für direkten Internet-Zugriff beinhaltet einen Internet-Zugangspunkt, über den die Erreichbarkeit der AEM Cloud Services gewährleistet wird, mit denen AEM Screens eine Verbindung herstellen muss.

AEM Screens verwendet für die Kommunikation standardmäßig die folgenden Ports:

* `ssl-secured https (TCP Port 443)`
  <br> oder</br>

* `http (TCP Port 80)`, wenn Ihr bestimmter Anwendungsfall nicht diese Sicherheitsstufe erfordert.

Abhängig von der Konfiguration Ihrer jeweiligen AEM-Konfigurationseinrichtung kommt es möglicherweise zu Abweichungen bei den Ports. In dieser Konfiguration sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der nachfolgenden Abbildung dargestellt.

![](/help/assets/direct-access-2.png)

Ferner beinhaltet die Konfiguration einen von einem Internet-Dienstanbieter (Internet Service Provider, ISP) bezogenen Internet-Zugang und die zugehörige Verbindung zum Internet. Die meisten Internet-Dienstanbieter bieten Internet-Router, die Internet-Modem, Netzwerk-Switch, WLAN-Zugangspunkt, Firewall und andere Netzwerkfunktionen vereinen (je nach Hersteller und Modell).

## Anbinden von AEM Screens-Playern für direkten Internet-Zugriff

Gehen Sie wie folgt vor, um eine ordnungsgemäße Anbindung der AEM Screens-Player in dieser Konfiguration sicherzustellen:

1. Stellen Sie sicher, dass alle AEM Screens-Player mit dem Netzwerk des Routers verbunden sind.
1. Testen Sie die Internet-Verbindung, indem Sie in Ihrem System-Browser eine URL aufrufen.

   >[!NOTE]
   >Wenn ein Fehler auftritt, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich gibt es zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration

1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit der des Routers übereinstimmt, und prüfen Sie, ob bereits die maximal zulässige Anzahl an in Ihrem Netzwerk verwendeten IP-Adressen erreicht wurde.
1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide Area Network (also dem Internet-Link) des Internet-Dienstanbieters verbunden ist. Auf Standard-Routern kann dies in der Regel auch durch eine Signal-LED festgestellt werden.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen Starten Sie AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Gehen Sie wie folgt vor, wenn bei AEM Screens Verbindungsprobleme auftreten und die erwarteten Inhalte nicht angezeigt werden:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.
   >1. Stellen Sie sicher, dass alle erforderlichen Ports zugelassen sind.

## Einrichten des Netzwerks für direkten Internet-Zugriff {#requirements-direct}

Das Netzwerk für direkten Zugriff ist logisch in zwei Blöcke unterteilt:

* WAN (Wide Area Network)

* LAN (Local Area Network)

### WAN (Wide Area Network) {#wan-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch der Betrieb von AEM Screens gewährleistet werden kann.

Wie viel *ausreichend* ist, hängt von der Anzahl der verbundenen AEM Screens-Geräte ab. Dies ist außerdem abhängig von der Nutzung anderer Verbrauchergeräte innerhalb des Netzwerks. Dazu gehören z. B. Smartphones, Tablets, Kassensysteme, Computer oder WLAN-Gastnetzwerke.

>[!NOTE]
>
>Alle oben genannten Geräte greifen gleichzeitig auf die Internet-Verbindung zu. Dementsprechend nimmt die Bandbreite mit der Zahl an weiteren Verbrauchergeräten oder Computern, die dem Netzwerk hinzugefügt werden, linear ab.

### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch ein reibungsloser Betrieb von AEM Screens gewährleistet werden kann.

LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 100 MBit/s und liefern daher auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite.
Sofern eine WLAN-Lösung für die Internet-Anbindung von AEM Screens vorgesehen ist, sollten moderne WLAN-Standards verwendet werden. Empfohlen wird hierfür mindestens `IEEE 802.11g`. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`.

>[!NOTE]
>
>Ist ein WLAN-Repeater erforderlich, empfiehlt Adobe, einen Mesh-WLAN-Zugangspunkt zu verwenden, z. B. Google Nest Mesh Wi-Fi oder vergleichbare Mesh-WLAN-Lösungen. Andere WLAN-Repeater-Technologien sind mit massiven Bandbreiteneinbußen im gesamten Netzwerk verbunden.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Digital-Signage-Anwendenden einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

So kann der Normalbetrieb, wenn sich z. B. eine definierte Wiedergabeliste häufig während des Tages aktualisiert, nahezu unabhängig vom Netzwerk ablaufen, nachdem alle Dateien auf dem Player gespeichert wurden.

Szenarien, in denen umfangreicher mit Sensoren oder Auslösern sowie dynamischen Inhalten interagiert wird, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

In der nachfolgenden Tabelle ist eine Übersicht der wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>
>Diese Daten zeigen auf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Mit jeder weiteren solchen Anfrage erhöht sich die Bandbreitennutzung, wodurch sich wiederum die Download-Zeit verlängert.

![](/help/assets/download-times-direct.png)
