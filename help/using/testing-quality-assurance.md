---
title: Tests und Qualitätssicherung
seo-title: Tests und Qualitätssicherung für AEM Screens
description: Auf dieser Seite werden die Best Practices für Tests und die Qualitätssicherung von AEM Screens beschrieben.
seo-description: Auf dieser Seite werden die Best Practices für Tests und die Qualitätssicherung von AEM Screens beschrieben.
translation-type: tm+mt
source-git-commit: f25176be89424059b8c51296969f069687328536
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 93%

---


# Tests und Qualitätssicherung {#testing-quality}

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind A/V-Integratoren.

Da wir uns der realen Implementierung des Netzwerks für digitale Beschilderung nähern, sollten wir einen Test- und QA-Plan erstellen, der alle Elemente des Netzwerks einschließlich der Hardwarekomponenten, Softwarekomponenten und Netzwerkkomponenten umfasst.
In dem Schritt sollten vollständige Prüfsysteme eingerichtet und gründlich getestet werden.

Es sollte eine Checkliste erstellt werden, in der alle zuvor definierten KPIs aufgeführt und anhand der entsprechenden Lieferziele gemessen werden.

>[!NOTE]
>
>Dieser Schritt sollte auch zur Erstellung eines Installations- und Benutzerhandbuchs genutzt werden, das später mit dem Gerät ausgeliefert und für künftige Referenzzwecke vor Ort aufbewahrt werden kann.

Folgende Elemente sollten berücksichtigt werden:

## 1. Mechanische Aspekte {#mechanical-considerations}

Folgende Überlegungen in Bezug auf die Mechanik werden empfohlen:

* Displaymontage
* Player-Montage
* Lüftung
* Peripheriegeräte
* Kabelmanagement
* Gerätenetzwerk

## 2. Software-Aspekte {#software-considerations}

Folgende Überlegungen in Bezug auf die Software werden empfohlen:

* Geräteregistrierung
* Media Publishing
* Wiedergabe
* Datenbankabhängigkeiten (zuvor definiert)


## 3. Aspekte der Geräteverwaltung {#device-management-considerations}


AEM Screens enthält ein Gerätesteuerungsmodul, das die Verwaltung von Endgeräten mit der Screens Player-Anwendung ermöglicht.

Dies bezieht sich auf alle *Player*-Hardwaregeräte, auf denen die Screens Player-Anwendung installiert ist und die für eine AEM-Instanz registriert sind.
Mit diesem Modul können Sie:

1. Anwendungsfehlerprotokolle des Players überwachen
1. Remote-Screenshots verwalten
1. Inhaltsdownloads verwalten
1. Probleme beim Neustart der Anwendung beheben

Ausführliche Informationen zur ***Gerätesteuerung*** finden Sie im Abschnitt [Problembehandlung in der Gerätesteuerung](https://helpx.adobe.com/experience-manager/6-5/screens/using/monitoring-screens.html) des **AEM Screens-Benutzerhandbuchs**.

>[!CAUTION]
>
> Verwenden Sie die Gerätesteuerung nicht für Folgendes:
>
> 1. Neue Versionen der Player-Anwendung installieren
> 1. Ressourcen auf Systemebene überwachen
> 1. Fehler auf der Systemebene beheben
> 1. Remote Desktop-Eingriffe zulassen



>[!NOTE]
>
> Adobe empfiehlt, für alle Bereitstellungen dedizierte Drittanbieter-Geräteverwaltungsplattformen zu verwenden.

The specific platform chosen depends on a number of factors including the ***target operating system***, ***project requirements*** and ***number of end points***.

Beispiele:

* Google Chrome-Geräteverwaltung
* TeamViewer
* AirWatch
* 42Gears
* Proprietäre AV-Integrator-Middleware
