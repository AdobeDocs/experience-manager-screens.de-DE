---
title: Einführung in Standard-Netzwerkkonfigurationen
seo-title: Einführung in Standard-Netzwerkkonfigurationen
description: Auf der Seite werden die Standard-Netzwerkeinstellungen beschrieben.
seo-description: Auf der Seite werden die Standard-Netzwerkeinstellungen beschrieben.
translation-type: tm+mt
source-git-commit: 6d6637d5222e861fa9a83f555baf0699f56f150a
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 24%

---


# Einführung in Standard-Netzwerkkonfigurationen {#intro-standard-networks}

Ein Netzwerk-Setup kann verschiedene Strukturen haben. In diesem Abschnitt erhalten Sie einen Überblick über die in einer Umgebung bereitgestellten Netzwerkstrukturen. Es gibt verschiedene Setups, die manchmal von Grund auf implementiert werden.

In diesem Abschnitt wird eine Einführung zu Proxyservern sowie die verschiedenen Netzwerkstrukturen, die in verschiedenen Organisationen eingerichtet werden, vorgestellt.

>[!NOTE]
>**Netzwerkanforderungen für AEM Screens **>Die AEM Screens kommunizieren direkt mit dem AEM-Cloud Service, daher muss eine stabile Verbindung zwischen diesen beiden Knoten hergestellt werden. Firewalls sind für den kommerziellen Internetzugang absolut zwingend erforderlich, und der Kunde muss wissen, welche Kommunikationsanschlüsse in Firewalls und anderen IT-Security-bezogenen Netzwerkkomponenten, die der Kontrolle des Kunden unterliegen, geöffnet werden müssen.

## Proxy Servers {#proxy-servers}

Ein Proxyserver ist ein dedizierter Computer oder ein Software-System, das auf einem Computer ausgeführt wird, der als Vermittler zwischen einem Endpunktgerät, z. B. einem Computer, und einem anderen Server fungiert, von dem aus ein Benutzer oder Client einen Dienst anfordert. Der Proxyserver kann sich auf demselben Computer wie ein Firewall-Server befinden oder auf einem separaten Server, der Anfragen über die Firewall weiterleitet.

Ein Vorteil eines Proxyservers besteht darin, dass der Cache allen Benutzern zur Verfügung stehen kann. Wenn eine oder mehrere Websites häufig angefordert werden, befinden sich diese wahrscheinlich im Cache des Proxys, was die Reaktionszeit für den Benutzer verbessert. Ein Proxy kann auch seine Interaktionen protokollieren, was bei der Fehlerbehebung hilfreich sein kann.

## Die Netzwerkeinstellungen {#network-setups}

Um ein Netzwerk-Setup zu implementieren, müssen Sie die folgenden Szenarien mit Stärken und Bereitstellungsdetails verwenden.

Es gibt drei große Arten von Netzwerken:

1. [Direct Internet Access](/help/using/direct-internet-access.md)
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
   <td><strong>Direct Internet Access</strong></td>
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


