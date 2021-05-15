---
title: Automatisieren von Asset-Aktualisierungen für einen AEM Screens-Kanal mit einem Workflow
seo-title: Automatisieren von Asset-Aktualisierungen für einen AEM Screens-Kanal mit einem Workflow
description: Erfahren Sie, wie Sie einen Workflow erstellen, um automatisch nach Adobe Experience Manager hochgeladene Assets zu verarbeiten und sie dynamisch einem Kanal zuzuweisen. In diesem Beispiel wird ein Workflow ausgelöst, bei dem ein dynamisches Wasserzeichen angewendet und das Bild einem Screens-Kanal zugewiesen wird, wenn einem bestimmten Ordner ein Bild hinzugefügt wird. Aus diesem Beispiel gewonnene Erkenntnisse können auf eine Vielzahl von Automatisierungsszenarien angewendet werden.
seo-description: Erfahren Sie, wie Sie einen Workflow erstellen, um automatisch nach Adobe Experience Manager hochgeladene Assets zu verarbeiten und sie dynamisch einem Kanal zuzuweisen. In diesem Beispiel wird ein Workflow ausgelöst, bei dem ein dynamisches Wasserzeichen angewendet und das Bild einem Screens-Kanal zugewiesen wird, wenn einem bestimmten Ordner ein Bild hinzugefügt wird. Aus diesem Beispiel gewonnene Erkenntnisse können auf eine Vielzahl von Automatisierungsszenarien angewendet werden.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Entwicklung in Screens
role: Developer
level: Intermediate
source-git-commit: 8d1633dab9e70ea988516cf9ee4d1b0a780bc7e9
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 4%

---


# Automatisieren Sie Asset-Updates mit dem Workflow für einen AEM Screens-Kanal {#automate-channel-updates-workflow}

Erfahren Sie, wie Sie einen Workflow erstellen, um automatisch nach Adobe Experience Manager hochgeladene Assets zu verarbeiten und sie dynamisch einem Kanal zuzuweisen. In diesem Beispiel wird ein Workflow ausgelöst, der eine dynamische Textüberlagerung (Wasserzeichenprozess) anwendet und das Bild einem Screens-Kanal zuweist, wenn einem bestimmten  ein Bild hinzugefügt wird. Aus diesem Beispiel gewonnene Erkenntnisse können auf eine Vielzahl von Automatisierungsszenarien angewendet werden.

## Voraussetzungen {#prerequisites}

Um dieses Tutorial abzuschließen, benötigen Sie Folgendes:

1. [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65.html?lang=de)
1. [AEM Service Pack 8 oder höher](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html?lang=de)
1. [AEM 6.5 Bildschirme FP7 oder höher](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103.html)

## Quick Setup {#quick-setup}

Im folgenden Video wird gezeigt, wie ein Beispielcode-Paket installiert wird, das einen neuen Arbeitsablauf für Adobe Experience Manager einführt. Diese Funktion ermöglicht es einem Benutzer, die Eigenschaften eines Ordners in AEM Assets zu aktualisieren, um auf einen Kanal zu verweisen. Jedes Mal, wenn ein Bild zu diesem Ordner hinzugefügt wird, wird es dem angegebenen Kanal für Bildschirme hinzugefügt.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Laden Sie das kompilierte Codepaket herunter: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Installieren Sie das oben stehende Paket mit AEM Package Manager.

## Workflow-Modell {#workflow-model}

Ein benutzerdefiniertes Schema für Ordnermetadaten wurde erstellt, um den Kanal &quot;Zielgruppe Screens&quot;zu erfassen, dem Bilder hinzugefügt werden sollen. Zur Automatisierung der Asset-Verarbeitung werden zwei Workflows verwendet. Der Arbeitsablauf **DAM-Update-Asset** wurde geändert, um einen benutzerdefinierten Workflow, **Bildschirme Demo-Asset-Verarbeitung**, aufzurufen. Dieser überprüft den zugehörigen Ordner des Assets, um den Kanal Zielgruppe Screens zu ermitteln. Der Arbeitsablauf **Bildschirme Demoelementverarbeitung** ist auch für die Anwendung des Wasserzeichens auf das Bild verantwortlich.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Schritte zum benutzerdefinierten Workflow-Prozess {#workflow-process-step}

Inspect zwei benutzerdefinierte Workflow-Prozessschritte, die als Teil des Arbeitsablaufs **Bildschirme Demoelementverarbeitung** verwendet werden.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

`AssetProcessingCheck.java` ist ein benutzerdefinierter Workflow-Prozess, der die Nutzlast des Workflows überprüft, um festzustellen, ob es sich bei der Nutzlast um ein Asset handelt und ob der Ordner, der dieses enthält, so konfiguriert ist, dass er auf einen Kanal verweist. Wenn die Anforderungen erfüllt sind, bleiben im Prozessschritt zwei Eigenschaften, `screen-channel` und `asset-path`, für die Metadaten des Workflows erhalten.

`AddAssetToChannel.java` ist ein benutzerdefinierter Workflow-Prozessschritt, der die Metadaten des Workflows prüft und den Kanal Bildschirme aktualisiert, um auf das Bild zu verweisen.

1. Quellcode herunterladen: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Entpacken und Ansicht des Codes mit Ihrer bevorzugten IDE.
