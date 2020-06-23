---
title: Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten
description: Auf der Seite werden Mobile Network mit Mobile Data Router und Active Network Components beschrieben.
translation-type: tm+mt
source-git-commit: 70dddffd46ebf1bd83b25515be548bc442e45fea
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 25%

---


# Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten {#mobile-network-setup}

Adobe AEM Screens Player kann auch über mobile oder mobile Netzwerke, die mindestens ein 3G-Netzwerk laufen, angeschlossen werden.
Innerhalb der AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Downloadzeiten aus und beeinflusst die Leistung der Display-Systeme überhaupt nicht.

Der Vorteil dieses Setups besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. Dies ist in der Regel in einer erhöhten und offenen Position mit so wenig umliegenden Beton- oder Metallkonstruktionen wie möglich.
Dieses Setup ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da keine Festnetzverbindung zum Verbinden von AEM Screens erforderlich ist.

![](/help/using/assets/mobile-network-1.png)

## AEM Screens Player mit Mobile Data Router und Active Network Components verbinden {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine Verbindung mit AEM-Screen-Playern in dieser Konfiguration herzustellen:

Die Konfiguration beinhaltet einen Internetzugang eines AEM Screens Controllers über einen eigenen 3/4/5G Datenlink.
Die ordnungsgemäße Verbindung der AEM-Screen-Player in dieser Konfiguration ist einfach:

1. Vergewissern Sie sich, dass der Mobile Data Router ordnungsgemäß mit dem zellulären Datennetzwerk verbunden ist, wie im Betriebssystem angegeben, und jeder AEM-Screen-Player mit dem Router-Netzwerk verbunden ist.
1. Testen Sie die Internetverbindung, indem Sie im Systembrowser eine URL aufrufen.
   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit der Router-Einstellung übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies kann auch mithilfe einer Signal-LED auf Standard Routern festgestellt werden.
1. Falls der URL-Aufruf erfolgreich war, können Sie die AEM Screens weiter installieren und entsprechend registrieren. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und nicht den erwarteten Inhalt anzeigen:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.



## Voraussetzungen für die Einrichtung eines mobilen Netzwerks mit dem MobildatenRouter und aktiven Netzwerkkomponenten {#requirements-direct}

Das Netzwerk-Setup kann logisch in zwei Blöcke getrennt werden:

* Mobile Internetverbindung

* Local Area Network

### Mobile Internetverbindung {#mobile-internet-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der zuvor erwähnten Erreichbarkeit des Netzwerks auch ein ebenso flüssiger wie reibungsloser Betrieb von AEM Screens gewährleistet werden kann.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.
Beachten Sie, dass alle Geräte gleichzeitig auf die Internet-Verbindung zugreifen und dass die Bandbreite mit der Zahl an weiteren Nutzern/Computern, die dem Netzwerk hinzugefügt werden, in der Regel linear abnimmt.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Abdeckung des MobilRouters zumindest &quot;gut&quot; ist. Auch der zugrunde liegende Monatsplan muss genügend Datenkapazität und genügend Bandbreite für alle angeschlossenen Clients im angeschlossenen LAN abdecken.
Die Datennetze bieten Standardbandbreite mit:

**3G**
* 42 Mbit/s

**4G**
* 150 Mbit/s

**5G**
* 1000 Mbit/s - 10000 Mbit/s

Es wird empfohlen, die folgenden Fragen zu beantworten, während geprüft wird, welches Datennetzwerk verwendet werden sollte:

* Wie viele Clients sind mit dem Router verbunden?

* Wie viele Inhaltsänderungen werden erwartet und wie hoch sind diese durchschnittlichen Dateigrößen?

>[!NOTE]
>Die erforderliche Datenpackage muss mindestens sein:
`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>Beim ersten Hochladen von Mediendateien, bei dem neue Player integriert werden, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten, die sich in den obigen Annahmen widerspiegeln. Ein 4G-Netzwerk mit *guter* Abdeckung und unbegrenzten Daten sollte mit den gebräuchlichsten Installationen in dieser Netzwerkeinrichtung übereinstimmen.


### Local Area Network {#lan-connection}

Das LAN muss ausreichend Bandbreite zur Verfügung stellen, damit neben der zuvor erwähnten Erreichbarkeit des Netzwerks auch ein ebenso flüssiger wie reibungsloser Betrieb von AEM Screens gewährleistet werden kann. In diesen Tagen ist das LAN-Netzwerk in der Regel mindestens 100 Mbit/s Netzwerk, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Sind Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen.

Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.
Falls eine WIFI-Lösung zur Verbindung des Bildschirms mit dem Internet-Link vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa 802.11h-n. Ist ein WLAN-Repeater erforderlich, wird für die Zugangspunkte dringend der Einsatz von Mesh-WLAN-Technologie empfohlen, z. B. Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Durch dieses Konzept ist der Großteil des Netzwerk-Traffics auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.
So kann der Normalbetrieb, also beispielsweise Fälle, in denen bei einer Wiedergabeliste für den Tagesverlauf nur wenige Änderungen definiert sind, nahezu unabhängig vom Netzwerk ablaufen, sobald alle Dateien auf dem Player gespeichert wurden.
Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.
Die folgenden Tabellen bieten einen guten Überblick darüber, welche wichtigen Daten zur Netzwerkverbindung für die zu erwartende Leistung und für potenzielle Wartezeiten erforderlich sind.

>[!NOTE]
>Alle Informationen beziehen sich auf den Verbrauch jedes Geräts im Netzwerk, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/mobile-router-download.png)



