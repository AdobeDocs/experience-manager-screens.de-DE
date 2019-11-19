---
title: Erstellen von Komponenten
seo-title: Erstellen von Komponenten
description: AEM-Komponenten werden verwendet, um den Content, den Sie auf Ihren Webseiten bereitstellen, zu speichern, zu formatieren und zu rendern. Folgen Sie dieser Seite, um mehr über das Authoring von Kanälen und das Rendern von Komponenten zu erfahren.
seo-description: AEM-Komponenten werden verwendet, um den Content, den Sie auf Ihren Webseiten bereitstellen, zu speichern, zu formatieren und zu rendern. Folgen Sie dieser Seite, um mehr über das Authoring von Kanälen und das Rendern von Komponenten zu erfahren.
uuid: 66c76dd5-495a-4dcb-ad18-7f8a92669752
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: cdc530d8-ef0e-4b61-b1f0-5f4d831f1392
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Erstellen von Komponenten {#creating-components}

AEM-Komponenten werden verwendet, um den Content, den Sie auf Ihren Webseiten bereitstellen, zu speichern, zu formatieren und zu rendern.

>[!NOTE]
>
>Weitere Informationen zum Erstellen von AEM-Komponenten finden Sie unter Entwickeln von AEM-Komponenten.

## Authoring von Kanälen {#authoring-channels}

Der Kanal ist das zentrale Objekt für Inhalte, die für eine Reihe von Displays bereitgestellt werden. Daher muss ein Inhaltsautor normalerweise einen Kanal im Editor öffnen, um Inhalt hinzuzufügen oder zu ändern. Since the Channel is a ***cq:Page*** it will follow the same traditional UX pattern to add and change components on the channel.

Da jedoch Komponenten innerhalb eines Kanals normalerweise im Vollbildmodus gerendert werden, ist beim Authoring die Bearbeitung von einzelnen Komponenten und das Erstellen eines neuen Auftrags beeinträchtigt. Deshalb nutzt der Kanal Selektoren, um verschiedene Ansichten der Komponenten zu rendern. Die Authoring-Umgebung nutzt die Bearbeitungsauswahl, um das benutzerdefinierte Kanalrendering zu aktivieren.

Beispiel, `http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html](http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html`

Der Benutzer muss sich während des Bearbeitens nicht um das Hinzufügen des Selektors zur URL kümmern. A client side logic is listening to the layer switch event and adds the selector if a the channel has the dedicated resource type *screens/core/components/channel.*

## Rendern von Komponenten {#rendering-components}

Um richtiges Authoring zu ermöglichen, müssen die Komponenten die folgenden beiden Darstellungen zur Verfügung stellen:

| **Component** | **Ausgabeformate** |
|---|---|
| *my-component/my-component.html* | Produktions-Rendering |
| *my-component/edit.html* | Bearbeiten der Wiedergabe in einer kleineren Ansicht |

Die integrierten Komponenten nutzen die folgenden Client-Bibliothekskategorien:

| **Component** | **Client-Bibliothek** |
|---|---|
| *cq.screens.components.edit* | CSS und JS, die beim Authoring geladen werden müssen |
| *cq.screens.components.production* | CSS und JS, die geladen werden müssen, wenn der Kanal ausgeführt wird |
| *cq.screens.components* | freigegebene CSS und JS |

>[!NOTE]
>
>To develop custom components, use the *** [AEM Screens sample component template](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template)***.

