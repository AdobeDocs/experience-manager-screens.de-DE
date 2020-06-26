---
title: Verwalten des Netzwerkverkehrs
description: Auf der Seite werden Standard-Netzwerkeinstellungen und die Verwaltung des Netzwerkverkehrs beschrieben.
translation-type: tm+mt
source-git-commit: 173ce977549ed64e3750bb751a8fe1b27e277aa2
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 4%

---


# Verwalten des Netzwerkverkehrs {#managing-network-traffic}

Eine Netzwerkkonfiguration kann auf diversen Strukturen basieren. In diesem Abschnitt werden die gebräuchlichsten Netzwerkkonfigurationen und die am häufigsten verwendeten generalisierten Ansätze innerhalb einer Organisation beschrieben.

In diesem Handbuch wird eine Einführung in Proxy-Server und die verschiedenen Netzwerkstrukturen, die in verschiedenen Organisationen eingerichtet werden, vorgestellt.

>[!NOTE]
>
>**Netzwerkanforderungen für AEM Screens**
>
>Die AEM Screens kommunizieren direkt mit dem AEM als Cloud Service. Daher ist es erforderlich, eine stabile Verbindung zwischen den beiden Knoten herzustellen. Firewalls sind für den kommerziellen Internetzugang absolut zwingend erforderlich. Als Kunde müssen Sie wissen, welche Kommunikationshäfen in diesen Firewalls und anderen IT-Security-bezogenen Netzwerkkomponenten geöffnet werden müssen.

## Übersicht über Proxyserver {#proxy-servers}

Eine Internetverbindung beruht auf der Verwendung eines Proxyservers. Ein Proxy-Server ist ein dedizierter Computer oder ein Software-System, das auf einem Computer ausgeführt wird, der als Vermittler zwischen einem Endpunktgerät wie einem Computer und einem anderen Server fungiert, von dem aus ein Benutzer oder Client einen Dienst anfordert. Der Proxyserver kann sich auf demselben Computer wie ein Firewall-Server befinden oder auf einem separaten Server vorhanden sein, der Anfragen über die Firewall weiterleitet.

Ein Vorteil eines Proxyservers besteht darin, dass sein Cache allen Benutzern zur Verfügung stehen kann. Wenn eine oder mehrere Websites häufig angefordert werden, befinden sich diese wahrscheinlich im Cache des Proxys, was die Reaktionszeit des Benutzers weiter verbessert. Ein Proxy kann auch seine Interaktionen protokollieren, die zur Fehlerbehebung verwendet werden können.

Wenn ein Proxyserver eine Anforderung für eine Internetressource erhält (z. B. eine Webseite oder während der Verbindung mit einem AEM Publisher), wird der lokale Cache der zuvor aufgerufenen URLs überprüft. Wenn die Seite gefunden wird, wird sie an den Benutzer zurückgegeben, ohne die Anforderung an das Internet weiterzuleiten. Wenn sich die Seite nicht im Cache befindet, ruft der Proxyserver (als Client) für den Benutzer auf und ruft die Seite vom Server im Internet ab. Wenn der Inhalt zurückgegeben wird, bezieht der Proxyserver ihn mit der ursprünglichen Anforderung und leitet ihn an den Benutzer weiter.

## Understanding the Standard Network Setups {#network-setups}

Um ein Netzwerk-Setup zu implementieren, müssen Sie die folgenden Szenarien mit ihren Stärken und Implementierungsdetails verwenden.

In diesem Leitfaden werden vier verschiedene Arten von Netzwerkkonfigurationen innerhalb einer Organisation hervorgehoben:

* **[Direct Internet Network (Wired/Wireless)](/help/using/direct-internet-network.md)**
* **[Direktes Mobilfunknetz](/help/using/mobile-network.md)**
* **[Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten](/help/using/mobile-network-router.md)**
* **[Engeschlossenes Unternehmensnetzwerk (Wired/Wireless)](/help/using/enclosed-corporate-network.md)**

In der folgenden Tabelle sind die verschiedenen Arten von Netzwerken mit Vor- und Nachteilen aufgeführt:

| Netzwerkeinrichtung | Vorteile | Nachteile |
|--- |--- |--- |
| **Direct Internet Network (Wired/Wireless)** | Einfach und direkt nach<br>SetUpGute Wahl für mittlere oder größere<br>InstallationenDedicated Network kann<br>EncapsulatedWenige<br>Fehlerpunkte relativ<br>UnkostengünstigGute Skalierbarkeit | Obligatorischer Internet-Datenplan |
| **Direktes Mobilfunknetz** | Einfache<br>EinrichtungGute Wahl für mittlere oder größere<br>InstallationenGute<br>SkalierbarkeitEingekapselte Bildschirme | Verbindliche Internetverbindung |
| **Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten** | Einfache<br>EinrichtungGute Wahl für mittlere oder größere<br>InstallationenDedicated Network kann<br>EncapsulatedWenige<br>FehlerquellenRelativ<br>unkostengünstige SkalierbarkeitGute Skalierbarkeit | Obligatorischer Internet-Datenplan |
| **Engeschlossenes Unternehmensnetzwerk (Wired/Wireless)** | Hohe Flexibilität und<br>SkalierbarkeitHohe Sicherheit dank verschiedener<br>VerteidigungslinienEncapsulated<br>NetworksEinfache Überwachung und<br>WartungZuverlässig | Kompliziert und<br>teuerEmpfohlen für Netzwerkspezialisten oder Systemintegratoren |
