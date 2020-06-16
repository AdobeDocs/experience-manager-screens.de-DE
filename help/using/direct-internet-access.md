---
title: Direct Internet Access
description: Direct Internet Access
translation-type: tm+mt
source-git-commit: 31a6b202cae200e43e87db1df4e60f6f9d75c1bf
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---


# Direct Internet Access {#direct-internet-access}

Das Direct Internet Access SetUp enthält einen Einstiegspunkt für den Internetzugang, um die AEM cloud services zu erreichen, zu denen AEM Screens eine Verbindung herstellen müssen.

Die Standardkommunikation über Ports für AEM Screens lautet:
* `http (TCP Port 80)`Oder
* `ssl-secured https (TCP Port 443)`

Die Anschlüsse können je nach Konfiguration Ihrer dedizierten AEM-Konfiguration variieren. In diesem SetUp sind alle Geräte direkt mit Ihrem Internet-Router verbunden, wie in der folgenden Abbildung dargestellt.

![](/help/assets/direct-access-2.png)

Die Konfiguration beinhaltet auch einen Internetzugang von jedem Internet-Dienstleister und es ist eine Internetverbindung. Die meisten ISPs bieten einen Internet-Router, der das Internet-Modem, den Netzwerk-Switch, den WIFI-Access-Point, die Firewall und andere Netzwerkfunktionen (je nach Hersteller und Modell) abdeckt.

>[!NOTE]
>**Tipps zur Fehlerbehebung **>Wenn AEM Screens keine ordnungsgemäße Verbindung herstellen und den erwarteten Inhalt anzeigen:
>
>1. Prüfen Sie Ihre Internet Router Firewall, wenn es irgendwelche Einschränkungen in Bezug auf `TCP/IP Port 80/443`.
>1. Stellen Sie sicher, dass alle erforderlichen Anschlüsse zulässig sind, und versuchen Sie es erneut.


## Anforderungen für die Einrichtung eines Direct Access-Netzwerks {#requirements-direct}

Die Netzwerkeinstellungen für Direct Access können logisch in zwei Blöcke getrennt werden. Der WAN/Outer World/Internet Connection Block und das interne LAN/Local Area Network.

### WAN/Internetverbindung {#wan-connection}

Die Leistung der Internetverbindung hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, eine ausreichende Bandbreite zur Verfügung gestellt, um AEM Screens angenehm und reibungslos zu bedienen. Im Einzelnen hängt &quot;ausreichend&quot;von der Anzahl der angeschlossenen AEM-Bildschirme und der Nutzung anderer Verbraucher im Netzwerk ab, wie Smartphones, Tablets, Kassierer, Computer oder WIFI-Netzwerke.
Denken Sie daran, dass alle Geräte einen gleichzeitigen Zugriff auf die Internetverbindung haben und dass die Bandbreite in der Regel linear sinkt, während dem Netzwerk mehr Benutzer/Computer hinzugefügt werden.

### LAN-Verbindung {#lan-connection}

Die Leistung des LAN hat, neben der bereits beschriebenen Netzwerkerreichbarkeit, ausreichend Bandbreite zur Verfügung zu stellen, um AEM Screens angenehm und reibungslos zu bedienen. In diesen Tagen ist das LAN-Netzwerk in der Regel mindestens 100 MBit/s Netzwerk, sodass es genügend Bandbreite geben sollte, um viele Geräte mit guter Leistung mit dem System zu verbinden.
Falls eine WIFI-Lösung zur Verbindung des Bildschirms mit dem Internetlink vorgesehen ist, wird empfohlen, moderne WIFI-Standards wie IEEE 802.11g als Minimum zu verwenden. Dieser Standard unterstützt Verbindungen bis zu 54 Mbit. Alle *neueren* Standards wie 802.11h-n sind von besserer Qualität. Wenn ein WIFI-Repeater benötigt wird, empfehlen wir dringend Mesh WIFI Access-Point Technologien wie Google Nest Mesh WIFI oder Ähnliches.
Andere WiFi-Wiederholungstechnologien führen schließlich zu einem massiven Bandbreitenverlust im gesamten Netzwerk.

## Herunterladen von Medien und Assets {#download}

AEM Screens bieten Digital Signage-Benutzern einen großen Vorteil. Es lädt alle erforderlichen Mediendateien wie Bilder und Videos herunter und speichert sie lokal. Aufgrund dieses Konzepts kommt es zu einem großen Netzwerk-Traffic, wenn neue Inhalte auf einem bestimmten Bildschirm angezeigt werden.
Bei normalem Betrieb, z. B. wenn die Wiedergabeliste definiert ist, die sich tagsüber nicht sehr häufig ändert, ist dies ein netzwerkunabhängiger Vorgang, sobald alle Dateien auf dem Player gespeichert wurden.
Für die Einsatzfälle, in denen mehr Interaktionen mit Sensoren oder anderen Triggern bestehen und Inhalt sehr dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung unverzichtbar, um eine optimale Kundenerfahrung zu gewährleisten.

Die folgende Tabelle gibt einen Überblick über die wichtigsten Daten zu Netzwerkverbindungen:

![](/help/assets/download-times-direct.png)

>[!NOTE]
>Die Informationen ermöglichen es Ihnen, den Verbrauch der einzelnen Geräte im Netzwerk zu Ansichten, die eine Internetquelle anfordern und herunterladen. Jede dieser Anforderungen ergibt also die Downloadzeit und verlängert sie.