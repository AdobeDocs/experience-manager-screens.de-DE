---
title: Verwalten des Netzwerk-Traffics
description: Auf dieser Seite werden die Standard-Netzwerkkonfigurationen sowie die Verwaltung des Netzwerk-Traffics beschrieben.
exl-id: b6d8f4a3-fca2-4556-9455-b9e27b138154
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 95%

---

# Verwalten des Netzwerk-Traffics {#managing-network-traffic}

Eine Netzwerkkonfiguration kann auf diversen Strukturen basieren. Dieser Abschnitt erläutert die gängigsten Netzwerkkonfigurationen und beschreibt in verallgemeinerter Form die innerhalb eines Unternehmens verwendeten Ansätze.

Dieses Handbuch bietet zunächst eine Einführung in Proxy-Server, um dann auf die diversen Netzwerkstrukturen einzugehen, die in unterschiedlichen Unternehmen eingerichtet werden.

>[!NOTE]
>**Netzwerkanforderungen von AEM Screens**
>AEM Screens kommuniziert direkt mit AEM as a Cloud Service. Zwischen den beiden Knoten muss daher eine stabile Verbindung gewährleistet sein. Da Firewalls für den Zugriff auf das kommerzielle Internet absolut unabdingbar sind, müssen Sie verstehen, für welche Ports Sie in Firewalls und anderen für die IT-Sicherheit implementierten Netzwerkkomponenten die Kommunikation zulassen müssen.

## Übersicht über Proxy-Server {#proxy-servers}

Über Proxy-Server wird der Aufbau einer Verbindung zum Internet ermöglicht. Ein Proxy-Server ist ein dediziertes Computer- oder Software-System, das auf einem Computer ausgeführt wird, der als Vermittler zwischen einem Endpunktgerät (z. B. einem Computer) und einem anderen Server fungiert, von dem aus ein Benutzer oder Client einen Dienst anfordert. Der Proxy-Server kann sich auf demselben Computer befinden wie ein Firewall-Server oder auf einem separaten Server, der Anfragen über die Firewall weiterleitet.

Ein Vorteil eines Proxy-Servers besteht darin, dass sein Cache allen Benutzern zur Verfügung stehen kann. Wenn eine oder mehrere Websites häufig aufgerufen werden, ist es wahrscheinlich, dass diese im Cache des Proxys gespeichert werden, wodurch sich die Reaktionszeit für Benutzer weiter verkürzt. Ein Proxy kann zudem die durch ihn verarbeiteten Interaktionen protokollieren, was bei der Fehlerbehebung hilfreich sein kann.

Erhält ein Proxy-Server eine Anfrage für eine Internet-Ressource (z. B. für eine Web-Seite oder infolge der Verbindung mit einem AEM-Publisher), prüft er die im lokalen Cache gespeicherten, zu einem früheren Zeitpunkt aufgerufenen URLs. Wenn die Seite darin gefunden wird, wird sie an den Benutzer zurückgegeben, ohne die Anfrage an das Internet weiterzuleiten. Ist die Seite nicht im Cache gespeichert, fungiert der Proxy-Server als Client, der für den Benutzer die Seite vom Server im Internet abruft. Wenn der Inhalt zurückgegeben wird, ordnet ihn der Proxy-Server der ursprünglichen Anfrage zu und leitet ihn an den Benutzer weiter.

## Grundlegendes zu Standard-Netzwerkkonfigurationen {#network-setups}

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
