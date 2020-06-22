---
title: Direct Internet Access
description: Direct Internet Access
translation-type: tm+mt
source-git-commit: e24fa2fbec09cbe863a3615e722ae61b57da5012
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%

---


# Direct Internet Access {#direct-internet-access}

Das Direct Internet Access SetUp enthält einen Einstiegspunkt für den Internetzugang, um die AEM cloud services zu erreichen, zu denen AEM Screens eine Verbindung herstellen müssen.

Die Standardkommunikation über Ports für AEM Screens lautet:
* `http (TCP Port 80)`Oder
* `ssl-secured https (TCP Port 443)`

Die Anschlüsse können je nach Konfiguration der dedizierten AEM-Konfiguration variieren. In diesem SetUp sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der folgenden Abbildung dargestellt.

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
1. Falls der URL-Aufruf erfolgreich war, können Sie die Installation der AEM Screens fortsetzen und sie entsprechend registrieren
1. Beginn-AEM Screens.

   >[!NOTE]
   >**Tipps zur Fehlerbehebung**
   >Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und nicht den erwarteten Inhalt anzeigen:
   >
   >1. Prüfen Sie Ihre Internet Router Firewall, wenn es irgendwelche Einschränkungen in Bezug auf `TCP/IP Port 80/443`.
   >1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind.


## Anforderungen für die Einrichtung eines Direct Access-Netzwerks {#requirements-direct}

Die Einrichtung des Direct Access-Netzwerks kann logisch in zwei Blöcke getrennt werden:

* Breites Netzwerk

* Local Area Network

### Breites Netzwerk {#wan-connection}

Die Leistung der Internetverbindung ist neben der Reichweite des Netzwerks auch die Bereitstellung ausreichender Bandbreite für den reibungslosen Betrieb von AEM Screens. Im Einzelnen hängt &quot;ausreichend&quot;von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.

>[!NOTE]
>Alle Geräte haben einen gleichzeitigen Zugriff auf die Internetverbindung und die Bandbreite sinkt in der Regel linear, wenn Sie mehr Benutzer/Computer zum Netzwerk hinzufügen.

### Local Area Network {#lan-connection}

Die Leistung des Local Area Network (LAN), neben der Netzwerkerreichbarkeit, bietet ausreichend Bandbreite, um AEM Screens angenehm und reibungslos zu bedienen.

Das LAN-Netzwerk entspricht in der Regel mindestens einem 100 MBit/s Netzwerk, sodass genügend Bandbreite vorhanden ist, um viele Geräte mit guter Leistung mit dem System zu verbinden.
Falls eine WIFI-Lösung zur Anbindung von AEM Screens an den Internetlink vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit. Alle *neueren* Standards wie 802.11h-n sind von besserer Qualität.

>[!NOTE]
>Wenn ein WIFI-Repeater benötigt wird, empfehlen wir dringend Mesh WIFI Access-Point Technologien wie Google Nest Mesh WIFI oder Ähnliches. Andere WiFi-Wiederholungstechnologien führen schließlich zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bieten Digital Signage-Benutzern einen großen Vorteil. Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerkverkehr, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Bei normalem Betrieb, z. B. wenn die Wiedergabeliste definiert ist, die sich tagsüber nicht sehr häufig ändert, ist dies ein netzwerkunabhängiger Vorgang, sobald alle Dateien auf dem Player gespeichert wurden.
Für die Einsatzfälle, in denen mehr Interaktionen mit Sensoren oder anderen Triggern bestehen und Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar, um eine optimale Kundenerfahrung zu gewährleisten.

Die folgende Tabelle gibt einen Überblick über die wichtigsten Daten zu Netzwerkverbindungen:

![](/help/assets/download-times-direct.png)

>[!NOTE]
>Die Informationen ermöglichen es Ihnen, den Verbrauch der einzelnen Geräte im Netzwerk zu Ansichten, die eine Internetquelle anfordern und herunterladen. Jede dieser Anforderungen addiert sich also und verlängert die Downloadzeit.