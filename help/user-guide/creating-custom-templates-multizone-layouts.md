---
title: Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts
description: Erfahren Sie mehr über das Erstellen benutzerdefinierter Vorlagen in MultiZone-Layouts für AEM Screens.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 3f4813f8-0438-4ce0-9046-84025de0ddd1
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 28%

---

# Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts {#creating-custom-templates-multizone}

Auf dieser Seite wird erläutert, wie Sie eine benutzerdefinierte Vorlage für ein Mehrzonen-Layout erstellen können.

## Wichtige Überlegungen {#considerations}

Es gibt zwei wichtige Aspekte, die Sie beachten müssen, bevor Sie eine benutzerdefinierte Vorlage für ein Mehrzonen-Layout erstellen:

1. **Feste Pixel-Größe oder Prozentwerte**:

   Entscheiden Sie, ob Sie für Ihr benutzerdefiniertes Layout eine feste Pixelgröße für verschiedene Bereiche verwenden möchten oder ob Sie ein benutzerdefiniertes Layout mit Prozentwerten erstellen möchten.

   >[!NOTE]
   >Der Vorteil der Verwendung von Prozentwerten zum Festlegen von Zonen für Ihr benutzerdefiniertes Layout ermöglicht die Wiederverwendung der Vorlage für verschiedene Bildschirmgrößen.

1. **Namenskonvention**:

   Bevor Sie wissen, wie Sie benutzerdefinierte Vorlagen für mehrere Bereiche erstellen, um sie in einem AEM Screens-Projekt zu verwenden, sollten Sie die Begriffe kennen, die Sie erstellen möchten.

   | **Layoutname** | **Beschreibung** |
   |---|---|
   | `Left20-LandscapeHD3Zone` | Ein dreistufiges Querformatlayout, mit dem Sie drei Bereiche erstellen können:<br>* Zone 1: 20 % des horizontalen und vertikalen Bildschirms von links<br>* Zone 2: 80 % des horizontalen Bildschirms und 20 % des vertikalen Bildschirms sind gerechtfertigt<br>* Zone 3: 100 % des horizontalen und 80 % des vertikalen Bildschirms mit Seitenverhältnis 16:9 |
   | `Upper20-PortraitHD2Zone` | Eine zweizonen-Hochformatvorlage, die 20 % des Bildschirms von oben abdeckt und ein Seitenverhältnis von 16:9 aufweist. |
   | `Right20-LandscapeSD3Zone` | Eine dreistufige Vorlage, die 20 % des Bildschirms von rechts abdeckt und ein Seitenverhältnis von 4:3 aufweist. |

   >[!IMPORTANT]
   >Die im benutzerdefinierten Layout definierten Zonen passen möglicherweise nicht zum Seitenverhältnis des gesamten Layouts. Mit der in diesem Dokument verwendeten Namenskonvention wird das Seitenverhältnis des benutzerdefinierten Layouts als Ganzes angegeben.

## Anwendungsbeispiel `Left20-LandscapeHD3Zone` Layout {#custom-template-one}

Gehen Sie wie folgt vor, um eine benutzerdefinierte Vorlage zu erstellen *`Left20-LandscapeHD3Zone`* mit der folgenden Konfiguration:

* **`Left20`** - Der obere Bereich auf der linken Seite, der 20 % der horizontalen und vertikalen Bildschirmgröße umfasst.
* **`Landscape`** - Die Bildschirmausrichtung.
* **`HD`** - Das Seitenverhältnis beträgt 16:9.
* **`3Zone`** - Drei Bereiche der Anzeige.

## Visuelle Darstellung des Mehrzonen-Layouts {#multi-layout-visual-one}

Die `Left20-LandscapeHD3Zone` Mit Layout können Sie das folgende Mehrzonen-Layout in Ihrem Projekt erstellen:

![Bild](/help/user-guide/assets/custom-multizone/landscape-3-zone-new.png)

## Erstellen einer `Left20-LandscapeHD3Zone` Layout {#landscape-layout-one}

Gehen Sie wie folgt vor, um eine `Left20-LandscapeHD3Zone` Layout für ein AEM Screens-Projekt.

1. Erstellen Sie ein AEM Screens-Projekt mit dem Titel **`customtemplate`**.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template2.png)

1. Navigieren Sie zu **CRXDE Lite** von Ihrer AEM-Instanz > Tools > **CRXDE Lite**.

1. Erstellen eines Ordners unter **apps** benannt als **`customtemplate`**. Erstellen Sie auf ähnliche Weise einen weiteren Ordner mit dem Titel **template** under **`customtemplate`**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template1.png)

   >[!NOTE]
   >Klicks **Alle speichern** aus der Aktionsleiste in CRXDE Lite jedes Mal, wenn Sie Inhalte erstellen, bearbeiten oder auf einen der Knoten kopieren. Andernfalls können Sie die Aktualisierungen nicht übertragen.

