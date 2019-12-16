---
title: Hinzufügen von Komponenten zu Kanälen
seo-title: Hinzufügen von Komponenten zu Kanälen
description: Folgen Sie dieser Seite, um sich über das Hinzufügen von Komponenten zu Kanälen in AEM Screens-Projekten zu informieren.
seo-description: Folgen Sie dieser Seite, um sich über das Hinzufügen von Komponenten zu Kanälen in AEM Screens-Projekten zu informieren.
uuid: 205d0edd-a696-47d0-a859-5f44d48c5e4a
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: bfbdd6eb-4921-4c2d-a179-1cac4583d568
docset: aem65
translation-type: tm+mt
source-git-commit: cec2a2f8b056bf713e56a9fab08d88e29263820b

---


# Hinzufügen von Komponenten zu Kanälen{#adding-components-to-a-channel}

Komponenten sind die grundlegenden Elemente des AEM(Adobe Experience Manager)-Erlebnisses. Sie können verschiedene Komponenten nutzen und diese Kanälen in AEM Screens-Projekten hinzufügen.

## Komponenten in AEM Screens {#components-in-aem-screens}

AEM Screens bietet verschiedene AEM-Komponenten zur Verwendung in Screens-Projekten.

### Anzeigen von AEM Screens-Komponenten {#viewing-aem-screens-components}

Beim Erstellen eines AEM Screens-Projekts wird eine Liste der Standardkomponenten angezeigt, die dem Projekt hinzugefügt werden können.

Gehen Sie wie folgt vor, um die Standardkomponenten für ein Screens-Projekt anzuzeigen:

1. Wählen Sie den Kanal aus. Beispiel: **We.Retail In-Store** &gt; **Kanäle** &gt;** Idle Channel**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den AEM-Editor zu öffnen.
1. Klicken Sie in der Seitenleiste auf das Symbol **+**, um die Komponenten zu öffnen.
1. Alle Komponenten, die standardmäßig in einem AEM Screens-Projekt enthalten sind, werden angezeigt (siehe nachfolgende Abbildung).

![screen_shot_2017-12-18at21350pm](assets/screen_shot_2017-12-18at21350pm.png)

### Hinzufügen neuer Komponenten {#adding-a-new-component}

AEM stellt eine Reihe von Komponenten bereit. Sie können Ihrem Projekt jederzeit weitere (nicht standardmäßig enthaltene) Komponenten hinzufügen, sofern diese mit AEM Screens kompatibel sind.

Im folgenden Beispiel sehen Sie, wie einem AEM Screens-Projekt eine Livefyre-Komponente hinzugefügt wird:

1. Wählen Sie den Kanal aus, dem eine neue Komponente hinzugefügt werden soll. Beispiel: **We.Retail In-Store** &gt; **Kanäle** &gt;** Idle Channel**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
1. Wählen Sie den **Designmodus** aus.
1. Wählen Sie rechts den kompletten Designeditor aus und klicken Sie auf das Einstellungssymbol, um das Dialogfeld **ParSys-Design** zu öffnen.
1. Sie können die Komponenten auswählen, die dem AEM Screens-Projekt hinzugefügt werden sollen. Im folgenden Beispiel wird das Hinzufügen der **Livefyre** -Komponente zu einem AEM Screens-Projekt veranschaulicht.

![adding_components](assets/adding_components.gif)

>[!NOTE]
>
>Auf die gleiche Weise können Sie dem Projekt eine beliebige Anzahl anderer neuer Komponenten hinzufügen, die mit AEM Screens kompatibel sind.

## Grundlegendes zu AEM Screens-Komponenten {#understanding-aem-screen-components}

Im folgenden Abschnitt werden die AEM Screens-Komponenten erläutert, die Sie in Ihrem Projekt verwenden können.

>[!NOTE]
>
>Um die Eigenschaften einer Komponente anzuzeigen, wählen Sie die Komponente aus und klicken Sie auf das Hammersymbol. Daraufhin werden die Eigenschaften geöffnet/eingeblendet.

