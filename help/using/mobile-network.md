---
title: Netzwerk für Direktanbindung an Mobilfunknetze
description: Auf dieser Seite wird die Konfiguration von Netzwerken für die Direktanbindung an Mobilfunknetze beschrieben.
translation-type: tm+mt
source-git-commit: 23bb59c719c675baa84c579f624adccc80377661
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 74%

---


# Netzwerk für Direktanbindung an Mobilfunknetze{#mobile-network-setup}

AEM Screens Player können auch über mobile oder zelluläre Netzwerke verbunden werden, die mindestens ein 3G-Netzwerk laufen.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Downloadzeiten sowie auf Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung der regelmäßigen Wiedergabe von Displays.

Der Vorteil der Verbindung von AEM Screens mit dem Mobilnetzbetreiber über Cellular 3/4/5G besteht darin, dass der Mobilnetzler an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. In der Regel ist dies an höher gelegenen, offenen Stellen der Fall, die so wenig wie möglich von Beton- oder Metallkonstruktionen umgeben sind.

Diese Einrichtung ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da keine Festnetzverbindung erforderlich ist, um eine Verbindung zu AEM Screens herzustellen. Dies ist besonders interessant für kurzlebige oder mobile Setups.

Die Konfiguration für die Direktanbindung an Mobilfunknetze umfasst ein einzelnes Segment für die Netzwerkverbindung sowie die Verbindung der einzelnen Player mit dem Mobilfunknetz, wie im nachfolgenden Diagramm dargestellt.

![](/help/using/assets/direct-mobile-1.png)

## Verbinden von AEM Screens-Playern mit dem Netzwerk für die Direktanbindung an ein Mobilfunknetz{#connecting-aem-screens-players}

Gehen Sie für eine in dieser Konfiguration ordnungsgemäße Anbindung der AEM Screens-Player wie folgt vor:

1. Stellen Sie sicher, dass alle AEM Screens-Player mit dem Netzwerk des Routers verbunden sind.

1. Testen Sie die Internet-Verbindung, indem Sie in Ihrem System-Browser eine URL aufrufen.

   >[!NOTE]
   >Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie die Netzwerkeinstellungen und vergewissern sich, dass ausreichend Netzabdeckung vorhanden ist und in der Betriebssystem-Firewall der Netzwerkzugriff der für die Kommunikation mit AEM Screens konfigurierten Ports zugelassen wird.

1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen und AEM Screens starten.

## Einrichten des Netzwerks für die Direktanbindung an ein Mobilfunknetz {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Internet-Verbindung stellt ausreichend Bandbreite zur Verfügung, um neben der Erreichbarkeit des Netzwerks auch einen reibungslosen Betrieb von AEM Screens zu gewährleisten.

Bei der Direktanbindung an Mobilfunknetze werden die einzelnen Player jeweils über eine eigene Karte für Mobildaten mit dem Datennetzwerk des jeweiligen Anbieters verbunden.

Nachfolgend sind die Datennetzwerke einschließlich der ihnen zugehörigen Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 MBit/s |
| 4G | 150 MBit/s |
| 5G | 1.000–10.000 MBit/s |

Bei der Wahl des Datennetzwerks empfiehlt es sich, die folgenden Fragen abzuwägen:

Die Geschwindigkeit des Netzwerks hängt vom jeweils mit dem Mobilnetzanbieter abgeschlossenen Abonnement und der Qualität der Netzabdeckung am Standort des AEM Screens-Controllers ab.
Bei dieser Konfiguration ist neben der entsprechend dem jeweiligen Daten-Abo verfügbaren Bandbreite auch zu beachten, dass einige Mobilnetzanbieter im Rahmen ihrer Abonnements auch das innerhalb eines bestimmten Zeitraums über das Netzwerk übertragbare Datenvolumen begrenzen. Daher muss sichergestellt werden, dass sowohl im Hinblick auf das Datenvolumen als auch auf die Bandbreite ausreichend Kapazitäten zur Verfügung stehen.
Die mindestens vom Daten-Abo abzudeckende Kapazität beträgt:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>
>Beim ersten Hochladen von Mediendateien, z. B. bei der Integration neuer Player, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten, die sich in den obigen Annahmen widerspiegeln. A 4G network with *good* coverage and *unlimited* data should match the most common installations in this Network Setup.

>[!NOTE]
>
>Ein Abonnement mit Datenübertragung mindestens nach 3G-Standard und guter Netzabdeckung sollte für einen AEM Screens-Player eine akzeptable Download-Leistung liefern. Bei nur mäßiger Abdeckung an einem bestimmten Standort sollte in Betracht gezogen werden, die gesamte Netzwerkkonfiguration auf ein [mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten ](/help/using/mobile-network-router.md) umzustellen.


### LAN (Local Area Network) {#lan-connection}

Die Leistungsanforderungen des Local Area Network (LAN) bestehen neben der Netzwerkanbindung darin, ausreichend Bandbreite für einen reibungslosen Betrieb von AEM Screens bereitzustellen. Für die LAN-Netzwerkgeschwindigkeiten wird empfohlen, mit mindestens 100 Mbit/s Netzwerken Beginn, sodass genügend Bandbreite vorhanden ist, um viele Geräte mit guter Systemleistung zu verbinden.

Sind aktive Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen. Beispielsweise sollten entsprechende Netzwerkkomponenten mindestens auf den 100 MBit/s-Standard ausgelegt sein und mit den Bandbreitenspezifikationen des Internet-Zugangs bzw. -Routers übereinstimmen. Andernfalls wird die Gesamtbandbreite durch das schwächste Glied in der Netzwerkkette begrenzt.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Der Großteil des Netzwerk-Traffics ist dadurch auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.

So kann der Normalbetrieb, also beispielsweise Fälle, in denen bei einer Wiedergabeliste für den Tagesverlauf häufige Updates definiert sind, nahezu unabhängig vom Netzwerk ablaufen, sobald alle Dateien auf dem Player gespeichert wurden.

Szenarien, in denen umfangreicher mit Sensoren oder Auslösern sowie dynamischen Inhalten interagiert wird, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Mit jeder weiteren solchen Anfrage summiert sich die Bandbreitennutzung, durch die sich wiederum die Download-Zeit verlängert.

![](/help/using/assets/download-times-mobile.png)



