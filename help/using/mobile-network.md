---
title: Netzwerk für Direktanbindung an Mobilfunknetze
description: Erfahren Sie mehr über die Einrichtung eines direkten mobilen Netzwerks in AEM Screens.
exl-id: 6775bd10-7625-422f-a7af-4f7b8793fa42
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 50%

---

# Netzwerk für Direktanbindung an Mobilfunknetze {#mobile-network-setup}

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Daher wirkt sich die verfügbare Bandbreite nur auf die anfänglichen Download-Zeiten und Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung der regelmäßigen Wiedergabe von Anzeigen.

Der Vorteil der Anbindung von AEM Screens-Playern über die 3G-, 4G- und 5G-Mobilgeräte an Ihren Mobilfunknetzanbieter besteht darin, dass der mobile WLAN-Router flexibel an einem Ort platziert werden kann, an dem eine optimale Netzabdeckung gewährleistet ist. In der Regel ist dies an einer erhöhten und offenen Position mit so wenig Beton- oder Metallstrukturen wie möglich.

Diese Konfiguration bietet Anwendern von AEM Screens besonders große Flexibilität, da für die Anbindung an AEM Screens keine Festnetzleitungen benötigt werden. Dies ist interessant für kurzlebige oder mobile Setups.

Die Konfiguration für die Direktanbindung an Mobilfunknetze umfasst ein einzelnes Segment für die Netzwerkverbindung sowie die Verbindung der einzelnen Player mit dem Mobilfunknetz, wie im nachfolgenden Diagramm dargestellt.

![](/help/using/assets/direct-mobile-1.png)

## Verbinden des AEM Screens-Players mit einem direkten mobilen Netzwerk

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

1. Stellen Sie sicher, dass alle AEM Screens-Player mit dem Netzwerk des Routers verbunden sind.

1. Testen Sie die Internetverbindung, indem Sie in Ihrem Systembrowser eine URL aufrufen.

   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen und überprüfen Sie, ob eine ausreichende Netzwerkverbindung vorhanden ist. Überprüfen Sie außerdem, ob die Firewall des Betriebssystems so konfiguriert ist, dass beim Verwenden der konfigurierten AEM Screens-Kommunikationsanschlüsse der Netzwerkzugriff zugelassen wird.

1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

## Einrichten eines Netzwerks für Direktanbindung an Mobilfunknetze {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Internet-Verbindung stellt ausreichend Bandbreite zur Verfügung, um neben der Erreichbarkeit des Netzwerks auch einen reibungslosen Betrieb von AEM Screens zu gewährleisten.

In einem Netzwerk für Direktanbindung an Mobilfunknetze ist jeder Player mit einer einzigen mobilen Datenkarte mit dem Datennetzwerk des Anbieters verbunden.

In der folgenden Tabelle sind die Datennetzwerke mit ihrer Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 MBit/s |
| 4G | 150 MBit/s |
| 5G | 1.000–10.000 MBit/s |

Beachten Sie bei der Erwägung, welches Datennetzwerk verwendet werden soll, Folgendes:

Die Geschwindigkeit des Netzwerks hängt vom jeweils mit dem Mobilnetzanbieter abgeschlossenen Abonnement und der Qualität der Netzabdeckung am Standort des AEM Screens-Controllers ab.
Beachten Sie bei dieser Konfiguration, dass neben der verfügbaren Bandbreite einige Mobilnetzanbieter-Pläne die verfügbare Datenmenge, die über die Verbindung innerhalb einer bestimmten Zeit übertragen wird, begrenzen. Es muss sichergestellt werden, dass die Daten- und Bandbreitenmengen genügend Kapazität aufweisen.
Als Folgemaßnahme muss das erforderliche Datenpaket mindestens Folgendes umfassen:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>Für den erstmaligen Upload der Mediendateien, z. B. bei der Integration neuer Player, muss ein höheres Datenvolumen und eine längere Download-Zeit einkalkuliert und in den oben ausgeführten Schätzungen berücksichtigt werden. Ein 4G-Netz mit *guter* Abdeckung und *unbegrenztem* Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.

>[!NOTE]
>Ein 3G-Mindestplan mit guter Netzabdeckung sollte zu einer akzeptablen Download-Performance für einen AEM Screens-Player führen. Wenn nur eine angemessene Abdeckung an einem bestimmten Ort verfügbar ist, sollten Sie die gesamte Netzwerkkonfiguration auf [Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten](/help/using/mobile-network-router.md).


### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch ein reibungsloser Betrieb von AEM Screens gewährleistet werden kann. Für die LAN-Netzwerkgeschwindigkeit wird empfohlen, mindestens 100 MBit/s mit Netzwerken zu verbinden, damit ausreichend Bandbreite zur Verfügung steht, um viele Geräte mit guter Leistung mit dem System zu verbinden.

Sind aktive Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen. Beispielsweise sollten entsprechende Netzwerkkomponenten mindestens auf den 100 MBit/s-Standard ausgelegt sein und mit den Bandbreitenspezifikationen des Internet-Zugangs bzw. -Routers übereinstimmen. Andernfalls wird die Gesamtbandbreite durch das schwächste Glied in der Netzwerkkette begrenzt.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen erheblichen Vorteil. dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

Bei normalen Vorgängen, z. B. einer definierten Wiedergabeliste, die im Laufe des Tages häufig aktualisiert wird, ist ein nahezu netzwerkunabhängiger Vorgang verfügbar, nachdem alle Dateien auf dem Player gespeichert wurden.

Szenarien, in denen umfangreicher mit Sensoren oder Auslösern sowie dynamischen Inhalten interagiert wird, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>
>Alle Informationen beziehen sich auf die Nutzung der einzelnen Geräte im Netzwerk, die eine Internet-Quelle anfordern und herunterladen. Mit jeder dieser Anforderungen wird die Download-Zeit addiert und verlängert.

![](/help/using/assets/download-times-mobile.png)
