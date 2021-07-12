---
title: Hinzufügen von Komponenten zu Kanälen
seo-title: Hinzufügen von Komponenten zu Kanälen
description: Auf dieser Seite erfahren Sie mehr über das Hinzufügen von Komponenten zu Kanälen in AEM Screens-Projekten.
seo-description: Auf dieser Seite erfahren Sie mehr über das Hinzufügen von Komponenten zu Kanälen in AEM Screens-Projekten.
uuid: 205d0edd-a696-47d0-a859-5f44d48c5e4a
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: bfbdd6eb-4921-4c2d-a179-1cac4583d568
docset: aem65
feature: Inhaltserstellung in Screens
role: Admin, Developer
level: Intermediate
exl-id: 56dbe098-05db-4fc3-977f-e50a0a312d64
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '1466'
ht-degree: 100%

---

# Hinzufügen von Komponenten zu Kanälen{#adding-components-to-a-channel}

Komponenten sind die grundlegenden Elemente des AEM (Adobe Experience Manager)-Erlebnisses. Sie können verschiedene Komponenten nutzen und Kanälen in AEM Screens-Projekten hinzufügen.

## Komponenten in AEM Screens {#components-in-aem-screens}

AEM Screens bietet verschiedene AEM-Komponenten, die sich in Screens-Projekten verwenden lassen.

### Anzeigen von AEM Screens-Komponenten {#viewing-aem-screens-components}

Beim Erstellen eines AEM Screens-Projekts wird eine Liste der Standardkomponenten angezeigt, die dem Projekt hinzugefügt werden können.

Gehen Sie wie folgt vor, um die Standardkomponenten für ein Screens-Projekt anzuzeigen:

1. Wählen Sie den Kanal aus. Beispiel: **We.Retail In-Store** > **Kanäle** > **Idle Channel**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den AEM-Editor zu öffnen.
1. Klicken Sie in der Seitenleiste auf das Symbol **+**, um die Komponenten zu öffnen.
1. Alle Komponenten, die standardmäßig in einem AEM Screens-Projekt enthalten sind, werden angezeigt (siehe nachfolgende Abbildung).

![screen_shot_2017-12-18at21350pm](assets/screen_shot_2017-12-18at21350pm.png)

### Hinzufügen neuer Komponenten {#adding-a-new-component}

AEM stellt eine Reihe von Komponenten bereit. Sie können Ihrem Projekt jederzeit weitere (nicht standardmäßig enthaltene) Komponenten hinzufügen, sofern diese mit AEM Screens kompatibel sind.

Im folgenden Beispiel sehen Sie, wie einem AEM Screens-Projekt eine Livefyre-Komponente hinzugefügt wird:

1. Wählen Sie den Kanal aus, dem eine neue Komponente hinzugefügt werden soll. Beispiel: **We.Retail In-Store** > **Kanäle** > **Idle Channel**.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.
1. Wählen Sie den Modus **Design** aus.
1. Wählen Sie rechts den kompletten Designeditor aus und klicken Sie auf das Einstellungssymbol, um das Dialogfeld **ParSys-Design** zu öffnen.
1. Sie können die Komponenten auswählen, die dem AEM Screens-Projekt hinzugefügt werden sollen. Im folgenden Beispiel sehen Sie, wie einem AEM Screens-Projekt eine **Livefyre**-Komponente hinzugefügt wird.

![adding_components](assets/adding_components.gif)

>[!NOTE]
>
>Auf die gleiche Weise können Sie dem Projekt eine beliebige Anzahl anderer neuer Komponenten hinzufügen, die mit AEM Screens kompatibel sind.

## Grundlegendes zu AEM Screens-Komponenten {#understanding-aem-screen-components}

Im folgenden Abschnitt werden die AEM Screens-Komponenten beschrieben, die Sie für Projekte nutzen können.

>[!NOTE]
>
>Um die Eigenschaften einer Komponente anzuzeigen, wählen Sie die Komponente aus und klicken Sie auf das Hammersymbol. Daraufhin werden die Eigenschaften geöffnet/eingeblendet.

### Anwendung {#application}

Mit der Komponente **Anwendung** können Sie Kanälen eine Anwendung hinzufügen.

Die Komponente „Anwendung“ verfügt über die folgenden Eigenschaften:

