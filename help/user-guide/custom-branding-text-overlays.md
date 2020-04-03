---
title: Anwenden von benutzerdefiniertem Branding und Formatierung für Textüberlagerungen
seo-title: Anwenden von benutzerdefiniertem Branding und Formatierung für Textüberlagerungen
description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Branding- und Stile für Textüberlagerungen anwenden.
seo-description: Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Branding- und Stile für Textüberlagerungen anwenden.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: f91faa23c7c5c4f0f705c77251554b64efaf2611

---


# Benutzerdefiniertes Branding und Formatierung für Textüberlagerungen {#creating-custom-branding-styling}

Auf dieser Seite erfahren Sie, wie Sie benutzerdefinierte Branding- und Stile für Textüberlagerungen anwenden.

## Erstellen von benutzerdefiniertem Branding und Stil für Textüberlagerungen {#steps-custom-branding}

Gehen Sie wie folgt vor, um benutzerdefinierte Branding- und Stile für Textüberlagerungen zu erstellen:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Titel **customstyle** und einen Kanal mit dem Titel **DemoBrand**, wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Ziehen Sie aus dem Editor ein Bild und legen Sie es ab und fügen Sie dem Asset eine Textüberlagerung hinzu.

   ![image](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Informationen zum Hinzufügen einer Textüberlagerung zu einem Asset in einem Kanal-Editor finden Sie unter [Textüberlagerung](/help/user-guide/text-overlay.md).

1. Navigieren Sie von Ihrer AEM-Instanz zu Tools > **CRXDE Lite**.

1. Sie müssen einen benutzerdefinierten Entwurf erstellen, `/apps/settings/wcm/designs/<your-project>/`z. B. in diesem Fall

   ![image](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Navigieren Sie zur Datei &quot;static.css&quot;und legen Sie die folgenden CSS-Regeln fest. Auch in der Abbildung unten dargestellt.

   ```shell
    //global styles
    .cq-Screens-textOverlay
    { … }
    //authoring overrides
    .aem-AuthorLayer-Edit .cq-Screens-textOverlay { … }
    // light text variant
    .cq-Screens-textOverlay-color--light
    { … }
     // dark text variant
    .cq-Screens-textOverlay-color--dark { … }
   ```
   ![image](/help/user-guide/assets/custom-brand/custom-brand4.png)

1. Kopieren Sie den Pfad zu Ihrem Projekt. In diesem Fall wird der Pfad `/apps/settings/wcm/designs/customstyle`verwendet.

1. Navigieren Sie zum Kanal mit dem Titel **DemoBrand** (erstellt in Schritt 1)) und klicken Sie in der Aktionsleiste auf **Eigenschaften** , nachdem Sie den Kanal ausgewählt haben.

1. Navigieren Sie zur Registerkarte &quot; **Erweitert** &quot;und aktivieren Sie das Feld &quot; **Design** &quot;.
   ![image](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Standardmäßig zeigt das Feld **Design** den Pfad zu Entwürfen im Ordner libs an.

1. Aktualisieren Sie das Feld **Design** mit dem Pfad zum Projektordner. In diesem Fall wird es `/apps/settings/wcm/designs/customstyle`sein.

   ![image](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Klicken Sie auf **Speichern &amp; Schließen** , um den Entwurfspfad zu aktualisieren.


## Anzeigen des Ergebnisses {#viewing-the-result}

Nachdem Sie die oben genannten Schritte ausgeführt haben, können Sie Ihre Datei &quot; *statis.css* &quot;von **CRXDE Lite** aktualisieren und die Aktualisierung daher auf das dem Asset hinzugefügte Textlayout Ansicht.

Gehen Sie wie folgt vor, um das aktualisierte Design in das Textlayout Ansicht:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt mit dem Titel **customstyle** und zu einem Kanal mit dem Titel **DemoBrand** und klicken Sie in der Aktionsleiste auf **Bearbeiten** , um den Editor zu öffnen.

1. Da Sie den Entwurf wie oben erwähnt in Ihr **Designfeld eingefügt haben, klicken Sie auf &quot;** Vorschau **** &quot;, um den aktuellen Bildstil mit der Textüberlagerung Ansicht.

   ![image](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigieren Sie in CRXDE Lite zu Ihrer Datei &quot;static.css&quot;, fügen Sie die Schriftart beispielsweise hinzu.
   ![image](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Nachdem Sie die Änderungen gespeichert und die Vorschau neu geladen haben, sehen Sie eine Aktualisierung der Textüberlagerungsschrift, wie in der Abbildung unten dargestellt.

   ![image](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Darüber hinaus können Sie die letzten beiden Codeblöcke aus der Datei &quot;static.css&quot;entfernen, um die Boxed-Formatierung um die Textüberlagerung zu entfernen.
   ![image](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. Sie werden die aktualisierte Änderung in Ihrer Vorschau, in der die Textüberlagerung zum Bild hinzugefügt wird, wie unten dargestellt, Ansicht.

   ![image](/help/user-guide/assets/custom-brand/custom-brand11.png)

Entsprechend den Schritten in den vorherigen Abschnitten können Sie Ihre Marke und Ihren benutzerdefinierten Stil für Textüberlagerungen aktualisieren, die zu Ihren Assets hinzugefügt wurden.









