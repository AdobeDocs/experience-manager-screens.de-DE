---
title: Datenauslöser
description: Erfahren Sie mehr über Daten-Trigger in AEM Screens.
exl-id: 23c4268e-48be-4c84-b5eb-c96152b166f7
TQID: https://experienceleague.adobe.com/oeJ7C6Rt8-Z9sFnEP1S1tn0VW4PuiKkXkeDYaz8Vd4s
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: eb3ad9f8-54a2-45f3-abb1-d3976415a718
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 0b0bfcd803c3da9298122200a0a1715fc2d5e49c
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 100%

---

# Dynamic Creative Optimization {#dynamic-creative}

>[!NOTE]
>
>Ein typischer Stakeholder für diese Aktivität ist eine Person, die AEM implementiert.

**Dynamic Creative Optimization** oder DCO dient dem Erstellen von Digital-Signage-Erlebnissen, die den individuellen Bedingungen eines bestimmten Standorts zu einer bestimmten Zeit sowie für bestimmte Benutzende gerecht werden.

Dies wird auch als Client-seitige Reduzierung von Inhalten bezeichnet.

So soll sichergestellt werden, dass jedes Player-Gerät bzw. jeder Endpunkt Datensätze verwenden kann, um anhand verschiedener Faktoren den besten Inhalt zu bestimmen, der automatisch wiedergegeben werden soll.

Durch diese Funktionalität erübrigt sich ein ständiges manuelles Eingreifen bei der Inhaltserstellung. Darüber hinaus trägt sie dazu bei, die Gesamtbetriebskosten für das Netzwerk zu reduzieren und digitale Erlebnisse relevanter, kontextbezogener und effektiver zu gestalten.

Beispiele dafür sind:

* Verwendung des aktuellen Lagerbestands der präsentierten Produkte
* Außentemperatur oder Wetter
* Vorhandensein einer Anzeigenkampagne in lokalen Medien
* Webtraffic und auch lokale Ereignisse, z. B. wenn ein Kunde ein Produkt zur Prüfung in die Hand nimmt

All diese und weitere Beispiele können für mehr Kontext und Personalisierung sorgen.

Wer über eine Strategie für visuelles Merchandising verfügt, die DCO beinhaltet, kann die Zahl der Betrachter im Netzwerk drastisch erhöhen.

Es gibt zwei Hauptarten von Datenauslösern:

* **Lokale Datenauslöser**: Diese Datenauslöser befinden sich lokal auf dem Gerät. Wenn Sie etwa den Bildschirm berühren, wird ein Sensor aktiviert, der einen lokalen Daten-Asset- oder Kanalwechsel auslöst.
* **Remote-Datenauslöser**: Dies beinhaltet einen durch Daten ausgelösten Kanalwechsel bzw. einen Asset-Wechsel, je nach den von einer Webservice-API zurückgegebenen Werten.
