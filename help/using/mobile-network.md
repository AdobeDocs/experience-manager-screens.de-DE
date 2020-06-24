---
title: Direktes Mobilfunknetz
description: Auf der Seite wird die Einrichtung des Direct Mobile-Netzwerks beschrieben.
translation-type: tm+mt
source-git-commit: 8e62b3fc4ce324e02aaec6fca9df79b1aaf94d72
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 8%

---


# Direktes Mobilfunknetz {#mobile-network-setup}

AEM Screens Player können auch über mobile oder zelluläre Netzwerke verbunden werden, die mindestens ein 3G-Netzwerk laufen.

Innerhalb der AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und ordnungsgemäß im zugrunde liegenden Betriebssystem gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Downloadzeiten aus und beeinflusst nicht die Leistung von Displays.

Anschluss von AEM Screens-Playern mit einer Mobilfunkverbindung 3/4/5G an Ihren Mobile Service-Datenanbieter. Der Vorteil dieses Setups besteht darin, dass der Mobile Router an einem optimierten Ort platziert werden kann, um eine bestmögliche Netzabdeckung zu gewährleisten. Dies ist in der Regel in einer erhöhten und offenen Position mit einer möglichst optimalen Umgebung aus Beton oder Metall.

Dieses Setup ermöglicht AEM-Bildschirmbenutzern eine große Flexibilität, da keine Festnetzverbindung erforderlich ist, um eine Verbindung zu AEM Screens herzustellen.

Das folgende Diagramm zeigt die Einrichtung des Direct Mobile-Netzwerks und besteht aus einem einzigen Segment der Netzwerkverbindung, der Verbindung jedes Players mit dem mobilen/zellulären Datennetzwerk.

![](/help/using/assets/direct-mobile-1.png)

## Anschließen von AEM Screens Player an das Direct Mobile-Netzwerk {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um AEM Screens-Player in dieser Konfiguration zu verbinden:

1. Vergewissern Sie sich, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.

1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit der Router-Einstellung übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies kann auch mithilfe einer Signal-LED auf Standard Routern festgestellt werden.

1. Falls der URL-Aufruf erfolgreich ist, können Sie die Installation der AEM Screens fortsetzen und sich registrieren. Beginn-AEM Screens.

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

Die Leistung der Internetverbindung bietet neben der Netzwerkerreichbarkeit genügend Bandbreite, um AEM Screens reibungslos zu bedienen.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.

>[!NOTE]
>Alle Geräte verfügen über einen gleichzeitigen Zugriff auf die Internetverbindung und die Bandbreite verringert sich linear, während gleichzeitig mehr Benutzer oder Computer zum Netzwerk hinzugefügt werden.

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

Die Leistung des Local Area Network (LAN) ist nicht nur die Netzwerkerreichbarkeit, sondern auch die Bereitstellung ausreichender Bandbreite für einen reibungslosen Betrieb von AEM Screens. Das LAN-Netzwerk ist in der Regel mindestens mit einem 100-Mbit/s-Netzwerk kompatibel, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden.

Bei Verwendung anderer aktiver Netzwerkkomponenten müssen alle diese den Anforderungen an die Netzwerkbandbreite entsprechen. Beispielsweise sollten die Netzwerkkomponenten mindestens dem 100-Mbit/s-Standard entsprechen und der Bandbreite entsprechen, die von der Internet Access/Router-Spezifikation bereitgestellt wird.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Daher kommt es zu hohem Netzwerkverkehr, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Bei normalem Betrieb, z. B. einer definierten Playlist, die nicht häufig aktualisiert wird, wird ein netzwerkunabhängiger Vorgang Angebot, sobald alle Dateien im Player gespeichert wurden.
Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Die folgende Tabelle gibt einen Überblick über die wichtigsten Daten zur Netzwerkverbindung, die für die zu erwartende Leistung und potenzielle Wartezeiten verantwortlich sind.

>[!NOTE]
>Alle Informationen beziehen sich auf den Verbrauch jedes Geräts im Netzwerk, das eine Internetquelle anfordert und herunterlädt. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/using/assets/download-times-mobile.png)