### Anwendung {#application}

Mit der Komponente **Anwendung** können Sie Kanälen eine Anwendung hinzufügen.

Die Komponente „Anwendung“ verfügt über die folgenden Eigenschaften:

| **Eigenschaft** | **Beschreibung** |
|---|---|
| ***Anwendungspfad*** | Damit wird der absolute Pfad zur Anwendung festgelegt. |
| ***Dauer (ms)*** | Damit wird die Dauer der Anwendung festgelegt. Standardmäßig ist die Dauer auf -1 eingestellt, d. h. das Element wird für immer ausgeführt (d. h. eine Einzelseitenanwendung). Wird unter „Dauer“ ein Wert über 0 festgelegt, wird das Element für die angegebene Dauer angezeigt und dann zum nächsten Element gewechselt. |

Im folgenden Beispiel sehen Sie, wie die Komponente „Anwendung“ hinzugefügt wird, einschließlich einer Vorschau ihrer Eigenschaften:

![adding_componentsApplication](assets/adding_componentsapplication.gif)

>[!NOTE]
>
>Im Beispiel oben sehen Sie, wie Eigenschaften aller nachfolgenden Komponenten aufgerufen werden können.

### Kanal {#channel}

Mit der Komponente **Kanal** können Sie Projekten einen vollständigen Kanal hinzufügen.

Die Komponente „Kanal“ verfügt über die folgenden Eigenschaften:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><strong><em>Kanalpfad</em></strong></td>
   <td>Damit wird der absolute Pfad zur Anwendung festgelegt.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Dauer (ms)</em></strong></td>
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wenn Sie die Dauer auf -1 festlegen, wird der eingebettete Kanal in einem bestimmten Kanal vollständig ausgeführt.</td>
  </tr>
 </tbody>
</table>

### Eingebettete Seite {#embedded-page}

Mit der Komponente **Eingebettete Seite** können Sie einem Projekt eine eingebettete Seite hinzufügen. Beispiel: eine Webanwendung oder einen Produktkatalog.

Die Komponente „Eingebettete Seite“ verfügt über die folgenden Eigenschaften:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><strong><em>Seitenpfad<br /> </em></strong></td>
   <td>Damit wird der absolute Pfad zum Pfad festgelegt.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Dauer (ms)</em></strong></td>
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wenn Sie die Dauer auf -1 festlegen, wird der eingebettete Kanal in einem bestimmten Kanal vollständig ausgeführt.</td>
  </tr>
 </tbody>
</table>

### Eingebettete Sequenz {#embedded-sequence}

>[!NOTE]
>
>Refer to [Embedded Sequences](embedded-sequences.md) under Authoring Screens section, to learn in detail about embedded sequences.

Mit der Komponente „Eingebettete Sequenz“ können Sie einen eingebetteten Sequenz-Kanal in einem vorhandenen Kanal (mit anderen Assets) hinzufügen.

Die Komponente „Eingebettete Sequenz“ verfügt über die folgenden Seiteneigenschaften:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td>Kanalpfad</td>
   <td>Damit wird der absolute Pfad zu der Sequenz festgelegt, die in den Kanal aufgenommen werden soll.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Dauer (ms)</em></strong></td>
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wenn Sie die Dauer auf -1 festlegen, wird der eingebettete Kanal in einem bestimmten Kanal vollständig ausgeführt.</td>
  </tr>
  <tr>
   <td><strong><em>Strategie</em></strong></td>
   <td>Set it to <strong>original</strong> or <strong>single</strong>. Setting the value to <strong>original</strong> means that the subsequence will run fully on each cycle of the parent sequence. The other possible value is <strong>single</strong> and that would only show one item of the subsequence on each run (for instance, the 1st item on the first loop, 2nd item on the second loop, and so on.)</td>
  </tr>
 </tbody>
</table>

### Dynamische eingebettete Sequenz {#dynamic-embedded-sequence}

Mit der Komponente „Dynamische eingebettete Sequenz“ können Sie, abhängig von der Kanalrolle, so wie oben beschrieben eine Sequenz hinzufügen. 

