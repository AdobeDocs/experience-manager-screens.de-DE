---
title: Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten
description: Auf dieser Seite wird das mobile Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten beschrieben.
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
source-git-commit: 02929219a064e3b936440431e77e67e0bf511bf6
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 49%

---

# Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#mobile-network-setup}

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Daher wirkt sich die verfügbare Bandbreite nur auf die anfänglichen Download-Zeiten und Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung der regelmäßigen Wiedergabe von Anzeigen.

Der Vorteil dieser Einrichtung besteht darin, dass der mobile WLAN-Router flexibel an einem Ort platziert werden kann, an dem eine optimale Netzabdeckung gewährleistet ist. In der Regel ist dies an einer erhöhten und offenen Position, mit so wenig Beton- oder Metallkonstruktionen wie möglich.
Diese Einrichtung bietet Anwendern von AEM-Bildschirmen Flexibilität, da für die Anbindung an AEM Screens kein Festnetz benötigt wird. Dies ist interessant für kurzlebige oder mobile Setups.

Das folgende Diagramm zeigt die Konfiguration des mobilen Netzwerks mit mobilem WLAN-Router und aktiven Netzwerkkomponenten. Es enthält einen Internetzugang für jeden der AEM Screens-Controller über einen direkten Internetzugang über eine eigene 3/4/5G-Datenverbindung.

![](/help/using/assets/mobile-network-1.png)

## Verbinden des AEM Screens-Players mit dem mobilen Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#connecting-aem-screens-players}

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

Die Konfiguration weist jedem AEM Screens-Controller einen Internet-Zugang über eine eigene 3G-, 4G- oder 5G-Datenverbindung zu.

1. Stellen Sie sicher, dass der mobile WLAN-Router entsprechend den Angaben im Betriebssystem ordnungsgemäß mit dem Mobilfunknetz verbunden ist und alle AEM Screens-Player an das Router-Netzwerk angebunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL im Browser Ihres Systems aufrufen.

   >[!NOTE]
   >Wenn ein Fehler auftritt, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich gibt es zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration

1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit der des Routers übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide Area Network (Internet Link) des Internet Service Providers verbunden ist. Auf Standard-Routern signalisiert dies in der Regel auch eine LED.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens nicht ordnungsgemäß eine Verbindung herstellt und der erwartete Inhalt nicht angezeigt wird, prüfen Sie in der Firewall des Internet-Routers, ob Einschränkungen für `TCP/IP Port 80/443` bestehen.


## Einrichten eines mobilen Netzwerks mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der bereits beschriebenen Erreichbarkeit des Netzwerks auch reibungslose Downloads von AEM Screens-Inhalten gewährleistet werden können.

*Ausreichend* hängt von der Anzahl der an AEM Screens angebundenen Geräte sowie vom Bandbreitenbedarf anderer verbundener Netzwerknutzer wie Smartphones, Tablets, Kassensystemen, Computern oder Gast-WLANs ab.
Beachten Sie, dass alle Geräte gleichzeitig auf die Internet-Verbindung zugreifen und dass die Bandbreite linear abnimmt und gleichzeitig mehr Verbraucher/Computer zum Netzwerk hinzugefügt werden.
Neben der theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Abdeckung des mobilen Routers mindestens &quot;gut&quot; ist. Ferner muss das im Rahmen des zugrunde liegenden Abonnements gebuchte monatliche Datenvolumen eine für alle an das Netzwerk angebundenen Clients ausreichende Kapazität und Bandbreite zur Verfügung stellen.

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
>Für den erstmaligen Upload der Mediendateien, z. B. bei der Integration neuer Player, muss ein höheres Datenvolumen und eine längere Download-Zeit einkalkuliert und in den oben ausgeführten Schätzungen berücksichtigt werden. Ein 4G-Netz mit *guter* Abdeckung und unbegrenztem Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.


### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der bereits beschriebenen Erreichbarkeit des Netzwerks auch reibungslose Downloads von AEM Screens-Inhalten gewährleistet werden können. Derzeit entspricht das LAN-Netzwerk in der Regel mindestens einem 100-MBit/s-Netzwerk, sodass ausreichend Bandbreite zur Verfügung stehen sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Bei der Verwendung anderer aktiver Netzwerkkomponenten müssen diese alle den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten entsprechende Netzwerkkomponenten mindestens auf den 100 MBit/s-Standard ausgelegt sein und mit den Bandbreitenspezifikationen des Internet-Zugangs/-Routers übereinstimmen.

Sofern eine WLAN-Lösung für die Internet-Anbindung des Bildschirms vorgesehen ist, sollten moderne WLAN-Standards wie IEEE verwendet werden. `802.11g` mindestens. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`. Wenn ein WLAN-Repeater erforderlich ist, empfiehlt Adobe Mesh Wi-Fi Access Point-Technologien wie Google Nest Wifi oder Ähnliches.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen erheblichen Vorteil. dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerk-Traffic, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden sollen.
Bei normalem Betrieb, z. B. wenn eine Wiedergabeliste definiert ist, die während des Tages nicht häufig aktualisiert wird, bietet dies nahezu netzwerkunabhängigen Betrieb, wenn alle Dateien auf dem Player gespeichert werden.
Für Anwendungsfälle, in denen es mehr Interaktionen mit Sensoren oder anderen Triggern gibt und Inhalte dynamisch sind, ist eine schnelle und zuverlässige Netzwerkverbindung unerlässlich, um eine sofortige Bildschirmreaktion zu ermöglichen und so ein bestmögliches Kundenerlebnis zu gewährleisten.
Nachfolgend finden Sie eine Aufschlüsselung der wichtigsten Daten zur Netzwerkverbindung und wie sich diese auf die zu erwartende Leistung und potenzielle Wartezeiten auswirken.

>[!NOTE]
>
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Jede dieser Anforderungen addiert die Download-Zeit und verlängert sie.

![](/help/using/assets/mobile-router-download.png)
