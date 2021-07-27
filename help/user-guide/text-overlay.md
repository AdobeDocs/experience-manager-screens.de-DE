---
title: Textüberlagerung
seo-title: Textüberlagerung
description: Textüberlagerung ist eine Funktion in AEM Screens, mit der Sie in einem Sequenzkanal für ein überzeugendes Erlebnis sorgen können, indem Sie einen Titel oder eine Beschreibung auf einem Bild einfügen. Auf dieser Seite erfahren Sie mehr.
seo-description: Textüberlagerung ist eine Funktion in AEM Screens, mit der Sie in einem Sequenzkanal für ein überzeugendes Erlebnis sorgen können, indem Sie einen Titel oder eine Beschreibung auf einem Bild einfügen. Auf dieser Seite erfahren Sie mehr.
uuid: 944477e8-0025-4cc7-aa61-6b72f4a245fd
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: b6fdb5a0-5601-4443-a3f4-85cc90c49914
noindex: true
feature: Inhaltserstellung in Screens
role: Admin, Developer
level: Intermediate
exl-id: bbc719df-24a7-4cfb-9786-1c3496f9f082
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: ht
source-wordcount: '850'
ht-degree: 100%

---

# Textüberlagerung {#text-overlay}

In diesem Abschnitt werden folgende Themen behandelt:

* **Überblick**
* **Verwenden von Textüberlagerung**
* **Verstehen der Eigenschaften von Textüberlagerung**
* **Verwenden von ContextHub-Werten in Textüberlagerung**

>[!CAUTION]
>
>Die Funktion **Textüberlagerung** ist nur verfügbar, wenn Sie AEM 6.3 Feature Pack 5 oder AEM 6.4 Feature Pack 3 installiert haben.

## Überblick {#overview}

Textüberlagerung ist eine Funktion in AEM Screens, mit der Sie in einem Sequenzkanal für ein überzeugendes Erlebnis sorgen können, indem Sie einen Titel oder eine Beschreibung auf einem Bild einfügen.

Informationen zum Erstellen einer eigenen benutzerdefinierten Komponente finden Sie unter **Erweitern einer AEM Screens-Komponente**.

In diesem Abschnitt wird nur gezeigt, wie die Poster-Komponente in einem AEM Screens-Projekt als Textüberlagerung in einem Ihrer Sequenz-Kanäle genutzt werden kann.

## Verwenden von Textüberlagerung {#using-text-overlay}

Im folgenden Abschnitt wird die Verwendung von Textüberlagerung in AEM Screens-Projekten beschrieben.

**Voraussetzungen**

Bevor Sie mit der Implementierung der Funktion beginnen, stellen Sie sicher, dass Sie als Voraussetzung ein Projekt eingerichtet haben. Beispiel:

* Erstellen Sie ein AEM Screens-Projekt (in diesem Beispiel **TextOverlayDemo**)

* Erstellen eines Sequenzkanals als **TextSample** im Ordner **Kanäle**

* Fügen Sie Inhalte zu Ihrem Kanal **TextSample** hinzu

Die folgende Abbildung zeigt das Projekt **TextOverlayDemo** mit dem Kanal **TextSample** im Ordner **Kanäle**.

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

Gehen Sie wie folgt vor, um die Textüberlagerung in einem AEM Screens-Kanal zu verwenden:

