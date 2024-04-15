---
title: Installieren des Screens-Players
description: Erfahren Sie, wie Sie einen AEM Screens-Player ordnungsgemäß installieren.
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 48%

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
>1. Navigieren Sie zu **Konfiguration** aus dem linken Aktionsmenü aus und geben Sie die Standortadresse der AEM Instanz in **Server** und wählen **Speichern**.
>1. Auswählen **Registrierung** über den Link im linken Aktionsmenü und die folgenden Schritte, um den Prozess zur Geräteregistrierung abzuschließen.

## Einfache Wiedergabe-Überwachung {#playback-monitoring}

Mit jedem `ping` (standardmäßig alle 30 Sekunden) meldet der Player verschiedene Wiedergabemetriken. Basierend auf diesen Metriken kann es verschiedene Edge-Fälle erkennen, wie z. B. festes Erlebnis, leerer Bildschirm und Planungsprobleme. Auf diese Weise können wir Probleme auf dem Gerät verstehen und beheben und somit gemeinsam mit Ihnen durchgeführte Untersuchungen und Abhilfemaßnahmen beschleunigen.

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

### Beschränkungen {#limitations}

Im Folgenden finden Sie einige Beschränkungen bei der einfachen Wiedergabeüberwachung:

* Der Player meldet dem Server seinen eigenen Wiedergabestatus, sodass eine aktive Verbindung erforderlich ist.

* Die `isContentRendering` -Eigenschaft, die prüft, ob die GPU zu ressourcenintensiv ist, um standardmäßig aktiviert zu werden, und eine explizite Anmeldung über die Player-Voreinstellungen erfordert. Adobe empfiehlt, es nicht mit Videos in der Produktion zu verwenden.

* Diese Funktion wird nur für Sequenzkanäle unterstützt und deckt noch nicht den Anwendungsfall für interaktive Kanäle (SPA) ab.

* Die Metriken sind noch nicht vollständig für Kunden verfügbar. Adobe arbeitet in Kürze an der Aktivierung von Dashboard-ähnlichen Berichterstellungs- und Warnmechanismen.

### Sonstige Ressourcen {#additional-resources}

Detaillierte Informationen finden Sie in den folgenden Themen:

* Um Android™ Player herunterzuladen, besuchen Sie **Google Play**. Weitere Informationen zur Implementierung von Android™ Watchdog finden Sie unter [Implementieren von Android™ Player](implementing-android-player.md).

* Informationen zur Implementierung des Chrome OS-Players finden Sie unter [Chrome Management Console](implementing-chrome-os-player.md) für weitere Informationen.

* Informationen zum Konfigurieren des AEM Screens Windows-Players finden Sie unter [Implementieren von Windows Player](implementing-windows-player.md).
