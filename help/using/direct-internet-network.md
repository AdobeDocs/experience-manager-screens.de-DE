---
title: Direkter Internet-Zugriff
description: Direkter Internet-Zugriff
translation-type: tm+mt
source-git-commit: d12de8de2b7bb29d85ebb0e046f2d1fd5051e928
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 7%

---


# Direct Internet Network (Wired/Wireless) {#direct-internet-access}

Das Direct Internet Network enthält einen Einstiegspunkt für den Internetzugang, um die AEM cloud services zu erreichen, mit denen AEM Screens eine Verbindung herstellen müssen.

AEM Screens verwendet für die Kommunikation standardmäßig die folgenden Ports:
* `http (TCP Port 80)`

   <br>Oder</br>

* `ssl-secured https (TCP Port 443)`

Die Anschlüsse können je nach Konfiguration der dedizierten AEM-Konfiguration variieren. In diesem SetUp sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der folgenden Abbildung dargestellt.

![](/help/assets/direct-access-2.png)

Die Konfiguration beinhaltet auch einen Internetzugang von jedem Internet-Dienstleister (ISP) und seine Internetverbindung. Die meisten ISPs bieten einen Internet-Router, der das Internet-Modem, den Netzwerk-Switch, Wi-Fi-Access Point, Firewall und andere Netzwerkfunktionen (je nach Hersteller und Modell) abdeckt.

## Anschließen des AEM Screens Player an den direkten Internetzugang {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine ordnungsgemäße Verbindung der AEM-Bildschirmplayer in dieser Konfiguration sicherzustellen:

1. Vergewissern Sie sich, dass alle AEM-Screen-Player mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internetverbindung, indem Sie eine URL in Ihrem Systembrowser aufrufen.

   >[!NOTE]
   >Wenn Sie einen Fehler erhalten, überprüfen Sie die Netzwerkeinstellungen. Es gibt im Grunde zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration


1. Stellen Sie sicher, dass die Netzwerkadaptereinstellung mit den Router-Einstellungen übereinstimmt, und überprüfen Sie, ob die maximale Anzahl an IP-Adressen in Ihrem Netzwerk nicht erreicht wird.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem ISP Wide Area Network (Internet Link) verbunden ist. Dies lässt sich auch mit einer Signal-LED auf Standard Routern identifizieren.
1. Falls der URL-Aufruf erfolgreich ist, können Sie die Installation der AEM Screens fortsetzen und sich registrieren. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipp zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und der erwartete Inhalt nicht angezeigt wird:
   >
   >1. Check in your Internet Router firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.


## Einrichten des Direct Access-Netzwerks {#requirements-direct}

Das direkte Internet-Netzwerk ist logisch in zwei Blöcke unterteilt:

* Breites Netzwerk

* Local Area Network

### Breites Netzwerk {#wan-connection}

Die Leistung der Internetverbindung ist nicht nur die Reichweite des Netzwerks, sondern auch die Bereitstellung ausreichender Bandbreite für den Betrieb von AEM Screens.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM-Bildschirme und von der Nutzung anderer Verbraucher im Netzwerk ab, z. B. Smartphones, Tablets, Kassierer, Computer oder WLAN-Gastnetzwerke.

>[!NOTE]
>Alle oben genannten Geräte haben einen gleichzeitigen Zugriff auf die Internetverbindung und die Bandbreite sinkt linear, wenn Sie mehr Benutzer oder Computer zum Netzwerk hinzufügen.

### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN) bietet neben der Erreichbarkeit des Netzwerks genügend Bandbreite für den Betrieb von AEM Screens.

Das LAN-Netzwerk entspricht in der Regel mindestens einem 100-Mbit/s-Netzwerk, sodass genügend Bandbreite vorhanden ist, um viele Geräte mit guter Leistung mit dem System zu verbinden.
In case that a Wi-Fi solution is envisaged to connect AEM Screens to the Internet Link it is recommended to use modern Wi-Fi standards like `IEEE 802.11g` as a minimum. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`

>[!NOTE]
>Wenn ein Wi-Fi-Repeater erforderlich ist, wird dringend empfohlen, einen Mesh Wi-Fi-Zugangspunkt wie Google Nest Mesh Wi-Fi oder Ähnliches. Andere Wi-Fi-Wiederholungstechnologien führen zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Anwendern von Digital Signage einen entscheidenden Vorteil dahingehend, Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Der große Netzwerkverkehr tritt auf, wenn auf einer bestimmten Anzeige neue Inhalte angezeigt werden.

Bei normalen Vorgängen beispielsweise wird eine definierte Playlist, die im Laufe des Tages häufig aktualisiert wird, als Angebot ein netzwerkunabhängiger Vorgang ausgeführt, sobald alle Dateien im Player gespeichert wurden.

In Szenarien, in denen es mehr Interaktionen mit Sensoren oder Triggern und dynamischen Inhalten gibt, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar, um eine sofortige Bildschirmreaktion zu gewährleisten und eine bestmögliche Kundenerfahrung zu gewährleisten.

Nachfolgend sind die wichtigsten Daten bezüglich Netzwerkverbindungen aufgeführt.

>[!NOTE]
>Die Informationen ermöglichen es Ihnen, den Verbrauch der einzelnen Geräte im Netzwerk zu Ansichten, die eine Internetquelle anfordern und herunterladen. Jede dieser Anforderungen erhöht die Downloadzeit und verlängert sie.

![](/help/assets/download-times-direct.png)

