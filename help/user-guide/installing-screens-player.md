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
source-git-commit: c6506ca62e806ec11d3380d6ac7670bcfcf13adb
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 36%

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


## Grundlegende Wiedergabe-Überwachung {#playback-monitoring}

Der Player meldet verschiedene Wiedergabemetriken mit jeweils `ping` , die standardmäßig 30 Sekunden betragen. Basierend auf diesen Metriken können wir verschiedene Edge-Fälle wie festes Erlebnis, leerer Bildschirm und Planungsprobleme erkennen. Dadurch können wir Probleme auf dem Gerät verstehen und beheben und so mit Ihnen eine Untersuchung und Korrekturmaßnahmen beschleunigen.

Die grundlegende Wiedergabe-Überwachung in einem AEM Screens-Player ermöglicht Folgendes:

* Remote-Überwachung, ob ein Player Inhalte ordnungsgemäß wiedergibt.

* Verbessern Sie die Reaktionsfähigkeit auf leere Bildschirme oder fehlerhafte Erlebnisse im Feld.

* Verringert das Risiko, dem Endbenutzer ein fehlerhaftes Erlebnis anzuzeigen.

### Eigenschaften {#understand-properties}

Die folgenden Eigenschaften sind in jedem `ping` enthalten:

| Eigenschaft | Beschreibung |
|---|---|
| id {string} | Player-ID |
| activeChannel {string} | derzeit den Kanalpfad wiedergeben, oder null, wenn nichts geplant ist |
| activeElements {string} | Kommagetrennte Zeichenfolge, derzeit sichtbare Elemente in allen wiedergegebenen Sequenzkanälen (mehrere bei einem Mehrzonen-Layout) |
| isDefaultContent {boolean} | &quot;true&quot;, wenn der Wiedergabekanal als Standard- oder Fallback-Kanal betrachtet wird (d. h. hat Priorität 1 und keinen Zeitplan) |
| hasContentChanged {boolean} | true , wenn der Inhalt in den letzten 5 Minuten geändert wurde, andernfalls false |
| lastContentChange {string} | Zeitstempel der letzten Inhaltsänderung |

>[!NOTE]
>Optional kann eine erweiterte Eigenschaft in den Player-Voreinstellungen (Enable Play-back Monitoring) aktiviert werden, und zwar:
>|Eigenschaft|Beschreibung|
>|—|—|
>|isContentRendering {boolean}|true , wenn die GPU bestätigen kann, dass tatsächliche Inhalte wiedergegeben werden (basierend auf der Pixelanalyse)|

### Beschränkungen {#limitations}

Im Folgenden finden Sie einige Einschränkungen bei der grundlegenden Wiedergabe-Überwachung:

* Der Player meldet dem Server seinen eigenen Wiedergabestatus, sodass eine aktive Verbindung erforderlich ist.

* Die `isContentRendering`-Eigenschaft, die die GPU prüft, ist derzeit zu ressourcenintensiv, um standardmäßig aktiviert zu werden, und erfordert eine explizite Anmeldung von den Player-Voreinstellungen. Es wird empfohlen, es nicht zusammen mit Videos in der Produktion zu verwenden.

* Diese Funktion wird nur für Sequenzkanäle unterstützt und deckt noch nicht den Anwendungsfall für interaktive Kanäle (SPA) ab.

* Die Metriken sind noch nicht vollständig für unsere Kunden verfügbar. Wir arbeiten intensiv daran, in naher Zukunft einen dashboard-ähnlichen Berichterstellungs- und Warnmechanismus zu aktivieren.

### Zusätzliche Ressourcen {#additional-resources}

In den folgenden Themen finden Sie ausführliche Informationen:

* Um Android-Player herunterzuladen, gehen Sie zu **Google Play**. Weitere Informationen zur Implementierung von Android Watchdog finden Sie unter [Implementieren des Android-Players](implementing-android-player.md).

* Weitere Informationen zur Implementierung von Chrome OS-Player finden Sie in der [Chrome Management Console](implementing-chrome-os-player.md).

* Informationen zum Konfigurieren von AEM Screens Windows Player finden Sie unter [Implementieren von Windows Player](implementing-windows-player.md).
