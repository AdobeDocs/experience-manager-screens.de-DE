---
title: Versionshinweise für Feature Pack 202008
description: „Auf dieser Seite finden Sie Informationen zu AEM Screens Feature Pack 202008, das am Donnerstag, 3. September 2020 veröffentlicht wurde.“
feature: Feature Pack
role: Developer
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 100%

---


# Versionshinweise für Feature Pack 202008 {#release-notes-for-feature-pack}

>[!CAUTION]
>
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

## Verfügbarkeit {#availability}

Das AEM 6.5 Feature Pack 5 wurde für AEM Screens veröffentlicht.

Das neueste Feature Pack für AEM Screens 6.5.5 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). Navigieren Sie zur Registerkarte **Adobe Experience Manager** und suchen Sie nach **Screens**, um das neueste Feature Pack herunterzuladen.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 202008 ist Donnerstag, 3. September 2020.

### Neue Funktionen {#what-is-new}

* **Timeline-Ansicht im Zeitplan-Dashboard**

   Die Timeline-Ansicht ermöglicht es dem Benutzer, die dem Kanal zugewiesenen Zeitpläne über das Anzeigen-Dashboard anzuzeigen.

   Weitere Informationen finden Sie unter [Timeline-Ansicht](/help/user-guide/channel-assignment-latest-fp.md#timeline-view).

* **Intervallzeitplan**

   Mit dem Intervallzeitplan können Sie einen Zeitplan für Ihren Kanal festlegen. Sie richten mehrere Intervallzeitpläne für einen Kanal ein.

   Weitere Informationen finden Sie unter [Intervallzeitplan](/help/user-guide/channel-assignment-latest-fp.md#recurrence-schedule).

* **Spracherkennungsfunktionen für AEM Screens**

   Die Spracherkennungsfunktion ermöglicht Inhaltsänderungen in einem AEM Screens-Kanal via Sprachinteraktionen.

   Ein Inhaltsautor kann eine Anzeige so konfigurieren, dass sie sprachaktiviert ist. Diese Funktion soll Kunden die Möglichkeit geben, Sprache als Methode der Interaktion mit ihren Anzeigen zu verwenden.

   Weitere Informationen finden Sie unter [Spracherkennung](voice-recognition.md).

### Bekannte Probleme und Fehlerbehebungen {#known-issues}

Wenn Sie das AEM Screens 6.5.5 Service Pack verwenden, müssen Sie eine Umgebung für den Windows- oder Android-Player einrichten.

Setzen Sie in der **Konfiguration der Adobe Experience Manager-Web-Konsole** das **SameSite-Attribut für die Anmeldungs-Token-Cookies** auf allen AEM-Autoren- und Veröffentlichungsinstanzen von **Lax** auf **Keine**.

* Weitere Informationen finden Sie unter [Implementieren von Windows 10 Player](implementing-windows-player.md#fp-environment-setup).

* Weitere Informationen finden Sie unter [Implementieren des Android Players](implementing-android-player.md#fp-environment-setup).

### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM Screens 6.5 Feature Pack 5 verfügbar.

* Chrome OS
* Windows
* Android

#### AEM Screens-Player-Downloads {#aem-screens-player-downloads}

Navigieren Sie zu **[AEM Screens-Player-Downloads](https://download.macromedia.com/screens/index.html)**, um den neusten AEM Screens-Player herunterzuladen und mehr über die Fehlerbehebungen zu erfahren.
