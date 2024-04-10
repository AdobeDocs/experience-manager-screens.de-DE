---
title: Tests und Qualitätssicherung
description: Erfahren Sie mehr über Tests und Qualitätssicherung für AEM Screens im Handbuch zu Best Practices.
exl-id: cc3bfb88-1341-43f8-b247-6a41f1d1a963
source-git-commit: a22702998599ea184529ab62eb8bd5113ad58e2c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 61%

---

# Tests und Qualitätssicherung {#testing-quality}

>[!NOTE]
>Typische Verantwortliche für diese Aktivität sind A/V-Integratoren.

Wenn Sie der Bereitstellung des Digital-Signage-Netzwerks näher kommen, erstellen Sie einen Test- und QA-Plan, der alle Elemente des Netzwerks einschließlich aller Hardware-Komponenten, Software-Komponenten und Netzwerkkomponenten behandelt.
In dem Schritt sollten vollständige Prüfsysteme eingerichtet und gründlich getestet werden.

Es sollte eine Checkliste erstellt werden, in der alle zuvor definierten KPIs identifiziert und die Ergebnisse mit ihnen verglichen werden.

>[!NOTE]
>
>Dieser Schritt sollte auch zur Erstellung eines Installations- und Benutzerhandbuchs genutzt werden, das später mit dem Gerät ausgeliefert und für künftige Referenzzwecke vor Ort aufbewahrt werden kann.

Folgende Elemente sollten berücksichtigt werden:

## 1. Mechanische Überlegungen {#mechanical-considerations}

Folgende Überlegungen in Bezug auf die Mechanik werden empfohlen:

* Display-Montage
* Player-Montage
* Lüftung
* Peripheriegeräte
* Kabelmanagement
* Gerätenetzwerk

## 2. Überlegungen zur Software {#software-considerations}

Folgende Überlegungen in Bezug auf die Software werden empfohlen:

* Geräteregistrierung
* Media Publishing
* Wiedergabe
* Datenbankabhängigkeiten (zuvor definiert)


## 3. Überlegungen zur Geräteverwaltung {#device-management-considerations}

AEM Screens enthält ein Gerätesteuerungsmodul, das die Verwaltung von Endgeräten mit der Screens Player-Anwendung ermöglicht.

Dies bezieht sich auf alle *Player*-Hardwaregeräte, auf denen die Screens Player-Anwendung installiert ist und die für eine AEM-Instanz registriert sind.
Mit diesem Modul können Sie:

1. Anwendungsfehlerprotokolle des Players überwachen
1. Remote-Screenshots verwalten
1. Inhaltsdownloads verwalten
1. Probleme beim Neustart der Anwendung beheben

Ausführliche Informationen zur ***Gerätesteuerung*** finden Sie im Abschnitt [Problembehandlung in der Gerätesteuerung](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/troubleshooting/monitoring-screens) des **AEM Screens-Benutzerhandbuchs**.

>[!CAUTION]
>
>Verwenden Sie das Gerätesteuerungscenter nicht für Folgendes:
>
>* Neue Versionen der Player-Anwendung installieren
>* Ressourcen auf Systemebene überwachen
>* Fehler auf der Systemebene beheben
>* Remote Desktop-Eingriffe zulassen


>[!NOTE]
>
> Adobe empfiehlt, für alle Bereitstellungen dedizierte Geräteverwaltungsplattformen von Drittanbietern zu verwenden.

Die ausgewählte Plattform hängt von mehreren Faktoren ab, darunter ***Zielbetriebssystem***, ***Projektanforderungen***, und ***Anzahl der Endpunkte***.

Im Folgenden finden Sie einige Beispiele:

* Google Chrome-Geräteverwaltung
* TeamViewer
* AirWatch
* `42Gears`
* Proprietäre AV-Integrator-Middleware
