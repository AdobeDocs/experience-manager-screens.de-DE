---
title: Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten
description: Auf dieser Seite wird das mobile Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten beschrieben.
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 27%

---

# Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#mobile-network-setup}

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Daher wirkt sich die verfügbare Bandbreite nur auf die anfänglichen Download-Zeiten und Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung der regelmäßigen Wiedergabe von Anzeigen.

Der Vorteil dieser Konfiguration besteht darin, dass der mobile Router flexibel an einem Ort platziert werden kann, an dem eine optimale Netzabdeckung gewährleistet ist. Dieser Ort befindet sich in der Regel in einer erhöhten und offenen Position, mit so wenigen umliegenden Beton- oder Metallstrukturen wie möglich.
Diese Einrichtung bietet Anwendern von AEM-Bildschirmen Flexibilität, da für die Anbindung an AEM Screens kein Festnetz benötigt wird. Es ist auch für kurzlebige oder mobile Setups interessant.

Das folgende Diagramm zeigt die Konfiguration des mobilen Netzwerks mit mobilem WLAN-Router und aktiven Netzwerkkomponenten. Es enthält einen Internetzugang für jeden der AEM Screens-Controller über einen direkten Internetzugang über eine eigene 3/4/5G-Datenverbindung.

![](/help/using/assets/mobile-network-1.png)

## Verbinden des AEM Screens-Players mit dem mobilen Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#connecting-aem-screens-players}

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

Die Konfiguration weist jedem AEM Screens-Controller einen Internetzugang über einen speziellen 3/4/5G-Datenlink zu.

1. Stellen Sie sicher, dass der mobile WLAN-Router ordnungsgemäß mit dem Mobilfunknetz verbunden ist, wie im Betriebssystem angegeben. Stellen Sie außerdem sicher, dass alle Player des AEM Screens mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL im Browser Ihres Systems aufrufen.

   >[!NOTE]
   >Falls ein Fehler auftritt, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich gibt es zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration

1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit der des Routers übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide Area Network (Internet Link) des Internet Service Providers verbunden ist. Sie können die Verwendung einer Signal-LED auf Standard-Routern überprüfen.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

   >[!TIP]
   >Möglicherweise funktioniert die AEM Screens-Verbindung nicht ordnungsgemäß. Der erwartete Inhalt wird nicht angezeigt. Überprüfen Sie in solchen Fällen die Firewall des Internet-Routers, ob Einschränkungen in Bezug auf `TCP/IP Port 80/443`.


## Einrichten eines mobilen Netzwerks mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der bereits beschriebenen Erreichbarkeit des Netzwerks auch reibungslose Downloads von AEM Screens-Inhalten gewährleistet werden können.

*Ausreichend* hängt von der Anzahl der verbundenen AEM Screens-Geräte ab. Dabei kommt es auch auf die Nutzung anderer verbundener Netzwerknutzer wie Smartphones, Tablets, Kassensystemen, Computern oder Gast-WLANs an.
Beachten Sie, dass alle Geräte gleichzeitig auf die Internet-Verbindung zugreifen und dass die Bandbreite linear abnimmt und gleichzeitig mehr Verbraucher/Computer zum Netzwerk hinzugefügt werden.
Neben der jeweiligen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Abdeckung des mobilen Routers mindestens *good*. Außerdem muss der zugrunde liegende Monatsplan ausreichend Datenkapazität und Bandbreite für alle angeschlossenen Kunden im LAN-Netz abdecken.

In der folgenden Tabelle sind die Datennetzwerke mit ihrer Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 MBit/s |
| 4G | 150 MBit/s |
| 5G | 1.000–10.000 MBit/s |

Bei der Erwägung, welches Datennetzwerk verwendet werden soll, empfiehlt Adobe, die folgenden Fragen zu beantworten:

* Wie viele Clients sind mit dem Router verbunden?
* Wie häufig werden Inhalte voraussichtlich geändert und welche Größe weisen die entsprechenden Dateien im Schnitt auf?

>[!NOTE]
>
>Die mindestens vom Daten-Package abzudeckende Kapazität beträgt:
>
>`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>
>Für den erstmaligen Upload von Mediendateien bei der Integration neuer Player ist ein höheres Datenvolumen und eine längere Download-Zeit zu erwarten. Dies spiegelt sich auch in den oben genannten Annahmen wider. Ein 4G-Netz mit *guter* Abdeckung und unbegrenztem Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.


### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der bereits beschriebenen Erreichbarkeit des Netzwerks auch reibungslose Downloads von AEM Screens-Inhalten gewährleistet werden können. Derzeit entspricht das LAN-Netzwerk in der Regel mindestens einem 100-MBit/s-Netzwerk, sodass ausreichend Bandbreite zur Verfügung stehen sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Bei Verwendung anderer aktiver Netzwerkkomponenten müssen diese alle den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten die Netzwerkkomponenten mindestens mit dem 100 MBit/s-Standard übereinstimmen und mit der Bandbreite übereinstimmen, die von der Spezifikation für Internet-Zugriff/Router bereitgestellt wird.

Sofern eine WLAN-Lösung für die Internet-Anbindung des Bildschirms vorgesehen ist, sollten moderne WLAN-Standards wie IEEE verwendet werden. `802.11g` mindestens. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`. Wenn ein WLAN-Repeater erforderlich ist, empfiehlt Adobe Mesh Wi-Fi Access Point-Technologien wie Google Nest Wifi oder Ähnliches.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen erheblichen Vorteil. dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Aufgrund dieses Konzepts tritt der große Netzwerk-Traffic auf, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden sollen.
Für den normalen Betrieb mit einer definierten Wiedergabeliste, die nicht häufig aktualisiert wird, bietet sie nahezu netzwerkunabhängigen Betrieb, wenn alle Dateien auf dem Player gespeichert werden.
Für Anwendungsfälle, in denen es mehr Interaktionen mit Sensoren oder anderen Triggern gibt und der Inhalt dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unerlässlich, um eine sofortige Bildschirmreaktion auszulösen. Dadurch wird das bestmögliche Kundenerlebnis sichergestellt.
Die folgenden Tabellen bieten einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und potenzielle Wartezeiten von Bedeutung sind.

>[!NOTE]
>
>Alle Informationen beziehen sich auf die Nutzung der einzelnen Geräte im Netzwerk, die eine Internet-Quelle anfordern und herunterladen. Jede dieser Anforderungen addiert die Download-Zeit und verlängert sie.

![](/help/using/assets/mobile-router-download.png)