1. Kopieren Sie die Vorlage „lbar-left“ unter `/libs/screens/core/templates/splitscreenchannel/lbar-left` und fügen Sie sie unter `/apps/customtemplate/template` ein.

1. Benennen Sie die kopierte Vorlage **lbar-left** (`/apps/customtemplate/template`) in **my-custom-layout** um.
   ![image](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigieren Sie zu `/apps/customtemplate/template/my-custom-layout` und aktualisieren Sie die Eigenschaften **`jcr:description`** nach *Vorlage für`Left20-LandscapeHD3Zone`* und **`jcr:title`** nach *`Left20-LandscapeHD3Zone`*.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Navigieren Sie zum **`offline-config`** Knoten von `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` und aktualisieren Sie **`jcr:title`** nach *`Left20-LandscapeHD3Zone`*.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Navigieren Sie zum *`jcr:content`* Eigenschaft von **my-custom-template** von `/apps/customtemplate/template/my-custom-layout/jcr:content` und aktualisieren Sie **`cq:cssClass`** -Eigenschaft, damit Sie **aem-layout my-custom-layout**.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Gemäß Schritt 4, in den Sie die Vorlage &quot;lbar-left&quot;kopiert haben, können Sie unter drei responsive Raster anzeigen `my-custom-layout/jcr:content`. Fügen Sie benutzerdefinierte CSS-Klassen zu jedem responsiven Raster im *`cq:cssClass`* -Eigenschaft, beispielsweise *my-custom-layout—top-left* für *r1c1* Knoten.

   ![image](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Fügen Sie auf die gleiche Weise *my-custom-layout--top-right* für den Knoten *r1c2* und *my-custom-layout--bottom* für den Knoten *r2c1* hinzu.

   >[!NOTE]
   >Diese benutzerdefinierten Klassen werden im CSS verwendet, um die Breite/Höhe für diese responsiven Raster festzulegen.

   >[!NOTE]
   >Je nachdem, wie viele Raster insgesamt benötigt werden, können Sie responsive Raster hinzufügen oder entfernen. In diesem Beispiel werden zwei Raster in der ersten Zeile und ein Raster in der zweiten Zeile angezeigt, sodass insgesamt drei responsive Raster vorhanden sind (r1c1, r1c2, r2c1).

1. Kopieren Sie `/libs/settings/wcm/designs/screens` und fügen Sie es unter `/apps/settings/wcm/designs/` ein. Benennen Sie das kopierte Design anschließend in **custom-template-designs** um.

1. Navigieren Sie zu `/apps/settings/wcm/designs/custom-template-designs` und die Eigenschaft aktualisieren *`jcr:title`* von **custom-template-designs** nach **customtemplate-design**.

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

1. Navigieren Sie zu `/apps/<project>/templates/my-custom-layout/jcr:content` und die Eigenschaft aktualisieren *`cq:designPath`* nach `/apps/settings/wcm/designs/customtemplate-designs` sodass Sie die in static.css konfigurierten Stile laden können.

   >[!NOTE]
   >Geben Sie alle Stile ein, anstatt sie zu kopieren oder einzufügen. Dies kann zu Leerzeichen führen, die zu CSS-Stilproblemen führen.

## Anzeigen des Ergebnisses {#viewing-result}

Gehen Sie wie folgt vor, um obige benutzerdefinierte Vorlage in Ihrem AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zu Ihrem Screens-Projekt, das Sie in Schritt 1 erstellt haben, und klicken Sie auf das **Kanäle** Ordner.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Klicks **Erstellen** in der Aktionsleiste auf die Vorlage klicken **`Left20-LandscapeHD3Zone`** aus dem **Erstellen** Assistent.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template9.png)

1. Nachdem Sie einen Kanal mit der angepassten Vorlage erstellt haben, können Sie Ihrem Kanal über den Editor Assets hinzufügen. Die folgende Vorschau zeigt die Bilder in einer benutzerdefinierten Vorlage.

   ![image](/help/user-guide/assets/custom-multizone/custom-template10.png)

## Einfügen eines Bildes als Hintergrundebene  {#inserting-image}

Sie können ein Bild als Hintergrundebene in das Layout einfügen:

Sie können die CSS-Regel so anpassen, dass &quot;data-uri&quot;verwendet wird und das Bild direkt inline (`Base64` kodiert) in der CSS-Datei, die Sie in Schritt 13 erstellt haben, *static.css*.

Dies geschieht wie folgt:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`

Sie können auch die folgenden Schritte ausführen:

1. Stellen Sie sicher, dass das Bild irgendwie in der Offline-Konfiguration für den Kanal enthalten ist.
1. Verwenden Sie einen direkten Link zum Bild in der obigen CSS-Datei anstelle der &quot;data-uri&quot;-Variante.


## Aktualisieren der Hintergrundfarbe {#updating-color}

Fügen Sie der xml-Datei *static.css*, die Sie in Schritt 13 erstellt haben, den folgenden Code hinzu, um die Hintergrundfarbe zu ändern.

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`
