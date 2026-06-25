---
title: Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten
description: Auf dieser Seite wird das mobile Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten beschrieben.
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
TQID: https://experienceleague.adobe.com/uKyl9w97xF0m6W9kj-PTAbIgt5HtZRAgkOUCstAuti4
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: d4664dd5678eaccabe656398c437dca264d4675e
workflow-type: tm+mt
source-wordcount: 824
ht-degree: 86%

---

# Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#mobile-network-setup}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Download-Zeiten sowie auf Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung bei der regelmäßigen Wiedergabe auf Anzeigen.

Der Vorteil dieser Einrichtung besteht darin, dass der mobile Router an einem optimierten Ort platziert werden kann, um eine optimale Netzabdeckung zu gewährleisten. Dieser Ort befindet sich in der Regel in einer erhöhten und offenen Position mit so wenig umgebenden Beton- oder Metallstrukturen wie möglich.
Diese Einrichtung bietet Benutzenden von AEM Screens Flexibilität, da für die Verbindung mit AEM Screens kein Festnetz erforderlich ist. Es ist auch für temporäre oder mobile Setups interessant.

Die folgende Abbildung zeigt das mobile Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten. Die Konfiguration umfasst für jeden AEM Screens-Controller einen Internet-Zugang, der mittels Direktzugriff auf das Internet über eine eigene 3G-, 4G- oder 5G- Datenverbindung umgesetzt wird.

![](/help/using/assets/mobile-network-1.png)

## Anbinden von AEM Screens-Playern an ein mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#connecting-aem-screens-players}

Gehen Sie wie folgt vor, um eine ordnungsgemäße Anbindung der AEM Screens-Player in dieser Konfiguration sicherzustellen:

Die Konfiguration weist jedem AEM Screens-Controller einen Internetzugang über eine eigene 3G-, 4G- oder 5G-Datenverbindung zu.

1. Stellen Sie sicher, dass der mobile Daten-Router ordnungsgemäß mit dem Mobilfunknetz verbunden ist, wie im Betriebssystem angegeben. Stellen Sie ebenfalls sicher, dass alle AEM Screens-Player mit dem Router-Netzwerk verbunden sind.
1. Testen Sie die Internet-Verbindung, indem Sie in Ihrem System-Browser eine URL aufrufen.

   >[!NOTE]
   >Wenn ein Fehler auftritt, überprüfen Sie die Netzwerkeinstellungen. Grundsätzlich gibt es zwei Optionen für eine ordnungsgemäße Netzwerkverbindung:
   >* DHCP
   >* Manuelle IP-Konfiguration

1. Stellen Sie sicher, dass die Einstellung des Netzwerkadapters mit der des Routers übereinstimmt.

1. Überprüfen Sie, ob der Router ordnungsgemäß mit dem Wide Area Network (also der Internet-Verbindung) des Internet-Dienstanbieters verbunden ist. Auf Standard-Routern können Sie dies anhand einer Signal-LED prüfen.
1. Im Falle eines erfolgreichen URL-Aufrufs können Sie mit der Installation der für AEM Screens verwendeten Bildschirme fortfahren, die Registrierung abschließen Starten Sie AEM Screens.

   >[!TIP]
   >Möglicherweise funktioniert die AEM Screens-Verbindung nicht ordnungsgemäß. Der erwartete Inhalt wird nicht angezeigt. Prüfen Sie in solchen Fällen, ob in der Firewall Ihres Internet-Routers Zugriffsbeschränkungen für `TCP/IP Port 80/443` eingerichtet sind.


## Einrichten eines mobilen Netzwerks mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#requirements-direct}

Die Netzwerkkonfiguration kann logisch in zwei Blöcke unterteilt werden:

* Mobile Internet-Verbindung

* LAN (Local Area Network)

### Mobile Internet-Verbindung {#mobile-internet-connection}

Die Internet-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der bereits beschriebenen Erreichbarkeit des Netzwerks auch reibungslose Downloads von AEM Screens-Inhalten gewährleistet werden können.

