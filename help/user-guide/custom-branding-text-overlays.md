---
title: Anwenden von benutzerdefiniertem Branding und Styling für Textüberlagerungen
seo-title: Anwenden von benutzerdefiniertem Branding und Styling für Textüberlagerungen
description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefiniertes Branding und Styling für Textüberlagerungen anwenden.
seo-description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefiniertes Branding und Styling für Textüberlagerungen anwenden.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 8492bdd071ae029a68ec4a4983c79ce326cac38b
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 100%

---


# Benutzerdefiniertes Branding und Styling für Textüberlagerungen {#creating-custom-branding-styling}

Auf dieser Seite erfahren Sie, wie Sie benutzerdefiniertes Branding und Styling für Textüberlagerungen anwenden, die auf Ihre Assets in einem Screens-Kanal angewendet werden.

## Erstellen von benutzerdefiniertem Branding und Styling für Textüberlagerungen {#steps-custom-branding}

Gehen Sie wie folgt vor, um benutzerdefiniertes Branding und Styling für Textüberlagerungen zu erstellen:

1. Erstellen Sie ein AEM Screens-Projekt. In diesem Beispiel wird die Funktionalität veranschaulicht, indem ein Projekt mit dem Namen **customstyle** und ein Kanal mit dem Namen **DemoBrand** erstellt werden (siehe Abbildung unten).

   ![image](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Ziehen Sie aus dem Editor ein Bild per Drag-and-Drop und fügen Sie dem Asset eine Textüberlagerung hinzu.

   ![image](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Informationen zum Hinzufügen einer Textüberlagerung zu einem Asset in einem Kanaleditor finden Sie unter [Textüberlagerung](/help/user-guide/text-overlay.md).

1. Navigieren Sie von Ihrer AEM-Instanz zu **Tools > CRXDE Lite**.

1. Erstellen Sie ein benutzerdefiniertes Design in `/apps/settings/wcm/designs/<your-project>/`. Navigieren Sie in diesem Beispiel zu `/apps/settings/wcm/designs/customstyle/`

   ![image](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Erstellen Sie die Datei *static.css* und legen Sie die folgenden CSS-Regeln fest. Dies wird auch als Beispiel in der Abbildung unter den CSS-Regeln gezeigt.

   ```shell
    //global styles
    cq-Screens-textOverlay {
    padding: 1em;
    font-size: 3rem;
    line-height: 1em;
     }
    //authoring overrides
   .aem-AuthorLayer-Edit .cq-Screens-textOverlay {
    display: none;
    padding: 0;
    font-size: 1rem;
    }
     // light text variant
    .cq-Screens-textOverlay-color--light {
     background-color: rgba(0, 0, 0, .6);
     }
     // dark text variant
     .cq-Screens-textOverlay-color--dark {
      background-color: rgba(255, 255, 255, .6);
    }
   ```

   ![image](/help/user-guide/assets/custom-brand/custom-brand4.png)

1. Kopieren Sie den Pfad zu Ihrem Projekt. In diesem Beispiel wird der Pfad `/apps/settings/wcm/designs/customstyle` verwendet.

1. Navigieren Sie zum Kanal mit dem Namen **DemoBrand** (erstellt in Schritt 1) und klicken Sie nach der Auswahl des Kanals in der Aktionsleiste auf **Eigenschaften**.

1. Navigieren Sie zur Registerkarte **Erweitert** und aktivieren Sie das Feld **Design**.
   ![image](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Standardmäßig zeigt das Feld **Design** den Pfad zu Designs im Ordner „libs“ an.

1. Aktualisieren Sie das Feld **Design** mit dem Pfad zum Projektordner. In diesem Beispiel ist dies `/apps/settings/wcm/designs/customstyle`.

   ![image](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Klicken Sie auf **Speichern und schließen**, um den Design-Pfad zu aktualisieren.

>[!IMPORTANT]
>
>Sie können die vorhandenen Screens-Vorlagen überlagern, um Ihre eigenen Designs standardmäßig einzufügen oder eine eigene Vorlage zu erstellen. Weitere Informationen finden Sie in den folgenden Schritten.

1. So überlagern Sie die vorhandenen Screens-Vorlagen, um Ihre eigenen Designs standardmäßig einzufügen:

   1. Überlagern Sie `/libs/screens/core/templates/sequencechannel` in `/apps/screens/core/templates/sequencechannel`.
   1. Ändern Sie die Eigenschaft *cq:designPath* in `/apps/screens/core/templates/sequencechannel/jcr:content`, um auf das neue Design zu verweisen.

1. So erstellen Sie eine eigene Vorlage:
   1. Kopieren Sie `/libs/screens/core/templates/sequencechannel` nach `/apps/customstyle/templates/styled-sequencechannel`.
   1. Ändern Sie die Eigenschaft *cq:designPath* in `/apps/customstyle/templates/styled-sequencechannel/jcr:content`, um auf das neue Design zu verweisen.


### Aktualisieren von ACLs {#updating-acls}

Aktualisieren Sie die ACLs für diese Designs, damit sie vom Player heruntergeladen werden können.

1. Navigieren Sie zu „useradmin“, wählen Sie `screens-<project>-devices group` aus und erteilen Sie Leseberechtigung für den benutzerdefinierten Design-Pfad.

1. Erteilen Sie der Gruppe `screens-<project>-administrators` Lese- und Änderungsberechtigung für diesen Pfad.

## Anzeigen des Ergebnisses {#viewing-the-result}

Nachdem Sie die oben genannten Schritte ausgeführt haben, können Sie die Datei *statis.css* von **CRXDE Lite** aus aktualisieren und somit die Aktualisierung Ihrer Textüberlagerung anzeigen, die dem Asset bereits hinzugefügt wurde.

Gehen Sie wie folgt vor, um die Textüberlagerung mit dem aktualisierten Design anzuzeigen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt mit dem Titel **customstyle** > **Kanäle** > **DemoBrand**. Wählen Sie den Kanal aus und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.

1. Da Sie jetzt das Design, wie oben erwähnt, dem Feld **Designs** hinzugefügt haben, klicken Sie auf **Vorschau**, um das aktuelle Bild-Styling mit der Textüberlagerung anzuzeigen.

   ![image](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigieren Sie zu Ihrer Datei *static.css* in CRXDE Lite und fügen Sie dieser Datei wie unten dargestellt die Schrift (z. B. `font-family: "Lucida Console", Courier, monospace;`) hinzu.
   ![image](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Nachdem Sie die Änderungen gespeichert und die Vorschau neu geladen haben, wird die Schrift der Textüberlagerung aktualisiert, wie in der Abbildung unten dargestellt.

   ![image](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Darüber hinaus können Sie die letzten beiden Code-Blöcke aus der Datei *static.css* entfernen, um Rahmen um die Textüberlagerung zu entfernen.
   ![image](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. Die aktualisierte Änderung wird in Ihrer Vorschau angezeigt, wo die Textüberlagerung zum Bild hinzugefügt wird.

   ![image](/help/user-guide/assets/custom-brand/custom-brand11.png)

Mithilfe des Tutorials können Sie jetzt Ihre Marke und Ihr benutzerdefiniertes Styling für Textüberlagerungen aktualisieren, die Ihren Assets hinzugefügt wurden.









