---
title: Verwalten des Netzwerkverkehrs
description: Auf der Seite werden Standard-Netzwerkeinstellungen und die Verwaltung des Netzwerkverkehrs beschrieben.
translation-type: tm+mt
source-git-commit: 93cc11459e23d3eb22d865bedeb26deaf7135636
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 11%

---


# Verwalten des Netzwerkverkehrs {#managing-network-traffic}

Eine Netzwerkkonfiguration kann auf diversen Strukturen basieren. In diesem Abschnitt werden die häufigsten Netzwerkkonfigurationen innerhalb der Netzwerkeinrichtung eines Unternehmens beschrieben.

In diesem Handbuch wird eine Einführung in Proxy-Server und die verschiedenen Netzwerkstrukturen, die in verschiedenen Organisationen eingerichtet werden, vorgestellt.

>[!NOTE]
>
>**Netzwerkanforderungen für AEM Screens**
>
>Die AEM Screens kommunizieren direkt mit dem AEM als Cloud Service, daher muss eine stabile Verbindung zwischen den beiden Knoten hergestellt werden. Firewalls sind für den kommerziellen Internetzugang absolut zwingend erforderlich, und als Kunde müssen Sie wissen, welche Kommunikationshäfen in Firewalls und anderen IT-Security-bezogenen Netzwerkkomponenten geöffnet werden müssen.

## Übersicht über Proxyserver {#proxy-servers}

Eine Internetverbindung beruht auf der Verwendung eines Proxyservers. Ein Proxy-Server ist ein dedizierter Computer oder ein Software-System, das auf einem Computer ausgeführt wird, der als Vermittler zwischen einem Endpunktgerät wie einem Computer und einem anderen Server fungiert, von dem aus ein Benutzer oder Client einen Dienst anfordert. Der Proxy-Server kann sich auf demselben Computer wie ein Firewall-Server befinden oder auf einem separaten Server, der Anfragen über die Firewall weiterleitet.

Der Vorteil eines Proxy-Servers besteht darin, dass sein Cache allen Benutzern zur Verfügung stehen kann. Wenn eine oder mehrere Websites häufig angefordert werden, befinden sich diese wahrscheinlich im Cache des Proxys, was die Reaktionszeit des Benutzers verbessert. Ein Proxy kann auch seine Interaktionen protokollieren, die zur Fehlerbehebung verwendet werden.

## Understanding the Standard Network Setups {#network-setups}

Um ein Netzwerk-Setup zu implementieren, müssen Sie die folgenden Szenarien mit ihren Stärken und Implementierungsdetails verwenden.

Es gibt vier große Arten von Netzwerken:

1. [Direct Internet Network (Wired/Wireless)](/help/using/direct-internet-network.md)
1. [Direktes Mobilfunknetz](/help/using/mobile-network.md)
1. [Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten](/help/using/mobile-network-router.md)
1. [Engeschlossenes Unternehmensnetzwerk (Wired/Wireless)](/help/using/enclosed-corporate-network.md)

In der folgenden Tabelle sind die verschiedenen Arten von Netzwerken mit Vor- und Nachteilen aufgeführt:

| Netzwerkeinrichtung | Vorteile | Nachteile |
|--- |--- |--- |
| Direct Internet Network (Wired/Wireless) | Einfach und direkt nach<br>SetUpGute Wahl für mittlere oder größere<br>InstallationenDedicated Network kann<br>EncapsulatedWenige<br>Fehlerpunkte relativ<br>UnkostengünstigGute Skalierbarkeit | Obligatorischer Internet-Datenplan |
| Direktes Mobilfunknetz | Einfache<br>EinrichtungGute Wahl für mittlere oder größere<br>InstallationenGute<br>SkalierbarkeitEingekapselte Bildschirme | Verbindliche Internetverbindung |
| Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten | Einfache<br>EinrichtungGute Wahl für mittlere oder größere<br>InstallationenDedicated Network kann<br>EncapsulatedWenige<br>FehlerquellenRelativ<br>unkostengünstige SkalierbarkeitGute Skalierbarkeit | Obligatorischer Internet-Datenplan |
| Engeschlossenes Unternehmensnetzwerk (Wired/Wireless) | Hohe Flexibilität und<br>SkalierbarkeitHohe Sicherheit dank verschiedener<br>VerteidigungslinienEncapsulated<br>NetworksEinfache Überwachung und<br>WartungZuverlässig | Kompliziert und<br>teuerEmpfohlen für Netzwerkspezialisten oder Systemintegratoren |
