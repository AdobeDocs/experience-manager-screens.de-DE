---
title: Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts
description: Erfahren Sie mehr über das Erstellen benutzerdefinierter Vorlagen in Mehrzonen-Layouts für AEM Screens.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 3f4813f8-0438-4ce0-9046-84025de0ddd1
source-git-commit: c142830a37461a36baae15f543bd43b0ae8a62a7
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 30%

---

# Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts {#creating-custom-templates-multizone}

Auf dieser Seite wird erläutert, wie Sie eine benutzerdefinierte Vorlage für ein Mehrzonen-Layout erstellen können.

## Wichtige Überlegungen {#considerations}

Es gibt zwei wichtige Aspekte, die Sie beachten müssen, bevor Sie eine benutzerdefinierte Vorlage für ein Mehrzonen-Layout erstellen:

1. **Feste Pixel-Größe oder Prozentwerte**:

   Entscheiden Sie, ob Sie eine feste Pixelgröße für verschiedene Bereiche für Ihr benutzerdefiniertes Layout verwenden oder ein benutzerdefiniertes Layout mit Prozentsätzen erstellen möchten.

   >[!NOTE]
   >Die Vorteile der Verwendung von Prozentsätzen zum Festlegen von Bereichen für Ihr benutzerdefiniertes Layout ermöglichen die Wiederverwendung der Vorlage in verschiedenen Bildschirmgrößen.

1. **Namenskonvention**:

   Bevor Sie verstehen, wie Sie benutzerdefinierte Mehrzonenvorlagen erstellen, die in einem AEM Screens-Projekt verwendet werden, sollten Sie sich mit dem Wortlaut der Vorlagen vertraut machen, die Sie erstellen möchten.

   | **Layoutname** | **Beschreibung** |
   |---|---|
   | `Left20-LandscapeHD3Zone` | Ein dreizoniges Querformat, mit dem Sie drei Zonen erstellen können:<br>* Zone 1 als 20 % des horizontalen und vertikalen Bildschirms von links<br>* Zone 2: 80 % des horizontalen und 20 % des vertikalen Bildschirms nach rechts<br>* Bereich 3: 100 % der horizontalen und 80 % der vertikalen Anzeige mit einem Seitenverhältnis von 16:9 |
   | `Upper20-PortraitHD2Zone` | Eine zweizonige Hochformat-Vorlage, die 20 % des Bildschirms von oben abdeckt, mit einem Seitenverhältnis von 16:9 |
   | `Right20-LandscapeSD3Zone` | Eine Drei-Zonen-Vorlage, die 20 % des Bildschirms von rechts abdeckt, mit einem Seitenverhältnis von 4:3 |

   >[!IMPORTANT]
   >Die im benutzerdefinierten Layout definierten Zonen passen möglicherweise nicht zum Seitenverhältnis des gesamten Layouts. Mit der in diesem Dokument verwendeten Namenskonvention wird das Seitenverhältnis des benutzerdefinierten Layouts als Ganzes angegeben.

## Anwendungsbeispiel `Left20-LandscapeHD3Zone` Layout {#custom-template-one}

Gehen Sie wie folgt vor, um eine benutzerdefinierte Vorlage zu erstellen *`Left20-LandscapeHD3Zone`* mit der folgenden Konfiguration:

* **`Left20`** - Der obere Bereich links deckt 20 % der horizontalen und vertikalen Bildschirmgröße ab.
* **`Landscape`** - Die Bildschirmausrichtung.
* **`HD`** - Das Seitenverhältnis von 16:9.
* **`3Zone`** - Drei Zonen des Displays.

## Visuelle Darstellung des Mehrzonen-Layouts {#multi-layout-visual-one}

Die `Left20-LandscapeHD3Zone` Mit Layout können Sie das folgende Mehrzonen-Layout in Ihrem Projekt erstellen:

![Bild](/help/user-guide/assets/custom-multizone/landscape-3-zone-new.png)

## Erstellen einer `Left20-LandscapeHD3Zone` Layout {#landscape-layout-one}

Gehen Sie wie folgt vor, um einen `Left20-LandscapeHD3Zone` Layout für ein AEM Screens-Projekt.

1. Erstellen Sie ein AEM Screens-Projekt mit dem Titel **`customtemplate`**.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template2.png)

1. Navigieren zu **CRXDE Lite** in Ihrer AEM-Instanz > Tools > **CRXDE Lite**.

1. Erstellen Sie einen Ordner unter **Apps** Titel: **`customtemplate`**. Erstellen Sie auf ähnliche Weise einen anderen Ordner mit dem Titel . **Schablone** unter **`customtemplate`**, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template1.png)

   >[!NOTE]
   >Auswählen **Alle speichern** in der Aktionsleiste im CRXDE Lite jedes Mal, wenn Sie Inhalte auf einem der Knoten erstellen, bearbeiten oder kopieren. Andernfalls können Sie die Aktualisierungen nicht übertragen.

