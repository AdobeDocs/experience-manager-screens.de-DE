---
title: Installieren des Screens-Players
description: Erfahren Sie, wie Sie einen AEM Screens-Player ordnungsgemäß installieren.
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 44%

---

# Installieren des AEM Screens-Players {#installing-player}

Auf dieser Seite wird die Installation des AEM Screens-Players beschrieben.

## Verfügbarer Screens-Player {#available-players}

Der AEM Screens-Player ist für Android™, Chrome OS und Windows verfügbar.

Um einen **AEM Screens-Player** herunterzuladen, rufen Sie die Seite [AEM 6.5 Player-Downloads](https://download.macromedia.com/screens/) auf.

>[!NOTE]
>
>Nach dem Herunterladen des neuesten Players (*.exe*), führen Sie die Schritte im Player aus, damit Sie die Ad-hoc-Installation abschließen können:
>
>1. Halten Sie die linke obere Ecke gedrückt, um das Admin-Bedienfeld zu öffnen.
>1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie die Standortadresse der AEM-Instanz unter **Server** ein und klicken Sie auf **Speichern**.
>1. Klicken Sie auf **Registrierung** über den Link im linken Aktionsmenü und die folgenden Schritte, um den Prozess zur Geräteregistrierung abzuschließen.

## Einfache Wiedergabe-Überwachung {#playback-monitoring}

Mit jedem `ping` (standardmäßig alle 30 Sekunden) meldet der Player verschiedene Wiedergabemetriken. Basierend auf diesen Metriken kann es verschiedene Edge-Fälle erkennen, wie z. B. festes Erlebnis, leerer Bildschirm und Planungsprobleme. Sie ermöglicht uns, Probleme auf dem Gerät zu verstehen und zu beheben und so eine Untersuchung und Korrekturmaßnahmen für Sie zu beschleunigen.

Die grundlegende Wiedergabe-Überwachung in einem AEM Screens-Player ermöglicht Folgendes:

* Fernüberwachung, ob ein Player Inhalte ordnungsgemäß wiedergibt.

* Verbessern der Reaktionsfähigkeit auf leere Bildschirme oder fehlerhafte Erlebnisse im Feld.

* Verringerung des Risikos, dem Endbenutzer ein fehlerhaftes Erlebnis anzuzeigen.

### Grundlegendes zu Eigenschaften {#understand-properties}

Die folgenden Eigenschaften sind in jedem `ping` enthalten:

| Eigenschaft | Beschreibung |
|---|---|
| id {Zeichenfolge} | die Player-Kennung |
| activeChannel {Zeichenfolge} | der derzeit wiedergebende Kanalpfad, oder null, wenn nichts geplant ist |
| activeElements {Zeichenfolge} | Kommagetrennte Zeichenfolgen, derzeit sichtbare Elemente in allen wiedergegebenen Sequenzkanälen (mehrere davon haben ein Mehrzonen-Layout) |
| isDefaultContent {Boolesch} | „true“, wenn der Wiedergabekanal als Standard- oder Fallback-Kanal betrachtet wird (d. h. hat Priorität 1 und keinen Zeitplan) |
| hasContentChanged {Boolesch} | „true“, wenn der Inhalt in den letzten 5 Minuten geändert wurde, andernfalls „false“ |
| lastContentChange {Zeichenfolge} | Zeitstempel der letzten Inhaltsänderung |

>[!NOTE]
>Optional kann eine erweiterte Eigenschaft in den Player-Voreinstellungen (Wiedergabeüberwachung aktivieren) aktiviert werden, und zwar:
>
>| Eigenschaft | Beschreibung |
>|---|---|
>| isContentRendering {boolean} | &quot;true&quot;, wenn die GPU bestätigen kann, dass tatsächlich Inhalt wiedergegeben wird (basierend auf der Pixelanalyse) |

### Einschränkungen {#limitations}

Im Folgenden finden Sie einige Einschränkungen für die grundlegende Wiedergabe-Überwachung:

* Der Player meldet dem Server seinen eigenen Wiedergabestatus, sodass eine aktive Verbindung erforderlich ist.

* Die `isContentRendering` -Eigenschaft, die die GPU überprüft, ist wesentlich ressourcenintensiver, um standardmäßig aktiviert zu werden, und erfordert eine explizite Anmeldung über die Player-Voreinstellungen. Adobe empfiehlt, es nicht mit Videos in der Produktion zu verwenden.

* Diese Funktion wird nur für Sequenzkanäle unterstützt und deckt noch nicht den Anwendungsfall für interaktive Kanäle (SPA) ab.

* Die Metriken sind noch nicht vollständig für Kunden verfügbar, aber Adobe arbeitet in Kürze an der Aktivierung von Dashboard-ähnlichen Berichterstellungs- und Warnmechanismen.

### Sonstige Ressourcen {#additional-resources}

Detaillierte Informationen finden Sie in den folgenden Themen:

* Um Android™ Player herunterzuladen, besuchen Sie **Google Play**. Weitere Informationen zur Implementierung von Android™ Watchdog finden Sie unter [Implementieren von Android™ Player](implementing-android-player.md).

* Informationen zur Implementierung des Chrome OS-Players finden Sie unter [Chrome Management Console](implementing-chrome-os-player.md) für weitere Informationen.

* Informationen zum Konfigurieren von AEM Screens Windows Player finden Sie unter [Implementieren von Windows Player](implementing-windows-player.md).
