---
title: Eingebettete Sequenzen
seo-title: Eingebettete Sequenzen
description: Folgen Sie dieser Seite, um sich über eingebettete Sequenzen für Kanäle zu informieren. Sie erfahren, wie auf diese Weise Komponenten im übergeordneten Kanal hinzugefügt sowie Inhalte von einem anderen Kanal wiederverwendet und in den übergeordneten Kanal eingebettet werden können.
seo-description: Folgen Sie dieser Seite, um sich über eingebettete Sequenzen für Kanäle zu informieren. Sie erfahren, wie auf diese Weise Komponenten im übergeordneten Kanal hinzugefügt sowie Inhalte von einem anderen Kanal wiederverwendet und in den übergeordneten Kanal eingebettet werden können.
uuid: 72a8d4e6-e5ce-4069-bf3b-864d03f61585
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: fc13d713-af30-4a54-8408-920f78fd2b2f
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Eingebettete Sequenzen {#embedded-sequences}

Using ***Embedded Sequences***, for channels, allows the user to add components in the parent channel and also to re-use the content from a different channel and embed it into the parent channel.

## Hinzufügen von eingebetteten Sequenzen {#adding-embedded-sequences}

Sie haben die Möglichkeit, dem Sequenzkanal die folgenden Komponenten hinzuzufügen:

* Eingebettete Sequenz
* Dynamische eingebettete Sequenz

>[!NOTE]
>
>Weitere Informationen zum Verwenden anderer Komponenten in Ihrem Screens-Projekt finden Sie unter [Hinzufügen von Komponenten zu einem Kanal](adding-components-to-a-channel.md).

### Hinzufügen einer eingebetteten Sequenz {#adding-an-embedded-sequence}

Sie können Ihrem Kanal eine eingebettete Sequenz hinzufügen. Eine eingebettete Sequenz ist ein anderer Kanal, der Elemente wie Bilder oder Videos enthält. Durch Hinzufügen einer eingebetteten Sequenz können Benutzer die Sequenz über den ***Kanalpfad in einen Kanal aufnehmen***.

>[!NOTE]
>
>***Kanalpfad ***definiert einen expliziten Verweis auf den Kanal.
>
>Weitere Informationen zum *Kanalpfad* finden Sie in „Inhaltserstellung in Screens“ unter [Kanalzuweisung](channel-assignment.md).

Gehen Sie wie folgt vor, um eine eingebettete Sequenz zu Ihrem Kanal hinzuzufügen:

1. Wählen Sie den Kanal aus, in dem eine Seite eingebettet werden soll. For example, **We.Retail In-Store** --&gt; **Channels** --&gt;** Idle Channel**.

1. Click **Edit** from the action bar to open the channel in the editor mode.
1. Klicken Sie in der linken Seitenleiste auf das Symbol „Komponenten“, um die eingebettete Seite hinzuzufügen. Drag and drop the **Embedded Sequence** to the editor.
1. Double-click the **Embedded Sequence** component to add the channel to your original sequence channel.
1. Wählen Sie den **Kanalpfad** des Kanals aus.
1. Select the **Duration (ms)** for your embedded channel in the **Sequence** tab. By default, the duration is set to **-1**, that means embedded channel is fully run. Wenn der Benutzer eine Dauer angibt, wird die Teilsequenz zur angegebenen Zeit unterbrochen (abgetrennt).

1. Legen Sie die **Strategie** für die kostenpflichtige Wiedergabe auf **normal** fest.

By default, it is set to **normal**. Setting the value to **normal*** (Play all items)* means that the subsequence will run fully on each cycle of the parent sequence. The other possible value is **Play a single item*** (Play a single item)* and that would only show one item of the subsequence on each run (for instance, the 1st item on the first loop, 2nd item on the second loop, and so on.)

>[!NOTE]
>
>**Wichtig:**
>
>Sie müssen den Kanal (in eingebetteter Reihenfolge verwendet) derselben Anzeige zuweisen.
>
>Gehen Sie wie folgt vor, nachdem Sie dem Kanal eine eingebettete Sequenz aus den folgenden Schritten hinzugefügt haben:
>
>1. Navigieren Sie zur Anzeige und wählen Sie die Anzeige aus dem **Ordner Speicherorte** aus.
>1. Klicken Sie in der Aktionsleiste auf **Dashboard** , um zum Dashboard zu navigieren.
>1. Wählen Sie **+ Kanäle** zuweisen aus den **ZUGEWIESENEN KANÄLEN UND GEPLANTEN BEDIENFELDERN** , um das Dialogfeld **"** Kanalzuweisung"zu öffnen.
   >
   >
1. Wählen Sie den Pfad des Kanals aus, den Sie (in eingebetteter Reihenfolge) im **Kanalpfad** verwenden.
>1. Stellen Sie sicher, dass die **Priorität** niedriger als der Hauptkanal ist.
   >
   >
1. Sie dürfen keine **unterstützten Ereignisse** auswählen.
>1. Klicken Sie nach Abschluss des Vorgangs auf **Speichern** .
>



Im folgenden Beispiel sehen Sie, wie eine eingebettete Sequenz (**Idle Channel – Night**) einem bereits vorhandenen Kanal (**Idle Channel**) hinzugefügt wird.

![new2](assets/new2.gif)

### Hinzufügen einer dynamischen eingebetteten Sequenz {#adding-a-dynamic-embedded-sequence}

Sie können Ihrem Kanal eine dynamische eingebettete Sequenz hinzufügen. Eine dynamische eingebettete Sequenz ist mit einer eingebetteten Sequenz vergleichbar. Sie unterscheidet sich allerdings dahingehend, dass der Benutzer einer Hierarchie folgen kann, bei der Änderungen/Aktualisierungen an einem Kanal auf einen anderen, in Bezug stehenden Kanal übertragen werden. Es folgt der Hierarchie von übergeordneter und untergeordneter Ebene und umfasst auch Elemente wie Bilder oder Videos. Durch Aufnahme einer dynamischen Sequenz kann der Benutzer einen Kanal anhand der Kanalrolle hinzufügen.

>[!NOTE]
>
>***Die Kanalrolle*** definiert den Kontext der Anzeige.
>
>Weitere Informationen zur *Kanalrolle* finden Sie in „Inhaltserstellung in Screens“ unter [Kanalzuweisung](channel-assignment.md).

Gehen Sie wie folgt vor, um eine eingebettete Sequenz zu Ihrem Kanal hinzuzufügen:

1. Wählen Sie den Kanal aus, in dem eine dynamische Sequenz eingebettet werden soll. For example, **We.Retail In-Store** --&gt; **Channels** --&gt; **Idle Channel**.

1. Click **Edit** from the action bar to open the channel in the editor mode.
1. Klicken Sie in der linken Seitenleiste auf das Symbol „Komponenten“, um die dynamische eingebettete Sequenz hinzuzufügen. Ziehen Sie die **dynamische** **eingebettete Sequenz **in den Editor.

1. Double-click the **Dynamic** **Embedded Sequence **component to add the page to your sequence channel.

1. Enter the **Channel Assignment Role**.
1. Legen Sie die **Strategie** für die kostenpflichtige Wiedergabe auf **normal** fest. By default, it is set to **normal**. Setting the value to **normal*** (Play all items)* means that the subsequence will run fully on each cycle of the parent sequence. The other possible value is **Play a single item*** (Play a single item)* and that would only show one item of the subsequence on each run (for instance, the 1st item on the first loop, 2nd item on the second loop, and so on.)

1. Select the **Duration (ms)** in **Sequence** tab for your embedded channel in the sequence.

![neueste](assets/latest.gif)

