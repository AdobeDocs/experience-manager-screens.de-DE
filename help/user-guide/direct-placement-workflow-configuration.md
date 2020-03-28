---
title: 'Konfiguration des Arbeitsablaufs für direkte Platzierung '
seo-title: Konfiguration des Arbeitsablaufs für direkte Platzierung
description: Diese Seite hebt die Konfiguration des Arbeitsablaufs für direkte Platzierung hervor.
seo-description: Diese Seite hebt die Konfiguration des Arbeitsablaufs für direkte Platzierung hervor.
translation-type: tm+mt
source-git-commit: 19baf90409eab4c72fb38e992c272338b0098d89

---


# Konfiguration des Arbeitsablaufs für direkte Platzierung {#direct-placement-workflow}

Auf dieser Seite erfahren Sie, wie Sie einen Asset-Workflow konfigurieren, mit dem Sie ein Asset programmgesteuert in einen vordefinierten AEM Screens-Kanal einfügen können.

In diesem Abschnitt werden folgende Themen behandelt:

* Überblick
* Konfigurieren des Arbeitsablaufs für die direkte Platzierung

## Überblick {#overview}

Die Konfiguration des Arbeitsablaufs für direkte Platzierung ordnet einen AEM Screens-Kanal einem bestimmten Ordner in Assets zu und ermöglicht die Platzierung von Assets in diesem Ordner. Es wird empfohlen, eine Offline-Massenaktualisierung auszulösen, um die Veröffentlichung abzuschließen.

Als Inhaltsersteller können Sie auch manuell auf Offline-Inhalte **aktualisieren** klicken.

>[!NOTE]
> Informationen zur Verwendung von Massen-Offline-Aktualisierungen finden Sie unter [Content Update As a Service](/help/user-guide/content-update-as-a-service.md).

## Konfigurieren des Arbeitsablaufs für die direkte Platzierung {#configuring-workflow}

>[!IMPORTANT]
> Vor dem Beginn der Konfiguration müssen Sie das [Demopaket](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip)installieren. Nachdem Sie das Paket installiert haben, sollten Sie in der Lage sein, über Ihre AEM-Instanz auf das Paket zuzugreifen —> Tools (Symbol) —> **Workflow** —> **Workflow-Modelle**.

Gehen Sie wie folgt vor, um den Arbeitsablauf für die direkte Platzierung zu konfigurieren:

1. Navigieren Sie von Ihrer AEM-Instanz zu AEM Screens und erstellen Sie ein Screens-Projekt mit dem Titel **Asset Workflow**.

1. Create a channel titled as **Workflow-Assets** under **Channels** folder.

1. 
