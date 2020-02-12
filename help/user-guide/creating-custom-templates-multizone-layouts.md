---
title: Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts
seo-title: Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts
description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Vorlagen für Mehrzonen-Layouts erstellen.
seo-description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Vorlagen für Mehrzonen-Layouts erstellen.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 87a86d60de9ea09dae93d08a1e0b42271c39249f

---


# Erstellen benutzerdefinierter Vorlagen für Mehrzonen-Layouts {#creating-custom-templates-multizone}

Auf dieser Seite wird erläutert, wie Sie eine benutzerdefinierte Vorlage in einem Layout mit mehreren Zonen erstellen können.

## Namenskonvention {#name-terms}

Bevor Sie wissen, wie Sie benutzerdefinierte Vorlagen für mehrere Bereiche erstellen, die in einem AEM Screens-Projekt verwendet werden sollen, sollten Sie die verschiedenen Vorlagen, die Sie erstellen möchten, kennen.

| **Layoutname** | **Beschreibung** |
|---|---|
| Left20-LandscapeHD3Zone | Bezieht sich auf ein Querformatlayout mit 3 Zonen, mit dem Sie 3 Zonen mit Zone 1 von 20 % des horizontalen und vertikalen Bildschirms von links, Zone 2 von 80 % des horizontalen Bildschirms und 20 % des vertikalen Bildschirms von rechts, Zone 3 von 100 % des horizontalen und 80 % des vertikalen Bildschirms mit einem Seitenverhältnis von 16:9 erstellen können |
| Upper20-PortraitHD2Zone | Bezieht sich auf eine 2-Zonen-Hochformatvorlage, die 20 % des Bildschirms von oben abdeckt, mit einem Seitenverhältnis von 16:9 |
| Right20-LandscapeSD3Zone | Bezieht sich auf eine 3-Zonen-Vorlage, die 20 % des Bildschirms von rechts abdeckt, mit einem Seitenverhältnis von 4:3 |

## Anwendungsbeispiele {#example-use-cases}

## Erstellen eines Left20-LandscapeHD3Zone-Layouts {#landscape-layout-one}

Gehen Sie wie folgt vor, um eine benutzerdefinierte Vorlage mit der folgenden Konfiguration zu erstellen:

* **&quot;Left20** &quot;bezieht sich auf den oberen Bereich links, der 20 % der horizontalen und vertikalen Bildschirmgröße umfasst.
* **Querformat** bezieht sich auf die Bildschirmausrichtung
* **HD** bezieht sich auf das Seitenverhältnis 16:9
* **3Zone** bezieht sich auf drei Bereiche der Anzeige

## Visuelle Darstellung des MultiZone-Layouts {#multi-layout-visual-one}

Das Layout Left20-LandscapeHD3Zone ermöglicht Ihnen das Erstellen des folgenden Layouts mit mehreren Zonen in Ihrem Projekt:

![image](/help/user-guide/assets/custom-multizone/custom-multizone1.png)






## Erstellen eines Upper20-PortraitHD2Zone-Layouts {#landscape-layout-two}

Gehen Sie wie folgt vor, um eine benutzerdefinierte Vorlage mit der folgenden Konfiguration zu erstellen:






![image](assets/custom-template1.png)


## Erstellen einer benutzerdefinierten Vorlage mit einer bestimmten Konfiguration {#basic-flow-setting}

Gehen Sie wie folgt vor, um eine benutzerdefinierte Vorlage zu erstellen.

1. Erstellen Sie die Vorlage in `/apps/<project>/templates/my-custom-layout`

   ```shell
    <?xml version="1.0" encoding="UTF-8"?>
    <jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:cq="http://www.day.com/jcr/cq/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:nt="http://www.jcp.org/jcr/nt/1.0"
    jcr:description="My Custom 3-zones layout "
    jcr:primaryType="cq:Template"
    jcr:title="3-zones layout"
    allowedParents="[/libs/screens/core/templates/channelfolder]"
    allowedPaths="[/content/screens(/.*)?]"
    ranking="{Long}20000">
    <jcr:content
        cq:cssClass="aem-Layout aem-Layout--3x1 my-CustomLayout"
        cq:designPath="/apps/settings/wcm/designs/<project>"
        cq:deviceGroups="[mobile/groups/responsive]"
        jcr:primaryType="cq:PageContent"
        sling:resourceSuperType="screens/core/components/channel"
        sling:resourceType="screens/core/components/multiscreenchannel">
        <r1c1
            cq:cssClass="aem-LayoutCell--1-1 my-CustomLayout-top"
            jcr:primaryType="nt:unstructured"
            sling:resourceType="wcm/foundation/components/responsivegrid"/>
        <r2c1
            cq:cssClass="aem-LayoutCell--1-1 my-CustomLayout-middle"
            jcr:primaryType="nt:unstructured"
            sling:resourceType="wcm/foundation/components/responsivegrid"/>
        <r3c1
            cq:cssClass="aem-LayoutCell--1-1 my-CustomLayout-bottom"
            jcr:primaryType="nt:unstructured"
            sling:resourceType="wcm/foundation/components/responsivegrid"/>
        <cq:responsive jcr:primaryType="nt:unstructured">
            <breakpoints jcr:primaryType="nt:unstructured"/>
        </cq:responsive>
        <offline-config/>
    </jcr:content>
   </jcr:root>
   ```

1. Erstellen Sie ein Seiten-Design in `/apps/settings/wcm/designs/<project>`.

   >[!NOTE]
   >
   >Vergewissern Sie sich, dass der obige `cq:designPath` mit dem Pfad übereinstimmt.

1. Aktualisieren Sie den Knoten **offline-config** für das Design, damit er auf den neuen Pfad verweist.

1. Fügen Sie eine **static.css**-Datei im Ordner `/apps/settings/wcm/designs/<project>` hinzu und setzen Sie deren Inhalt auf

   ```shell
   .cq-Screens-channel--multizone.my-CustomLayout {}
   .cq-Screens-channel--multizone.my-CustomLayout .my-CustomLayout-top { height: 150px; }
   .cq-Screens-channel--multizone.my-CustomLayout .my-CustomLayout-middle { height: 1470px; }
   .cq-Screens-channel--multizone.my-CustomLayout .my-CustomLayout-bottom { height: 300px; }
   ```

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



