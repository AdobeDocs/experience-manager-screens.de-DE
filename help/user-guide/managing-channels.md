---
title: Erstellen und Verwalten von Kanälen
description: Erfahren Sie mehr über das Erstellen und Verwalten von Kanälen. Außerdem wird auf dieser Seite das Kanal-Dashboard und die Bearbeitung von Inhalten für einen Kanal erklärt.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 7bbd211a-f54f-42b9-a1b3-516efe6fb579
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 100%

---

# Erstellen und Verwalten von Kanälen {#creating-and-managing-channels}

Ein Kanal zeigt eine Sequenz von Inhalten (Bilder und Videos) oder eine Website oder Single Page Application an.

Auf dieser Seite wird gezeigt, wie Kanäle für AEM Screens erstellt und verwaltet werden.

**Voraussetzungen**:

* [Konfigurieren und Bereitstellen von Screens](configuring-screens-introduction.md)
* [Erstellen und Verwalten von Screens-Projekten](creating-a-screens-project.md)

## Erstellen von neuen Kanälen {#creating-a-new-channel}

Nachdem Sie Ihr Projekt für AEM Screens erstellt haben, gehen Sie wie folgt vor, um einen Kanal für Ihr Projekt zu erstellen:

1. Klicken Sie auf den Link zu Adobe Experience Manager (oben links) und dann auf „Screens“.  Sie haben alternativ die Möglichkeit, direkt zur folgenden URL zu wechseln: `https://localhost:4502/screens.html/content/screens`.

1. Navigieren Sie zu Ihrem Screens-Projekt und klicken Sie auf den Ordner **Kanäle**.

1. Klicken Sie in der Aktionsleiste auf **Erstellen**.

   ![demochannel](assets/create-channel1.png)

1. Klicken Sie im Assistenten zum **Erstellen** auf die Vorlage **Sequenz-Kanal** und dann auf **Weiter**.

   ![demochannel](assets/create-channel2.png)

1. Geben Sie unter „Titel“ den Wert **ScreensChannel** ein und klicken Sie auf **Erstellen**.

   ![demochannel](assets/create-project4.png)

1. Dem **Kanal-Ordner** wird nun ein Sequenzkanal hinzugefügt.

### Kanaltypen {#channel-types}

Beim Verwenden des Assistenten stehen unter anderem die folgenden Vorlagenoptionen zur Verfügung:

| **Vorlagenoption** | **Beschreibung** |
|---|---|
| Kanal-Ordner | Zum Erstellen eines Ordners zum Speichern von Kanalsammlungen. |
| Sequenzkanal | Zum Erstellen eines Kanals zum sequenziellen Wiedergeben der Komponenten (einzeln in einer Dia-Show). |
| Anwendungskanal | Zum Anzeigen benutzerdefinierter Web-Anwendungen im Screens-Player. |
| 1×1-Splitscreen-Kanal | Zum Anzeigen einer Komponente in einer einzigen Zone. |
| 1×2-Splitscreen-Kanal | Zum Anzeigen der Assets in zwei Zonen (horizontal geteilt). |
| 2×1-Splitscreen-Kanal | Zum Anzeigen der Assets in zwei Zonen (vertikal geteilt). |
| 2×2-Splitscreen-Kanal | Zum Anzeigen der Assets in vier Zonen (horizontal und vertikal in einer Matrix geteilt). |
| 2:3-Splitscreen-Kanal | Zum Anzeigen der Assets in zwei Zonen (horizontal geteilt), wobei eine Zone größer als die andere ist. |
| Splitscreen-Kanal mit L-Balken links oder rechts | Inhaltsautorinnen und Inhaltsautoren können verschiedene Arten von Assets in entsprechend großen Zonen anzeigen. |

>[!NOTE]
>
>Die Splitscreen-Kanäle teilen die Anzeige in mehrere Zonen, sodass Sie mehrere Erlebnisse gleichzeitig nebeneinander wiedergeben können. Die Erlebnisse können entweder statische Assets/Text oder eingebettete Sequenzen sein.

