---
title: Erstellen und Verwalten einer Live Copy
description: Erfahren Sie, wie Sie Live Copies von Kanälen in AEM Screens erstellen und verwalten.
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 4a4b3a83-2b02-42a0-86a7-fce6bbf47c7d
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 54%

---

# Erstellen und Verwalten einer Live Copy {#creating-and-managing-a-live-copy}

Auf dieser Seite wird beschrieben, wie Live Copies von Kanälen erstellt und verwaltet werden.

Eine ***Live Copy*** ist eine Kopie spezifischer Site-Inhalte, für die eine Live-Beziehung zur ursprünglichen Quelle beibehalten wird. Durch diese Live-Beziehung kann die Live Copy Inhalts- und Seiteneigenschaften der Quelle übernehmen.

Auf dieser Seite wird beschrieben, wie Sie eine Live Copy eines Kanals erstellen, Eigenschaften anzeigen, den Status überprüfen und Änderungen von einem Kanal auf dessen Live Copy übertragen.


## Erstellen von Live Copies {#creating-a-live-copy}

Gehen Sie wie folgt vor, um eine Live Copy eines Kanals in Ihrem Projektordner zu erstellen.

1. Klicken Sie auf den Link Adobe Experience Manager (oben links) und dann **Screens**. Sie haben auch die Möglichkeit, direkt zur folgenden URL zu wechseln: `http://localhost:4502/screens.html/content/screens`.

1. Navigieren Sie zum Screens-Projekt und klicken Sie auf **Kanäle**.
1. Klicks **Erstellen** und klicken **Live Copy** damit Sie eine Live Copy des Kanals erstellen können.
1. Klicken Sie auf das Ziel und klicken Sie auf **Nächste**.
1. Klicken Sie auf den Speicherort, an dem sich die Live Copy befinden kann.
1. Geben Sie auf der Seite **Live Copy erstellen** den **Titel** und den **Namen** ein.

1. Klicks **Öffnen** zum Anzeigen des Inhalts der neuen Live Copy oder **Fertig** , um zur Hauptseite zurückzukehren.

Sie können auch die folgenden Schritte ausführen, um zu sehen, wie Sie eine neue Live Copy eines Kanals erstellen.

Das folgende Beispiel zeigt die Erstellung einer Live Copy (***IdleLiveCopy***) für ***Idle Channel*** mit dem Zielordner als ***Kanäle***.

![chlimage_1-2](assets/chlimage_1-2.gif)

## Anzeigen des Inhalts des Live Copy-Kanals {#viewing-content-of-the-live-copy-channel}

Eine Live Copy ist eine Kopie eines existierenden Kanals.

Um den Inhalt einer Live Copy anzuzeigen, gehen Sie wie folgt vor:

1. Navigieren Sie zum Screens-Projekt und klicken Sie auf den Speicherort, an dem Sie ursprünglich eine Live Copy erstellt haben, wie im Abschnitt oben gezeigt. (Hier wurde der Standort als **Kanäle** folder)

   ![chlimage_1-18](assets/chlimage_1-18.png)

1. Klicken Sie in der Aktionsleiste auf **Erstellen**. 

   ![chlimage_1-19](assets/chlimage_1-19.png)

   >[!NOTE]
   >
   >Wenn Sie Inhalte für einen Live Copy-Kanal anzeigen, sehen Sie im Menü das zusätzliche Element **Live Copy-Status**. Weitere Informationen finden Sie im folgenden Abschnitt.

### Anzeigen der Eigenschaften einer Live Copy {#viewing-properties-of-a-live-copy}

Außerdem können Sie die Eigenschaften Ihres Live Copy-Kanals anzeigen.

1. Navigieren Sie zu Ihrem Live Copy-Kanal und klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   ![chlimage_1-20](assets/chlimage_1-20.png)

1. Klicken Sie auf **Live Copy** -Tab, damit Sie Details zu Ihrem Kanal anzeigen können.

   ![chlimage_1-21](assets/chlimage_1-21.png)

### Live Copy-Status {#live-copy-status}

Der in der folgenden Abbildung dargestellte Modus **Live Copy-Status** ermöglicht es Ihnen, den Beziehungsstatus aller Assets im Kanal anzuzeigen.

1. Klicks **Bearbeiten** so können Sie die **Live Copy-Status**. Sie können auch die Zuordnung Ihres Kanalinhalts zum ursprünglichen Kanal anzeigen, von dem aus die Live Copy generiert wird.

   ![chlimage_1-22](assets/chlimage_1-22.png)

1. Klicks **Live Copy-Status** sodass Sie die Vorschauseite anzeigen können.

   Bei allen Ressourcen mit grünem Rand wurde der Inhalt des ursprünglichen Kanals übernommen.

   ![chlimage_1-23](assets/chlimage_1-23.png)

### Aufheben der Vererbung {#breaking-the-inheritance}

Sie können auch die Vererbung der Live Copy aufheben, sodass der Inhalt von der ursprünglichen Verzweigung unabhängig wird.

Das folgende Beispiel zeigt, dass Sie auf das Bild im Bearbeitungsmodus klicken und oben rechts auf das Symbol Vererbung abbrechen klicken.

![chlimage_1-24](assets/chlimage_1-24.png)

### Übertragen der Änderungen auf den Live Copy-Kanal {#propagating-changes-to-the-live-copy-channel}

Wenn Sie Änderungen oder Aktualisierungen im ursprünglichen Kanal vornehmen, propagieren Sie diese Änderungen auch in Ihren Live Copy-Kanal.

Führen Sie die folgenden Schritte aus, um sicherzustellen, dass Ihre Änderungen vom ursprünglichen Kanal auf den Live Copy-Kanal übertragen werden:

1. Klicken Sie auf den ursprünglichen Kanal (***Idle Channel***) und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Bearbeiten Sie den Kanalinhalt.  Löschen Sie beispielsweise ein Bild aus diesem Kanal.

   ![chlimage_1-26](assets/chlimage_1-26.png)

1. Klicken Sie auf die Live Copy des Kanals (***IdleLiveCopy***) und klicken Sie auf **Bearbeiten** in der Aktionsleiste aus. Beachten Sie, dass das von Ihnen gelöschte Bild noch in der Live Copy sichtbar ist.

   Um die Änderungen zu übertragen, müssen Sie den Kanal synchronisieren.

   ![chlimage_1-27](assets/chlimage_1-27.png)

1. Um Änderungen an den Live Copy-Kanal zu übertragen, navigieren Sie zum AEM Dashboard, klicken Sie auf den Live Copy-Kanal und klicken Sie auf **Eigenschaften** in der Aktionsleiste aus.

   ![chlimage_1-28](assets/chlimage_1-28.png)

1. Klicken Sie auf **Live Copy** Registerkarte und klicken Sie auf **Synchronisieren** in der Aktionsleiste aus.

   ![chlimage_1-29](assets/chlimage_1-29.png)

1. Klicks **Synchronisieren** Klicken Sie auf **Speichern und schließen** , um zum AEM Dashboard zurückzukehren.

   ![chlimage_1-30](assets/chlimage_1-30.png)

   Beachten Sie, dass das Bild jetzt auch aus dem Live Copy-Kanal gelöscht ist.