| **Eigenschaft** | **Beschreibung** |
|---|---|
| ***Anwendungspfad*** | Damit wird der absolute Pfad zur Anwendung festgelegt. |
| ***Dauer (ms)*** | Damit wird die Dauer der Anwendung festgelegt. Standardmäßig ist die Dauer auf den Wert „-1“ eingestellt. Dies bedeutet, dass das Element auf unbestimmte Zeit ausgeführt wird (bei einer Single Page Application). Wird unter „Dauer“ ein Wert über 0 festgelegt, wird das Element für die angegebene Dauer angezeigt. Anschließend wird zum nächsten Element gewechselt. |

Im folgenden Beispiel sehen Sie, wie die Komponente „Anwendung“ hinzugefügt wird, einschließlich einer Vorschau ihrer Eigenschaften:

![adding_componentsapplication](assets/adding_componentsapplication.gif)

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
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wird unter „Dauer“ ein Wert von „-1“ eingestellt, bedeutet dies, dass der eingebettete Kanal in einem bestimmten Kanal in vollständiger Länge ausgeführt wird.</td>
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
   <td>Damit wird der absolute Pfad zum Kanal festgelegt.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Dauer (ms)</em></strong></td>
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wird unter „Dauer“ ein Wert von „-1“ eingestellt, bedeutet dies, dass der eingebettete Kanal in einem bestimmten Kanal in vollständiger Länge ausgeführt wird.</td>
  </tr>
 </tbody>
</table>

### Eingebettete Sequenz {#embedded-sequence}

>[!NOTE]
>
>Ausführliche Informationen zu eingebetteten Sequenzen finden Sie in „Inhaltserstellung in Screens“ unter [Eingebettete Sequenzen](embedded-sequences.md).

Mit der Komponente „Eingebettete Sequenz“ können Sie einen eingebetteten Sequenzkanal in einem vorhandenen Kanal (mit anderen Assets) hinzufügen.

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
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wird unter „Dauer“ ein Wert von „-1“ eingestellt, bedeutet dies, dass der eingebettete Kanal in einem bestimmten Kanal in vollständiger Länge ausgeführt wird.</td>
  </tr>
  <tr>
   <td><strong><em>Strategie</em></strong></td>
   <td>Für diese Eigenschaft kann <strong>original</strong> oder <strong>einzeln</strong> festgelegt werden. Ist der Wert auf <strong>original</strong> eingestellt, wird die Teilsequenz bei jedem Zyklus der übergeordneten Sequenz vollständig ausgeführt. Der andere mögliche Wert lautet <strong>einzeln</strong>. Dabei wird nur ein Element der Teilsequenz bei jeder Ausführung angezeigt (beispielsweise das erste Element bei der ersten Schleife, das zweite Element bei der zweiten Schleife usw.).</td>
  </tr>
 </tbody>
</table>

### Dynamische eingebettete Sequenz {#dynamic-embedded-sequence}

Mit der Komponente „Dynamische eingebettete Sequenz“ können Sie, abhängig von der Kanalrolle, wie oben beschrieben eine Sequenz hinzufügen.

Ausführliche Informationen zu eingebetteten Sequenzen finden Sie in „Inhaltserstellung in Screens“ unter [Eingebettete Sequenzen](embedded-sequences.md).

Die Komponente „Dynamische eingebettete Sequenz“ verfügt über die folgenden Eigenschaften:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><strong><em>Kanalzuordnungsrolle</em></strong><br /> </td>
   <td>Geben Sie die Kanalrolle an.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Dauer (ms)</em></strong></td>
   <td>Damit wird die Gesamtdauer des Kanals festgelegt. Wird unter „Dauer“ ein Wert von „-1“ eingestellt, bedeutet dies, dass der eingebettete Kanal in einem bestimmten Kanal in vollständiger Länge ausgeführt wird.</td>
  </tr>
  <tr>
   <td><strong><em>Strategie</em></strong></td>
   <td>Für diese Eigenschaft kann <strong>original</strong> oder <strong>einzeln</strong> festgelegt werden. Ist der Wert auf <strong>original</strong> eingestellt, wird die Teilsequenz bei jedem Zyklus der übergeordneten Sequenz vollständig ausgeführt. Der andere mögliche Wert lautet <strong>einzeln</strong>. Dabei wird nur ein Element der Teilsequenz bei jeder Ausführung angezeigt (beispielsweise das erste Element bei der ersten Schleife, das zweite Element bei der zweiten Schleife usw.).</td>
  </tr>
 </tbody>