>[!IMPORTANT]
>
>Nachdem Sie die Inhalte erstellt und dem Kanal hinzugefügt haben, müssen Sie als Nächstes einen Ort und dann eine Anzeige erstellen. Außerdem müssen Sie diesen Kanal einer Anzeige zuweisen. Weitere Informationen finden Sie über die am Ende des Abschnitts genannten Ressourcen.

## Arbeiten mit Kanälen {#working-with-channels}

Sie können Änderungen vornehmen, Eigenschaften und Dashboard anzeigen sowie einen Kanal kopieren, in der Vorschau anzeigen und löschen.


![screen_shot_2019-07-24at103723am](assets/screen_shot_2019-07-24at103723am.png)

### Hinzufügen/Bearbeiten von Inhalt eines Kanals {#adding-editing-content-to-a-channel}

Um Inhalt in einem Kanal hinzuzufügen oder zu bearbeiten, gehen Sie wie folgt vor:

1. Klicken Sie auf den Kanal, den Sie bearbeiten möchten (wie in der obigen Abbildung gezeigt).
1. Klicken Sie in der oberen linken Ecke der Aktionsleiste auf **Bearbeiten**, um die Kanaleigenschaften zu bearbeiten. Der Editor wird geöffnet. Sie haben die Möglichkeit, Ihrem Kanal Assets/Komponenten hinzuzufügen, die Sie veröffentlichen möchten.

>[!NOTE]
>Sie können Ihrem Kanal Komponenten hinzufügen. Weitere Informationen finden Sie unter **[Hinzufügen von Komponenten zu Kanälen](adding-components-to-a-channel.md)**.

![demochannel1](assets/demochannel1.gif)

**Hochladen von Videos in den Kanal**

Gehen Sie wie folgt vor, um Videos in Ihren Kanal hochzuladen:

1. Klicken Sie auf den Kanal, in den Sie das Video hochladen möchten.
1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**.
1. Klicken Sie im Editor unter „Assets“ auf die Option **Videos** und verschieben Sie die betreffenden Videos per Drag-and-Drop.

>[!NOTE]
>Wenn Sie beim Hochladen von Videos in Ihren Kanal auf Probleme stoßen, lesen Sie [Fehlerbehebung beim Arbeiten mit Videos](troubleshoot-videos.md).

### Anzeigen oder Bearbeiten von Eigenschaften eines Kanals {#viewing-properties}

1. Klicken Sie auf den Kanal, den Sie bearbeiten möchten.
1. Klicken Sie in der Aktionsleiste auf **Eigenschaften**, um die Kanaleigenschaften anzuzeigen/zu bearbeiten. Anhand der folgenden Registerkarte können Sie die Optionen ändern.

![Eigenschaften](assets/properties.gif)

### Anzeigen des Dashboards {#viewing-dashboard}

1. Klicken Sie auf den Kanal, den Sie bearbeiten möchten.
1. Klicken Sie in der Aktionsleiste auf **Dashboard**.

![dashboard](assets/dashboard.gif)

### Kanalinformationen {#channel-information}

Im Bedienfeld „Kanalinformationen“ werden die Kanaleigenschaften zusammen mit der Kanalvorschau beschrieben. Darüber hinaus finden Sie dort Informationen dazu, ob der Kanal offline oder online ist.

Klicken Sie in der in Aktionsleiste **KANALINFORMATIONEN** auf (**...**), um Eigenschaften anzuzeigen, Inhalt zu bearbeiten oder den Cache (Offline-Inhalt) für den Kanal zu aktualisieren.

![screen_shot_2017-12-20at82048am](assets/screen_shot_2017-12-20at82048am.png)

#### Anzeigen des Manifests {#view-manifest}

Sie können das Manifest vom Kanal-Dashboard aus anzeigen.

