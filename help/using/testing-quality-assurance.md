---
title: Tests und Qualitätssicherung
seo-title: Tests und Qualitätssicherung für AEM Screens
description: Auf dieser Seite werden die Best Practices für Tests und die Qualitätssicherung von AEM Screens beschrieben.
seo-description: Auf dieser Seite werden die Best Practices für Tests und die Qualitätssicherung von AEM Screens beschrieben.
translation-type: tm+mt
source-git-commit: 12b1cc4f2b359742966c2073d233b0113459e2de

---


# Tests und Qualitätssicherung {#testing-quality}

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind A/V-Integratoren.

Da wir uns der realen Implementierung des Digital Signage-Netzwerks nähern, sollten wir einen Test- und QA-Plan erstellen, der alle Elemente des Netzwerks einschließlich der Hardwarekomponenten, Softwarekomponenten und Netzwerkkomponenten umfasst.
In dem Schritt sollten vollständige Prüfsysteme eingerichtet und gründlich getestet werden.

Es sollte eine Checkliste erstellt werden, in der alle zuvor definierten KPIs aufgeführt und anhand der entsprechenden Lieferziele gemessen werden.

Folgende Elemente sollten berücksichtigt werden:

## 1. Mechanische Überlegungen {#mechanical-considerations}

Folgende mechanische Aspekte werden empfohlen:

* Displaymontage
* Player-Montage
* Lüftung
* Peripheriegeräte
* Kabelmanagement
* Gerätenetzwerk

## 2. Überlegungen zur Software {#software-considerations}

Die folgenden Softwareüberlegungen werden empfohlen:

* Geräteregistrierung
* Media Publishing
* Wiedergabe
* Datenbankabhängigkeiten (zuvor definiert)

>[!NOTE]
> Dieser Schritt sollte auch zur Erstellung eines Installations- und Benutzerhandbuchs genutzt werden, das später mit dem Gerät ausgeliefert und für künftige Referenzzwecke vor Ort aufbewahrt werden kann.

## 3. Überlegungen zur Geräteverwaltung {#device-management-considerations}


AEM Screens enthält ein Device Control Center-Modul, das die Verwaltung von Screens Player-Endpunkten ermöglicht.

Dies bezieht sich auf alle *Player* -Hardwaregeräte, auf denen die Bildschirmplayer-Anwendung installiert ist und die für eine AEM-Instanz registriert sind.
Dieses Modul ermöglicht Ihnen Folgendes:

1. Anwendungsfehlerprotokolle überwachen
1. Remote-Screenshots verwalten
1. Verwalten von Inhaltsdownloads
1. Anwendungsneustarts

>[!CAUTION]
> SIE SOLLTEN DAS Gerätesteuerungscenter NICHT VERWENDEN, UM:
>
> 1. Neue Versionen der Player-Anwendung installieren
> 1. Systemebene überwachen
> 1. Konfigurationen auf Systemebene konfigurieren
> 1. Remote-Eingreifen des Desktop zulassen.



>[!NOTE]
> Adobe empfiehlt, dass für alle Bereitstellungen dedizierte Drittanbieter-Geräteverwaltungsplattformen verwendet werden sollten.

Die gewählte Plattform hängt von einer Reihe von Faktoren ab, darunter dem ***Zielbetriebssystem***, den ***Projektanforderungen*** und der ***Anzahl der Endpunkte***.

Einige Beispiele sind:

* Google Chrome-Geräteverwaltung
* TeamViewer
* AirWatch42
* Geflügel
* Soti