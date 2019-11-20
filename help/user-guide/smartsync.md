---
title: Übergang von ContentSync zu SmartSync
seo-title: Übergang von ContentSync zu SmartSync
description: Auf dieser Seite erfahren Sie mehr über die Funktion SmartSync und wie Sie von ContentSync zu SmartSync wechseln können.
seo-description: Auf dieser Seite erfahren Sie mehr über die Funktion SmartSync und wie Sie von ContentSync zu SmartSync wechseln können.
uuid: c0619b56-1f6f-465a-a428-6df28e40b555
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 822dfbc1-3584-4509-a35c-1d68e5f84509
docset: aem65
translation-type: tm+mt
source-git-commit: 66c741bb73bd5deb2bb5b06dd46f2e407d9c4b7e

---


# Übergang von ContentSync zu SmartSync {#transitioning-from-contentsync-to-smartsync}

In diesem Abschnitt erhalten Sie einen Überblick über die SmartSync-Funktion und darüber, wie damit Serverlade/-speicher und Netzwerkverkehr minimiert werden, um Kosten zu senken.

## Überblick {#overview}

SmartSync ist der neueste von AEM Screens verwendete Mechanismus. Es dient als Ersatz für die aktuelle Methode, die zum Zwischenspeichern von Offlinekanälen und deren Bereitstellung an den Player verwendet wird.

Es wird sowohl serverseitig als auch clientseitig ausgeführt.

**Serverseitig**:

* Der Inhalt der Kanäle, einschließlich der Assets, wird in */var/contentsync* zwischengespeichert.
* Der Cache wird den Playern über ein Manifest zur Verfügung gestellt, das den verfügbaren Inhalt für eine Anzeige beschreibt.

**Auf Client-Seite**:

* Der Player aktualisiert seinen Inhalt auf Grundlage des oben generierten Manifests.

### Vorteile von SmartSync {#benefits-of-using-smartsync}

Die SmartSync-Funktion bietet eine Reihe von Vorteilen für Ihr AEM Screens-Projekt. Es ermöglicht

* Deutliche Reduzierung der Anforderungen an Netzwerkverkehr und serverseitige Speicherung
* Der Player lädt Assets nur dann intelligent herunter, wenn das Asset fehlt oder geändert wurde
* Serverseitige und clientseitige Speicheroptimierungen

>[!NOTE]
>
>Adobe empfiehlt dringend, SmartSync für AEM Screens-Projekte zu verwenden.

## Migration von ContentSync zu SmartSync {#migrating-from-contentsync-to-smartsync}

>[!NOTE]
>
>Wenn Sie AEM 6.3 Feature Pack 5 und AEM 6.4 Feature Pack 3 bereits installiert haben, können Sie SmartSync für Assets aktivieren, um die Speichernutzung zu verbessern. Um SmartSync zu aktivieren, folgen Sie dem unten stehenden Abschnitt, um von ContentSync auf SmartSync zu wechseln und so SmartSync zu aktivieren.
>
>SmartSync ist für Screens Player mit unterstützten AEM 6.4.3 FP3-Servern verfügbar.
>
>Informationen zum Herunterladen des neuesten Players finden Sie unter [AEM Screens Player-Downloads](https://download.macromedia.com/screens/) . In der folgenden Tabelle wird die Mindestversion des Players beschrieben, die für jede Plattform erforderlich ist:

| **Plattform** | **Mindestens unterstützte Player-Version** |
|---|---|
| Android | 3.3.72 |
| Chrome OS | 1.0.136 |
| Windows | 1.0.136 |

Gehen Sie wie folgt vor, um von ContentSync zu SmartSync zu wechseln:

1. Für die Migration von ContentSync zu SmartSync muss der ContentSync-Cache gelöscht werden, bevor SmartSync aktiviert wird.

   Navigieren Sie mithilfe des Links ***https://localhost:4502/libs/cq/contentsync/content/console.html*** zur ContentSync-Konsole und klicken Sie auf Cache **leeren**, wie in der folgenden Abbildung dargestellt:

   ![clear_contesync_cache](assets/clear_contesync_cache.png)

   >[!CAUTION]
   >
   >Der gesamte Inhaltscache muss vor der erstmaligen Verwendung von SmartSync gelöscht werden.

1. Navigieren Sie zur **Adobe Experience Manager Web Console-Konfiguration** über AEM-Instanz —&gt; Hammer-Symbol —&gt; **Vorgänge** —&gt; **Web-Konsole**.

   ![screen_shot_2019-02-11at15339pm](assets/screen_shot_2019-02-11at15339pm.png)

1. **Adobe Experience Manager Web Console Configuration **wird geöffnet. Suchen Sie nach *Offlinecontentservices*.

   Zum Durchsuchen der **Screens Offline Content Service** -Eigenschaft drücken Sie **Befehl+F** für **Mac** und **Strg+F** für **Windows**.

   ![screen_shot_2019-02-19at22643pm](assets/screen_shot_2019-02-19at22643pm.png)

1. Klicken Sie auf **Speichern** , um die **Screens Offline Content Services** -Eigenschaft zu aktivieren und verwenden Sie deshalb SmartSync für AEM Screens.
1. Nachdem Sie SmartSync aktiviert haben, müssen Sie zu Ihrem Projekt navigieren und auf "Offline-Inhalt **** aktualisieren"klicken *(aus der Aktionsleiste),* wie in der Abbildung unten dargestellt.

   ![screen_shot_2019-02-25at102605am](assets/screen_shot_2019-02-25at102605am.png)