>[!IMPORTANT]
>Diese Option ist nur mit AEM 6.4 Feature Pack 8 oder AEM 6.5 Feature Pack 4 verfügbar.

Führen Sie die folgenden Schritte aus, um diese Option im Kanal-Dashboard zu aktivieren:

1. **Kanal auf „Offline“ festlegen**
   1. Klicken Sie auf den Kanal und dann in der Aktionsleiste auf **Eigenschaften**.
   1. Navigieren Sie zur Registerkarte **Kanal** und deaktivieren Sie die Option **Entwicklermodus (Kanal erzwingen, um online zu sein)**.
   1. Klicken Sie auf **Speichern und schließen**.
1. **Offline-Inhalt aktualisieren**
   1. Klicken Sie auf den Kanal und dann in der Aktionsleiste auf **Dashboard**.
   1. Navigieren Sie zum Bedienfeld **KANALINFORMATIONEN** und klicken Sie auf *…*
   1. Klicken Sie auf **Offline-Inhalt aktualisieren**.

Jetzt sollten Sie im Kanal-Dashboard im Dialogfeld **KANALINFORMATIONEN** die Option **Manifest anzeigen** sehen.

![image1](assets/channel-one.png)


### Online- und Offline-Kanäle {#online-and-offline-channels}

>[!NOTE]
>Wenn Sie einen Kanal erstellen, ist der Kanal standardmäßig offline.

Wenn Sie einen Kanal erstellen, kann er entweder als Online- oder als Offline-Kanal definiert werden.

Ein ***Online-Kanal*** zeigt den aktualisierten Inhalt in der Echtzeitumgebung an, während ein ***Offline-Kanal*** den im Cache gespeicherten Inhalt wiedergibt.

Gehen Sie wie folgt vor, um den Kanal online zu schalten:

1. Navigieren Sie über **TestProject** > **Kanäle** > **TestChannel** zum Kanal.

   Klicken Sie auf den Kanal.

   ![screen_shot_2019-08-01at31406pm](assets/screen_shot_2019-08-01at31406pm.png)

   Klicken Sie in der Aktionsleiste auf **Dashboard**, um den Status des Players anzuzeigen. Im Fenster **KANALINFORMATIONEN** wird angezeigt, ob der Kanal online oder offline ist.

   ![screen_shot_2019-08-01at31458pm](assets/screen_shot_2019-08-01at31458pm.png)

1. Klicken Sie in der Aktionsleiste auf **Eigenschaften** und navigieren Sie zur Registerkarte **Kanal**, wie unten gezeigt:

   ![screen_shot_2019-08-01at31542pm](assets/screen_shot_2019-08-01at31542pm.png)

1. Aktivieren Sie den **Entwicklermodus** **(erzwingen, dass der Kanal online ist)**, um den Kanal in den Online-Modus zu schalten.

   Klicken Sie auf **Speichern und schließen**, um Ihre Option zu speichern.

   ![screen_shot_2019-08-01at31658pm](assets/screen_shot_2019-08-01at31658pm.png)

   Navigieren Sie zurück zum Kanal-Dashboard. Das Bedienfeld **KANALINFORMATIONEN** zeigt jetzt an, dass der Player online ist.

   ![screen_shot_2019-08-01at31821pm](assets/screen_shot_2019-08-01at31821pm.png)

>[!NOTE]
>Um den Kanal erneut als offline zu konfigurieren, deaktivieren Sie auf der Registerkarte **Eigenschaften** die Option „Entwicklermodus“ (wie in Schritt (3) gezeigt). Klicken Sie dann im Bedienfeld **KANALINFORMATIONEN** auf **Offline-Inhalt aktualisieren**, wie in der folgenden Abbildung dargestellt.

![dashboard2](assets/dashboard2.gif)

#### Automatische oder manuelle Aktualisierungen über das Geräte-Dashboard {#automatic-versus-manual-updates-from-the-device-dashboard}

