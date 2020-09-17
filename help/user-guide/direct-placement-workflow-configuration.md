---
title: 'Konfigurieren des Workflows für die direkte Platzierung '
seo-title: Konfigurieren des Workflows für die direkte Platzierung
description: Auf dieser Seite wird die Konfiguration des Workflows für die direkte Platzierung beschrieben.
seo-description: Auf dieser Seite wird die Konfiguration des Workflows für die direkte Platzierung beschrieben.
translation-type: ht
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: ht
source-wordcount: '214'
ht-degree: 100%

---


# Konfigurieren des Workflows für die direkte Platzierung {#direct-placement-workflow}

Auf dieser Seite erfahren Sie, wie Sie einen Asset-Workflow konfigurieren, mit dem Sie ein Asset programmgesteuert in einen vordefinierten AEM Screens-Kanal einfügen können.

In diesem Abschnitt werden folgende Themen behandelt:

* Überblick
* Konfigurieren des Workflows für die direkte Platzierung

## Überblick {#overview}

Die Konfiguration des Workflows für die direkte Platzierung ordnet einen Kanal in einem AEM Screens-Projekt einem bestimmten Ordner in Assets zu und ermöglicht die Platzierung von Assets in diesem Ordner. Es wird empfohlen, ein Massen-Offline-Update auszulösen, um die Veröffentlichung durchzuführen.

Alternativ kann der Inhaltsautor manuell auf **Offline-Inhalt aktualisieren** klicken.

>[!NOTE]
>
>Informationen zur Verwendung von Massen-Offline-Updates finden Sie unter [Inhaltsaktualisierung als Dienst](/help/user-guide/content-update-as-a-service.md).

## Konfigurieren des Workflows für die direkte Platzierung {#configuring-workflow}

>[!IMPORTANT]
>
>Installieren Sie das [Demopaket](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip), bevor Sie mit der Konfiguration beginnen. Nachdem Sie das Paket installiert haben, sollten Sie es über Ihre AEM-Instanz > „Tools“ (Symbol) > **Workflow** > **Workflow-Modelle** anzeigen und darauf zugreifen können.

So konfigurieren Sie den Workflow für die direkte Platzierung:

1. Navigieren Sie von Ihrer AEM-Instanz aus zu AEM Screens und erstellen Sie ein Screens-Projekt mit dem Titel **Asset Workflow**.

1. Erstellen Sie im Ordner **Kanäle** einen Kanal mit dem Titel **Workflow-Assets**.

