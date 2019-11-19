---
title: Tests und Qualitätssicherung
seo-title: Tests und Qualitätssicherung für AEM Screens
description: Auf dieser Seite werden die Best Practices für Tests und die Qualitätssicherung von AEM Screens beschrieben.
seo-description: Auf dieser Seite werden die Best Practices für Tests und die Qualitätssicherung von AEM Screens beschrieben.
translation-type: tm+mt
source-git-commit: d5eb9fadffcc41ede9b1f9399c5edbeac3363954

---


# Tests und Qualitätssicherung {#testing-quality}

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind A/V-Integratoren.

Da wir uns der realen Implementierung des Digital Signage-Netzwerks nähern, sollten wir einen Test- und QA-Plan erstellen, der alle Elemente des Netzwerks einschließlich der Hardwarekomponenten, Softwarekomponenten und Netzwerkkomponenten umfasst.
In dem Schritt sollten vollständige Prüfsysteme eingerichtet und gründlich getestet werden.

Es sollte eine Checkliste erstellt werden, in der alle zuvor definierten KPIs aufgeführt und anhand der entsprechenden Lieferziele gemessen werden.

>[!NOTE]
> Dieser Schritt sollte auch zur Erstellung eines Installations- und Benutzerhandbuchs genutzt werden, das später mit dem Gerät ausgeliefert und für künftige Referenzzwecke vor Ort aufbewahrt werden kann.

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


## 3. Überlegungen zur Geräteverwaltung {#device-management-considerations}


AEM Screens enthält ein Device Control Center-Modul, das die Verwaltung von Screens Player-Endpunkten ermöglicht.

Dies bezieht sich auf alle *Player* -Hardwaregeräte, auf denen die Bildschirmplayer-Anwendung installiert ist und die für eine AEM-Instanz registriert sind.
Dieses Modul ermöglicht Ihnen Folgendes:

1. Fehlerprotokolle der Player-Anwendung
1. Remote-Screenshots verwalten
1. Verwalten von Inhaltsdownloads
1. Probleme beim Neustart von Anwendungen verwalten

Ausführliche Informationen zum ***Gerätesteuerungszentrum*** finden Sie im Benutzerhandbuch[zu ](https://helpx.adobe.com/experience-manager/6-5/screens/using/monitoring-screens.html)AEM Screens unter **Fehlerbehebung im Gerätesteuerungszentrum** .

>[!CAUTION]
> Sie sollten Device Control Center nicht verwenden, um:
>
> 1. Neue Versionen der Player-Anwendung installieren
> 1. Systemebene überwachen
> 1. Fehlerbehebung bei Fehlern auf Systemebene
> 1. Remote-Desktop-Intervention zulassen



>[!NOTE]
> Adobe empfiehlt, dass für alle Bereitstellungen dedizierte Drittanbieter-Geräteverwaltungsplattformen verwendet werden sollten.

Die gewählte Plattform hängt von einer Reihe von Faktoren ab, darunter dem ***Zielbetriebssystem***, den ***Projektanforderungen*** und der ***Anzahl der Endpunkte***.

Einige Beispiele sind:

* Google Chrome-Geräteverwaltung
* TeamViewer
* AirWatch
* 42Gears
* proprietäre AV Integrator Middleware