1. Navigieren Sie zu **TextOverlayDemo** > **Kanäle** > **TextSample** und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Wählen Sie das Bild aus und klicken Sie auf **Konfigurieren** (Schraubenschlüsselsymbol), um das Dialogfeld „Eigenschaften“ zu öffnen.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Wählen Sie in der Navigationsleiste des Dialogfelds die Option **Textüberlagerung**, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Verstehen der Eigenschaften von Textüberlagerung {#understanding-text-overlay-properties}

Mithilfe der Eigenschaften für Textüberlagerung können Sie einer beliebigen Komponente in einem Screens-Projekt Text hinzufügen. Im folgenden Abschnitt erhalten Sie eine Übersicht über die Eigenschaften, die in der Textüberlagerung verfügbar sind:

![text](assets/text.gif)

Sie können dem Textfeld einen Text hinzufügen und typografische Hervorhebungen wie Fett, Kursiv, Unterstrichen usw. anwenden.

**Farbvariante** Mit dieser Option kann der Text entweder dunkel (Text in schwarzer Farbe) oder hell (Text in weißer Farbe) dargestellt werden.

**Größe und Anordnung** Mit dieser Option kann der Benutzer den Text horizontal oder vertikal ausrichten oder zusätzlich präzise Tools für die Textausrichtung verwenden.

>[!NOTE]
>
>Für einen richtigen Einsatz der Tools müssen Sie die gewünschte Position in Pixel mit „px“ als Suffix angeben (z. B. „200px“). Das Ergebnis dieses Ausdrucks ist 200 Pixel vom Anfangspunkt entfernt.

## Verwenden von ContextHub-Werten in Textüberlagerung {#using-text-overlay-context-hub}

Im folgenden Abschnitt wird die Verwendung von Werten aus einem Datenspeicher beschrieben, z. B. Google-Tabellen in der Komponente für Textüberlagerung.

**Voraussetzungen**

Sie müssen ContextHub-Konfigurationen für Ihr AEM Screens-Projekt einrichten.

Informationen zum Einrichten und Verwalten datengesteuerter Asset-Änderungen mithilfe eines Datenspeichers finden Sie unter [Konfigurieren von ContextHub in AEM Screens](https://docs.adobe.com/content/help/de-DE/experience-manager-screens/user-guide/developing/configuring-context-hub.html).

Nachdem Sie die erforderlichen Konfigurationen für Ihr Projekt eingerichtet haben, führen Sie die folgenden Schritte aus, um Werte aus den Google-Tabellen zu verwenden:

1. Navigieren Sie zu **TextOverlayDemo** > **Kanäle** > **TextSample** und klicken Sie in der Aktionsleiste auf **Eigenschaften**.

1. Wählen Sie die Registerkarte **Personalisierung**, um die ContextHub-Konfigurationen einzurichten.

   1. Wählen Sie unter **ContextHub-Pfad** den Wert **libs** > **settings** > **cloudsettings** > **default** > **ContextHub Konfigurationen** aus und klicken Sie auf **Auswählen**.

   1. Wählen Sie unter **Segmentpfad** den Wert **conf** > **screens** > **settings** > **wcm** > **segments** aus und klicken Sie auf **Auswählen**.

   1. Klicken Sie auf **Speichern und schließen**.

      >[!NOTE]
      >
      >Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie Ihre Kontexthub-Konfigurationen und -Segmente anfänglich gespeichert haben.

      ![image1](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigieren Sie zu **TextOverlayDemo** > **Kanäle** > **TextSample** und klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Fügen Sie eine Bild- und eine Textüberlagerungskomponente zu Ihrem Bild hinzu, wie im Abschnitt [Verwenden von Textüberlagerung](/help/user-guide/text-overlay.md#using-text-overlay) auf dieser Seite beschrieben.

1. Klicken Sie auf **Konfigurieren** (Schraubenschlüsselsymbol), um das Dialogfeld **Bild** zu öffnen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Navigieren Sie zur Registerkarte **ContextHub** im Dialogfeld **Bild**. Klicken Sie auf **Hinzufügen**.

   >[!NOTE]
   >Wenn Sie Ihre ContextHub-Konfigurationen nicht eingerichtet haben, wird diese Option für Ihr Projekt deaktiviert.

1. Geben Sie **Wert** in das Feld **Platzhalter** ein, wählen Sie die Zeile aus, die Sie aus Ihrer Google-Tabelle in der **ContextHub-Variable** abrufen möchten (in diesem Fall wird der Wert aus Zeile 2 und Spalte 1 aus den Google-Tabellen abgerufen), und geben Sie den **Standardwert** wie in der Abbildung unten dargestellt als **20** ein. Klicken Sie auf das Häkchen, sobald Sie fertig sind.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >Für Ihre Referenz zeigt das folgende Bild den Wert an, der aus den Google-Tabellen abgerufen wird:

   ![image1](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Gehen Sie im Dialogfeld „Bild“ zurück zur Registerkarte **Textüberlagerung** und fügen Sie den Text *Aktuelle Temperatur {Wert}* hinzu, wie in der nachstehenden Abbildung dargestellt.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Klicken Sie auf **Vorschau**, um die gewünschte Ausgabe anzuzeigen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay10.png)
