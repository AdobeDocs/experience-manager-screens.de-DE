---
title: Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts
seo-title: Creating Custom Templates in MultiZone Layouts
description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Vorlagen für Mehrzonen-Layouts erstellen.
seo-description: Follow this page to learn about creating custom templates in MultiZone layouts.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 3f4813f8-0438-4ce0-9046-84025de0ddd1
source-git-commit: d1adadbab2cb13626dd8ce70deacced9f55aa4c9
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 96%

---

# Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts {#creating-custom-templates-multizone}

Auf dieser Seite wird erläutert, wie Sie eine benutzerdefinierte Vorlage für ein Mehrzonen-Layout erstellen können.

## Wichtige Überlegungen {#considerations}

Es gibt zwei wichtige Aspekte, die Sie beachten müssen, bevor Sie eine benutzerdefinierte Vorlage für ein Mehrzonen-Layout erstellen:

1. **Feste Pixel-Größe oder Prozentwerte**:

   Sie müssen entscheiden, ob Sie für Ihr benutzerdefiniertes Layout eine feste Pixel-Größe für verschiedene Zonen verwenden möchten oder ob Sie ein benutzerdefiniertes Layout mithilfe von Prozentwerten erstellen möchten.

   >[!NOTE]
   >Die Verwendung von Prozentwerten zum Festlegen von Zonen für Ihr benutzerdefiniertes Layout ermöglicht es Ihnen, die Vorlage für verschiedene Bildschirmgrößen wiederzuverwenden.

1. **Namenskonvention**:

   Bevor Sie sich damit vertraut machen, wie Sie benutzerdefinierte Mehrzonen-Vorlagen zur Verwendung in einem AEM Screens-Projekt erstellen, sollten Sie die Terminologie der zu erstellenden Vorlagen kennen.

   | **Layoutname** | **Beschreibung** |
   |---|---|
   | Left20-LandscapeHD3Zone | Bezieht sich auf ein Querformatlayout mit 3 Zonen, bei dem Zone 1 20 % des horizontalen und vertikalen Bildschirms von links, Zone 2 80 % des horizontalen Bildschirms und 20 % des vertikalen Bildschirms von rechts und Zone 3 100 % des horizontalen und 80 % des vertikalen Bildschirms mit einem Seitenverhältnis von 16:9 einnimmt. |
   | Upper20-PortraitHD2Zone | Bezieht sich auf eine 2-Zonen-Hochformatvorlage, die 20 % des Bildschirms von oben abdeckt und ein Seitenverhältnis von 16:9 aufweist. |
   | Right20-LandscapeSD3Zone | Bezieht sich auf eine 3-Zonen-Vorlage, die 20 % des Bildschirms von rechts abdeckt und ein Seitenverhältnis von 4:3 aufweist. |

   >[!IMPORTANT]
   >Die im benutzerdefinierten Layout definierten Zonen passen möglicherweise nicht zum Seitenverhältnis des gesamten Layouts. Mit der in diesem Dokument verwendeten Namenskonvention wird das Seitenverhältnis des benutzerdefinierten Layouts als Ganzes angegeben.

## Anwendungsbeispiel Layout &quot;Left20-LandscapeHD3Zone&quot; {#custom-template-one}

Gehen Sie wie folgt vor, um die benutzerdefinierte Vorlage *Left20-LandscapeHD3Zone* mit der folgenden Konfiguration zu erstellen:

* **Left20** bezieht sich auf den oberen Bereich links, der 20 % der horizontalen und vertikalen Bildschirmgröße umfasst.
* **Querformat** beschreibt sich auf die Bildschirmausrichtung
* **HD** bezieht sich auf das Seitenverhältnis 16:9
* **3Zone** weist auf drei Bereiche der Anzeige hin

## Visuelle Darstellung des Mehrzonen-Layouts {#multi-layout-visual-one}

Das Layout Left20-LandscapeHD3Zone ermöglicht Ihnen das Erstellen des folgenden Layouts mit mehreren Zonen in Ihrem Projekt:

![image](/help/user-guide/assets/custom-multizone/landscape-3-zone-new.png)

## Erstellen eines Left20-LandscapeHD3Zone-Layouts {#landscape-layout-one}

Gehen Sie wie folgt vor, um ein Left20-LandscapeHD3Zone-Layout für ein AEM Screens-Projekt zu erstellen:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Titel **customtemplate**.

   ![image](/help/user-guide/assets/custom-multizone/custom-template2.png)

1. Navigieren Sie zu **CRXDE Lite** von Ihrer AEM-Instanz > Tools > **CRXDE Lite**.

1. Erstellen Sie unter **Apps** einen Ordner mit dem Titel **customtemplate**. Erstellen Sie in gleicher Weise unter **customtemplate** einen weiteren Ordner mit dem Titel **template**, wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/custom-multizone/custom-template1.png)

   >[!NOTE]
   >Jedes Mal, wenn Sie Inhalte auf einem Knoten erstellen, bearbeiten oder kopieren, sollten Sie in der Aktionsleiste von CRXDE Lite auf **Alle speichern** klicken. Andernfalls können Sie die Änderungen nicht übernehmen.

1. Kopieren Sie die Vorlage „lbar-left“ unter `/libs/screens/core/templates/splitscreenchannel/lbar-left` und fügen Sie sie unter `/apps/customtemplate/template` ein.

