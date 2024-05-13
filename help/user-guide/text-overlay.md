---
title: Textüberlagerung
description: Erfahren Sie mehr über die Textüberlagerung in AEM Screens, mit der Sie in einem Sequenzkanal für ein überzeugendes Erlebnis sorgen können, indem Sie einen Titel oder eine Beschreibung auf einem Bild als Überlagerung einfügen.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: bbc719df-24a7-4cfb-9786-1c3496f9f082
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 63%

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

Textüberlagerung ist eine Funktion, die in AEM Screens verfügbar ist. Damit können Sie in einem Sequenzkanal ein überzeugendes Erlebnis erstellen, indem Sie einen Titel oder eine Beschreibung angeben, die über einem Bild überlagert ist.

Informationen zum Erstellen einer eigenen benutzerdefinierten Komponente finden Sie unter **Erweitern einer AEM Screens-Komponente**.

In diesem Abschnitt wird nur gezeigt, wie die Poster-Komponente in einem AEM Screens-Projekt verwendet und angewendet wird. Außerdem wird gezeigt, wie Sie es als Textüberlagerung in einem Ihrer Sequenzkanäle verwenden.

## Verwenden von Textüberlagerung {#using-text-overlay}

Im folgenden Abschnitt wird die Verwendung von Textüberlagerung in AEM Screens-Projekten beschrieben.

**Voraussetzungen**

Stellen Sie vor der Implementierung der Funktion sicher, dass Sie als Voraussetzung für den Start der Implementierung der Textüberlagerung ein Projekt eingerichtet haben. Zum Beispiel:

* Erstellen Sie ein AEM Screens-Projekt (in diesem Beispiel **TextOverlayDemo**)

* Erstellen Sie einen Sequenzkanal mit dem Titel **TextSample** unter **Kanäle** Ordner

* Fügen Sie Inhalte zu Ihrem Kanal **TextSample** hinzu

Die folgende Abbildung zeigt die **TextOverlayDemo** -Projekt mit **TextSample** -Kanal im **Kanäle** Ordner.

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

Gehen Sie wie folgt vor, um die Textüberlagerung in einem AEM Screens-Kanal zu verwenden:

1. Navigieren Sie zu **TextOverlayDemo** > **Kanäle** > **TextSample** und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Klicken Sie auf das Bild und klicken Sie auf **Konfigurieren** (Schraubenschlüsselsymbol), um das Dialogfeld &quot;Eigenschaften&quot;zu öffnen.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Klicken Sie auf **Textüberlagerung** in der Navigationsleiste des Dialogfelds, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Verstehen der Eigenschaften von Textüberlagerung {#understanding-text-overlay-properties}

Mit den Eigenschaften der Textüberlagerung können Sie zu jeder Komponente in Ihrem Screens-Projekt Text hinzufügen. Im folgenden Abschnitt erhalten Sie eine Übersicht über die Eigenschaften, die in der Textüberlagerung verfügbar sind:

![text](assets/text.gif)

Sie können dem Textfeld einen Text hinzufügen und typografische Hervorhebungen wie fett, kursiv und unterstrichen hinzufügen.

**Farbvariante**: Mit dieser Option kann der Text entweder dunkel (Text in schwarzer Farbe) oder hell (Text in weißer Farbe) dargestellt werden.

**Größe und Anordnung**: Mit dieser Option können Benutzende den Text horizontal oder vertikal ausrichten oder zusätzlich fein abgestufte Werkzeuge für die Textausrichtung verwenden.

>[!NOTE]
>
>Achten Sie bei Verwendung von fein abgestuften Tools darauf, die richtige Position in Pixel mit (px) als Suffix anzugeben, z. B. 200 px. Das Ergebnis dieses Ausdrucks ist 200 Pixel vom Startpunkt entfernt.

## Verwenden von ContextHub-Werten in Textüberlagerung {#using-text-overlay-context-hub}

Im folgenden Abschnitt wird die Verwendung von Werten aus einem Datenspeicher beschrieben, z. B. Google-Tabellen in der Textüberlagerungskomponente.

**Voraussetzungen**

Erstellen Sie ContextHub-Konfigurationen für Ihr AEM Screens-Projekt.

Informationen zum Einrichten und Verwalten datengesteuerter Asset-Änderungen mithilfe eines Datenspeichers finden Sie unter [Konfigurieren von ContextHub in AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/developing/configuring-context-hub).

Nachdem Sie die erforderlichen Konfigurationen für Ihr Projekt eingerichtet haben, führen Sie die folgenden Schritte aus, um Werte aus den Google-Tabellen zu verwenden:

1. Navigieren Sie zu **TextOverlayDemo** > **Kanäle** > **TextSample** und klicken **Eigenschaften** in der Aktionsleiste aus.

1. Klicken Sie auf **Personalisierung** -Registerkarte, damit Sie die ContextHub-Konfigurationen einrichten können.

   1. Klicken Sie auf **ContextHub-Pfad** as **libs** > **settings** > **cloudsettings** > **default** > **ContextHub-Konfigurationen** und klicken **Auswählen**.

   1. Klicken Sie auf **Segmentpfad** as **conf** > **screens** > **settings** > **wcm** > **Segmente** und klicken **Auswählen**.

   1. Klicken Sie auf **Speichern und schließen**.

      >[!NOTE]
      >
      >Verwenden Sie den ContextHub- und den Segmentpfad, in dem Sie Ihre Kontexthub-Konfigurationen und -Segmente anfänglich gespeichert haben.

      ![image1](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigieren Sie zu **TextOverlayDemo** > **Kanäle** > **TextSample** und klicken Sie in der Aktionsleiste auf **Bearbeiten**.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Fügen Sie Ihrem Bild eine Komponente für Bild- und Textüberlagerung hinzu, wie in [Verwenden von Textüberlagerung](/help/user-guide/text-overlay.md#using-text-overlay) auf dieser Seite.

1. Klicken Sie auf **Konfigurieren** (Schraubenschlüsselsymbol), um das Dialogfeld **Bild** zu öffnen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Navigieren Sie zur Registerkarte **ContextHub** im Dialogfeld **Bild**. Klicken Sie auf **Hinzufügen**.

   >[!NOTE]
   >Wenn Sie Ihre ContextHub-Konfigurationen nicht eingerichtet haben, ist diese Option für Ihr Projekt deaktiviert.

1. Geben Sie den **Wert** im Feld **Platzhalter** ein. Klicken Sie auf die Zeile, die Sie aus Ihrem Google-Blatt abrufen möchten, in **ContextHub-Variable**. In diesem Fall wird der Wert aus Zeile 2 und Spalte 1 aus den Google-Tabellen abgerufen. Geben Sie nun die **Standardwert** as **20**, wie in der folgenden Abbildung dargestellt. Wenn Sie fertig sind, klicken Sie auf das Häkchen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >Für Ihre Referenz zeigt das folgende Bild den Wert an, der aus den Google-Tabellen abgerufen wird:

   ![image1](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Gehen Sie im Dialogfeld „Bild“ zurück zur Registerkarte **Textüberlagerung** und fügen Sie den Text *Aktuelle Temperatur {Wert}* hinzu, wie in der nachstehenden Abbildung dargestellt.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Klicken Sie auf **Vorschau**. 

   ![image1](/help/user-guide/assets/text-overlay/text-overlay10.png)
