---
title: Direkter Internet-Zugriff
description: Direkter Internet-Zugriff
translation-type: tm+mt
source-git-commit: 70dddffd46ebf1bd83b25515be548bc442e45fea
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 30%

---


# Direkter Internet-Zugriff {#direct-internet-access}

Das Direct Internet Access SetUp enthält einen Einstiegspunkt für den Internetzugang, um die AEM cloud services zu erreichen, zu denen AEM Screens eine Verbindung herstellen müssen.

AEM Screens verwendet für die Kommunikation standardmäßig die folgenden Ports:
* `http (TCP Port 80)`
oder
* `ssl-secured https (TCP Port 443)`

Die Anschlüsse können je nach Konfiguration der dedizierten AEM-Konfiguration variieren. In dieser Konfiguration sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der nachfolgenden Abbildung dargestellt.

![](/help/assets/direct-access-2.png)

Die Konfiguration beinhaltet auch einen Internetzugang von jedem Internet-Dienstleister (ISP) und seine Internetverbindung. Die meisten ISPs bieten einen Internet-Router, der das Internet-Modem, den Netzwerk-Switch, den WIFI-Access-Point, die Firewall und andere Netzwerkfunktionen (je nach Hersteller und Modell) abdeckt.

## Anschließen des AEM Screens Player an den direkten Internetzugang {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine Verbindung mit AEM-Screen-Playern in dieser Konfiguration herzustellen:

1. Vergewissern Sie sich, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit der Router-Einstellung übereinstimmt, und überprüfen Sie, ob die maximale Anzahl an verfügbaren IP-Adressen in Ihrem Netzwerk nicht erreicht wird.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies kann in der Regel auch mit einer Signal-LED auf Standard Routern identifiziert werden.
1. Falls der URL-Aufruf erfolgreich ist, können Sie die AEM Screens weiterhin installieren und entsprechend registrieren. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und nicht den erwarteten Inhalt anzeigen:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.


## Voraussetzungen für die Einrichtung eines Netzwerks für direkten Internet-Zugriff {#requirements-direct}

Die Einrichtung des Direct Access-Netzwerks kann logisch in zwei Blöcke getrennt werden:

* Breites Netzwerk

* Local Area Network

### Breites Netzwerk {#wan-connection}

Die Leistung der Internetverbindung ist neben der Reichweite des Netzwerks auch die Bereitstellung ausreichender Bandbreite für den reibungslosen Betrieb von AEM Screens.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.

>[!NOTE]
>Alle Geräte haben einen gleichzeitigen Zugriff auf die Internetverbindung und die Bandbreite sinkt in der Regel linear, wenn Sie mehr Benutzer/Computer zum Netzwerk hinzufügen.

### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN), neben der Netzwerkerreichbarkeit, bietet ausreichend Bandbreite, um AEM Screens angenehm und reibungslos zu bedienen.

Das LAN-Netzwerk entspricht in der Regel mindestens einem 100 MBit/s Netzwerk, sodass genügend Bandbreite vorhanden ist, um viele Geräte mit guter Leistung mit dem System zu verbinden.
Falls eine WIFI-Lösung zur Anbindung von AEM Screens an den Internetlink vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa 802.11h-n.

>[!NOTE]
>Ist ein WLAN-Repeater erforderlich, wird für die Zugangspunkte dringend der Einsatz von Mesh-WLAN-Technologie empfohlen, z. B. Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen. Andere WLAN-Repeater-Technologien sind mit massiven Bandbreiteneinbußen verbunden.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerkverkehr, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
So kann der Normalbetrieb, also beispielsweise Fälle, in denen bei einer Wiedergabeliste für den Tagesverlauf nur wenige Änderungen definiert sind, nahezu unabhängig vom Netzwerk ablaufen, sobald alle Dateien auf dem Player gespeichert wurden.
Anwendungsfälle, in denen umfangreicher mit Sensoren oder anderen Auslösern interagiert wird und hochgradig dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung, da nur so eine verzögerungsfreie Reaktion am Bildschirm und damit das bestmögliche Kundenerlebnis gewährleistet werden kann.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>Diese Daten zeigen auf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/assets/download-times-direct.png)

