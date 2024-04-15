---
title: Automatisieren von Asset-Aktualisierungen für einen AEM Screens-Kanal mit einem Workflow
description: Erfahren Sie, wie Sie einen Workflow erstellen, um in Adobe Experience Manager hochgeladene Assets automatisch zu verarbeiten und sie dynamisch einem Screens-Kanal zuzuweisen.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
source-git-commit: 3c4b37b3b9f268b500562fa4ce3782b7be1e7d74
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 56%

---


# Automatisieren von Asset-Aktualisierungen für einen AEM Screens-Kanal mit einem Workflow {#automate-channel-updates-workflow}

Erfahren Sie, wie Sie einen Workflow erstellen, um in Adobe Experience Manager hochgeladene Assets automatisch zu verarbeiten und sie dynamisch einem Screens-Kanal zuzuweisen. In diesem Beispiel wird beim Hinzufügen eines Bildes zu einem bestimmten Ordner ein Workflow ausgelöst, der ein dynamisches Text-Overlay (Wasserzeichen-Vorgang) anbringt und das Bild einem Screens-Kanal zuweist. Die aus diesem Beispiel gewonnenen Erkenntnisse lassen sich auf eine Vielzahl von Automatisierungsszenarien anwenden.

## Voraussetzungen {#prerequisites}

Um dieses Tutorial abzuschließen, benötigen Sie Folgendes:

1. [AEM 6.5](https://experienceleague.adobe.com/en/docs/experience-manager-65)
1. [AEM Service Pack 8 oder höher](https://experienceleague.adobe.com/de/docs/experience-manager-65/content/release-notes/release-notes)
1. [AEM 6.5 Screens FP7 oder höher](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103)

## Schnelleinstellungen {#quick-setup}

Im folgenden Video erfahren Sie, wie Sie ein Beispielcodepaket installieren, das einen neuen Workflow für Adobe Experience Manager einführt. Mit dieser Funktion kann ein Benutzer die Eigenschaften eines Ordners in AEM Assets so aktualisieren, dass er auf einen Screens-Kanal verweist. Jedes Mal, wenn ein Bild diesem Ordner hinzugefügt wird, wird es zum angegebenen AEM Screens-Kanal hinzugefügt.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Laden Sie das kompilierte Code-Paket herunter: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Installieren Sie das oben genannte Paket mit dem AEM Package Manager.

## Workflow-Modell {#workflow-model}

Es wurde ein benutzerdefiniertes Ordner-Metadatenschema erstellt, um den Ziel-Kanal in Screens zu erfassen, dem die Bilder hinzugefügt werden sollen. Zur Automatisierung der Asset-Verarbeitung werden zwei Workflow-Modelle verwendet. Die **DAM-Update-Asset** Der Workflow wurde geändert, um einen benutzerdefinierten Workflow aufzurufen. **Verarbeitung von Screens Demo-Assets** , der den Ordner des Assets prüft, um den Ziel-Screens-Kanal zu bestimmen. Der Workflow **Demo-Asset-Verarbeitung in Screens** ist auch für das Aufbringen des Wasserzeichens auf das Bild verantwortlich.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Benutzerdefinierte Workflow-Prozessschritte {#workflow-process-step}

Untersuchen Sie zwei Schritte des benutzerdefinierten Workflow-Prozesses, die als Teil des Workflows **Demo-Asset-Verarbeitung in Screens** verwendet werden.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

Die `AssetProcessingCheck.java` benutzerdefinierter Workflow ist ein Prozess, der eine Überprüfung der Payload des Workflows durchführt. Sie bestimmt, ob die Payload ein Asset ist und ob der Ordner, der die Datei enthält, so konfiguriert ist, dass er auf einen AEM Screens-Kanal verweist. Wenn die Anforderungen erfüllt sind, fügt der Prozessschritt zwei Eigenschaften, `screen-channel` und `asset-path`, zu den Metadaten des Workflows hinzu.

Die `AddAssetToChannel.java` Der benutzerdefinierte Workflow ist ein Prozessschritt, der die Metadaten des Workflows prüft und den AEM Screens-Kanal aktualisiert, um auf das Bild zu verweisen.

1. Laden Sie den Quell-Code herunter: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Entpacken Sie den Code und zeigen Sie ihn mit Ihrer bevorzugten IDE an.
