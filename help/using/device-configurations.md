---
title: Gerätespezifikationen
description: Erfahren Sie mehr über Gerätespezifikationen im Zusammenhang mit AEM Screens.
exl-id: c2e521b3-89f5-4537-a751-0bfa031286c4
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: ht
source-wordcount: '211'
ht-degree: 100%

---

# Gerätekonfigurationen {#device-configurations}

>[!NOTE]
>
>Ein typischer Stakeholder für diese Aktivität ist eine Person, die Audio-Video-Integration betreibt.

Beantworten Sie vor Beginn der Entwicklung unter Einsatz der an *Tag 0* gesammelten Informationen folgende Fragen:

* Welche Ausrichtung, Abmessungen und Auflösung haben die verwendeten Bildschirme?

* Wie viele Bildschirme werden pro Standort installiert? Und in welcher Konfiguration?

* Welche Software und welches Betriebssystem müssen auf den Anzeigegeräten installiert sein?

* Ist für Player eine Internet-Verbindung erforderlich, damit sich die Bildschirme mit AEM-Servern synchronisieren lassen?

* Wann werden Inhalte auf Playern aktualisiert?

* Wenn Sie Videos wiedergeben, müssen Sie die Spezifikationen Ihres Geräts kennen, damit sich Inhalte korrekt anzeigen lassen.

* Ist mit Blick auf die genannten Umgebungsaspekte eher Solid-State- oder Festplattenspeicher angemessen?

* Ermitteln Sie, wie viel Speicherkapazität und -leistung Sie benötigen. Beispiele:
   * Gibt es bei Ihnen besondere Speicherüberlegungen (mehrere Laufwerke, Bootgeräte vs. Massenspeicher)?
   * Welche RAM-Kapazitäten benötigen Sie?


>[!NOTE]
>
>Außerdem müssen Sie die Spezifikationen der ausgewählten Hardware prüfen, um sicherzustellen, dass diese die in Entwicklung befindliche Anwendung unterstützen kann. Wenn die Anwendung zum Beispiel fünf High-Definition-Videos gleichzeitig ausführen soll: Ist das mit der Hardware möglich?
