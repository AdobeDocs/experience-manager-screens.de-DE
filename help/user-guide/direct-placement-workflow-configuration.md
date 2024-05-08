---
title: Konfigurieren des Workflows für die direkte Platzierung
description: Auf dieser Seite wird die Konfiguration des Workflows für die direkte Platzierung beschrieben.
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 40%

---


# Konfigurieren des Workflows für die direkte Platzierung {#direct-placement-workflow}

Auf dieser Seite erfahren Sie, wie Sie einen Asset-Workflow konfigurieren, mit dem Sie ein Asset programmgesteuert in einen vordefinierten AEM Screens-Kanal einfügen können.

In diesem Abschnitt werden folgende Themen behandelt:

* Überblick
* Konfigurieren des Workflows für die direkte Platzierung

## Überblick {#overview}

Die Konfiguration des Workflows für die direkte Platzierung ordnet einen Kanal in einem AEM Screens-Projekt einem bestimmten Ordner in Assets zu und ermöglicht die Platzierung von Assets in diesem Ordner. Adobe empfiehlt, ein Massen-Offline-Update Trigger, um die Veröffentlichung abzuschließen.

Alternativ können Sie als Inhaltsautor manuell auf **Offline-Inhalt aktualisieren**.

>[!NOTE]
>
>Informationen zur Verwendung der Massen-Offline-Aktualisierung finden Sie unter [Inhaltsaktualisierung als Dienst](/help/user-guide/content-update-as-a-service.md).

## Konfigurieren des Workflows für die direkte Platzierung {#configuring-workflow}

>[!IMPORTANT]
>
>Installieren Sie vor Beginn der Konfiguration die `[Demo  Package](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip)`. Nachdem Sie das Paket installiert haben, sollten Sie es über Ihre AEM-Instanz > Tools (Symbol) > **Workflow** > **Workflow-Modelle**.

So konfigurieren Sie den Workflow für die direkte Platzierung:

1. Navigieren Sie von Ihrer AEM zu AEM Screens und erstellen Sie ein Screens-Projekt mit dem Titel **Asset-Workflow**.

1. Erstellen Sie im Ordner **Kanäle** einen Kanal mit dem Titel **Workflow-Assets**.

