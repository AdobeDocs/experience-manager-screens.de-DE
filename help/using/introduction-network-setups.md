---
title: Einführung in Standard-Netzwerkkonfigurationen
description: Auf der Seite werden die Standard-Netzwerkeinstellungen beschrieben.
translation-type: tm+mt
source-git-commit: 8e62b3fc4ce324e02aaec6fca9df79b1aaf94d72
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 12%

---


# Verwalten des Netzwerkverkehrs {#managing-network-traffic}

Eine Netzwerkkonfiguration kann auf diversen Strukturen basieren. In diesem Abschnitt werden die häufigsten Netzwerkkonfigurationen innerhalb der Netzwerkeinrichtung eines Unternehmens beschrieben.

In diesem Handbuch wird eine Einführung in Proxy-Server und die verschiedenen Netzwerkstrukturen, die in verschiedenen Organisationen eingerichtet werden, vorgestellt.

>[!NOTE]
>**Netzwerkanforderungen für AEM Screens **>Die AEM Screens kommunizieren direkt mit dem AEM als Cloud Service, daher muss eine stabile Verbindung zwischen den beiden Knoten hergestellt werden. Firewalls sind für den kommerziellen Internetzugang absolut zwingend erforderlich, und als Kunde müssen Sie wissen, welche Kommunikationshäfen in Firewalls und anderen IT-Security-bezogenen Netzwerkkomponenten geöffnet werden müssen.

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

<table>
 <tbody>
  <tr>
   <td><strong>Netzwerkeinrichtung</strong></td>
   <td><strong>Vorteile</strong></td>
   <td><strong>Nachteile</strong></td>
  </tr>
  <tr>
   <td><strong>Direct Internet Network (Wired/Wireless)</strong></td>
   <td>Einfache und unkomplizierte Einrichtung<br>Gute Wahl für mittelgroße oder größere Installationen<br>Dedicated Network kann durch Encapsulated<br>wenigen Fehlerquellen<br>Relativ unkostengünstige<br>gute Skalierbarkeit.</td>
   <td>Obligatorischer Internet-Datenplan </td>
  </tr>
    <tr>
   <td><strong>Direktes Mobilfunknetz</strong></td>
   <td>Einfache Einrichtung<br>Gute Wahl für mittlere oder größere Installationen<br>Gute Skalierbarkeit<br>verkapselte Bildschirme
</td>
   <td>Verbindliche Internetverbindung</td>
  </tr>
    <tr>
<tr>
   <td><strong>Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten</strong></td>
   <td>Einfache Einrichtung<br>Gute Wahl für mittelgroße oder größere Installationen<br>Dedicated Network kann durch die Encapsulation<br>wenigen Fehlerquellen<br>Relativ unkostengünstig<br>Gute Skalierbarkeit</br></td>
   <td>Obligatorischer Internet-Datenplan</td>
  </tr>
    <tr>

<td><strong>Engeschlossenes Unternehmensnetzwerk (Wired/Wireless)</strong></td>
   <td>Hohe Flexibilität und Skalierbarkeit<br>Hochsicher dank verschiedener Verteidigungslinien<br>verkapselte Netzwerke<br>einfach zu überwachen und zu warten<br>zuverlässig</td>
   <td>Komplex und teuer<br>für Netzwerk-Spezialisten oder Systemintegratoren empfohlen</td>
  </tr>
  </tr>
 </tbody>
</table>