</table>

### Experience Fragment {#experience-fragment}

Mit einem Experience Fragment können Sie dem AEM Screens-Kanal ein Experience Fragment hinzufügen (Gruppe aus einer oder mehreren Komponenten, einschließlich Inhalt und Layout, auf die in Seiten verwiesen werden kann). Ziehen Sie die Komponente in den AEM-Editor und wählen Sie das Experience Fragment aus.

Weitere Informationen zum Erstellen eines Experience Fragments und dessen Verwendung in einem AEM Screens-Projekt finden Sie unter [Verwenden von Experience Fragmenten](experience-fragments-in-screens.md).

![exp](assets/exp.gif)

| **Eigenschaft** | **Beschreibung** |
|---|---|
| **Experience Fragment** |
| ***Experience Fragment*** | Wählen Sie das Experience Fragment aus. |
| ***Dauer*** | Wählen Sie die Gesamtdauer des Experience Fragment aus, das im Kanal wiedergegeben wird. |
| **Offline-Konfiguration** |
| ***Client-seitige Bibliotheken*** | JavaScript- und CSS-Dateien. |
| ***Statische Dateien*** | Statische Dateien, die Sie als Offline-Konfigurationen Ihrem Experience Fragment hinzufügen können. |

>[!NOTE]
>
>Die **Client-seitigen Bibliotheken** und **statischen Dateien**, die Sie aus dieser Komponente hinzufügen, werden zusätzlich zu den bereits konfigurierten **Client-seitigen Bibliotheken** und statischen Dateien bereitgestellt, die über die **Eigenschaften** des Experience Fragment hinzugefügt werden.

### Bild {#image}

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
| **Erreichbarkeit** |
| ***Alternativtext*** | Hierbei handelt es sich um Alternativtext für das Bild. |
| **Sequenz** |
| ***Dauer*** | Standardmäßig ist die Dauer auf *8000 ms* eingestellt. Wenn Sie die Wiedergabedauer des Bildes ändern möchten, aktualisieren Sie das Feld **Dauer**. |

### Übergang {#transition}

Mit der Komponente „Übergang“ können Sie Screens-Projekten einen Übergang hinzufügen.

Die folgende Abbildung veranschaulicht die (per Drag-and-Drop hinzugefügte) Übergangskomponente im Editor.

![screen_shot_2019-07-25at104237am](assets/screen_shot_2019-07-25at104237am.png)

Wählen Sie das Übergangssymbol aus und klicken Sie auf **Konfigurieren** (das Schraubenschlüsselsymbol), um das Dialogfeld **Übergang** zu öffnen. Dieses Dialogfeld enthält drei Registerkarten:

* **Übergang**
* **Sequenz**
* **Aktivierung**

>[!NOTE]
>
>Standardmäßig ist die Sequenz auf 600 ms eingestellt. Sie können die Übergangssequenz auf einen anderen Wert aktualisieren, indem Sie die Registerkarte **Sequenz** nutzen.

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
   <td><p>Hierbei handelt es sich um den Typ des Übergangs zwischen zwei aufeinanderfolgenden Elementen. Der <strong>Typ</strong> des Übergangs umfasst die folgenden Optionen:</p>
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
   <td>Damit wird die Gesamtdauer des Übergangs festgelegt. Standardmäßig ist der Wert auf 600 ms eingestellt.</td>
  </tr>
  <tr>
   <td><strong>Aktivierung</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Aktiv ab</em></strong></td>
   <td>Zeitstempel, der beschreibt, ab wann der Übergang aktiv sein kann.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Aktiv bis</em></strong></td>
   <td>Zeitstempel, der beschreibt, bis wann der Übergang aktiv sein kann.</td>
  </tr>
  <tr>
   <td><strong><em>Zeitplan</em></strong></td>
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
   <td>Damit wird die Dauer des Videos festgelegt. Standardmäßig ist unter „Dauer“ ein Wert von „-1“ eingestellt. Dies bedeutet, dass das Element auf unbestimmte Zeit ausgeführt wird. Wird unter „Dauer“ ein Wert über 0 festgelegt, wird das Element für die angegebene Dauer angezeigt. Anschließend wird zum nächsten Element gewechselt.<br /> </td>
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
