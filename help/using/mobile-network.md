---
title: Netzwerk für Direktanbindung an Mobilfunknetze
description: Erfahren Sie mehr über die Einrichtung direkter mobiler Netzwerke in AEM Screens.
exl-id: 6775bd10-7625-422f-a7af-4f7b8793fa42
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 55%

---

# Netzwerk für Direktanbindung an Mobilfunknetze {#mobile-network-setup}

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Daher wirkt sich die angegebene Bandbreite nur auf die anfänglichen Download-Zeiten und Inhaltsaktualisierungen aus und hat keinen Einfluss auf die Leistung der regulären Wiedergabe von Displays.

Der Vorteil der Anbindung von AEM Screens-Playern über Mobilfunk 3/4/5G an Ihren Mobilfunkanbieter besteht darin, dass der mobile Router an einem optimierten Ort platziert werden kann, um eine optimale Netzabdeckung zu gewährleisten. Diese befindet sich in der Regel in einer erhöhten und offenen Position mit möglichst wenig umgebenden Beton- oder Metallstrukturen.

Diese Konfiguration bietet Anwendern von AEM Screens besonders große Flexibilität, da für die Anbindung an AEM Screens keine Festnetzleitungen benötigt werden. Dies ist für temporäre oder mobile Setups interessant.

Die Konfiguration für die Direktanbindung an Mobilfunknetze umfasst ein einzelnes Segment für die Netzwerkverbindung sowie die Verbindung der einzelnen Player mit dem Mobilfunknetz, wie im nachfolgenden Diagramm dargestellt.

![](/help/using/assets/direct-mobile-1.png)

## Verbinden des AEM Screens-Players mit einem direkten Mobilnetzwerk

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

1. Stellen Sie sicher, dass alle AEM Screens-Player mit dem Netzwerk des Routers verbunden sind.

1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen und überprüfen Sie, ob eine ausreichende Netzwerkverbindung vorhanden ist. Überprüfen Sie außerdem, ob die Betriebssystem-Firewall so konfiguriert ist, dass sie Netzwerkzugriff zulässt, während Sie die konfigurierten AEM Screens-Kommunikations-Ports verwenden.

1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

## Einrichten eines direkten mobilen Netzwerks {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Internet-Verbindung stellt ausreichend Bandbreite zur Verfügung, um neben der Erreichbarkeit des Netzwerks auch einen reibungslosen Betrieb von AEM Screens zu gewährleisten.

Im Direct Mobile Network ist jeder Player über eine einzelne Mobile Data Card mit dem Datennetzwerk des Anbieters verbunden.

In der folgenden Tabelle sind die Datennetzwerke mit ihrer Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 MBit/s |
| 4G | 150 MBit/s |
| 5G | 1.000–10.000 MBit/s |

Berücksichtigen Sie bei der Entscheidung, welches Datennetzwerk verwendet werden sollte, Folgendes:

Die Geschwindigkeit des Netzwerks hängt vom jeweils mit dem Mobilnetzanbieter abgeschlossenen Abonnement und der Qualität der Netzabdeckung am Standort des AEM Screens-Controllers ab.
Beachten Sie bei dieser Einrichtung, dass neben der verfügbaren Bandbreite einige Pläne für mobile Datenanbieter die verfügbare Datenmenge, die über die Verbindung innerhalb eines bestimmten Zeitraums übertragen wird, einschränken. Es muss sichergestellt werden, dass ausreichend Kapazität in den Daten- und Bandbreitenmengen vorhanden ist.
Als Folgemaßnahme muss das erforderliche Datenpaket mindestens Folgendes umfassen:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>Für den erstmaligen Upload der Mediendateien, z. B. bei der Integration neuer Player, muss ein höheres Datenvolumen und eine längere Download-Zeit einkalkuliert und in den oben ausgeführten Schätzungen berücksichtigt werden. Ein 4G-Netz mit *guter* Abdeckung und *unbegrenztem* Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.

>[!NOTE]
>Ein Abonnement mit Datenübertragung mindestens nach 3G-Standard und guter Netzabdeckung sollte für einen AEM Screens-Player eine akzeptable Download-Leistung liefern. Wenn an einem bestimmten Standort nur eine angemessene Abdeckung verfügbar ist, sollten Sie die Netzwerkeinrichtung insgesamt auf umstellen. [Mobiles Netzwerk mit mobilem Datenrouter und aktiven Netzwerkkomponenten](/help/using/mobile-network-router.md).


### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der Erreichbarkeit des Netzwerks auch ein reibungsloser Betrieb von AEM Screens gewährleistet werden kann. Es wird empfohlen, mindestens bei 100-Mbit/s-Netzwerken zu beginnen, damit ausreichend Bandbreite vorhanden ist, um viele Geräte mit guter Leistung an das System anzuschließen.

Sind aktive Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen. Beispielsweise sollten entsprechende Netzwerkkomponenten mindestens auf den 100 MBit/s-Standard ausgelegt sein und mit den Bandbreitenspezifikationen des Internet-Zugangs bzw. -Routers übereinstimmen. Andernfalls wird die Gesamtbandbreite durch das schwächste Glied in der Netzwerkkette begrenzt.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Benutzenden von Digital Signage einen erheblichen Vorteil. dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

Für den Normalbetrieb bietet beispielsweise eine definierte Wiedergabeliste, die tagsüber häufig aktualisiert wird - einen nahezu netzwerkunabhängigen Betrieb, nachdem alle Dateien auf dem Player gespeichert wurden.

Szenarien, in denen umfangreicher mit Sensoren oder Auslösern sowie dynamischen Inhalten interagiert wird, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Jede dieser Anfragen addiert sich und verlängert die Download-Zeit.

![](/help/using/assets/download-times-mobile.png)
