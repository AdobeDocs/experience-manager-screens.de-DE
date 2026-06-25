---
title: Eingebettete Sequenzen
description: Erfahren Sie mehr über eingebettete Sequenzen für Kanäle, mit denen Sie Komponenten zum übergeordneten Kanal hinzufügen können. Alternativ können Sie den Inhalt von einem anderen Kanal wiederverwenden und in den übergeordneten Kanal einbetten.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: cdfaee19-15d9-4bcb-bc85-0b43c59d88d2
TQID: https://experienceleague.adobe.com/NK6M9ShPUQdDQQvgx7kD9c4uvfKjy61wJ6jSH0gB17E
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2: id: ba4275ba-c29a-4197-90dc-5a633402ca3cid: d4878390-3838-4e80-8cb3-33bc1a01ea16id: d8a4be83-7d41-47be-b4a6-f8f3d35cacebid: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: d4664dd5678eaccabe656398c437dca264d4675e
workflow-type: tm+mt
source-wordcount: 811
ht-degree: 93%

---

# Eingebettete Sequenzen {#embedded-sequences}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Mithilfe ***eingebetteter Sequenzen*** für Kanäle können Benutzende Komponenten im übergeordneten Kanal hinzufügen sowie Inhalte von einem anderen Kanal wiederverwenden und in den übergeordneten Kanal einbetten.

## Hinzufügen von eingebetteten Sequenzen {#adding-embedded-sequences}

Sie haben die Möglichkeit, die folgenden Komponenten zu Ihrem Sequenzkanal hinzuzufügen:

* Eingebettete Sequenz
* Dynamische eingebettete Sequenz

>[!NOTE]
>
>Weitere Informationen zum Verwenden anderer Komponenten in Ihrem Screens-Projekt finden Sie unter [Hinzufügen von Komponenten zu einem Kanal](adding-components-to-a-channel.md).

### Hinzufügen einer eingebetteten Sequenz {#adding-an-embedded-sequence}

Sie können Ihrem Kanal eine eingebettete Sequenz hinzufügen. Bei einer eingebetteten Sequenz handelt es sich um einen weiteren Kanal mit Assets wie Bildern oder Videos. Durch Hinzufügen einer eingebetteten Sequenz können Benutzer die Sequenz über den ***Kanalpfad*** in einen Kanal aufnehmen.

>[!NOTE]
>***Kanalpfad*** definiert einen expliziten Verweis zum Kanal.
>Weitere Informationen zum *Kanalpfad* finden Sie unter [Kanalzuweisung](channel-assignment.md) in Authoring-Screens.

Gehen Sie wie folgt vor, um Ihrem Kanal eine eingebettete Sequenz hinzuzufügen:

1. Wählen Sie den Kanal aus, in den eine Seite eingebettet werden soll. z. B. **`We.Retail`In-Store** > **Channels** > **Idle Channel**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**.
1. Klicken Sie im Editormodus in der linken Seitenleiste auf das Symbol „Komponenten“, um dann die eingebettete Seite hinzuzufügen. Ziehen Sie die **eingebettete Sequenz** in den Editor.
1. Doppelklicken Sie auf die Komponente **Eingebettete Sequenz**, um den Kanal Ihrem ursprünglichen Sequenz-Kanal hinzuzufügen.
1. Wählen Sie den **Kanalpfad** des Kanals aus.
1. Wählen Sie die **Dauer (Millisekunden)** für Ihren eingebetteten Kanal auf der Registerkarte **Sequenz** aus. Standardmäßig ist die Dauer auf **-1** festgelegt. Dies bedeutet, dass der eingebettete Kanal vollständig ausgeführt wird. Wenn Benutzende eine Dauer angeben, wird die Teilsequenz zur angegebenen Zeit unterbrochen (d. h. abgetrennt).

1. Legen Sie die **gemessene Wiedergabestrategie** auf **normal** fest.

Standardmäßig ist diese auf **normal** eingestellt. Ist der Wert auf **normal** (Alle Elemente abspielen) eingestellt, wird die Teilsequenz bei jedem Zyklus der übergeordneten Sequenz vollständig ausgeführt. Der andere mögliche Wert lautet **Einzelnes Element abspielen**. Dieser Wert zeigt nur ein Element der Teilsequenz bei jeder Ausführung an. Beispielsweise das erste Element bei der ersten Schleife und das zweite Element bei der zweiten Schleife.