*Ausreichend* hängt von der Anzahl der angeschlossenen AEM Screens-Geräte ab. Es hängt auch von der Verwendung anderer Verbraucher innerhalb des Netzwerks ab, z. B. Smartphones, Tablets, Kassensysteme, Computer oder Gast-WLAN-Netzwerke.
Beachten Sie, dass alle Geräte gleichzeitig auf die Internetverbindung zugreifen und dass die Bandbreite linear abnimmt, während dem Netzwerk mehr Verbraucher/Computer hinzugefügt werden.
Neben der spezifischen theoretischen Netzwerkverbindung muss sichergestellt sein, dass die Abdeckung des mobilen Routers mindestens &quot;*&quot;*. Außerdem muss der zugrunde liegende Monatsplan genügend Datenkapazität und Bandbreite abdecken, um alle verbundenen Clients innerhalb des verbundenen LANs zu bedienen.

Nachfolgend sind die Datennetze einschließlich der ihnen zugehörigen Standardbandbreite aufgeführt:

| Datennetzwerk | Bandbreite |
|--- |--- |
| 3G | 42 MBit/s |
| 4G | 150 MBit/s |
| 5G | 1.000–10.000 MBit/s |

Bei der Wahl des Datennetzes empfiehlt Adobe, die folgenden Fragen abzuwägen:

* Wie viele Clients sind mit dem Router verbunden?
* Wie häufig werden Inhalte voraussichtlich geändert und welche Größe weisen die entsprechenden Dateien im Schnitt auf?

>[!NOTE]
>
>Die mindestens vom Daten-Package abzudeckende Kapazität beträgt:
>
>`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>
>Für den erstmaligen Upload der Mediendateien bei der Integration neuer Player muss ein höheres Datenvolumen und eine längere Download-Zeit einkalkuliert werden. Dies spiegelt sich auch in den oben genannten Annahmen wider. Ein 4G-Netz mit *guter* Abdeckung und unbegrenztem Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.


### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der bereits beschriebenen Erreichbarkeit des Netzwerks auch reibungslose Downloads von AEM Screens-Inhalten gewährleistet werden können. LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 100 MBit/s und sollten daher auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite liefern. Bei der Verwendung anderer aktiver Netzwerkkomponenten müssen diese alle den Anforderungen an die Netzwerkbandbreite entsprechen.

Beispielsweise sollten entsprechende Netzwerkkomponenten mindestens auf den Standard 100 MBit/s ausgelegt sein und mit den Bandbreitenspezifikationen des Internet-Zugangs/-Routers übereinstimmen.

Sofern eine WLAN-Lösung für die Internet-Anbindung von Screens vorgesehen ist, sollten moderne WLAN-Standards verwendet werden. Empfohlen wird hierfür mindestens IEEE `802.11g`. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`. Ist ein WLAN-Repeater erforderlich, empfiehlt Adobe dringend den Einsatz von Mesh-WLAN-Technologie für die Zugangspunkte, z. B. Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Benutzenden von Digital Signage einen erheblichen Vorteil. Es werden alle erforderlichen Mediendateien, wie Bilder und Videos, heruntergeladen und lokal gespeichert. Aufgrund dieses Konzepts erfolgt der Großteil des Netzwerk-Traffics für den Fall, dass neue Inhalte auf einem bestimmten Bildschirm angezeigt werden sollen.
Für den normalen Betrieb bietet sie mit einer definierten Wiedergabeliste, die nicht häufig aktualisiert wird, einen nahezu netzwerkunabhängigen Betrieb, wenn alle Dateien auf dem Player gespeichert werden.
Für Anwendungsfälle, bei denen mehr Interaktionen mit Sensoren oder anderen Trigger auftreten und der Inhalt dynamisch ist, ist eine schnelle und zuverlässige Netzwerkverbindung für eine sofortige Bildschirmreaktion unerlässlich. Es sorgt für das bestmögliche Kundenerlebnis.
Die folgenden Tabellen bieten einen guten Überblick darüber, was die wichtigsten Daten zur Netzwerkkonnektivität für die erwartete Leistung und potenzielle Wartezeiten bedeuten.

>[!NOTE]
>
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Mit jeder weiteren solchen Anfrage erhöht sich die Bandbreitennutzung, wodurch sich wiederum die Download-Zeit verlängert.

![](/help/using/assets/mobile-router-download.png)
