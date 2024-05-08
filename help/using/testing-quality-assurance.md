---
title: Tests und Qualitätssicherung
description: Weitere Informationen zu Tests und Qualitätssicherung für AEM Screens finden Sie im Best Practices-Handbuch.
exl-id: cc3bfb88-1341-43f8-b247-6a41f1d1a963
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 50%

---

# Tests und Qualitätssicherung {#testing-quality}

>[!NOTE]
>Typische Verantwortliche für diese Aktivität sind Audio-/Video-Integratoren.

Wenn Sie sich der Bereitstellung des Digital Signage-Netzwerks nähern, erstellen Sie einen Test- und QA-Plan, der alle Elemente des Netzwerks einschließlich aller Hardwarekomponenten, Softwarekomponenten und Netzwerkkomponenten abdeckt.
In dem Schritt sollten vollständige Prüfsysteme eingerichtet und gründlich getestet werden.

Es sollte eine Checkliste erstellt werden, in der alle zuvor definierten KPIs aufgeführt und die Lieferziele anhand dieser KPIs gemessen werden.

>[!NOTE]
>
>Dieser Schritt sollte auch zur Erstellung eines Installations- und Benutzerhandbuchs genutzt werden, das später mit dem Gerät ausgeliefert und für künftige Referenzzwecke vor Ort aufbewahrt werden kann.

Folgende Elemente sollten berücksichtigt werden:

## 1. Mechanische Aspekte {#mechanical-considerations}

Folgende Überlegungen in Bezug auf die Mechanik werden empfohlen:

* Display-Montage
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

Ausführliche Informationen zu ***Gerätesteuerung***, siehe [Problembehebung in der Gerätesteuerung](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/troubleshooting/monitoring-screens) in **AEM Screens-Benutzerhandbuch**.

>[!CAUTION]
>
>Verwenden Sie das Device Control Center nicht für:
>
>* Neue Versionen der Player-Anwendung installieren
>* Ressourcen auf Systemebene überwachen
>* Fehler auf der Systemebene beheben
>* Remote Desktop-Eingriffe zulassen


>[!NOTE]
>
> Adobe empfiehlt die Verwendung von dedizierten Geräteverwaltungsplattformen von Drittanbietern für alle Implementierungen.

Die gewählte Plattform hängt von verschiedenen Faktoren ab, darunter dem ***Zielbetriebssystem***, ***Projektanforderungen***, und ***Anzahl der Endpunkte***.

Nachfolgend finden Sie einige Beispiele:

* Google Chrome-Geräteverwaltung
* TeamViewer
* AirWatch
* `42Gears`
* Proprietäre Audio-/Video-Integrator-Middleware
