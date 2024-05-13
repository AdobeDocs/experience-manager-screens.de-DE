---
title: Netzwerk für die Direktanbindung an Mobilfunknetze
description: Erfahren Sie mehr über die Einrichtung eines Netzwerks für die Direktanbindung an ein Mobilfunknetz in AEM Screens.
exl-id: 6775bd10-7625-422f-a7af-4f7b8793fa42
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 67%

---

# Netzwerk für die Direktanbindung an Mobilfunknetze {#mobile-network-setup}

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Download-Zeiten sowie auf Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung bei der regelmäßigen Wiedergabe auf Anzeigen.

Der Vorteil der Anbindung von AEM Screens-Playern über die 3G-, 4G- und 5G-Mobilgeräte an Ihren Mobilfunknetzanbieter besteht darin, dass der mobile WLAN-Router flexibel an einem Ort platziert werden kann, an dem er sich befindet. Dadurch wird die bestmögliche Netzabdeckung gewährleistet. Diese Lage ist in der Regel in einer erhöhten und offenen Position mit so wenigen umliegenden Beton- oder Metallstrukturen wie möglich.

Diese Konfiguration ermöglicht AEM Anwendern von Bildschirmen eine große Flexibilität, da für die Anbindung an AEM Screens keine Festnetzleitungen benötigt werden. Diese Anordnung ist für kurzlebige oder mobile Setups interessant.

Das folgende Diagramm zeigt die Einrichtung des direkten mobilen Netzwerks. Es besteht aus einem einzigen Segment für die Netzwerkverbindung und der Verbindung jedes Players zum mobilen oder zellulären Datennetzwerk.

![](/help/using/assets/direct-mobile-1.png)

## Verbinden von AEM Screens-Playern mit einem Netzwerk für die Direktanbindung an ein Mobilfunknetz

Gehen Sie wie folgt vor, um eine ordnungsgemäße Anbindung der AEM Screens-Player in dieser Konfiguration sicherzustellen:

1. Stellen Sie sicher, dass alle AEM Screens-Player mit dem Netzwerk des Routers verbunden sind.

1. Testen Sie die Internetverbindung, indem Sie in Ihrem Systembrowser eine URL aufrufen.

   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen und kontrollieren Sie, ob eine ausreichende Netzwerkverbindung vorhanden ist. Überprüfen Sie außerdem, ob die Firewall des Betriebssystems so konfiguriert ist, dass bei Verwendung der konfigurierten AEM Screens-Kommunikations-Port ein Netzwerkzugriff zugelassen wird.

1. Wenn der URL-Aufruf erfolgreich ist, können Sie mit der Installation von AEM Screens fortfahren und sich registrieren. und AEM Screens starten.

## Einrichten eines Netzwerks für die Direktanbindung an ein Mobilfunknetz {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Internet-Verbindung stellt ausreichend Bandbreite zur Verfügung, um neben der Erreichbarkeit des Netzwerks auch einen reibungslosen Betrieb von AEM Screens zu gewährleisten.

In einem Netzwerk für die Direktanbindung an ein Mobilfunknetz werden die einzelnen Player jeweils über eine eigene Karte für mobile Daten mit dem Datennetz des jeweiligen Anbieters verbunden.

Nachfolgend sind die Datennetze einschließlich der ihnen zugehörigen Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 MBit/s |
| 4G | 150 MBit/s |
| 5G | 1.000–10.000 MBit/s |

Beachten Sie Folgendes bei der Entscheidung, welches Datennetz verwendet werden soll:

Die Geschwindigkeit des Netzwerks hängt vom jeweils mit dem Mobilnetzanbieter abgeschlossenen Abonnement und der Qualität der Netzabdeckung am Standort des AEM Screens-Controllers ab.
Bei diesem Setup ist neben der entsprechend dem jeweiligen Daten-Abo verfügbaren Bandbreite auch zu beachten, dass einige Mobilnetzanbieter im Rahmen ihrer Abonnements auch das innerhalb eines bestimmten Zeitraums über das Netzwerk übertragbare Datenvolumen begrenzen. Es muss sichergestellt werden, dass die Daten- und Bandbreitenmengen genügend Kapazität aufweisen.
Die vom Daten-Abo abzudeckende Mindestkapazität beträgt:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>Für den erstmaligen Upload von Mediendateien bei der Integration neuer Player müssen ein höheres Datenvolumen und eine längere Download-Zeit erwartet werden; dies spiegelt sich in den oben stehenden Annahmen wider. Ein 4G-Netz mit *guter* Abdeckung und *unbegrenztem* Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.

>[!NOTE]
>Ein 3G-Mindestplan mit guter Netzabdeckung sollte zu einer akzeptablen Download-Performance für einen AEM Screens-Player führen. Bei nur mäßiger Abdeckung an einem bestimmten Standort sollte ggf. das gesamte Netzwerk-Setup auf ein [mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten](/help/using/mobile-network-router.md) umgestellt werden.


### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch ein reibungsloser Betrieb von AEM Screens gewährleistet werden kann. Für die LAN-Netzwerkgeschwindigkeit werden mindestens 100 MBit/s empfohlen, sodass genügend Bandbreite verfügbar ist, um viele Geräte bei stabiler System-Performance zu verbinden.

Sind aktive Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen. Beispielsweise sollten die Netzwerkkomponenten mindestens mit dem 100 MBit/s-Standard übereinstimmen und mit der Bandbreite übereinstimmen, die von der Internet-Zugangs- oder WLAN-Spezifikation bereitgestellt wird. Andernfalls wird die Gesamtbandbreite durch das schwächste Glied in der Netzwerkkette begrenzt.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Digital-Signage-Anwendenden einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

So kann der Normalbetrieb, wenn sich z. B. eine definierte Wiedergabeliste häufig während des Tages aktualisiert, nahezu unabhängig vom Netzwerk ablaufen, nachdem alle Dateien auf dem Player gespeichert wurden.

In Szenarien, in denen es mehr Interaktionen mit Sensoren oder Triggern und dynamischen Inhalten gibt, ist eine schnelle und zuverlässige Netzwerkverbindung unerlässlich, um eine sofortige Reaktion auf den Bildschirm zu ermöglichen und so ein bestmögliches Kundenerlebnis zu gewährleisten.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>
>Alle Informationen beziehen sich auf die Nutzung der einzelnen Geräte im Netzwerk, die eine Internet-Quelle anfordern und herunterladen. Mit jeder weiteren solchen Anfrage summiert sich die Bandbreitennutzung, durch die sich wiederum die Download-Zeit verlängert.

![](/help/using/assets/download-times-mobile.png)
