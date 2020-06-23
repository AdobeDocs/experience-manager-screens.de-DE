---
title: Einführung in Standard-Netzwerkkonfigurationen
seo-title: Einführung in Standard-Netzwerkkonfigurationen
description: Auf der Seite werden die Standard-Netzwerkeinstellungen beschrieben.
seo-description: Auf der Seite werden die Standard-Netzwerkeinstellungen beschrieben.
translation-type: tm+mt
source-git-commit: ae7da9c48188c3f7567d05d0e9a5a6b72383d539
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 37%

---


# Verwalten des Netzwerkverkehrs {#managing-network-traffic}

Eine Netzwerkkonfiguration kann auf diversen Strukturen basieren. Dieser Abschnitt bietet einen Überblick über die in einer Umgebung implementierten Netzwerkstrukturen. Es gibt verschiedene Setups, die manchmal von Grund auf implementiert werden.

In diesem Abschnitt wird eine Einführung zu Proxyservern sowie die verschiedenen Netzwerkstrukturen, die in verschiedenen Organisationen eingerichtet werden, vorgestellt.

>[!NOTE]
>**Netzwerkanforderungen für AEM Screens **>Die AEM Screens kommunizieren direkt mit dem AEM-Cloud Service, daher muss eine stabile Verbindung zwischen diesen beiden Knoten hergestellt werden. Firewalls sind für den kommerziellen Internetzugang absolut zwingend erforderlich, und der Kunde muss wissen, welche Kommunikationsanschlüsse in Firewalls und anderen IT-Security-bezogenen Netzwerkkomponenten, die der Kontrolle des Kunden unterliegen, geöffnet werden müssen.

## Proxy-Server {#proxy-servers}

Ein Proxy-Server ist ein dedizierter Computer oder ein Software-System, das auf einem Computer ausgeführt wird, der als Vermittler zwischen einem Endpunktgerät, z. B. einem Computer, und einem anderen Server fungiert, von dem aus ein Benutzer oder Client einen Dienst anfordert. Der Proxy-Server kann sich auf demselben Computer wie ein Firewall-Server befinden oder auf einem separaten Server, der Anfragen über die Firewall weiterleitet.

Der Vorteil eines Proxy-Servers besteht darin, dass sein Cache allen Benutzern zur Verfügung stehen kann. Wenn eine oder mehrere Websites häufig angefordert werden, befinden sich diese wahrscheinlich im Cache des Proxys, was die Reaktionszeit für den Benutzer verbessert. Ein Proxy kann auch seine Interaktionen protokollieren, was bei der Fehlerbehebung hilfreich sein kann.

## Understanding the Standard Network Setups {#network-setups}

Um ein Netzwerk-Setup zu implementieren, müssen Sie die folgenden Szenarien mit Stärken und Bereitstellungsdetails verwenden.

Prinzipiell wird zwischen drei Grundtypen von Netzwerkkonfigurationen unterschieden:

1. [Direkter Internet-Zugriff](/help/using/direct-internet-access.md)
1. [Direktes Mobilfunknetz](/help/using/mobile-network-setup.md)
1. [Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten](/help/using/mobile-network-setup-router.md)
1. [Geschlossenes Unternehmensnetzwerk](/help/using/enclosed-corporate-network.md)

In der folgenden Tabelle sind die verschiedenen Arten von Netzwerken mit Vor- und Nachteilen aufgeführt:

<table>
 <tbody>
  <tr>
   <td><strong>Netzwerkeinrichtung</strong></td>
   <td><strong>Vorteile</strong></td>
   <td><strong>Nachteile</strong></td>
  </tr>
  <tr>
   <td><strong>Direkter Internet-Zugriff</strong></td>
   <td>Einfach und direkt nach vorn zu Einrichten<br>Gute Wahl für mittelgroße oder größere Installationen<br>Dedicated Network kann verkapselt<br>wenigen Fehlerquellen<br>Relativ günstig<br>Gute Skalierbarkeitgute Skalierbarkeit</td>
   <td>Angemessener Internetdatenplan obligatorisch</td>
  </tr>
    <tr>
   <td><strong>Direktes Mobilfunknetz</strong></td>
   <td>Einfach und direkt nach vorn einrichten<br>Gute Wahl für mittelgroße oder größere Installationen<br>Gute Skalierbarkeit<br>Eingekapselte Bildschirme
</td>
   <td>Angemessene Internetverbindung erforderlich</td>
  </tr>
    <tr>
<tr>
   <td><strong>Mobiles Netzwerk mit mobilem DatenRouter und aktiven Netzwerkkomponenten</strong></td>
   <td>Einfach und direkt nach vorn zu Einrichten<br>Gute Wahl für mittelgroße oder größere Installationen<br>Dedicated Network kann verkapselt<br>wenigen Fehlerquellen<br>Relativ günstig<br>Gute SkalierbarkeitGute Skalierbarkeit</br></td>
   <td>Angemessener Internetdatenplan obligatorisch</td>
  </tr>
    <tr>

<td><strong>Geschlossenes Unternehmensnetzwerk</strong></td>
   <td>Hohe Flexibilität und Skalierbarkeit<br>Hochsicher aufgrund der verschiedenen Lines von<br>Verteidigungsnetzwerken<br>Einfach zu überwachen und zu warten<br>zuverlässig</td>
   <td>Komplizierte und teure<br>Netzwerkspezialisten oder Systemintegrator empfohlen</td>
  </tr>
  </tr>
 </tbody>
</table>


