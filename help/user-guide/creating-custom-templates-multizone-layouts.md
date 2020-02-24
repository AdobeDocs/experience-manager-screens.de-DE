---
title: Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts
seo-title: Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts
description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Vorlagen für Mehrzonen-Layouts erstellen.
seo-description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Vorlagen für Mehrzonen-Layouts erstellen.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 23208ed9e4e293cfcec65305918f35573c20cc02

---


# Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts {#creating-custom-templates-multizone}

Auf dieser Seite wird erläutert, wie Sie eine benutzerdefinierte Vorlage in einem Layout mit mehreren Zonen erstellen können.

## Namenskonvention {#name-terms}

Bevor Sie wissen, wie Sie benutzerdefinierte Multi-Zone-Vorlagen erstellen, die in einem AEM Screens-Projekt verwendet werden, sollten Sie die Version der Vorlagen verstehen, die Sie erstellen möchten.

| **Layoutname** | **Beschreibung** |
|---|---|
| Left20-LandscapeHD3Zone | Bezieht sich auf ein Querformatlayout mit 3 Zonen, mit dem Sie 3 Zonen mit Zone 1 von 20 % des horizontalen und vertikalen Bildschirms von links, Zone 2 von 80 % des horizontalen Bildschirms und 20 % des vertikalen Bildschirms von rechts, Zone 3 von 100 % des horizontalen und 80 % des vertikalen Bildschirms mit einem Seitenverhältnis von 16:9 erstellen können |
| Upper20-PortraitHD2Zone | Bezieht sich auf eine 2-Zonen-Hochformatvorlage, die 20 % des Bildschirms von oben abdeckt, mit einem Seitenverhältnis von 16:9 |
| Right20-LandscapeSD3Zone | Bezieht sich auf eine 3-Zonen-Vorlage, die 20 % des Bildschirms von rechts abdeckt, mit einem Seitenverhältnis von 4:3 |

## Anwendungsbeispiele {#example-use-cases}

## Left20-LandscapeHD3Zone-Layout {#custom-template-one}

Gehen Sie wie folgt vor, um eine benutzerdefinierte Vorlage *Left20-LandscapeHD3Zone* mit der folgenden Konfiguration zu erstellen:

* **&quot;Left20** &quot;bezieht sich auf den oberen Bereich links, der 20 % der horizontalen und vertikalen Bildschirmgröße umfasst.
* **Querformat** bezieht sich auf die Bildschirmausrichtung
* **HD** bezieht sich auf das Seitenverhältnis 16:9
* **3Zone** bezieht sich auf drei Bereiche der Anzeige

## Visuelle Darstellung des MultiZone-Layouts {#multi-layout-visual-one}

Das Layout Left20-LandscapeHD3Zone ermöglicht Ihnen das Erstellen des folgenden Layouts mit mehreren Zonen in Ihrem Projekt:

![image](/help/user-guide/assets/custom-multizone/custom-multizone1.png)

## Erstellen eines Left20-LandscapeHD3Zone-Layouts {#landscape-layout-one}

Gehen Sie wie folgt vor, um ein Left20-LandscapeHD3Zone-Layout für ein AEM Screens-Projekt zu erstellen:

1. Create an AEM Screens project titled as **customtemplate**.

   ![image](/help/user-guide/assets/custom-multizone/custom-template2.png)

1. Navigieren Sie von Ihrer AEM-Instanz zu **CRXDE Lite** —> Tools —> **CRXDE Lite**.

1. Erstellen Sie einen Ordner unter **Apps** mit dem Titel **customtemplate**. Erstellen Sie entsprechend einen weiteren Ordner mit dem Titel &quot; **Vorlage** &quot;unter &quot; **Vorlage**&quot;wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/custom-multizone/custom-template1.png)

   > [!NOTE]
   > Es wird empfohlen, bei jedem Erstellen, Bearbeiten oder Kopieren von Inhalten auf einer der Knoten in der Aktionsleiste von CRXDE Lite auf Alle **** speichern zu klicken. Andernfalls können die Updates nicht übernommen werden.

1. Kopieren Sie die linke Vorlage von `/libs/screens/core/templates/splitscreenchannel/lbar-left` nach `/apps/customtemplate/template`.