Refer to [Embedded Sequences](embedded-sequences.md) under Authoring Screens section, to learn in detail about embedded sequences.

Die Komponente „Dynamische eingebettete Sequenz“ verfügt über die folgenden Eigenschaften:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><strong><em>Kanalzuordnungsrolle</em></strong><br /> </td>
   <td>Geben Sie die Kanalrolle ein.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Dauer (ms)</em></strong></td>
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wenn Sie die Dauer auf -1 festlegen, wird der eingebettete Kanal in einem bestimmten Kanal vollständig ausgeführt.</td>
  </tr>
  <tr>
   <td><strong><em>Strategie</em></strong></td>
   <td>Set it to <strong>original</strong> or <strong>single</strong>. Setting the value to <strong>original</strong> means that the subsequence will run fully on each cycle of the parent sequence. The other possible value is <strong>single</strong> and that would only show one item of the subsequence on each run (for instance, the 1st item on the first loop, 2nd item on the second loop, and so on.)</td>
  </tr>
 </tbody>
</table>

### Experience Fragment {#experience-fragment}

Mit einem Erlebnisfragment können Sie Ihrem AEM-Bildschirmkanal ein Erlebnisfragment (eine Gruppe aus einer oder mehreren Komponenten, einschließlich Inhalt und Layout, auf die auf Seiten verwiesen werden kann) hinzufügen. Ziehen Sie die Komponente in den AEM-Editor und wählen Sie das Erlebnisfragment aus.

Weitere Informationen zum Erstellen eines Erlebnisfragments und dessen Nutzung in einem AEM Screens-Projekt finden Sie unter [Verwenden von Erlebnisfragmenten](experience-fragments-in-screens.md).

![exp](assets/exp.gif)

| **Eigenschaft** | **Beschreibung** |
|---|---|
| **Experience Fragment** |
| ***Experience Fragment*** | Wählen Sie das Erlebnisfragment aus. |
| ***Dauer*** | Wählen Sie die gesamte Dauer des Erlebnisfragments aus, das im Kanal wiedergegeben wird. |
| **Offline-Konfiguration** |
| ***Client-seitige Bibliotheken*** | JavaScript- und CSS-Dateien. |
| ***Statische Dateien*** | Statische Dateien, die Sie als Offline-Konfigurationen zu Ihrem Erlebnisfragment hinzufügen können. |

>[!NOTE]
>
>Die **clientseitigen Bibliotheken** und die **statischen Dateien** , die Sie aus dieser Komponente hinzufügen, werden zusätzlich zu den bereits konfigurierten **clientseitigen Bibliotheken** und statischen Dateien bereitgestellt, die aus den **Eigenschaften** des Erlebnisfragments hinzugefügt werden.

### Bild{#image}

Mit der Komponente „Bild“ können Sie dem Kanal ein Bild hinzufügen.

Das Bild-Asset besitzt die drei Registerkarten **Bild**, **Erreichbarkeit** und **Sequenz**:

| **Eigenschaft** | **Beschreibung** |
|---|---|
| **Bild** |
| ***Bild-Asset*** | Damit wird das Bild-Asset festgelegt. |
| ***Titel*** | Hierbei handelt es sich um den Titel des Bildes. |
| ***Verknüpfung zu*** | Damit wird dem Bild ein Link hinzugefügt. |
| ***Beschreibung*** | Hierbei handelt es sich um eine kurze Beschreibung des Bildes. |
| ***Größe*** | Hierbei handelt es sich um die Größe des Bildes. |
| **Barrierefreiheit** |
| ***Alternativtext*** | Hierbei handelt es sich um Alternativtext für das Bild. |
| **Sequenz** |
| ***Dauer*** | Standardmäßig ist die Dauer auf *8000 ms* festgelegt. Wenn Sie die Wiedergabedauer des Bildes ändern möchten, aktualisieren Sie das Feld **Dauer** . |

### Übergang {#transition}