>[!IMPORTANT]
>
>Weisen Sie den in der eingebetteten Sequenz verwendeten Kanal derselben Anzeige zu.
>
>Führen Sie die folgenden Schritte aus, nachdem Sie Ihrem Kanal aus den vorangegangenen Schritten eine eingebettete Sequenz hinzugefügt haben:
>
>1. Navigieren Sie zur Anzeige und klicken Sie im Ordner **Standorte** auf die Anzeige.
>1. Klicken Sie in der Aktionsleiste auf **Dashboard**.
>1. Wählen Sie im Anzeigen-Dashboard **+ Kanäle zuweisen** über die **BEDIENFELDER „ZUGEWIESENE KANÄLE“ UND „GEPLANT“**, um das **Dialogfeld „Kanalzuweisung“** zu öffnen.
>
>1. Wählen Sie unter **Kanalpfad** den Pfad des Kanals aus, den Sie in der eingebetteten Sequenz verwendet haben.
>1. Stellen Sie sicher, dass die **Priorität** niedriger als die des Hauptkanals ist.
>
>1. Wählen Sie keine **unterstützten Ereignisse** aus.
>1. Klicken Sie auf **Speichern**, wenn Sie fertig sind.
>

Im folgenden Beispiel sehen Sie, wie eine eingebettete Sequenz (**Idle Channel – Night**) einem bereits vorhandenen Kanal (**Idle Channel**) hinzugefügt wird.

![new2](assets/new2.gif)

### Hinzufügen einer dynamischen eingebetteten Sequenz {#adding-a-dynamic-embedded-sequence}

Sie können Ihrem Kanal eine dynamische eingebettete Sequenz hinzufügen. Eine dynamische eingebettete Sequenz ist mit einer eingebetteten Sequenz vergleichbar. Sie unterscheidet sich allerdings dahingehend, dass Benutzende einer Hierarchie folgen können, bei der Änderungen/Aktualisierungen an einem Kanal auf einen anderen, in Bezug stehenden Kanal übertragen werden. Sie folgt einer über- und untergeordneten Hierarchie und umfasst zudem Assets wie Bilder und Videos. Durch Aufnahme einer dynamischen Sequenz können Benutzende einen Kanal anhand der Kanalrolle hinzufügen.

>[!NOTE]
>
>Mit der ***Kanalrolle*** wird der Kontext der Anzeige definiert.
>
>Weitere Informationen zur *Kanalrolle* finden Sie in „Inhaltserstellung in Screens“ unter [Kanalzuweisung](channel-assignment.md).

Gehen Sie wie folgt vor, um Ihrem Kanal eine eingebettete Sequenz hinzuzufügen:

1. Klicken Sie auf den Kanal, in den Sie eine dynamische Sequenz einbetten möchten. z. B. **`We.Retail`In-Store** > **Channels** > **Idle Channel**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**.
1. Klicken Sie im Editormodus in der linken Seitenleiste auf das Symbol „Komponenten“, um dann die dynamische, eingebettete Sequenz hinzuzufügen. Ziehen Sie die Komponente **Dynamische** **eingebettete Sequenz** per Drag-and-Drop in den Editor.

1. Doppelklicken Sie auf die Komponente **Dynamische** **eingebettete Sequenz**, um die Seite Ihrem Sequenzkanal hinzuzufügen.

1. Geben Sie die **Kanalzuordnungsrolle** ein.
1. Legen Sie die **gemessene Wiedergabestrategie** auf **normal** fest. Standardmäßig ist diese auf **normal** eingestellt. Ist der Wert auf **normal** (Alle Elemente abspielen) eingestellt, wird die Teilsequenz bei jedem Zyklus der übergeordneten Sequenz vollständig ausgeführt. Der andere mögliche Wert lautet **Einzelnes Element abspielen**. Dieser Wert zeigt nur ein Element der Teilsequenz bei jeder Ausführung an. Beispielsweise das erste Element bei der ersten Schleife und das zweite Element bei der zweiten Schleife.

1. Klicken Sie auf der Registerkarte **Sequenz** auf die Option **Dauer (ms)** für Ihren in die Sequenz eingebetteten Kanal.

![latest](assets/latest.gif)