1. Benennen Sie das kopierte **lbar-left** (`/apps/customtemplate/template`) in **my-custom-layout**um.
   ![image](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigieren Sie zu `/apps/customtemplate/template/my-custom-layout` und aktualisieren Sie die Eigenschaften **jcr:description** zu *Template für Left20-LandscapeHD3Zone* und **jcr:title** zu *Left20-LandscapeHD3Zone*.

   ![image](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Navigieren Sie zum Knoten **offline-config** von `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` und aktualisieren Sie **jcr:title** auf *Left20-LandscapeHD3Zone*.

   ![image](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Navigieren Sie zur Eigenschaft *jcr:content* von **my-custom-template** `/apps/customtemplate/template/my-custom-layout/jcr:content` und aktualisieren Sie die Eigenschaft **cq:cssClass** auf **aem-Layout my-custom-layout**.

   ![image](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Bezogen auf Schritt (4), in dem Sie die linke Vorlage kopiert haben, sehen Sie 3 interaktive Raster unter `my-custom-layout/jcr:content`. Fügen Sie der Eigenschaft *cq:cssClass* benutzerdefinierte CSS-Klassen zu jedem interaktiven Raster hinzu, z. B. *my-custom-layout - top-left* für den Knoten *r1c1* .

   ![image](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Fügen Sie *my-custom-layout - top-right* for *r1c2* and, *my-custom-layout - bottom* for *r2c1* node hinzu.

   >[!NOTE]
   >Diese benutzerdefinierten Klassen werden im CSS verwendet, um die Breite/Höhe für diese interaktiven Raster festzulegen.

   >[!NOTE]
   > Sie können die reaktionsfähigen Raster je nach der gewünschten Gesamtanzahl der Raster hinzufügen oder entfernen. In diesem Beispiel zeigen wir die Raster 2 in der ersten Zeile und 1 in der zweiten Zeile, sodass insgesamt 3 interaktive Raster (r1c1, r1c2, r2c1) vorhanden sind.

1. Kopieren Sie `/libs/settings/wcm/designs/screens` in den kopierten Entwurf und benennen Sie ihn in `/apps/settings/wcm/designs/`custom-template-designs **** um.

1. Navigieren Sie zur Eigenschaft `/apps/settings/wcm/designs/custom-template-designs`jcr:title *von* custom-template-designs **und aktualisieren Sie sie auf** customtemplate-design **** .

1. Navigieren Sie zu der Datei static.css `/apps/settings/wcm/designs/custom-template-designs` und erstellen Sie sie.

1. Kopieren Sie den Inhalt in die Datei &quot;static.css&quot;:

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
   > Sie können die Prozentsätze entsprechend den Anforderungen für Ihre benutzerdefinierte Vorlage aktualisieren.

1. Navigieren Sie zur Eigenschaft `/apps/<project>/templates/my-custom-layout/jcr:content`cq:designPath *und aktualisieren Sie sie,* `/apps/settings/wcm/designs/customtemplate-designs` um die in static.css konfigurierten Stile zu laden.

   >[!NOTE]
   > Es wird empfohlen, alle Stile einzugeben, anstatt sie zu kopieren oder einzufügen. Dies kann zu Leerzeichen führen, die zu CSS-Stilproblemen führen.

## Anzeigen des Ergebnisses {#viewing-result}

Gehen Sie wie folgt vor, um die oben genannte benutzerdefinierte Vorlage in Ihrem AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zu dem in Schritt 1 erstellten Projekt &quot;Bildschirme&quot;und wählen Sie den Ordner &quot; **Kanäle** &quot;aus.

   ![image](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Klicken Sie in der Aktionsleiste auf **Erstellen** und wählen Sie die Vorlage **Left20-LandscapeHD3Zone** im Assistenten **Erstellen** aus.

1. Nachdem Sie einen Kanal mit der benutzerdefinierten Vorlage erstellt haben, können Sie Assets aus dem Editor zu Ihrem Kanal hinzufügen.

## Einfügen eines Bildes als Hintergrundebene {#inserting-image}

Sie können ein Bild als Hintergrundebene in das Layout einfügen:

Sie können die CSS-Regel so anpassen, dass sie den sogenannten „data-uri“ verwendet und das Bild (Base64-kodiert) direkt in die CSS-Datei einbindet.

Dies geschieht wie folgt:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`

Sie können auch die folgenden Schritte ausführen:

1. Stellen Sie sicher, dass das Bild in der Offline-Konfiguration für den Kanal enthalten ist.
1. Verwenden Sie einen direkten Link zum Bild im obigen CSS anstelle der „data-uri“-Variante.


## Aktualisieren der Hintergrundfarbe {#updating-color}

Fügen Sie der xml-Datei den folgenden Code hinzu, um die Hintergrundfarbe zu ändern:

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`



