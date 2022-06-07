---
title: Implementieren der Fernbedienungs-Steuerung
seo-title: Impementing the Remote Control
description: Auf dieser Seite erfahren Sie mehr über die Fernbedienungs-Steuerung von Screens.
seo-description: Follow  this page to learn about using the Screens Remote Control Feature.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 6cb2705e-83e6-46f3-bd71-6688d7edc11f
source-git-commit: 6cd68194bf3128464ec368f3e7fd69d20925c3d6
workflow-type: ht
source-wordcount: '354'
ht-degree: 100%

---

# Verwenden der Fernbedienungs-Steuerung von Screens  {#implementing-remote-control}

Die Fernbedienungs-Steuerung erleichtert den Zugriff auf die Admin-Benutzeroberfläche, den Kanalumschalter oder Funktionen wie „Cache löschen“ und „Neu laden“. Außerdem bietet sie Ihnen eine Methode, die lokale Firmware-Version und Systeminformationen auf dem Player anzuzeigen. Dies ist besonders nützlich, da es schwierig sein kann, eine Maus anzuschließen und auf Produktionsgeräten zu arbeiten, die außer Reichweite sind, und umso mehr, wenn der Player die Verbindung zu AEM verloren hat. Dies ist auch bei der Verwendung von Samsung RMS nützlich, da es aufgrund der unterschiedlichen Auflösung sehr schwierig sein kann, die Admin-Benutzeroberfläche mit einer Maus zu finden und zu öffnen.

## Gängige Tastenkombinationen für die Fernbedienungs-Steuerung {#using-common-remote-control}

Auf allen Playern können Sie die folgenden Tastenkombinationen in der Fernbedienungs-Steuerung von Screens verwenden:

1. Admin-Benutzeroberfläche ein/aus - STRG+1
1. Kanalumschalter ein/aus - STRG+2
1. Cache löschen - STRG+ALT+3
1. Player neu laden - STRG+4

## Tizen-spezifische Tastenkombinationen für die Fernbedienungs-Steuerung {#using-tizen-remote-control}

Speziell für den Tizen-Player können Sie entweder die Hardware-Fernbedienung oder die in Samsung RMS verfügbare Software-Fernbedienung verwenden, um auf diese Funktionen zuzugreifen:

1. A - Admin-Benutzeroberfläche ein/aus
1. B - Kanalumschalter ein/aus
1. C - Cache löschen
1. D - Player neu laden

## Zusätzliche Nutzungshinweise {#using-additional-remote-control}

1. Wenn die Admin-Benutzeroberfläche geöffnet ist, können Sie mit den Pfeiltasten nach oben und unten durch die Registerkarten navigieren, um Informationen auf den verschiedenen Registerkarten anzuzeigen.
1. Wenn der Kanalumschalter geöffnet ist, können Sie mit den Pfeiltasten nach oben und unten durch die Kanäle navigieren und die Eingabetaste (oder die Taste in der Mitte der Pfeile auf der Fernbedienung) drücken, um den Kanal zu wechseln.

Die folgende Abbildung veranschaulicht die Verwendung der Tasten auf einer Samsung-Fernbedienung:
![image](assets/tizen/remote.png)

>[!NOTE]
>Wenn Sie die Gerätekonfigurationswerte von enableAdminUI und/oder enableOSD auf „false“ setzen, werden die Admin-Benutzeroberfläche und der Kanalumschalter durch die Fernbedienung nicht ein-/ausgeschaltet. Sie können dann auch nicht mit den Pfeiltasten in der Admin-Benutzeroberfläche oder in den Kanälen navigieren. Sie können jedoch weiterhin den Cache löschen und den Player neu laden. Sie können die Fernbedienungs-Steuerungsfunktion deaktivieren, wenn eine der Tastenkombinationen mit Ihren interaktiven Inhalten in Konflikt steht, indem Sie diesen Code verwenden:

```
require(['util/ScreensDisplay'], function() {window.ScreensDisplay.ignoreRemoteControl = true;}); 
```
