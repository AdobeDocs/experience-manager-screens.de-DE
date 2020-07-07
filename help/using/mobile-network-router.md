---
title: Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten
description: Auf dieser Seite wird das mobile Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten beschrieben.
translation-type: tm+mt
source-git-commit: ec8af4e49694937a79ccbd78d51569f1031ca251
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 75%

---


# Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#mobile-network-setup}

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Downloadzeiten sowie auf Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung der regelmäßigen Wiedergabe von Displays.

Der Vorteil dieses Setups besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. Das ist in der Regel in einer erhöhten und offenen Position mit so wenig umliegenden Beton- oder Metallkonstruktionen wie möglich.
Dieses Setup ermöglicht AEM-Bildschirmbenutzern Flexibilität, da keine Festnetzverbindung für die Verbindung mit AEM Screens erforderlich ist. Dies ist besonders interessant für kurzlebige oder mobile Setups.

Die Konfiguration für das mobile Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten umfasst für jeden AEM Screens-Controller einen Internet-Zugang, der mittels Direktzugriff auf das Internet über eine eigene 3G-, 4G- oder 5G- Datenverbindung umgesetzt wird (wie im nachfolgenden Diagramm dargestellt).

![](/help/using/assets/mobile-network-1.png)

## Anbinden von AEM Screens-Playern an ein mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#connecting-aem-screens-players}

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

Die Konfiguration weist jedem AEM Screens-Controller einen Internetzugang über einen eigenen 3/4/5G-Datenlink zu.

1. Stellen Sie sicher, dass der mobile WLAN-Router entsprechend den Angaben im Betriebssystem ordnungsgemäß mit dem Mobilfunknetz verbunden ist und alle AEM Screens-Player an das Router-Netzwerk angebunden sind.
1. Testen Sie die Internetverbindung, indem Sie im Systembrowser eine URL aufrufen.
   >[!NOTE]
   >Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich bestehen für eine ordnungsgemäße Netzwerkverbindung zwei Optionen:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit der des Routers übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide Area Network (also der Internet-Verbindung) des Internet-Dienstanbieters (Internet Service Provider, ISP) verbunden ist. Auf Standard-Routern signalisiert dies in der Regel auch eine LED.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Gehen Sie wie folgt vor, wenn bei AEM Screens Verbindungsprobleme auftreten und die erwarteten Inhalte nicht angezeigt werden:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.



## Einrichten eines mobilen Netzwerks mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Leistung der Internetverbindung muss neben der bereits beschriebenen Netzwerkerreichbarkeit ausreichend Bandbreite bereitstellen, um AEM Screens-Content-Downloads reibungslos durchführen zu können.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirmgeräte und von der Nutzung anderer Verbraucher im Netzwerk ab, z. B. Smartphones, Tablets, Kassierer, Computer oder WLAN-Gastnetzwerke.
Denken Sie daran, dass alle Geräte einen gleichzeitigen Zugriff auf die Internetverbindung haben und dass die Bandbreite in der Regel linear sinkt, während dem Netzwerk mehr Benutzer/Computer hinzugefügt werden.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Reichweite des MobilRouters mindestens &quot;gut&quot; ist. Ferner muss das im Rahmen des zugrunde liegenden Abonnements gebuchte monatliche Datenvolumen eine für alle an das Netzwerk angebundenen Clients ausreichende Kapazität und Bandbreite zur Verfügung stellen.

Nachfolgend sind die Datennetzwerke einschließlich der ihnen zugehörigen Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 MBit/s |
| 4G | 150 MBit/s |
| 5G | 1.000–10.000 MBit/s |

Bei der Wahl des Datennetzwerks empfiehlt es sich, die folgenden Fragen abzuwägen:

* Wie viele Clients sind mit dem Router verbunden?

* Wie häufig werden Inhalte voraussichtlich geändert und welche Größe weisen die entsprechenden Dateien im Schnitt auf?

>[!NOTE]
>Die mindestens vom Datenabo abzudeckende Kapazität beträgt: 
`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>Für den erstmaligen Upload der Mediendateien, z. B. bei der Integration neuer Player, muss ein höheres Datenvolumen und eine längere Download-Zeit einkalkuliert und in den oben ausgeführten Schätzungen berücksichtigt werden. Ein 4G-Netz mit *guter* Abdeckung und unbegrenztem Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.


### LAN (Local Area Network) {#lan-connection}

Die Leistung des LAN muss neben der bereits beschriebenen Netzwerkerreichbarkeit ausreichend Bandbreite bereitstellen, um AEM Screens-Downloads reibungslos zu bedienen. LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 100 MBit/s und sollten daher auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite liefern. Sind aktive Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen.

Beispielsweise sollten entsprechende Netzwerkkomponenten mindestens auf den 100 MBit/s-Standard ausgelegt sein und mit den Bandbreitenspezifikationen des Internet-Zugangs/-Routers übereinstimmen.

Sofern eine WLAN-Lösung für die Internet-Anbindung der Bildschirme vorgesehen ist, sollten moderne WLAN-Standards verwendet werden. Empfohlen wird hierfür mindestens IEEE 802.11g. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa 802.11h-n. Ist ein WLAN-Repeater erforderlich, wird für die Zugangspunkte dringend der Einsatz von Mesh-WLAN-Technologie empfohlen, z. B. Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Durch dieses Konzept ist der Großteil des Netzwerk-Traffics auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.
So kann der Normalbetrieb, also beispielsweise Fälle, in denen bei einer Wiedergabeliste für den Tagesverlauf nur wenige Updates definiert sind, nahezu unabhängig vom Netzwerk ablaufen, sobald alle Dateien auf dem Player gespeichert wurden.
Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.
Nachfolgend finden Sie eine Aufschlüsselung der wichtigsten Daten zur Netzwerkverbindung und wie sich diese auf die zu erwartende Leistung und potenzielle Wartezeiten auswirken.

>[!NOTE]
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Mit jeder weiteren solchen Anfrage summiert sich die Bandbreitennutzung, durch die sich wiederum die Download-Zeit verlängert.

![](/help/using/assets/mobile-router-download.png)