1. Kopieren Sie die Vorlage „lbar-left“ unter `/libs/screens/core/templates/splitscreenchannel/lbar-left` und fügen Sie sie unter `/apps/customtemplate/template` ein.

1. Benennen Sie die kopierte Vorlage **lbar-left** (`/apps/customtemplate/template`) in **my-custom-layout** um.
   ![image](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigieren zu `/apps/customtemplate/template/my-custom-layout` und aktualisieren Sie die Eigenschaften **`jcr:description`** bis *Vorlage für`Left20-LandscapeHD3Zone`* und **`jcr:title`** bis *`Left20-LandscapeHD3Zone`*.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Navigieren Sie zu . **`offline-config`** Knoten aus `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` und aktualisieren Sie **`jcr:title`** bis *`Left20-LandscapeHD3Zone`*.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Navigieren Sie zu . *`jcr:content`* Eigenschaft von **my-custom-template** von `/apps/customtemplate/template/my-custom-layout/jcr:content` und aktualisieren Sie **`cq:cssClass`** -Eigenschaft verwenden, damit Sie **aem-layout my-custom-layout**.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Bezüglich Schritt (4), in dem Sie die Vorlage „lbar-left“ kopiert haben, können Sie drei responsive Raster anzeigen unter `my-custom-layout/jcr:content`. Hinzufügen einer benutzerdefinierten CSS-Klasse zu jedem responsiven Raster im *`cq:cssClass`* Eigenschaft, z. B *my-custom-layout - oben links* für *R1C1* Knoten.

   ![image](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Fügen Sie auf die gleiche Weise *my-custom-layout--top-right* für den Knoten *r1c2* und *my-custom-layout--bottom* für den Knoten *r2c1* hinzu.

   >[!NOTE]
   >Diese benutzerdefinierten Klassen werden im CSS verwendet, um die Breite/Höhe für diese responsiven Raster festzulegen.

   >[!NOTE]
   >Je nachdem, wie viele Raster insgesamt benötigt werden, können Sie responsive Raster hinzufügen oder entfernen. In diesem Beispiel werden zwei Raster in der ersten Zeile und ein Raster in der zweiten Zeile angezeigt. Es gibt also insgesamt drei responsive Raster (r1c1, r1c2, r2c1).

1. Kopieren Sie `/libs/settings/wcm/designs/screens` und fügen Sie es unter `/apps/settings/wcm/designs/` ein. Benennen Sie das kopierte Design anschließend in **custom-template-designs** um.

1. Navigieren zu `/apps/settings/wcm/designs/custom-template-designs` und aktualisieren Sie die Eigenschaft *`jcr:title`* von **custom-template-designs** bis **customtemplate-design**.

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

1. Navigieren zu `/apps/<project>/templates/my-custom-layout/jcr:content` und aktualisieren Sie die Eigenschaft *`cq:designPath`* bis `/apps/settings/wcm/designs/customtemplate-designs` Damit können Sie die in static.css konfigurierten Stile laden.

   >[!NOTE]
   >Geben Sie alle Stile ein, anstatt sie zu kopieren oder einzufügen. Dies kann zu Leerzeichen führen, die zu Problemen mit der CSS-Formatierung führen können.

## Anzeigen des Ergebnisses {#viewing-result}

Gehen Sie wie folgt vor, um obige benutzerdefinierte Vorlage in Ihrem AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zum in Schritt 1 erstellten Projekt und wählen Sie den Ordner **Kanäle** aus.

   ![image](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Auswählen **Erstellen** Wählen Sie in der Aktionsleiste die Vorlage aus **`Left20-LandscapeHD3Zone`** vom **Erstellen** Assistent.

   ![Bild](/help/user-guide/assets/custom-multizone/custom-template9.png)

1. Nachdem Sie einen Kanal mit der angepassten Vorlage erstellt haben, können Sie über den Editor Assets zu Ihrem Kanal hinzufügen. Die folgende Vorschau zeigt die Bilder in einer benutzerdefinierten Vorlage.

   ![image](/help/user-guide/assets/custom-multizone/custom-template10.png)

## Einfügen eines Bildes als Hintergrundebene  {#inserting-image}

Sie können ein Bild als Hintergrundebene in das Layout einfügen:

Sie können die CSS-Regel so anpassen, dass „data-uri“ verwendet wird und das Bild direkt inline angezeigt wird (`Base64` in der CSS-Datei kodiert), die Sie in erstellt haben (Schritt 13), *static.css*.

Dies geschieht wie folgt:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`

Sie können auch die folgenden Schritte ausführen:

1. Stellen Sie sicher, dass das Bild irgendwie in der Offline-Konfiguration für den Kanal enthalten ist.
1. Verwenden Sie im obigen CSS einen direkten Link zum Bild anstelle der Variante „data-uri„.


## Aktualisieren der Hintergrundfarbe {#updating-color}

Fügen Sie der xml-Datei *static.css*, die Sie in Schritt 13 erstellt haben, den folgenden Code hinzu, um die Hintergrundfarbe zu ändern.

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`