1. Benennen Sie die kopierte Vorlage **lbar-left** (`/apps/customtemplate/template`) in **my-custom-layout** um.
   ![image](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigieren Sie zu `/apps/customtemplate/template/my-custom-layout` und ändern Sie die Eigenschaft **jcr:description** in *Vorlage für Left20-LandscapeHD3Zone* und die Eigenschaft **jcr:title** in *Left20-LandscapeHD3Zone*.

   ![image](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Navigieren Sie über `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` zum Knoten **offline-config** und ändern Sie **jcr:title** in *Left20-LandscapeHD3Zone*.

   ![image](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Navigieren Sie über `/apps/customtemplate/template/my-custom-layout/jcr:content` zur Eigenschaft *jcr:content* von **my-custom-template** und ändern Sie die Eigenschaft **cq:cssClass** in **aem-Layout my-custom-layout**.

   ![image](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Nachdem Sie in Schritt 4 die Vorlage „lbar-left“ kopiert haben, werden Ihnen nun unter `my-custom-layout/jcr:content` drei responsive Raster angezeigt. Fügen Sie zu jedem responsiven Raster in der Eigenschaft *cq:cssClass* benutzerdefinierte CSS-Klassen hinzu, beispielsweise *my-custom-layout--top-left* für den Knoten *r1c1*.

   ![image](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Fügen Sie auf die gleiche Weise *my-custom-layout--top-right* für den Knoten *r1c2* und *my-custom-layout--bottom* für den Knoten *r2c1* hinzu.

   >[!NOTE]
   >Diese benutzerdefinierten Klassen werden im CSS verwendet, um die Breite/Höhe für die responsiven Raster festzulegen.

   >[!NOTE]
   >Je nachdem, wie viele Raster insgesamt benötigt werden, können Sie responsive Raster hinzufügen oder entfernen. In diesem Beispiel sehen Sie zwei Raster in der ersten Zeile und ein Raster in der zweiten Zeile. Insgesamt gibt es also drei responsive Raster („r1c1“, „r1c2“, „r2c1“).

1. Kopieren Sie `/libs/settings/wcm/designs/screens` und fügen Sie es unter `/apps/settings/wcm/designs/` ein. Benennen Sie das kopierte Design anschließend in **custom-template-designs** um.

1. Navigieren Sie zu `/apps/settings/wcm/designs/custom-template-designs` und ändern Sie die Eigenschaft *jcr:title* von **custom-template-designs** in **customtemplate-design**.

1. Navigieren Sie zu `/apps/settings/wcm/designs/custom-template-designs` und erstellen Sie eine Datei mit dem Namen „static.css“.

1. Kopieren Sie den Inhalt in die Datei `static.css`:

   ```shell
       /*my-custom-layout styles*/
      .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--top-left {
       width:20%;
       height: 36%;
      float: left !important;
      }
     .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--top-right {
      width:80%;
      height: 36%;
     float: left !important;
     }
     .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--bottom {
     width:100%;
     height: 64%;
     }
   ```

   >[!NOTE]
   >Sie können die Prozentwerte entsprechend den Anforderungen für Ihre benutzerdefinierte Vorlage ändern.

1. Navigieren Sie zu `/apps/<project>/templates/my-custom-layout/jcr:content` und ändern Sie die Eigenschaft *cq:designPath* in `/apps/settings/wcm/designs/customtemplate-designs`, um die in „static.css“ konfigurierten Stile zu laden.

   >[!NOTE]
   >Alle Stile sollten manuell eingegeben werden, da bei der Eingabe durch Kopieren und Einfügen Leerzeichen hinzugefügt werden könnten, die zu Problemen im Zusammenhang mit den CSS-Stilen führen.

## Anzeigen des Ergebnisses {#viewing-result}

Gehen Sie wie folgt vor, um obige benutzerdefinierte Vorlage in Ihrem AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zum in Schritt 1 erstellten Projekt und wählen Sie den Ordner **Kanäle** aus.

   ![image](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Klicken Sie in der Aktionsleiste auf **Erstellen**. Wählen Sie anschließend im Assistenten **Erstellen** die Vorlage **Left20-LandscapeHD3Zone** aus.

   ![image](/help/user-guide/assets/custom-multizone/custom-template9.png)

1. Nachdem Sie einen Kanal mit der benutzerdefinierten Vorlage erstellt haben, können Sie Assets aus dem Editor zu Ihrem Kanal hinzufügen. Die folgende Vorschau zeigt die Bilder in einer benutzerdefinierten Vorlage.

   ![image](/help/user-guide/assets/custom-multizone/custom-template10.png)

## Einfügen eines Bildes als Hintergrundebene  {#inserting-image}

Sie können ein Bild als Hintergrundebene in das Layout einfügen:

Sie können die CSS-Regel so anpassen, dass sie den sogenannten „data-uri“ verwendet und das Bild (Base64-codiert) direkt in die CSS-Datei *static.css* einbindet, die Sie in Schritt 13 erstellt haben.

Dies geschieht wie folgt:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`

Sie können auch die folgenden Schritte ausführen:

1. Stellen Sie sicher, dass das Bild in der Offline-Konfiguration für den Kanal enthalten ist.
1. Verwenden Sie einen direkten Link zum Bild im obigen CSS anstelle der „data-uri“-Variante.


## Aktualisieren der Hintergrundfarbe {#updating-color}

Fügen Sie der xml-Datei *static.css*, die Sie in Schritt 13 erstellt haben, den folgenden Code hinzu, um die Hintergrundfarbe zu ändern.

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`