Mit der Komponente „Übergang“ können Sie Screens-Projekten einen Übergang hinzufügen.

Die folgende Abbildung zeigt die Übergangskomponente (per Drag &amp; Drop hinzugefügt) im Editor.

![screen_shot_2019-07-25at104237am](assets/screen_shot_2019-07-25at104237am.png)

Wählen Sie das Übergangssymbol aus und klicken Sie auf das Symbol " **Konfigurieren** "(Schraubenschlüsselsymbol), um das Dialogfeld " **Übergang** "zu öffnen. Dieses Dialogfeld enthält drei Registerkarten:

* **Übergang**
* **Sequenz**
* **Activation**

>[!NOTE]
>
>Standardmäßig ist die Sequenz auf 600 ms eingestellt. Sie können die Übergangssequenz auf einen anderen Wert aktualisieren, indem Sie die Registerkarte " **Sequenz** "verwenden.

![Übergang](assets/transition.gif)

Die Komponente „Übergang“ verfügt über die folgenden Eigenschaften:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><strong>Übergang</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Typ</em></strong></td>
   <td><p>Hierbei handelt es sich um den Typ des Übergangs zwischen zwei aufeinanderfolgenden Elementen. Der <strong>Übergangstyp</strong> umfasst die folgenden Optionen:</p>
    <ul>
     <li><strong>Normal</strong></li>
     <li><strong>Überblendung</strong></li>
     <li><strong>Von rechts einfügen</strong></li>
     <li><strong>Von links einfügen</strong></li>
     <li><strong>Von oben einfügen</strong></li>
     <li><strong>Von unten einfügen</strong></li>
    </ul> </td>
  </tr>
  <tr>
   <td><strong>Sequenz</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Dauer</em></strong></td>
   <td>Damit wird die Gesamtdauer des Übergangs festgelegt. Standardmäßig ist sie auf 600 ms eingestellt.</td>
  </tr>
  <tr>
   <td><strong>Activation</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Aktiv von</em></strong></td>
   <td>Zeitstempel, der beschreibt, wann der Übergang aktiv sein kann.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Aktiv bis</em></strong></td>
   <td>Zeitstempel, der so lange beschreibt, bis der Übergang aktiv sein kann.</td>
  </tr>
  <tr>
   <td><strong><em>Plan</em></strong></td>
   <td>Fügen Sie einen vordefinierten Zeitplan hinzu.</td>
  </tr>
 </tbody>
</table>

### Video {#video}

Mit der Komponente „Video“ können Sie Screens-Projekten ein Video hinzufügen.

Die Komponente „Video“ verfügt über die folgenden Eigenschaften:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><em><strong>Video-Asset</strong></em></td>
   <td>Damit wird der Link zum Video festgelegt.</td>
  </tr>
  <tr>
   <td><em><strong>Dauer</strong></em></td>
   <td>Damit wird die Dauer des Videos festgelegt. Standardmäßig ist die Dauer auf -1 eingestellt, d. h. das Element wird für immer ausgeführt. Wird unter „Dauer“ ein Wert über 0 festgelegt, wird das Element für die angegebene Dauer angezeigt und dann zum nächsten Element gewechselt.<br /> </td>
  </tr>
  <tr>
   <td><em><strong>Rendering</strong></em></td>
   <td><p>Wenn das Seitenverhältnis des Videos nicht auf den Bildschirm passt, können Sie „Rendering“ auf <strong>enthalten</strong> oder <strong>Cover</strong> einstellen.</p> <p><em>enthalten</em> bedeutet, dass das vollständige Video gezeigt wird; fehlende Bereiche werden mit schwarzem Rand aufgefüllt.</p> <p><em>Cover</em> bedeutet, dass das Video zwar den gesamten Viewport abdeckt, aber dass bestimmte, über die Seiten hinausgehende Teile nicht dargestellt werden.</p> </td>
  </tr>
  <tr>
   <td><em><strong>Größe</strong></em></td>
   <td>Hierbei handelt es sich um die Größe des Videos.</td>
  </tr>
 </tbody>
</table>

