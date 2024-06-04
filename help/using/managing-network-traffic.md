---
title: Verwalten des Netzwerk-Traffics
description: Auf dieser Seite werden die Standard-Netzwerkkonfigurationen sowie die Verwaltung des Netzwerk-Traffics beschrieben.
exl-id: b6d8f4a3-fca2-4556-9455-b9e27b138154
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 82%

---

# Verwalten des Netzwerk-Traffics {#managing-network-traffic}

Eine Netzwerkkonfiguration kann auf diversen Strukturen basieren. Dieser Abschnitt erläutert die gängigsten Netzwerkkonfigurationen und beschreibt in verallgemeinerter Form die innerhalb eines Unternehmens verwendeten Ansätze.

Dieses Handbuch bietet zunächst eine Einführung in Proxy-Server, um dann auf die diversen Netzwerkstrukturen einzugehen, die in unterschiedlichen Unternehmen eingerichtet werden.

>[!NOTE]
>**Netzwerkanforderungen von AEM Screens**
>AEM Screens kommuniziert direkt mit AEM as a Cloud Service. Zwischen den beiden Knoten muss daher eine stabile Verbindung gewährleistet sein. Firewalls sind für den kommerziellen Internetzugang obligatorisch. Als Kundin oder Kunde sollten Sie wissen, welche Kommunikationsanschlüsse in diesen Firewalls und anderen IT-Sicherheit-bezogenen Netzwerkkomponenten geöffnet werden müssen.

## Überblick über Proxy-Server {#proxy-servers}

Eine Internet-Verbindung beruht auf der Verwendung eines Proxy-Servers. Ein Proxy-Server ist ein dedizierter Computer oder ein Software-System, das auf einem Computer ausgeführt wird. Er fungiert als Vermittler zwischen einem Endpunktgerät, z. B. einem Computer, und einem anderen Server, von dem aus Benutzende oder Clients einen Dienst anfordern. Der Proxy-Server kann sich auf demselben Computer befinden wie ein Firewall-Server oder auf einem separaten Server, der Anfragen über die Firewall weiterleitet.

Ein Vorteil eines Proxy-Servers besteht darin, dass sein Cache allen Benutzern zur Verfügung stehen kann. Wenn eine oder mehrere Websites häufig angefordert werden, befinden sich diese Sites wahrscheinlich im Cache des Proxys. Durch diese Zwischenspeicherung wird die Reaktionszeit der Benutzer weiter verbessert. Ein Proxy kann zudem die durch ihn verarbeiteten Interaktionen protokollieren, was bei der Fehlerbehebung hilfreich sein kann.

Erhält ein Proxy-Server eine Anfrage für eine Internet-Ressource (z. B. für eine Web-Seite oder infolge der Verbindung mit einem AEM-Publisher), prüft er die im lokalen Cache gespeicherten, zu einem früheren Zeitpunkt aufgerufenen URLs. Wenn die Seite darin gefunden wird, wird sie an den Benutzer zurückgegeben, ohne die Anfrage an das Internet weiterzuleiten. Wenn sich die Seite nicht im Cache befindet, fungiert der Proxy-Server als Client im Namen des Benutzers und fordert die Seite vom Server im Internet an. Wenn der Inhalt zurückgegeben wird, ordnet ihn der Proxy-Server der ursprünglichen Anfrage zu und leitet ihn an den Benutzer weiter.

## Grundlagen zu Standard-Netzwerkkonfigurationen {#network-setups}

Informationen zum Implementieren einer Netzwerkkonfiguration finden Sie in den folgenden Szenarien mit ihren Stärken und Implementierungsdetails.

Dieses Handbuch erläutert vier Varianten von Netzwerkkonfigurationen, die innerhalb eines Unternehmens eingerichtet werden können:

* **[Netzwerk für direkten Internet-Zugriff (kabelgebunden/kabellos)](/help/using/direct-internet-network.md)**
* **[Netzwerk für Direktanbindung an Mobilfunknetze](/help/using/mobile-network.md)**
* **[Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten](/help/using/mobile-network-router.md)**
* **[Geschlossenes Unternehmensnetzwerk (kabelgebunden/kabellos)](/help/using/enclosed-corporate-network.md)**

Im Folgenden sind die Vor- und Nachteile der einzelnen Netzwerkkonfigurationen aufgeführt:

| Netzwerkkonfiguration | Vorteile | Nachteile |
|--- |--- |--- |
| **Netzwerk für direkten Internet-Zugriff (kabelgebunden/kabellos)** | Unkomplizierte Einrichtung<br>Gut geeignet für mittlere oder größere Installationen<br>Kapselung von dediziertem Netzwerk möglich<br>Wenige potenzielle Quellen für Ausfälle<br>Vergleichsweise kostengünstig<br>Gute Skalierbarkeit | Erfordert Daten-Abo für Internet-Zugang |
| **Netzwerk für Direktanbindung an Mobilfunknetze** | Einfache Einrichtung<br>Gut geeignet für mittlere oder größere Installationen<br>Gute Skalierbarkeit<br>Kapselung der Bildschirme | Erfordert Verbindung zum Internet |
| **Mobiles Netzwerk mit mobilem WLAN-Router und aktiven Netzwerkkomponenten** | Einfache Einrichtung<br>Gut geeignet für mittlere oder größere Installationen<br>Kapselung von dediziertem Netzwerk möglich<br>Wenige potenzielle Quellen für Ausfälle<br>Vergleichsweise kostengünstig<br>Gute Skalierbarkeit | Erfordert Daten-Abo für Internet-Zugang |
| **Geschlossenes Unternehmensnetzwerk (kabelgebunden/kabellos)** | Hohe Flexibilität und Skalierbarkeit<br>Starke Sicherheit durch mehrere Absicherungsstufen<br>Kapselung der Netzwerke<br>Einfache Überwachung und Wartung<br>Zuverlässig | Kompliziert und kostenintensiv<br>Empfohlen für Netzwerkspezialisten oder Systemintegratoren |
