---
title: Anwenden von benutzerdefiniertem Branding und Styling für Textüberlagerungen
description: Erfahren Sie, wie Sie benutzerdefiniertes Branding und Styling für Textüberlagerungen anwenden, die auf Assets in einem AEM Screens-Kanal angewendet werden.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 059e1b19-e9b5-48f0-8f2f-141f0c2f7842
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 100%

---

# Benutzerdefiniertes Branding und Styling für Textüberlagerungen {#creating-custom-branding-styling}

Erfahren Sie, wie Sie benutzerdefiniertes Branding und Styling für Textüberlagerungen anwenden, die auf Ihre Assets in einem AEM Screens-Kanal angewendet werden.

## Erstellen von benutzerdefiniertem Branding und Styling für Textüberlagerungen {#steps-custom-branding}

Gehen Sie wie folgt vor, um benutzerdefiniertes Branding und Styling für Textüberlagerungen zu erstellen:

1. Erstellen Sie ein AEM Screens-Projekt. In diesem Beispiel wird die Funktionalität veranschaulicht, indem ein Projekt mit dem Namen **`customstyle`** und ein Kanal mit dem Namen **DemoBrand** erstellt werden (siehe Abbildung unten).

   ![Bild](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Ziehen Sie aus dem Editor ein Bild per Drag-and-Drop und fügen Sie dem Asset eine Textüberlagerung hinzu.

   ![Bild](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Informationen zum Hinzufügen einer Textüberlagerung zu einem Asset in einem Kanaleditor finden Sie unter [Textüberlagerung](/help/user-guide/text-overlay.md).

1. Navigieren Sie von Ihrer AEM-Instanz zu „Tools“ > **CRXDE Lite**.

1. Erstellen Sie beispielsweise ein benutzerdefiniertes Design in `/apps/settings/wcm/designs/<your-project>/`. In diesem Fall navigieren Sie zu `/apps/settings/wcm/designs/customstyle/`.

   ![Bild](/help/user-guide/assets/custom-brand/custom-brand3.png)

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

1. Kopieren Sie den Pfad zu Ihrem Projekt. In diesem Fall ist der Pfad `/apps/settings/wcm/designs/customstyle`.

1. Navigieren Sie zum Kanal mit dem Namen **DemoBrand** (erstellt in Schritt 1) und klicken Sie nach der Auswahl des Kanals in der Aktionsleiste auf **Eigenschaften**.

1. Navigieren Sie zur Registerkarte **Erweitert** und aktivieren Sie das Feld **Design**.
   ![image](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Standardmäßig zeigt das Feld **Design** den Pfad an, der auf die Designs im Ordner „libs“ verweist.

1. Aktualisieren Sie das Feld **Design** mit dem Pfad zum Projektordner. In diesem Beispiel ist er auf `/apps/settings/wcm/designs/customstyle` festgelegt.

   ![image](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Klicken Sie auf **Speichern und schließen**, um den Design-Pfad zu aktualisieren.

   >[!IMPORTANT]
   >Sie können optional die vorhandenen Screens-Vorlagen überlagern, um Ihre eigenen Designs standardmäßig einzufügen oder eine eigene Vorlage zu erstellen. Führen Sie die folgenden Schritte aus, um mehr zu erfahren.

1. So überlagern Sie die vorhandenen Screens-Vorlagen, um Ihre eigenen Designs standardmäßig einzufügen:

   1. Überlagern Sie `/libs/screens/core/templates/sequencechannel` in `/apps/screens/core/templates/sequencechannel`.
   1. Ändern Sie die Eigenschaft *`cq:designPath`* in `/apps/screens/core/templates/sequencechannel/jcr:content` so, dass sie auf das neue Design verweist.

1. So erstellen Sie eine eigene Vorlage:
   1. Kopieren Sie `/libs/screens/core/templates/sequencechannel` nach `/apps/customstyle/templates/styled-sequencechannel`.
   1. Ändern Sie die Eigenschaft *`cq:designPath`* in `/apps/customstyle/templates/styled-sequencechannel/jcr:content` so, dass sie auf das neue Design verweist.


### Aktualisieren von ACLs {#updating-acls}

Aktualisieren Sie die ACLs für diese Designs, damit der Player sie herunterladen kann.

1. Navigieren Sie zu „useradmin“, wählen Sie die `screens-<project>-devices group` aus und erteilen Sie Leseberechtigung für den benutzerdefinierten Design-Pfad.

1. Erteilen Sie der Gruppe `screens-<project>-administrators` eine Lese- und Änderungsberechtigung für diesen Pfad.

## Anzeigen des Ergebnisses {#viewing-the-result}

Wenn Sie die obigen Schritte abgeschlossen haben, können Sie die Datei *statis.css* von **CRXDE Lite** aus aktualisieren, um die Aktualisierung Ihrer Textüberlagerung anzuzeigen, die dem Asset bereits hinzugefügt wurde.

Gehen Sie wie folgt vor, um die Textüberlagerung mit dem aktualisierten Design anzuzeigen:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt mit dem Titel **`customstyle`** > **Channels** > **DemoBrand**. Klicken Sie auf den Kanal und dann in der Aktionsleiste auf **Bearbeiten**.

1. Da Sie jetzt das Design, wie oben erwähnt, dem Feld **Designs** hinzugefügt haben, klicken Sie auf **Vorschau**, um das aktuelle Bild-Styling mit der Textüberlagerung anzuzeigen.

   ![image](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigieren Sie zu Ihrer Datei *static.css* in CRXDE Lite und fügen Sie dieser Datei wie unten dargestellt die Schrift (z. B. `font-family: "Lucida Console", Courier, monospace;`) hinzu.

   ![image](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Wenn Sie die Änderungen gespeichert und die Vorschau neu geladen haben, wird die Schrift der Textüberlagerung aktualisiert, wie in der Abbildung unten dargestellt.

   ![Bild](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Darüber hinaus können Sie die letzten beiden Code-Blöcke aus der Datei *static.css* entfernen, um die Rahmen um die Textüberlagerung zu entfernen.

![Bild](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. Die aktualisierte Änderung wird in Ihrer Vorschau angezeigt, wo die Textüberlagerung zum Bild hinzugefügt wird.

   ![Bild](/help/user-guide/assets/custom-brand/custom-brand11.png)

   Jetzt können Sie Ihre Marke und Ihr benutzerdefiniertes Styling für Textüberlagerungen aktualisieren, die Ihren Assets hinzugefügt wurden.
