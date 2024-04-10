---
title: Installieren des Screens-Players
seo-title: Installing Screens Player
description: Auf dieser Seite erfahren Sie mehr über die Installation des verfügbaren AEM Screens-Players.
seo-description: Installing Screens Player
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 92%

---

# Installieren des AEM Screens-Players {#installing-player}

Auf dieser Seite wird die Installation des AEM Screens-Players beschrieben.

## Verfügbarer Screens-Player {#available-players}

Der AEM Screens-Player ist für Android, Chrome OS und Windows verfügbar.

Um einen **AEM Screens-Player** herunterzuladen, rufen Sie die Seite [AEM 6.5 Player-Downloads](https://download.macromedia.com/screens/) auf.

>[!NOTE]
>
>Nachdem Sie den aktuellen Player (*.exe*) heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:
>
>1. Halten Sie die linke obere Ecke gedrückt, um den Admin-Bereich zu öffnen.
>1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie die Standortadresse der AEM-Instanz unter **Server** ein und klicken Sie auf **Speichern**.
>1. Klicken Sie im linken Aktionsmenü auf den Link **Registrierung** und führen Sie die folgenden Schritte aus, um die Geräteregistrierung abzuschließen.

## Einfache Wiedergabe-Überwachung {#playback-monitoring}

Mit jedem `ping` (standardmäßig alle 30 Sekunden) meldet der Player verschiedene Wiedergabemetriken. Basierend auf diesen Metriken können wir verschiedene Randfälle wie steckengebliebenes Erlebnis, leerer Bildschirm und Terminprobleme erkennen. Auf diese Weise können wir Probleme auf dem Gerät verstehen und beheben und somit gemeinsam mit Ihnen durchgeführte Untersuchungen und Abhilfemaßnahmen beschleunigen.

Eine einfache Wiedergabe-Überwachung in einem AEM Screens-Player ermöglicht Folgendes:

* Fernüberwachung, ob ein Player Inhalte ordnungsgemäß wiedergibt.

* Verbessern der Reaktionsfähigkeit auf leere Bildschirme oder fehlerhafte Erlebnisse im Feld.

* Verringerung des Risikos, dem Endbenutzer ein fehlerhaftes Erlebnis anzuzeigen.

### Grundlegendes zu Eigenschaften {#understand-properties}

Die folgenden Eigenschaften sind in jedem `ping` enthalten:

| Eigenschaft | Beschreibung |
|---|---|
| id {Zeichenfolge} | die Player-Kennung |
| activeChannel {Zeichenfolge} | der derzeit wiedergebende Kanalpfad, oder null, wenn nichts geplant ist |
| activeElements {Zeichenfolge} | Kommagetrennte Zeichenfolge, derzeit sichtbare Elemente in allen wiedergegebenen Sequenzkanälen (mehrere bei einem Mehrzonen-Layout) |
| isDefaultContent {Boolesch} | „true“, wenn der Wiedergabekanal als Standard- oder Fallback-Kanal betrachtet wird (d. h. hat Priorität 1 und keinen Zeitplan) |
| hasContentChanged {Boolesch} | „true“, wenn der Inhalt in den letzten 5 Minuten geändert wurde, andernfalls „false“ |
| lastContentChange {Zeichenfolge} | Zeitstempel der letzten Inhaltsänderung |

>[!NOTE]
>Optional kann eine erweiterte Eigenschaft in den Player-Voreinstellungen (Wiedergabeüberwachung aktivieren) aktiviert werden, und zwar:
>|Eigenschaft|Beschreibung|
>|---|---|
>|isContentRendering {Boolesch}|„true“, wenn die GPU bestätigen kann, dass tatsächliche Inhalte wiedergegeben werden (basierend auf der Pixelanalyse)|

### Beschränkungen {#limitations}

Im Folgenden finden Sie einige Beschränkungen bei der einfachen Wiedergabeüberwachung:

* Der Player meldet dem Server seinen eigenen Wiedergabestatus, sodass eine aktive Verbindung erforderlich ist.

* Die `isContentRendering`-Eigenschaft, die die GPU prüft, ist derzeit zu ressourcenintensiv, als dass sie standardmäßig aktiviert werden könnte, und erfordert eine explizite Anmeldung aus den Player-Voreinstellungen heraus. Es wird empfohlen, sie nicht zusammen mit Videos in der Produktion zu verwenden.

* Diese Funktion wird nur für Sequenzkanäle unterstützt und deckt noch nicht den Anwendungsfall für interaktive Kanäle (SPA) ab.

* Die Metriken sind noch nicht vollständig für unsere Kunden verfügbar. Wir arbeiten intensiv daran, in naher Zukunft einen Dashboard-ähnlichen Reporting- und Warnmechanismus zu ermöglichen.

### Zusätzliche Ressourcen {#additional-resources}

Detaillierte Informationen finden Sie in den folgenden Themen:

* Um Android-Player herunterzuladen, gehen Sie zu **Google Play**. Weitere Informationen zur Implementierung von Android Watchdog finden Sie unter [Implementieren des Android-Players](implementing-android-player.md).

* Informationen zur Implementierung des Chrome OS-Players finden Sie unter [Chrome Management Console](implementing-chrome-os-player.md) für weitere Informationen.

* Informationen zum Konfigurieren des AEM Screens Windows-Players finden Sie unter [Implementieren von Windows Player](implementing-windows-player.md).
