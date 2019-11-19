---
title: 'Erstellen und Verwalten von Kanälen '
seo-title: Verwalten von Kanälen
description: Folgen Sie dieser Seite, um sich über das Erstellen und Verwalten von Kanälen zu informieren. Außerdem wird auf dieser Seite das Kanal-Dashboard und die Bearbeitung von Inhalt für einen Kanal erklärt.
seo-description: Folgen Sie dieser Seite, um sich über das Erstellen und Verwalten von Kanälen zu informieren. Außerdem wird auf dieser Seite das Kanal-Dashboard und die Bearbeitung von Inhalt für einen Kanal erklärt.
uuid: cdf09ced-9089-4249-ba51-471d6fa0e507
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: a8006686-8ee5-4971-ab79-0c7b01f108f2
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Erstellen und Verwalten von Kanälen{#creating-and-managing-channels} 

Ein Kanal zeigt eine Sequenz von Inhalten an und zeigt Bilder und Videos an, kann aber auch eine Website oder eine Einzelseitenanwendung anzeigen.

Auf dieser Seite wird gezeigt, wie Kanäle für Screens erstellt und verwaltet werden.

**Voraussetzungen**:

* [Konfigurieren und Bereitstellen von Screens](configuring-screens-introduction.md) 
* [Bildschirmprojekt erstellen und verwalten](creating-a-screens-project.md)

## Erstellen eines neuen Kanals {#creating-a-new-channel}

Wenn Sie Ihr Projekt für Screens erstellen, gehen Sie wie folgt vor, um einen neuen Kanal für ein Screens-Projekt zu erstellen:

1. Wählen Sie den Adobe Experience Manager-Link (oben links) und dann Screens aus. Alternatively, you can ﻿go directly to: `https://localhost:4502/screens.html/content/screens`.
1. Navigieren Sie zum Screens-Projekt und klicken Sie auf **Kanäle**.
1. Click **Create** next to the plus icon in the action bar. Ein Assistent wird angezeigt (*Weitere Informationen finden Sie unter „Kanaltypen“*).

1. Select the template from the wizard and click **Next**.
1. Enter the properties for **Title and Tags**, **More Titles and Description**, **On/Off Time**, and **Vanity URL**.

1. Klicken Sie auf **Erstellen**. Der Kanal wird erstellt und Ihrem Kanalordner hinzugefügt.

### Kanaltypen {#channel-types}

Beim Verwenden des Assistenten stehen die folgenden Vorlagenoptionen zur Verfügung, wie zum Beispiel:

| **Vorlagenoption** | **Beschreibung** |
|---|---|
| Kanal-Ordner | Ermöglicht die Erstellung eines Ordners zum Speichern von Kanalsammlungen |
| Sequenz-Kanal | Ermöglicht die Erstellung eines Kanals, in dem die Komponenten nacheinander wiedergegeben werden (nacheinander in einer Diashow). |
| Anwendungskanal | Ermöglicht die Präsentation benutzerdefinierter Webanwendungen im Screens-Player |
| 1x1-Splitscreen-Kanal | Ermöglicht die Anzeige der Komponente in einer einzigen Zone. |
| 1x2-Splitscreen-Kanal | Ermöglicht die Anzeige der Assets in zwei Zonen (horizontal geteilt). |
| 2X1 Split Screen Channel | Ermöglicht die Anzeige der Assets in zwei Zonen (vertikal geteilt). |
| 2x2-Splitscreen-Kanal | Ermöglicht die Anzeige der Assets in vier Bereichen (horizontal und vertikal in einer Matrix unterteilt). |
| 2:3-Splitscreen-Kanal | Ermöglicht die Anzeige der Assets in zwei Zonen (horizontal geteilt), wobei eine der Zonen größer als die andere ist. |
| L-Balken-Teilungsbildschirm links oder rechts | Ermöglicht es Inhaltserstellern, verschiedene Arten von Assets in entsprechend großen Zonen anzuzeigen. |

>[!NOTE]
>
>Die Kanäle "Bildschirm teilen"teilen die Anzeige in mehrere Bereiche, sodass Sie mehrere Erlebnisse gleichzeitig nebeneinander abspielen können. Die Erlebnisse können entweder statische Assets/Text oder eingebettete Sequenzen sein.

The following example shows the creation of a Sequence Channel (C *hannelOne*) for a Screens project (*DemoProject*).

![demochannel](assets/demochannel.gif)

>[!NOTE]
>
>Sie können unterschiedliche Bereiche mithilfe der Vorlagenoptionen erstellen, etwa die oben genannten 1x2-, 2x2- oder 2:3-Splitscreen-Kanäle.

***Wichtig***:

Nachdem Sie Inhalte erstellt und dem Kanal hinzugefügt haben, müssen Sie als Nächstes einen Ort und dann eine Anzeige erstellen. Außerdem müssen Sie diesen Kanal einer Anzeige zuweisen. Weitere Informationen finden Sie über die am Ende des Abschnitts genannten Ressourcen.

## Arbeiten mit Kanälen {#working-with-channels}

Sie können Änderungen vornehmen, Eigenschaften und Dashboard anzeigen sowie einen Kanal kopieren, in der Vorschau anzeigen und löschen.

>[!NOTE]
>
>Klicken Sie auf das Symbol auf der linken Seite, um ein Element auszuwählen. Beispiel: Klicken Sie auf das Symbol für den Kanal und führen Sie die Schritte aus, die in der folgenden Abbildung dargestellt sind.

![screen_shot_2019-07-24at103723am](assets/screen_shot_2019-07-24at103723am.png)

### Hinzufügen/Bearbeiten von Inhalt eines Kanals {#adding-editing-content-to-a-channel}

Um Inhalt in einem Kanal hinzuzufügen oder zu bearbeiten, gehen Sie wie folgt vor:

1. Klicken Sie auf den Kanal, den Sie bearbeiten möchten (siehe Abbildung oben).
1. Click **Edit** from the top left corner of the action bar to edit the channel properties. Der Editor wird geöffnet. Sie haben die Möglichkeit, Ihrem Kanal Assets/Komponenten hinzuzufügen, die Sie veröffentlichen möchten.

>[!NOTE]
>
>Sie können Komponenten zu Ihrem Kanal hinzufügen. Weitere Informationen finden Sie unter Komponenten zu einem Kanal **[hinzufügen](adding-components-to-a-channel.md)** .

![demochannel1](assets/demochannel1.gif)

**Hochladen von Videos auf den Kanal** Gehen Sie wie folgt vor, um Videos auf Ihren Kanal hochzuladen:

1. Wählen Sie den Kanal aus, in den Sie das Video hochladen möchten.
1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
1. Wählen Sie unter „Assets“ die Option **Videos** und verschieben Sie die betreffenden Videos per Drag-and-Drop.

>[!NOTE]
>
>If you encounter issues uploading videos in your channel, see [Troubleshooting Videos](troubleshoot-videos.md).

### Anzeigen von Eigenschaften {#viewing-properties}

Um die Eigenschaften eines Kanals anzuzeigen oder zu bearbeiten, gehen Sie wie folgt vor:

1. Klicken Sie auf den Kanal, den Sie bearbeiten möchten.
1. Click **Properties** from the action bar to view/edit the channel properties. Anhand der folgenden Registerkarten können Sie die Optionen ändern.

![properties](assets/properties.gif)

### Anzeigen des Dashboards {#viewing-dashboard}

Um das Dashboard eines Kanals anzuzeigen, gehen Sie wie folgt vor:

1. Klicken Sie auf den Kanal, den Sie bearbeiten möchten.
1. Click **Dashboard** from the action bar to view the dashobard. The **CHANNEL INFORMATION**,**ASSIGNED DISPLAYS**, and **PENDING LAUNCHES** panel opens, as shown in the figure below:

![Dashboard](assets/dashboard.gif)

### Kanalinformationen {#channel-information}

Im Bereich Kanalinformationen werden die Kanaleigenschaften zusammen mit der Vorschau des Kanals beschrieben. Darüber hinaus finden Sie dort Informationen dazu, ob der Kanal offline oder online ist.

Klicken Sie in der in Aktionsleiste **Kanalinformationen** auf (**...**), um Eigenschaften anzuzeigen, Inhalt zu bearbeiten oder den Cache (Offline-Inhalt) für den Kanal zu aktualisieren.

![screen_shot_2017-12-20at82048am](assets/screen_shot_2017-12-20at82048am.png)

### Online- und Offline-Kanäle {#online-and-offline-channels}

>[!NOTE]
>
>Wenn Sie einen Kanal erstellen, ist der Kanal standardmäßig offline.

Wenn Sie einen Kanal erstellen, kann er entweder als Online- oder als Offline-Kanal definiert werden.

An ***Online Channel***, will show the updated content in the real time environment whereas an ***Offline Channel***, shows the cached content.

Gehen Sie wie folgt vor, um den Kanal online zu schalten:

1. Navigieren Sie über **TestProject** &gt; **Channels** &gt; **TestChannel** zum Kanal.

   Wählen Sie den Kanal aus.

   ![screen_shot_2019-08-01at31406pm](assets/screen_shot_2019-08-01at31406pm.png)

   Click **Dashboard** from the action bar to view the status of the player. Der Bereich **KANALINFORMATIONEN **enthält Informationen darüber, ob der Kanal online oder offline ist.

   ![screen_shot_2019-08-01at31458pm](assets/screen_shot_2019-08-01at31458pm.png)

1. Klicken Sie in der Aktionsleiste auf **Eigenschaften** und navigieren Sie zur Registerkarte **Kanal**, wie unten gezeigt:

   ![screen_shot_2019-08-01at31542pm](assets/screen_shot_2019-08-01at31542pm.png)

1. Überprüfen Sie den **Developer** - **Modus (zwingen Sie den Kanal dazu, online zu sein)** , um den Kanal als online zu gestalten.

   Klicken Sie auf **Speichern und schließen**, um Ihre Option zu speichern.

   ![screen_shot_2019-08-01at31658pm](assets/screen_shot_2019-08-01at31658pm.png)

   Navigate back to the channel dashboard and now the **CHANNEL INFORMATION** panel shows the online status of the player.

   ![screen_shot_2019-08-01at31821pm](assets/screen_shot_2019-08-01at31821pm.png)

>[!NOTE]
>
>Wenn Sie den Kanal erneut als offline konfigurieren möchten, deaktivieren Sie die Option "Entwicklermodus"auf der Registerkarte " **Eigenschaften** "(wie in Schritt 3 gezeigt) und klicken Sie anschließend im Bedienfeld " **KANALINFORMATIONEN** "auf "Offline-Inhalt **** aktualisieren", wie in der folgenden Abbildung dargestellt.

![dashboard2](assets/dashboard2.gif)

#### Automatische oder manuelle Aktualisierungen über das Geräte-Dashboard {#automatic-versus-manual-updates-from-the-device-dashboard}

In der folgenden Tabelle werden die Ereignisse im Zusammenhang mit automatischen und manuellen Aktualisierungen über das Geräte-Dashboard zusammengefasst.

<table>
 <tbody>
  <tr>
   <td><strong>Ereignis</strong></td>
   <td><strong>Automatische Aktualisierung des Geräts</strong></td>
   <td><strong>Manuelle Aktualisierung des Geräts</strong></td>
  </tr>
  <tr>
   <td>Änderung im Online-Kanal</td>
   <td>Inhalt automatisch aktualisiert</td>
   <td><p>Inhalt aktualisiert auf "Gerät: Push Config"</p> <p>Oder</p> <p>Inhalt auf <strong><i>Gerät aktualisiert: Neustart</i></strong></p> </td>
  </tr>
  <tr>
   <td>Änderungen im Offline-Kanal, aber Kanal "Push Content"wird NICHT ausgelöst (keine erneute Erstellung von Offline-Paketen)</td>
   <td>Keine Inhaltsaktualisierung</td>
   <td>Keine Inhaltsaktualisierung</td>
  </tr>
  <tr>
   <td>Änderungen im Offline-Kanal und Kanal "Push-Inhalt"werden ausgelöst (neues Offline-Paket)</td>
   <td>Inhalt automatisch aktualisiert</td>
   <td><p>Inhalt auf <strong><i>Gerät aktualisiert: Push-Konfiguration</i></strong></p> <p>Oder</p> <p>Inhalt auf <strong><i>Gerät aktualisiert: Neustart</i></strong></p> </td>
  </tr>
  <tr>
   <td><p>Änderung in Config</p>
    <ul>
     <li>Anzeige (Zwangskanal)</li>
     <li>Gerät</li>
     <li>Kanalzuweisungen (neuer Kanal, entfernter Kanal)</li>
     <li>Kanalzuweisung (Rolle, Ereignis, Planung)</li>
    </ul> </td>
   <td>Konfiguration automatisch aktualisiert</td>
   <td><p>Konfiguration auf <strong><i>Gerät aktualisiert: Push-Konfiguration</i></strong></p> <p>Oder</p> <p>Konfiguration auf <strong><i>Gerät aktualisiert: Neustart</i></strong></p> </td>
  </tr>
 </tbody>
</table>

### Zugewiesene Anzeigen {#assigned-displays}

Das Fenster „Zugewiesene Anzeigen“ zeigt die zum Kanal gehörende Anzeige. Es bietet einen Überblick über die zugewiesene Anzeige und die Auflösung.

Die zugeordneten Anzeigen werden im Fenster **Zugewiesene Anzeigen** aufgelistet, wie unten gezeigt:

![chlimage_1-27](assets/chlimage_1-27.png)

>[!NOTE]
>
>Weitere Informationen zum Erstellen eines Displays an einem Ort finden Sie unter:
>
>* [Orte erstellen und verwalten](managing-locations.md)
>* [Anzeigen erstellen und verwalten](managing-displays.md)
>



Außerdem können Sie auf die Anzeige im Fenster **ZUGEWIESENE ANZEIGEN** klicken, um die Anzeigeinformationen anzuzeigen, wie unten gezeigt:

![chlimage_1-28](assets/chlimage_1-28.png)

### Die nächsten Schritte {#the-next-steps}

Der nächste Schritt nach dem Erstellen eines Kanals und dem Hinzufügen/Bearbeiten von Inhalt in Ihrem Kanal ist das Erstellen eines Orts und einer Anzeige. Schließlich muss dieser Anzeige dann noch ein Kanal zugewiesen werden.

Informationen zu den nächsten Schritten finden Sie in den folgenden Ressourcen:

* [Kanäle erstellen und verwalten](managing-channels.md)
* [Orte erstellen und verwalten](managing-locations.md)
* [Anzeigen erstellen und verwalten](managing-displays.md)

