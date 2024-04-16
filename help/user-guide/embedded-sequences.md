---
title: Eingebettete Sequenzen
description: Erfahren Sie mehr über eingebettete Sequenzen für Kanäle, mit denen Sie Komponenten im übergeordneten Kanal hinzufügen und den Inhalt von einem anderen Kanal wiederverwenden und in den übergeordneten Kanal einbetten können.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: cdfaee19-15d9-4bcb-bc85-0b43c59d88d2
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 26%

---

# Eingebettete Sequenzen {#embedded-sequences}

Verwenden ***Eingebettete Sequenzen*** ermöglicht es dem Benutzer für Kanäle, Komponenten im übergeordneten Kanal hinzuzufügen und den Inhalt von einem anderen Kanal wiederzuverwenden und ihn in den übergeordneten Kanal einzubetten.

## Hinzufügen von eingebetteten Sequenzen {#adding-embedded-sequences}

Sie haben die Möglichkeit, die folgenden Komponenten zu Ihrem Sequenzkanal hinzuzufügen:

* Eingebettete Sequenz
* Dynamische eingebettete Sequenz

>[!NOTE]
>
>Weitere Informationen zur Verwendung anderer Komponenten in Ihrem Screens-Projekt finden Sie unter [Hinzufügen von Komponenten zu Kanälen](adding-components-to-a-channel.md).

### Hinzufügen einer eingebetteten Sequenz {#adding-an-embedded-sequence}

Sie können Ihrem Kanal eine eingebettete Sequenz hinzufügen. Bei einer eingebetteten Sequenz handelt es sich um einen weiteren Kanal mit Assets wie Bildern oder Videos. Durch Hinzufügen einer eingebetteten Sequenz können Benutzer die Sequenz über den ***Kanalpfad*** in einen Kanal aufnehmen.

>[!NOTE]
>Der ***Kanalpfad ***definiert einen expliziten Verweis zum Kanal.
>Weitere Informationen zu *Kanalpfad*, siehe [Kanalzuweisung](channel-assignment.md) in Autorenbildschirmen.

Gehen Sie wie folgt vor, um Ihrem Kanal eine eingebettete Sequenz hinzuzufügen:

1. Klicken Sie auf den Kanal, in den Sie eine Seite einbetten möchten. Beispiel: **`We.Retail`Im Store** > **Kanäle** > **Idle Channel**.

1. Klicks **Bearbeiten** in der Aktionsleiste aus.
1. Klicken Sie im Editor-Modus in der linken Seitenleiste auf das Symbol &quot;Komponenten&quot;, damit Sie die eingebettete Seite hinzufügen können. Ziehen Sie die **eingebettete Sequenz** in den Editor.
1. Doppelklicken Sie auf die **Eingebettete Sequenz** -Komponente, damit Sie den Kanal zu Ihrem ursprünglichen Sequenzkanal hinzufügen können.
1. Klicken Sie auf **Kanalpfad** des Kanals.
1. Klicken Sie auf **Dauer (Millisekunden)** für Ihren eingebetteten Kanal im **Sequenz** Registerkarte. Standardmäßig ist die Dauer auf **-1** eingestellt. Dies bedeutet, dass der eingebettete Kanal vollständig ausgeführt wird. Wenn der Benutzer eine Dauer angibt, wird die Teilsequenz zur angegebenen Zeit unterbrochen (abgeschnitten).

1. Legen Sie die **gemessene Wiedergabestrategie** auf **normal** fest.

Standardmäßig ist diese auf **normal** eingestellt. Festlegen des Werts auf **normal** (Alle Elemente abspielen) bedeutet, dass die Teilsequenz bei jedem Zyklus der übergeordneten Sequenz vollständig ausgeführt wird. Der andere mögliche Wert lautet **Einzelnes Element abspielen**. Dieser Wert zeigt nur ein Element der Teilsequenz bei jeder Ausführung an. Beispielsweise das erste Element bei der ersten Schleife und das zweite Element bei der zweiten Schleife.

