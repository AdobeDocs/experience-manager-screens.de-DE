---
title: Tests und Qualitätssicherung
description: Erfahren Sie mehr über die Best Practices für Tests und die Qualitätssicherung von AEM Screens.
exl-id: cc3bfb88-1341-43f8-b247-6a41f1d1a963
TQID: https://experienceleague.adobe.com/So83gHv7n21zhdoCdWHVf0yswyQuSr1hLWmCA7uHSiE
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 0b0bfcd803c3da9298122200a0a1715fc2d5e49c
workflow-type: tm+mt
source-wordcount: 346
ht-degree: 97%

---

# Tests und Qualitätssicherung {#testing-quality}

>[!NOTE]
>Ein typischer Stakeholder für diese Aktivität ist eine Person, die Audio-Video-Integration betreibt.

Wenn die Bereitstellung des Digital-Signage-Netzwerks Beschilderung näher rückt, sollten Sie einen Test- und QA-Plan erstellen, der alle Elemente des Netzwerks, einschließlich der Hardware-, Software- und Netzwerkkomponenten, umfasst.
In dem Schritt sollten vollständige Prüfsysteme eingerichtet und gründlich getestet werden.

Es sollte eine Checkliste erstellt werden, in der alle zuvor definierten KPIs aufgeführt und anhand der entsprechenden Lieferziele gemessen werden.

>[!NOTE]
>
>Diese Phase sollte auch zur Erstellung eines Installations- und Benutzerhandbuchs dienen. Beide können später mit dem Gerät ausgeliefert und für künftige Referenzzwecke vor Ort aufbewahrt werden.

Folgende Elemente sollten berücksichtigt werden:

## &#x200B;1. Mechanische Aspekte {#mechanical-considerations}

Folgende Überlegungen in Bezug auf die Mechanik werden empfohlen:

* Display-Montage
* Player-Montage
* Lüftung
* Peripheriegeräte
* Kabelmanagement
* Gerätenetzwerk

## &#x200B;2. Überlegungen zur Software {#software-considerations}

Folgende Überlegungen in Bezug auf die Software werden empfohlen:

* Geräteregistrierung
* Media Publishing
* Wiedergabe
* Datenbankabhängigkeiten (zuvor definiert)


## &#x200B;3. Überlegungen zur Geräteverwaltung {#device-management-considerations}

AEM Screens enthält das Modul „Geräte-Kontrollzentrum“, das die Verwaltung von Screens Player-Anwendungsendpunkten ermöglicht.

Dies bezieht sich auf alle *Player*-Hardware-Geräte, auf denen die Screens Player-Anwendung installiert ist und die bei einer AEM-Instanz registriert sind.
Mit diesem Modul können Sie:

1. Anwendungsfehlerprotokolle des Players überwachen
1. Remote-Screenshots verwalten
1. Inhalts-Downloads verwalten
1. Probleme beim Neustart der Anwendung beheben

Ausführliche Informationen zum ***Geräte-Kontrollzentrum*** finden Sie im Abschnitt [Problembehebung über das Geräte-Kontrollzentrum](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/troubleshooting/monitoring-screens) des **AEM Screens-Benutzerhandbuchs**.

>[!CAUTION]
>
>Verwenden Sie das Geräte-Kontrollzentrum nicht für folgende Vorgänge:
>
>* Neue Versionen der Player-Anwendung installieren
>* Ressourcen auf Systemebene überwachen
>* Fehler auf der Systemebene beheben
>* Remote Desktop-Eingriffe zulassen


>[!NOTE]
>
> Adobe empfiehlt, für alle Bereitstellungen dedizierte Drittanbieter-Geräteverwaltungsplattformen zu verwenden.

Die gewählte Plattform hängt von einer Reihe von Faktoren ab, darunter dem ***Zielbetriebssystem***, den ***Projektanforderungen*** und der ***Anzahl der Endpunkte***.

Nachfolgend finden Sie einige Beispiele:

* Google Chrome-Geräteverwaltung
* TeamViewer
* AirWatch
* `42Gears`
* Proprietäre Audio-Video-Integrator-Middleware
