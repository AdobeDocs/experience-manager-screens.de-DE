---
title: Installieren des Screens-Players
description: Erfahren Sie, wie Sie einen AEM Screens-Player ordnungsgemäß installieren.
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: ht
source-wordcount: '503'
ht-degree: 100%

---

# Installieren eines AEM Screens-Players {#installing-player}

Auf dieser Seite wird die Installation eines AEM Screens-Players beschrieben.

## Verfügbarer Screens-Player {#available-players}

Der AEM Screens-Player ist für Android™, Chrome OS und Windows verfügbar.

Um einen **AEM Screens-Player** herunterzuladen, rufen Sie die Seite [AEM 6.5 Player-Downloads](https://download.macromedia.com/screens/) auf.

>[!NOTE]
>
>Nachdem Sie den aktuellen Player (*.exe*) heruntergeladen haben, folgen Sie den Schritten im Player, um die Ad-hoc-Installation abzuschließen:
>
>1. Halten Sie die linke obere Ecke eine Weile gedrückt, um das Admin-Bedienfeld zu öffnen.
>1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie die Speicherortadresse der AEM-Instanz unter **Server** ein und klicken Sie auf **Speichern**.
>1. Klicken Sie im linken Aktionsmenü auf den Link **Registrierung** und führen Sie die Schritte darunter aus, um die Geräteregistrierung abzuschließen.

## Einfache Wiedergabe-Überwachung {#playback-monitoring}

Mit jedem `ping` (standardmäßig alle 30 Sekunden) meldet der Player verschiedene Wiedergabemetriken. Basierend auf diesen Metriken können wir verschiedene Randfälle wie Feststecken, leerer Bildschirm und Terminprobleme erkennen. Auf diese Weise können wir Probleme auf dem Gerät verstehen und beheben, was die Untersuchung und die Abhilfemaßnahmen für Sie beschleunigt.

Die grundlegende Überwachung der Wiedergabe in einem AEM Screens-Player ermöglicht Folgendes:

* Fernüberwachung, ob ein Player Inhalte ordnungsgemäß wiedergibt.

* Verbessern der Reaktionsfähigkeit auf leere Bildschirme oder fehlerhafte Erlebnisse im Feld.

* Verringerung des Risikos, dem Endbenutzer ein fehlerhaftes Erlebnis anzuzeigen.

### Grundlegendes zu Eigenschaften {#understand-properties}

Die folgenden Eigenschaften sind in jedem `ping` enthalten:

| Eigenschaft | Beschreibung |
|---|---|
| id {Zeichenfolge} | die Player-Kennung |
| activeChannel {Zeichenfolge} | der derzeit wiedergebende Kanalpfad, oder null, wenn nichts geplant ist |
| activeElements {Zeichenfolge} | Kommagetrennte Zeichenfolgen, aktuell sichtbare Elemente in allen wiedergegebenen Sequenzkanälen (mehrere bei einem Mehrzonen-Layout) |
| isDefaultContent {Boolesch} | „true“, wenn der Wiedergabekanal als Standard- oder Fallback-Kanal betrachtet wird (d. h. hat Priorität 1 und keinen Zeitplan) |
| hasContentChanged {Boolesch} | „true“, wenn der Inhalt in den letzten 5 Minuten geändert wurde, andernfalls „false“ |
| lastContentChange {Zeichenfolge} | Zeitstempel der letzten Inhaltsänderung |

>[!NOTE]
>Optional kann eine erweiterte Eigenschaft in den Player-Voreinstellungen (Wiedergabeüberwachung aktivieren) aktiviert werden, und zwar:
>
>| Eigenschaft | Beschreibung |
>|---|---|
>| isContentRendering {Boolesch} | „true“, wenn die GPU bestätigen kann, dass tatsächliche Inhalte wiedergegeben werden (basierend auf der Pixelanalyse) |

### Einschränkungen {#limitations}

Im Folgenden finden Sie einige Beschränkungen bei der grundlegenden Wiedergabeüberwachung:

* Der Player meldet dem Server seinen eigenen Wiedergabestatus, weswegen eine aktive Verbindung erforderlich ist.

* Die Eigenschaft `isContentRendering`, mit der die GPU geprüft wird, ist zu ressourcenintensiv, als dass sie standardmäßig aktiviert werden könnte, und erfordert eine explizite Aktivierung in den Player-Voreinstellungen. Adobe empfiehlt, sie nicht zusammen mit Videos in der Produktion zu verwenden.

* Diese Funktion wird nur für Sequenzkanäle unterstützt und deckt noch nicht den Anwendungsfall für interaktive Kanäle (SPA) ab.

* Die Metriken sind noch nicht vollständig für Kundinnen und Kunden verfügbar, aber Adobe arbeitet an der baldigen Bereitstellung eines Dashboard-ähnlichen Berichts- und Warnmechanismus.

### Sonstige Ressourcen {#additional-resources}

In den folgenden Themen finden Sie ausführliche Informationen:

* Um den Android™-Player herunterzuladen, gehen Sie zu **Google Play**. Weitere Informationen zur Implementierung von Android™ Watchdog finden Sie unter [Implementieren des Android™-Players](implementing-android-player.md).

* Weitere Informationen zur Implementierung des Chrome OS-Players finden Sie unter [Chrome Management Console](implementing-chrome-os-player.md).

* Informationen zur Konfiguration des AEM Screens-Windows-Players finden Sie unter [Implementieren des Windows-Players](implementing-windows-player.md).