In der folgenden Tabelle werden die Ereignisse im Zusammenhang mit automatischen und manuellen Aktualisierungen über das Geräte-Dashboard zusammengefasst.

<table>
 <tbody>
  <tr>
   <td><strong>Ereignis</strong></td>
   <td><strong>Automatische Geräteaktualisierung</strong></td>
   <td><strong>Manuelle Geräteaktualisierung</strong></td>
  </tr>
  <tr>
   <td>Änderung am Online-Kanal</td>
   <td>Inhalt wird automatisch aktualisiert</td>
   <td><p>Inhalt aktualisiert über „Gerät: Push-Konfiguration“</p> <p>ODER</p> <p>Inhalt aktualisiert über <strong><i>Gerät: Neustart</i></strong></p> </td>
  </tr>
  <tr>
   <td>Änderung am Offline-Kanal, aber „Push-Inhalt“ wird für den Kanal NICHT ausgelöst (keine Neuerstellung des Offline-Pakets)</td>
   <td>Keine Aktualisierung des Inhalts</td>
   <td>Keine Aktualisierung des Inhalts</td>
  </tr>
  <tr>
   <td>Änderung am Offline-Kanal und „Push-Inhalt“ wird für den Kanal ausgelöst (neues Offline-Paket)</td>
   <td>Inhalt wird automatisch aktualisiert</td>
   <td><p>Inhalt aktualisiert über <strong><i>Gerät: Push-Konfiguration</i></strong></p> <p>ODER</p> <p>Inhalt aktualisiert über <strong><i>Gerät: Neustart</i></strong></p> </td>
  </tr>
  <tr>
   <td><p>Änderung an Konfiguration</p>
    <ul>
     <li>Anzeige (erzwungener Kanal)</li>
     <li>Gerät</li>
     <li>Kanalzuweisungen (neuer Kanal, entfernter Kanal)</li>
     <li>Kanalzuweisung (Rolle, Ereignis, Planung)</li>
    </ul> </td>
   <td>Konfiguration wird automatisch aktualisiert</td>
   <td><p>Konfiguration wird aktualisiert über <strong><i>Gerät: Push-Konfiguration</i></strong></p> <p>ODER</p> <p>Konfiguration aktualisiert über <strong><i>Gerät: Neustart</i></strong></p> </td>
  </tr>
 </tbody>
</table>

### Zugewiesene Anzeigen {#assigned-displays}

Im Bedienfeld **Zugewiesene Anzeigen** wird die zum Kanal gehörende Anzeige angezeigt. Es bietet einen Überblick über die zugewiesene Anzeige und die Auflösung.

Die zugeordneten Anzeigen werden im Bedienfeld **Zugewiesene Anzeigen** aufgelistet, wie unten gezeigt:

![chlimage_1-27](assets/chlimage_1-27.png)

>[!NOTE]
>Weitere Informationen zum Erstellen einer Anzeige an einem Standort finden Sie unter:
>
>* [Erstellen und Verwalten von Standorten](managing-locations.md)
>* [Erstellen und Verwalten von Anzeigen](managing-displays.md)
>

Außerdem können Sie auf die Anzeige im Bedienfeld **ZUGEWIESENE ANZEIGEN** klicken, um Anzeigeinformationen anzuzeigen, wie unten dargestellt:

![chlimage_1-28](assets/chlimage_1-28.png)

### Die nächsten Schritte {#the-next-steps}

Der nächste Schritt nach dem Erstellen eines Kanals und dem Hinzufügen/Bearbeiten von Inhalt in Ihrem Kanal ist das Erstellen eines Orts und einer Anzeige.  Schließlich muss dieser Anzeige dann noch ein Kanal zugewiesen werden.

Informationen zu den nächsten Schritten finden Sie in den folgenden Ressourcen:

* [Erstellen und Verwalten von Kanälen](managing-channels.md)
* [Erstellen und Verwalten von Standorten](managing-locations.md)
* [Erstellen und Verwalten von Anzeigen](managing-displays.md)
