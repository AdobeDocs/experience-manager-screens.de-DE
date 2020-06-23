---
title: Direktes Mobilfunknetz
description: Auf der Seite wird die Einrichtung des Direct Mobile-Netzwerks beschrieben.
translation-type: tm+mt
source-git-commit: 70dddffd46ebf1bd83b25515be548bc442e45fea
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 16%

---


# Direktes Mobilfunknetz {#mobile-network-setup}

AEM Screens Player können auch über mobile oder zelluläre Netzwerke verbunden werden, die mindestens ein 3G-Netzwerk laufen.

Innerhalb der AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Dadurch wirkt sich die angegebene Bandbreite nur auf die anfänglichen Downloadzeiten aus und beeinflusst nicht die Leistung von Displays.

Anschluss von AEM Screens-Playern mit einer Mobilfunkverbindung 3/4/5G an Ihren Mobile Service-Datenanbieter. Der Vorteil dieses Setup ist, dass der Mobile Router an einem optimierten Ort platziert werden kann, um die bestmögliche Netzwerkabdeckung sicherzustellen. Dies ist in der Regel in einer erhöhten und offenen Position mit so wenig umliegenden Beton- oder Metallkonstruktionen wie möglich.

Dieses Setup ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da zum Verbinden von AEM Screens keine Festnetzverbindung erforderlich ist.

![](/help/using/assets/direct-mobile-1.png)

## Anschließen von AEM Screens Player an das Direct Mobile-Netzwerk {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine Verbindung mit AEM-Screen-Playern in dieser Konfiguration herzustellen:

1. Vergewissern Sie sich, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.

1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit der Router-Einstellung übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies kann auch mithilfe einer Signal-LED auf Standard Routern festgestellt werden.

1. Falls der URL-Aufruf erfolgreich ist, können Sie die AEM Screens weiter installieren und entsprechend registrieren. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und nicht den erwarteten Inhalt anzeigen:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.



## Voraussetzungen für die Einrichtung des mobilen Netzwerks {#requirements-direct}

Das Netzwerk-Setup kann logisch in zwei Blöcke getrennt werden:

* Mobile Internetverbindung

* Local Area Network

### Mobile Internetverbindung {#mobile-internet-connection}

Die Leistung der Internetverbindung bietet neben der Reichweite des Netzwerks genügend Bandbreite, um AEM Screens angenehm und reibungslos zu bedienen.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.
Beachten Sie, dass alle Geräte gleichzeitig auf die Internet-Verbindung zugreifen und dass die Bandbreite mit der Zahl an weiteren Nutzern/Computern, die dem Netzwerk hinzugefügt werden, in der Regel linear abnimmt.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt werden, dass die Reichweite des mobilen Routers mindestens &quot;gut&quot; ist (siehe Handbuch für den mobilen Router). Auch der zugrunde liegende Monatsplan muss genügend Datenkapazität und genügend Bandbreite für alle angeschlossenen Clients im angeschlossenen LAN abdecken.

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
>Stellen Sie sicher, dass genügend Puffer vorhanden ist.
>Beim ersten Hochladen von Mediendateien, z. B. bei der Integration neuer Player, sind eine höhere Datenmenge und eine höhere Downloadzeit zu erwarten und in den obigen Annahmen widerzuspiegeln.Ein 4G-Netzwerk mit *guter* Abdeckung und *unbegrenzten* Daten sollte mit den gebräuchlichsten Installationen in diesem Netzwerk-Setup übereinstimmen.


### Local Area Network {#lan-connection}

Das LAN muss ausreichend Bandbreite zur Verfügung stellen, damit neben der zuvor erwähnten Erreichbarkeit des Netzwerks auch ein ebenso flüssiger wie reibungsloser Betrieb von AEM Screens gewährleistet werden kann. In diesen Tagen ist das LAN-Netzwerk in der Regel mindestens 100 Mbit/s Netzwerk, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden. Sind Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen. Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Video herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerkverkehr, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Bei normalem Betrieb, z. B. einer definierten Playlist, die nicht sehr oft während des Tages geändert wird, wird ein nahtloser netzwerkunabhängiger Vorgang Angebot, sobald alle Dateien auf dem Player gespeichert wurden.
Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Die folgende Tabelle gibt einen Überblick darüber, welche wichtigen Daten zur Netzwerkkonnektivität für die zu erwartende Leistung und für potenzielle Wartezeiten erforderlich sind.
>[!NOTE]
>Alle Informationen beziehen sich auf den Verbrauch jedes Geräts im Netzwerk, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/download-times-mobile.png)



