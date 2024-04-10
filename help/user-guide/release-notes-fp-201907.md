---
title: Versionshinweise für Feature Pack 201907
seo-title: Release Notes for Feature Pack 201907
description: Auf dieser Seite finden Sie Informationen zu AEM Screens Feature Pack 201907, das am 31. Juli 2019 veröffentlicht wurde.
seo-description: Follow this page to get information for AEM Screens Feature Pack 201907 released on July 31, 2019.
uuid: e5349c92-d532-4f04-a757-7c4545cdb074
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: release-notes
content-type: reference
discoiquuid: 826d1599-02d1-4d24-b15d-26c1ffee36a2
docset: aem65
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: 6a05a014-aedf-4261-849d-abf1ce070964
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 84%

---

# Versionshinweise für Feature Pack 201907 {#release-notes-for-feature-pack}

>[!CAUTION]
>
>Es wird empfohlen, ein Upgrade auf die neueste Version von Adobe Experience Manager (AEM) durchzuführen. Screens bietet Wartungs-Support für die AEM 6.3 Screens-Plattform.

AEM Screens hat AEM 6.4.5 Feature Pack 5 und AEM 6.5.1 Feature Pack 1 mit folgenden Details veröffentlicht.

## Veröffentlichungsdatum {#release-date}

Das Veröffentlichungsdatum für AEM Screens Feature Pack 201907 ist der 31. Juli 2019.

### Neue Funktionen {#what-s-new}

* **Datenauslöser treiben die Asset-Änderung in einem AEM Screens-Kanal**

Der Player wechselt zu einem Kanal, in dem die Notfallinformationen angezeigt werden, wenn er ein vom Notfallsystem ausgelöstes Ereignis empfängt. Es wird nur dieser Kanal wiedergegeben, bis die Notsituation beendet ist.

Siehe [Notfallkanal](emergency-channel.md) Anwendungsbeispiel für die Implementierung.

* Targeting für asynchrone Komponenten aktiviert

Targeting kann jetzt für Assets aktiviert werden, die im AEM Screens-Projekt verwendet werden.

Weitere Informationen dazu, wie Sie Targeting für Assets im AEM Screens-Projekt aktivieren können, finden Sie unter [Konfigurieren von ContextHub in AEM Screens](configuring-context-hub.md).

Nachdem Sie ContextHub für Ihr AEM Screens-Projekt konfiguriert haben, gehen Sie die verschiedenen Nutzungsszenarios durch, um zu verstehen, wie datengesteuerte Assets in verschiedenen Branchen eine wichtige Rolle spielen:

**[Zielgerichtete Aktivierung des Einzelhandelsinventars](retail-inventory-activation.md)**

**[Temperaturaktivierung für ein Reiseangebot](local-temperature-activation.md)**

**[Aktivierung der Gastgewerbereservierung](hospitality-reservation-activation.md)**

* **Verbesserungen bei den Update-Handlern**

Der Update-Handler analysiert nun die Experience Fragments und erfasst alle damit verbundenen Bilder, Videos oder Produkte.

* **Launches**

Mit Launches können Inhaltsersteller zukünftige Versionen der Kanäle erstellen. Mithilfe von Launches können Autoren die einzelnen Kanäle im Launch in der Vorschau anzeigen und sollten eine Anfrage zur Überprüfung starten können. Die Gruppe der Genehmigenden erhält eine Benachrichtigung und kann die Anfrage genehmigen oder ablehnen. Wenn das Live-Datum erreicht ist, wird der Inhalt auf den Geräten abgespielt.
Siehe [Launches](launches.md) für weitere Details.

* **Offline-Konfigurationen in Experience Fragments**

Sie können jetzt Offline-Konfigurationen (Client-seitige Bibliotheken und statische Dateien) beim Konfigurieren eines Screens-Experience-Fragments hinzufügen. Siehe [Verwenden von Experience Fragments](experience-fragments-in-screens.md) für weitere Details.

### Veröffentlichte AEM Screens-Player {#released-aem-screens-players}

Die folgenden AEM Screens-Player sind für AEM 6.4.5 Feature Pack 5 und AEM 6.5.1 Feature Pack 1 verfügbar:

* ChromeOS
* Windows
* Android

#### AEM Screens-Player-Downloads   {#aem-screens-player-downloads}

Informationen zum Herunterladen des neuesten AEM Screens-Players und zu weiteren Fehlerbehebungen finden Sie unter [AEM Screens Player-Downloads](https://download.macromedia.com/screens/).