>[!IMPORTANT]
>
>Weisen Sie den in der eingebetteten Sequenz verwendeten Kanal derselben Anzeige zu.
>
>Führen Sie die folgenden Schritte aus, nachdem Sie Ihrem Kanal aus den vorangegangenen Schritten eine eingebettete Sequenz hinzugefügt haben:
>
>1. Navigieren Sie zur Anzeige und klicken Sie auf die Anzeige von **Standorte** Ordner.
>1. Klicks **Dashboard** in der Aktionsleiste aus.
>1. Klicken Sie im Anzeigen-Dashboard auf **+ Kanäle zuweisen** aus dem **ZUGEWIESENE KANÄLE UND GEPLANTE BEREICHE** Sie können die **Dialogfeld &quot;Kanalzuweisung&quot;**.
>
>1. Klicken Sie auf den Pfad des Kanals, in dem Sie (in eingebetteter Sequenz) **Kanalpfad**.
>1. Stellen Sie sicher, dass die **Priorität** niedriger als die des Hauptkanals ist.
>
>1. Klicken Sie nicht auf **Unterstützte Ereignisse**.
>1. Klicks **Speichern** wann geschehen.
>

Das folgende Beispiel zeigt das Hinzufügen einer eingebetteten Sequenz (**Idle Channel - Night**) zu einem vorhandenen Kanal (**Idle Channel**).

![new2](assets/new2.gif)

### Hinzufügen einer dynamischen eingebetteten Sequenz {#adding-a-dynamic-embedded-sequence}

Sie können Ihrem Kanal eine dynamische eingebettete Sequenz hinzufügen. Eine dynamische eingebettete Sequenz ähnelt einer eingebetteten Sequenz, ermöglicht es dem Benutzer jedoch, einer Hierarchie zu folgen, in der Änderungen/Aktualisierungen, die an einem Kanal vorgenommen werden, in Bezug auf einen anderen übertragen werden. Sie folgt einer Hierarchie und umfasst zudem Assets wie Bilder und Videos. Durch Aufnahme einer dynamischen Sequenz kann der Benutzer einen Kanal anhand der Kanalrolle hinzufügen.

>[!NOTE]
>
>Die ***Kanalrolle*** definiert den Kontext der Anzeige.
>
>Weitere Informationen zu *Kanalrolle*, siehe [Kanalzuweisung](channel-assignment.md) in Autorenbildschirmen.

Gehen Sie wie folgt vor, um Ihrem Kanal eine eingebettete Sequenz hinzuzufügen:

1. Klicken Sie auf den Kanal, in den Sie eine dynamische Sequenz einbetten möchten. Beispiel: **`We.Retail`Im Store** > **Kanäle** > **Idle Channel**.

1. Klicks **Bearbeiten** in der Aktionsleiste aus.
1. Klicken Sie im Editor-Modus in der linken Seitenleiste auf das Symbol &quot;Komponenten&quot;, damit Sie die dynamische eingebettete Sequenz hinzufügen können. Ziehen Sie die **Dynamik** **Eingebettete Sequenz** in den Editor.

1. Doppelklicken Sie auf die **Dynamik** **Eingebettete Sequenz** -Komponente, damit Sie die Seite Ihrem Sequenzkanal hinzufügen können.

1. Geben Sie die **Kanalzuordnungsrolle** ein.
1. Legen Sie die **gemessene Wiedergabestrategie** auf **normal** fest. Standardmäßig ist diese auf **normal** eingestellt. Festlegen des Werts auf **normal** (Alle Elemente abspielen) bedeutet, dass die Teilsequenz bei jedem Zyklus der übergeordneten Sequenz vollständig ausgeführt wird. Der andere mögliche Wert lautet **Einzelnes Element abspielen**. Dieser Wert zeigt nur ein Element der Teilsequenz bei jeder Ausführung an. Beispielsweise das erste Element bei der ersten Schleife und das zweite Element bei der zweiten Schleife.

1. Klicken Sie auf **Dauer (Millisekunden)** in **Sequenz** für Ihren eingebetteten Kanal in der Sequenz.

![latest](assets/latest.gif)
