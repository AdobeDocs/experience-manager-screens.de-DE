---
title: Erstellen von Komponenten
description: Erfahren Sie, wie Sie mit AEM-Komponenten auf Ihren Web-Seiten bereitgestellte Inhalte speichern, formatieren und rendern.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 4d673039-4963-458a-89e9-023a993dd354
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 100%

---

# Erstellen von Komponenten {#creating-components}

AEM-Komponenten werden verwendet, um den Inhalt, den Sie auf Ihren Web-Seiten bereitstellen, zu speichern, zu formatieren und zu rendern.

>[!NOTE]
>
>Detaillierte Informationen über die Erstellung von AEM-Komponenten finden Sie unter „Entwickeln von AEM-Komponenten“.

## Authoring von Kanälen {#authoring-channels}

Der Kanal ist das zentrale Objekt von Inhalten, die für eine Reihe von Anzeigen bereitgestellt werden. Daher öffnet eine Inhaltsautorin bzw. ein Inhaltsautor normalerweise einen Kanal im Editor, um Inhalte hinzuzufügen oder zu ändern. Da der Kanal eine ***`cq:Page`*** ist, folgt er demselben herkömmlichen UX-Muster zum Hinzufügen und Bearbeiten von Komponenten des Kanals.

Da jedoch Komponenten innerhalb eines Kanals normalerweise im Vollbildmodus gerendert werden, ist das Authoring-Erlebnis bei der Bearbeitung von einzelnen Komponenten und dem Erstellen eines neuen Auftrags beeinträchtigt. Deshalb nutzt der Kanal Selektoren, um verschiedene Ansichten der Komponenten zu rendern. Die Authoring-Umgebung verwendet den Bearbeitungsselektor, um das Rendering des benutzerdefinierten Kanals zu aktivieren.

Beispiel: `http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html](http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html`

Der Benutzer muss sich während des Bearbeitens nicht um das Hinzufügen des Selektors zur URL kümmern. Eine Client-seitige Logik wartet auf das Ebenen-Wechselereignis und fügt den Selektor hinzu, wenn der Kanal den dedizierten Ressourcentyp *screens/core/components/channel* aufweist.

## Rendern von Komponenten {#rendering-components}

Um richtiges Authoring zu ermöglichen, müssen die Komponenten die folgenden beiden Ausgabedarstellungen zur Verfügung stellen:

| **Komponente** | **Wiedergaben** |
|---|---|
| *my-component/my-component.html* | Produktionswiedergabe |
| *my-component/edit.html* | Bearbeiten der Wiedergabe in einer kleineren Ansicht |

Die integrierten Komponenten nutzen die folgenden Client-Bibliothekskategorien:

| **Komponente** | **Client-Bibliothek** |
|---|---|
| *cq.screens.components.edit* | CSS und JS, die bei der Inhaltserstellung geladen werden müssen |
| *cq.screens.components.production* | CSS und JS, die geladen werden müssen, wenn der Kanal ausgeführt wird |
| *cq.screens.components* | freigegebene CSS und JS |

>[!NOTE]
>
>Um eigene Komponenten zu entwickeln, verwenden Sie die ***[Beispielvorlage für AEM Screens-Komponenten](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template)***.
