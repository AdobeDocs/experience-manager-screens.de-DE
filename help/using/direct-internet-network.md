---
title: Direkter Internet-Zugriff
description: Direkter Internet-Zugriff
translation-type: tm+mt
source-git-commit: 77cf87cbce39a00528b2690d9689861b91e61fc5
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 15%

---


# Direct Internet Network (Wired/Wireless) {#direct-internet-access}

Das Direct Internet Network enthält einen Einstiegspunkt für den Internetzugang, um AEM cloud services zu erreichen, mit denen AEM Screens eine Verbindung herstellen müssen.

AEM Screens verwendet für die Kommunikation standardmäßig die folgenden Ports:
* `http (TCP Port 80)`
oder
* `ssl-secured https (TCP Port 443)`

Die Anschlüsse können je nach Konfiguration der dedizierten AEM-Konfiguration variieren. In diesem SetUp sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der folgenden Abbildung dargestellt.

![](/help/assets/direct-access-2.png)

Die Konfiguration beinhaltet auch einen Internetzugang von jedem Internet-Dienstleister (ISP) und seine Internetverbindung. Die meisten ISPs bieten einen Internet-Router, der das Internet-Modem, den Netzwerk-Switch, den WIFI-Access-Point, die Firewall und andere Netzwerkfunktionen umfasst (je nach Hersteller und Modell).

## Anschließen des AEM Screens Player an den direkten Internetzugang {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine Verbindung mit AEM-Screen-Playern in dieser Konfiguration herzustellen:

1. Vergewissern Sie sich, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn Sie eine Fehlermeldung erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit der Router-Einstellung übereinstimmt, und überprüfen Sie, ob die maximale Anzahl an IP-Adressen in Ihrem Netzwerk nicht erreicht wird.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies lässt sich auch mit einer Signal-LED auf Standard Routern identifizieren.
1. Falls der URL-Aufruf erfolgreich ist, können Sie die Installation der AEM Screens fortsetzen und sich registrieren. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und nicht den erwarteten Inhalt anzeigen:
   >
   >1. Prüfen Sie, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.


## Voraussetzungen für die Einrichtung eines Netzwerks für direkten Internet-Zugriff {#requirements-direct}

Das direkte Internet-Netzwerk kann logischerweise in zwei Blöcke unterteilt werden:

* Breites Netzwerk

* Local Area Network

### Breites Netzwerk {#wan-connection}

Die Leistung der Internetverbindung ist nicht nur die Reichweite des Netzwerks, sondern auch die Bereitstellung ausreichender Bandbreite für den Betrieb von AEM Screens.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und von der Nutzung anderer Verbraucher im Netzwerk ab, z. B. Smartphones, Tablets, Kassierer, Computer oder WIFI-Gastnetzwerke.

>[!NOTE]
>Alle Geräte haben einen gleichzeitigen Zugriff auf die Internetverbindung, und die Bandbreite sinkt linear, wenn Sie mehr Benutzer oder Computer zum Netzwerk hinzufügen.

### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN) bietet neben der Erreichbarkeit des Netzwerks genügend Bandbreite für den Betrieb von AEM Screens.

Das LAN-Netzwerk entspricht in der Regel mindestens einem 100-Mbit/s-Netzwerk, sodass genügend Bandbreite vorhanden ist, um viele Geräte mit guter Leistung mit dem System zu verbinden.
In case that a WIFI solution is envisaged to connect AEM Screens to the Internet Link it is recommended to use modern WIFI standards like `IEEE 802.11g` as a minimum. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`

>[!NOTE]
>Ist ein WLAN-Repeater erforderlich, wird für die Zugangspunkte dringend der Einsatz von Mesh-WLAN-Technologie empfohlen, z. B. Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen. Andere WiFi-wiederholende Technologien führen zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Der große Netzwerkverkehr tritt auf, wenn auf einer bestimmten Anzeige neue Inhalte angezeigt werden.

Bei normalen Vorgängen, z. B. wenn Sie eine Playlist definiert haben, die im Laufe des Tages häufig aktualisiert wird, wird hier ein netzwerkunabhängiger Vorgang Angebot, sobald alle Dateien im Player gespeichert wurden.

Für die Einsatzfälle, in denen mehr Interaktionen mit Sensoren oder anderen Triggern bestehen und Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar, um eine optimale Kundenerfahrung zu gewährleisten.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>Diese Daten zeigen auf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/assets/download-times-direct.png)

