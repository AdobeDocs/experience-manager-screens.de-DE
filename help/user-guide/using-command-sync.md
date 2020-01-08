---
title: Verwenden der Befehlssynchronisierung
seo-title: Verwenden der Befehlssynchronisierung
description: Auf dieser Seite erfahren Sie, wie Sie die Befehlssynchronisierung verwenden.
seo-description: Auf dieser Seite erfahren Sie, wie Sie die Befehlssynchronisierung verwenden.
translation-type: tm+mt
source-git-commit: 8f9ede8681c8c23cefa66c1177e2761ed8aae2fd

---


# Verwenden der Befehlssynchronisierung {#using-command-sync}

Auf der folgenden Seite wird die Verwendung der Befehlssynchronisierung beschrieben. Die automatische Synchronisierung ermöglicht die synchronisierte Wiedergabe über verschiedene Player hinweg. Die Player können unterschiedliche Inhalte wiedergeben, aber jedes Asset muss dieselbe Dauer haben.

## Überblick {#overview}

Lösungen für digitale Schilder müssen Videowände und synchronisierte Wiedergabe unterstützen, um Szenarien wie Jahreszählungen oder große Videoschnitte zu unterstützen, die über mehrere Bildschirme verteilt abgespielt werden können. In diesem Fall wird die Inhaltssynchronisierung sofort abgespielt.

Um die Inhaltssynchronisierung zu verwenden, fungiert ein Player als *Master* und sendet Befehl, und alle anderen Player agieren als *Clients* und spielen, wenn sie den Befehl erhalten. Der *Master* sendet einen Befehl an alle registrierten Clients, wenn er die Wiedergabe eines Elements gerade startet. Die Nutzlast kann der Index des wiederzugebenden Elements und/oder der äußere HTML-Code des abzuspielenden Elements sein.



