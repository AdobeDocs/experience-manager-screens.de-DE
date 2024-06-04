---
title: Verwenden eines Workflows zur Automatisierung von Asset-Aktualisierungen für einen AEM Screens-Kanal
description: Erfahren Sie, wie Sie einen Workflow erstellen, um in Adobe Experience Manager hochgeladene Assets automatisch zu verarbeiten und sie dynamisch einem Screens-Kanal zuzuweisen.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 78%

---


# Verwenden eines Workflows zur Automatisierung von Asset-Aktualisierungen für einen AEM Screens-Kanal {#automate-channel-updates-workflow}

Erfahren Sie, wie Sie einen Workflow erstellen, um in Adobe Experience Manager hochgeladene Assets automatisch zu verarbeiten und sie dynamisch einem Screens-Kanal zuzuweisen. In diesem Beispiel wird ein Workflow ausgelöst, wenn einem bestimmten Ordner ein Bild hinzugefügt wird. Der Workflow wendet eine dynamische Textüberlagerung (Wasserzeichenprozess) an und weist das Bild einem Screens-Kanal zu. Die aus diesem Beispiel gewonnenen Erkenntnisse lassen sich auf eine Vielzahl von Automatisierungsszenarien anwenden.

## Voraussetzungen {#prerequisites}

Um dieses Tutorial abzuschließen, benötigen Sie Folgendes:

1. [AEM 6.5](https://experienceleague.adobe.com/de/docs/experience-manager-65)
1. [AEM Service Pack 8 oder höher](https://experienceleague.adobe.com/de/docs/experience-manager-65/content/release-notes/release-notes)
1. [AEM 6.5 Screens FP7 oder höher](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103)

## Schnell-Setup {#quick-setup}

Das folgende Video veranschaulicht die Installation eines Beispiel-Code-Pakets, mit dem ein neuer Workflow in Adobe Experience Manager eingeführt wird. Mit dieser Funktion können Benutzende die Eigenschaften eines Ordners in AEM Assets so aktualisieren, dass er auf einen Screens-Kanal verweist. Immer, wenn ein Bild zu diesem Ordner hinzugefügt wird, wird es dem angegebenen AEM Screens-Kanal hinzugefügt.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Laden Sie das kompilierte Code-Paket herunter: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Installieren Sie das oben genannte Paket mit dem AEM Package Manager.

## Workflow-Modell {#workflow-model}

Es wurde ein benutzerdefiniertes Ordner-Metadatenschema erstellt, um den Ziel-Kanal in Screens zu erfassen, dem die Bilder hinzugefügt werden sollen. Zur Automatisierung der Asset-Verarbeitung werden zwei Workflow-Modelle verwendet. Die **DAM-Update-Asset** Der Workflow wurde bearbeitet, um einen benutzerdefinierten Workflow aufzurufen, die &quot;Verarbeitung von Screens-Demo-Assets&quot;, die den Ordner des Assets prüft, um den Zielkanal für Screens zu bestimmen. Der Workflow **Demo-Asset-Verarbeitung in Screens** ist auch für das Aufbringen des Wasserzeichens auf das Bild verantwortlich.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Schritte des benutzerdefinierten Workflow-Prozesses {#workflow-process-step}

Untersuchen Sie zwei Schritte des benutzerdefinierten Workflow-Prozesses, die als Teil des Workflows **Demo-Asset-Verarbeitung in Screens** verwendet werden.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

Der `AssetProcessingCheck.java` benutzerdefinierter Workflow ist ein Prozess, der eine Überprüfung der Payload des Workflows durchführt. Er bestimmt, ob die Payload ein Asset ist und ob der Ordner, der die Datei enthält, so konfiguriert ist, dass er auf einen AEM Screens-Kanal verweist. Wenn die Anforderungen erfüllt sind, fügt der Prozessschritt zwei Eigenschaften, `screen-channel` und `asset-path`, zu den Metadaten des Workflows hinzu.

Der `AddAssetToChannel.java`benutzerdefinierte Workflow ist ein Prozessschritt, der die Metadaten des Workflows untersucht und den Screens-Kanal aktualisiert, sodass er auf das Bild verweist.

1. Laden Sie den Quell-Code herunter: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Entpacken Sie den Code und zeigen Sie ihn mit Ihrer bevorzugten IDE an.
