---
title: Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten
description: Auf der Seite werden Mobile Network mit Mobile Data Router und Active Network Components beschrieben.
translation-type: tm+mt
source-git-commit: ec8af4e49694937a79ccbd78d51569f1031ca251
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 8%

---


# Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten {#mobile-network-setup}

Adobe AEM Screens Player kann auch über mobile oder mobile Netzwerke, die mindestens ein 3G-Netzwerk laufen, angeschlossen werden.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Downloadzeiten sowie auf Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung der regelmäßigen Wiedergabe von Displays.

Der Vorteil dieses Setups besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. Das ist in der Regel in einer erhöhten und offenen Position mit so wenig umliegenden Beton- oder Metallkonstruktionen wie möglich.
Dieses Setup ermöglicht AEM-Bildschirmbenutzern Flexibilität, da keine Festnetzverbindung für die Verbindung mit AEM Screens erforderlich ist. Dies ist besonders interessant für kurzlebige oder mobile Setups.

Das folgende Diagramm zeigt die Konfiguration von Mobile Network mit Mobile Data Router und Active Network Components und enthält einen Internetzugriff für jeden AEM Screens Controller über einen eigenen 3/4/5G-Datenlink.

![](/help/using/assets/mobile-network-1.png)

## AEM Screens Player mit Mobile Data Router und Active Network Components verbinden {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine ordnungsgemäße Verbindung der AEM-Bildschirmplayer in dieser Konfiguration sicherzustellen:

Die Konfiguration weist jedem AEM Screens-Controller einen Internetzugang über einen eigenen 3/4/5G-Datenlink zu.

1. Vergewissern Sie sich, dass der Mobile Data Router ordnungsgemäß mit dem zellulären Datennetzwerk verbunden ist, wie im Betriebssystem angegeben, und jeder AEM-Screen-Player mit dem Router-Netzwerk verbunden ist.
1. Testen Sie die Internetverbindung, indem Sie im Systembrowser eine URL aufrufen.
   >[!NOTE]
   >Wenn Sie einen Fehler erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit der Router-Einstellung übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies kann auch mithilfe einer Signal-LED auf Standard Routern festgestellt werden.
1. Falls der URL-Aufruf erfolgreich ist, können Sie die Installation der AEM Screens fortsetzen und sich registrieren. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und der erwartete Inhalt nicht angezeigt wird:
   >
   >1. Check in your Internet Router firewall if there are any restrictions regarding `TCP/IP Port 80/443`.



## Einrichten eines mobilen Netzwerks mit dem MobildatenRouter und aktiven Netzwerkkomponenten {#requirements-direct}

Das Netzwerk-Setup kann logisch in zwei Blöcke getrennt werden:

* Mobile Internetverbindung

* Local Area Network

### Mobile Internetverbindung {#mobile-internet-connection}

Die Leistung der Internetverbindung muss neben der bereits beschriebenen Netzwerkerreichbarkeit ausreichend Bandbreite bereitstellen, um AEM Screens-Content-Downloads reibungslos durchführen zu können.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirmgeräte und von der Nutzung anderer Verbraucher im Netzwerk ab, z. B. Smartphones, Tablets, Kassierer, Computer oder WLAN-Gastnetzwerke.
Denken Sie daran, dass alle Geräte einen gleichzeitigen Zugriff auf die Internetverbindung haben und dass die Bandbreite in der Regel linear sinkt, während dem Netzwerk mehr Benutzer/Computer hinzugefügt werden.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Reichweite des MobilRouters mindestens &quot;gut&quot; ist. Auch der zugrunde liegende Monatsplan muss genügend Datenkapazität und genügend Bandbreite für alle angeschlossenen Clients im angeschlossenen LAN abdecken.

In der folgenden Tabelle sind die Datennetzwerke mit ihrer Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 Mbit/s |
| 4G | 150 Mbit/s |
| 5G | 1000 - 10000 Mbit/s |

Es wird empfohlen, die folgenden Fragen zu beantworten, während geprüft wird, welches Datennetzwerk verwendet werden sollte:

* Wie viele Clients sind mit dem Router verbunden?

* Wie viele Inhaltsänderungen werden erwartet und wie hoch sind diese durchschnittlichen Dateigrößen?

>[!NOTE]
>Die erforderliche Datenpackage muss mindestens sein:
`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>Beim ersten Hochladen von Mediendateien, bei dem neue Player integriert werden, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten, die sich in den obigen Annahmen widerspiegeln. Ein 4G-Netzwerk mit *guter* Abdeckung und unbegrenzten Daten sollte mit den gebräuchlichsten Installationen in dieser Netzwerkeinrichtung übereinstimmen.


### Local Area Network {#lan-connection}

Die Leistung des LAN muss neben der bereits beschriebenen Netzwerkerreichbarkeit ausreichend Bandbreite bereitstellen, um AEM Screens-Downloads reibungslos zu bedienen. In diesen Tagen ist das LAN-Netzwerk in der Regel mindestens 100 Mbit/s Netzwerk, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Bei Verwendung anderer aktiver Netzwerkkomponenten müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.

Falls eine Wi-Fi-Lösung vorgesehen ist, um den Bildschirm mit dem Internet-Link zu verbinden, wird empfohlen, moderne Wi-Fi-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa 802.11h-n. Wenn ein Wi-Fi-Repeater erforderlich ist, empfehlen wir dringend Mesh Wi-Fi Access-Point Technologien wie Google Nest Mesh Wi-Fi oder Ähnliches.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Durch dieses Konzept ist der Großteil des Netzwerk-Traffics auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.
Bei normalem Betrieb, z.B. wenn Sie eine Playlist definiert haben, die nicht regelmäßig aktualisiert wird, wird hier ein netzwerkunabhängiger Vorgang Angebot, sobald alle Dateien auf dem Player gespeichert wurden.
Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.
Die folgenden Tabellen bieten einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und für potenzielle Wartezeiten erforderlich sind.

>[!NOTE]
>Alle Informationen beziehen sich auf den Verbrauch jedes Geräts im Netzwerk, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/mobile-router-download.png)



