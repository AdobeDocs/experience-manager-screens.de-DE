---
title: Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten
description: Auf dieser Seite wird das mobile Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten beschrieben.
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: ht
source-wordcount: '1043'
ht-degree: 100%

---

# Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten {#mobile-network-setup}

AEM Screens-Player können auch über Mobilfunknetze angebunden werden, sofern die Datenübertragung mindestens nach 3G-Standard erfolgt.

Innerhalb von AEM Screens werden die erforderlichen Inhalte physisch auf den Player-Controller oder Computer heruntergeladen und dem zugrunde liegenden Betriebssystem entsprechend ordnungsgemäß gespeichert. Die angegebene Bandbreite wirkt sich daher nur auf die anfänglichen Download-Zeiten sowie auf Inhaltsaktualisierungen aus und beeinflusst nicht die Leistung bei der regelmäßigen Wiedergabe auf Anzeigen.

Der Vorteil dieses Setups besteht darin, dass der mobile WLAN-Router flexibel an einem Ort platziert werden kann, an dem eine optimale Netzabdeckung sichergestellt ist. In der Regel ist dies an höher gelegenen, offenen Stellen der Fall, die so wenig wie möglich von Beton- oder Metallkonstruktionen umgeben sind.
Mit diesem Setup sind AEM Screens-Benutzende flexibler, da für die Anbindung an AEM Screens keine Festnetzleitung benötigt wird. Dies ist auch interessant für kurzlebige oder mobile Setups.

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

Wie viel *ausreichend* ist, hängt von der Anzahl der verbundenen AEM Screens-Geräte ab. Dies ist außerdem abhängig von der Nutzung anderer Verbrauchergeräte innerhalb des Netzwerks. Dazu gehören z. B. Smartphones, Tablets, Kassensysteme, Computer oder WLAN-Gastnetzwerke.
Beachten Sie, dass alle Geräte gleichzeitig auf die Internet-Verbindung zugreifen und dass die Bandbreite mit der Zahl an weiteren Verbrauchergeräten/Computern, die dem Netzwerk hinzugefügt werden, linear abnimmt.
Neben einer für die jeweilige Netzwerkverbindung theoretisch ausreichenden Bandbreite muss außerdem eine *gute oder sehr gute* Netzabdeckung des mobilen WLAN-Routers sichergestellt sein.  Ferner muss das im Rahmen des zugrunde liegenden Abonnements gebuchte monatliche Datenvolumen eine für alle an das Netzwerk angebundenen Clients ausreichende Kapazität und Bandbreite zur Verfügung stellen.

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
>Für den erstmaligen Upload der Mediendateien bei der Integration neuer Player muss ein höheres Datenvolumen und eine längere Download-Zeit einkalkuliert werden.  Dies spiegelt sich auch in den oben genannten Annahmen wider. Ein 4G-Netz mit *guter* Abdeckung und unbegrenztem Datenvolumen sollte für die im Rahmen dieser Netzwerkkonfiguration gängigsten Installationen jedoch ausreichen.


### LAN (Local Area Network) {#lan-connection}

Die LAN-Verbindung muss ausreichend Bandbreite zur Verfügung stellen, damit neben der bereits beschriebenen Erreichbarkeit des Netzwerks auch reibungslose Downloads von AEM Screens-Inhalten gewährleistet werden können. LAN-Netzwerke unterstützen in der Regel Übertragungsraten von mindestens 100 MBit/s und sollten daher auch bei der Anbindung einer Vielzahl von Geräten an das System eine für eine angemessene Leistung ausreichende Bandbreite liefern. Sind aktive Netzwerkkomponenten anderer Art im Einsatz, müssen diese allesamt die Anforderungen an die Netzwerkbandbreite erfüllen.

Beispielsweise sollten entsprechende Netzwerkkomponenten mindestens auf den Standard 100 MBit/s ausgelegt sein und mit den Bandbreitenspezifikationen des Internet-Zugangs/-Routers übereinstimmen.

Sofern eine WLAN-Lösung für die Internet-Anbindung von Screens vorgesehen ist, sollten moderne WLAN-Standards verwendet werden. Empfohlen wird hierfür mindestens IEEE `802.11g`. Dieser Standard unterstützt Verbindungen mit bis zu 54 MBit/s. Eine bessere Qualität liefern jedoch *neuere* Standards wie etwa `802.11h-n`. Ist ein WLAN-Repeater erforderlich, empfiehlt Adobe dringend den Einsatz von Mesh-WLAN-Technologie für die Zugangspunkte, z. B. Google Nest Wifi oder vergleichbare Mesh-WLAN-Lösungen.

## Herunterladen von Medien und Assets {#download}

AEM Screens bietet Digital-Signage-Anwendenden einen entscheidenden Vorteil dahingehend, dass die Lösung alle erforderlichen Mediendateien (z. B. Bilder und Videos) herunterlädt und lokal speichert. Durch dieses Konzept ist der Großteil des Netzwerk-Traffics auf Phasen konzentriert, in denen neue Inhalte für die Anzeige auf einem bestimmten Bildschirm übertragen werden.
So kann der Normalbetrieb, bei dem eine bestimmte Wiedergabeliste nicht regelmäßig aktualisiert wird, nahezu unabhängig vom Netzwerk ablaufen, sobald alle Dateien auf dem Player gespeichert wurden.
Anwendungsfälle, in denen mehr mit Sensoren oder anderen Auslösern interagiert wird und dynamische Inhalte zum Einsatz kommen, erfordern dagegen unbedingt eine schnelle und zuverlässige Netzwerkverbindung für verzögerungsfreie Reaktionen. Dadurch wird das bestmögliche Kundenerlebnis gewährleistet.
Nachfolgend finden Sie eine Aufschlüsselung der wichtigsten Daten zur Netzwerkverbindung und wie sich diese auf die zu erwartende Leistung und potenzielle Wartezeiten auswirken.

>[!NOTE]
>
>Die Daten beziehen sich allesamt darauf, wie viel Bandbreite jedes einzelne mit dem Netzwerk verbundene Gerät beim Anfragen und Herunterladen einer Internet-Quelle beansprucht. Mit jeder weiteren solchen Anfrage erhöht sich die Bandbreitennutzung, wodurch sich wiederum die Download-Zeit verlängert.

![](/help/using/assets/mobile-router-download.png)
