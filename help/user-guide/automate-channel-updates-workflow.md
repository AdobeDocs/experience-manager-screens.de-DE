---
title: Automatisieren von Asset-Aktualisierungen für einen AEM Screens-Kanal mit einem Workflow
seo-title: Automatisieren von Asset-Aktualisierungen für einen AEM Screens-Kanal mit einem Workflow
description: Erfahren Sie, wie Sie einen Workflow erstellen, um in Adobe Experience Manager hochgeladene Assets automatisch zu verarbeiten und sie dynamisch einem Screens-Kanal zuzuweisen. In diesem Beispiel wird beim Hinzufügen eines Bildes zu einem bestimmten Ordner ein Workflow ausgelöst, der ein dynamisches Wasserzeichen anbringt und das Bild einem Screens-Kanal zuweist. Die aus diesem Beispiel gewonnenen Erkenntnisse lassen sich auf eine Vielzahl von Automatisierungsszenarien anwenden.
seo-description: Erfahren Sie, wie Sie einen Workflow erstellen, um in Adobe Experience Manager hochgeladene Assets automatisch zu verarbeiten und sie dynamisch einem Screens-Kanal zuzuweisen. In diesem Beispiel wird beim Hinzufügen eines Bildes zu einem bestimmten Ordner ein Workflow ausgelöst, der ein dynamisches Wasserzeichen anbringt und das Bild einem Screens-Kanal zuweist. Die aus diesem Beispiel gewonnenen Erkenntnisse lassen sich auf eine Vielzahl von Automatisierungsszenarien anwenden.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Entwicklung in Screens
role: Developer
level: Intermediate
source-git-commit: 8d1633dab9e70ea988516cf9ee4d1b0a780bc7e9
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 100%

---


# Automatisieren von Asset-Aktualisierungen für einen AEM Screens-Kanal mit einem Workflow {#automate-channel-updates-workflow}

Erfahren Sie, wie Sie einen Workflow erstellen, um in Adobe Experience Manager hochgeladene Assets automatisch zu verarbeiten und sie dynamisch einem Screens-Kanal zuzuweisen. In diesem Beispiel wird beim Hinzufügen eines Bildes zu einem bestimmten Ordner ein Workflow ausgelöst, der ein dynamisches Text-Overlay (Wasserzeichen-Vorgang) anbringt und das Bild einem Screens-Kanal zuweist. Die aus diesem Beispiel gewonnenen Erkenntnisse lassen sich auf eine Vielzahl von Automatisierungsszenarien anwenden.

## Voraussetzungen {#prerequisites}

Um dieses Tutorial abzuschließen, benötigen Sie Folgendes:

1. [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65.html?lang=de)
1. [AEM Service Pack 8 oder höher](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html?lang=de)
1. [AEM 6.5 Screens FP7 oder höher](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103.html?lang=de)

## Schnell-Setup {#quick-setup}

Das folgende Video veranschaulicht die Installation eines Beispiel-Code-Pakets, mit dem ein neuer Workflow in Adobe Experience Manager eingeführt wird. Mit dieser Funktion kann ein Benutzer die Eigenschaften eines Ordners in AEM Assets so aktualisieren, dass er auf einen Screens-Kanal verweist. Immer, wenn ein Bild zu diesem Ordner hinzugefügt wird, wird es dem angegebenen Screens-Kanal hinzugefügt.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Laden Sie das kompilierte Code-Paket herunter: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Installieren Sie das oben genannte Paket mit dem AEM Package Manager.

## Workflow-Modell {#workflow-model}

Es wurde ein benutzerdefiniertes Ordner-Metadatenschema erstellt, um den Ziel-Kanal in Screens zu erfassen, dem die Bilder hinzugefügt werden sollen. Zur Automatisierung der Asset-Verarbeitung werden zwei Workflows verwendet. Der Workflow **DAM Update Asset** wurde geändert, um einen benutzerdefinierten Workflow, **Demo-Asset-Verarbeitung in Screens**, aufzurufen. Dieser überprüft den zugehörigen Ordner des Assets, um den Ziel-Kanal in Screens zu ermitteln. Der Workflow **Demo-Asset-Verarbeitung in Screens** ist auch für das Aufbringen des Wasserzeichens auf das Bild verantwortlich.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Schritte des benutzerdefinierten Workflow-Prozesses {#workflow-process-step}

Untersuchen Sie zwei Schritte des benutzerdefinierten Workflow-Prozesses, die als Teil des Workflows **Demo-Asset-Verarbeitung in Screens** verwendet werden.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

`AssetProcessingCheck.java` ist ein benutzerdefinierter Workflow-Prozess, der die Payload des Workflows überprüft, um festzustellen, ob es sich bei der Payload um ein Asset handelt und ob der enthaltende Ordner so konfiguriert ist, dass er auf einen Screens-Kanal verweist. Wenn die Anforderungen erfüllt sind, fügt der Prozessschritt zwei Eigenschaften, `screen-channel` und `asset-path`, zu den Metadaten des Workflows hinzu.

`AddAssetToChannel.java` ist ein benutzerdefinierter Workflow-Prozessschritt, der die Metadaten des Workflows untersucht und den Screens-Kanal aktualisiert, sodass er auf das Bild verweist.

1. Laden Sie den Quell-Code herunter: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Entpacken Sie den Code und zeigen Sie ihn mit Ihrer bevorzugten IDE an.
