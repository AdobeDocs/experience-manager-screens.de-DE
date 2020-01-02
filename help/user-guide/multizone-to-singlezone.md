---
title: MultiZone zu SingleZone-Übergangsfall
description: Auf dieser Seite erfahren Sie mehr über den Einsatzfall MultiZone zu SingleZone Transitions.
seo-description: MultiZone zu SingleZone Transitions Anwendungsfall.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 6f770734941635a0cd404986c259022137355af3

---


# Übergang von mehreren Zonen zu einer Einzone {#multizone-to-singlezone-use-case}


## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Abschnitt wird ein Verwendungsfallbeispiel beschrieben, in dem hervorgehoben wird, wie ein Mehrzonenlayoutkanal eingerichtet wird, der durch einen einzonigen Layoutkanal ersetzt wird. Der Mehrzonenkanal verfügt über sequenzierende Bild-/Video-Assets und zeigt, wie Sie ein Projekt einrichten können, das von einer Multizone zu einer Einzone wechselt und umgekehrt.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Anwendungsfall beginnen, sollten Sie wissen, wie:

* **[Kanäle erstellen und verwalten](managing-channels.md)**
* **[Orte erstellen und verwalten](managing-locations.md)**
* **[Zeitpläne erstellen und verwalten](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Inhaltsersteller

## Setting up the Project {#setting-up-the-project}

Gehen Sie wie folgt vor, um ein Projekt einzurichten:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Namen **TakeoverLoop**, wie unten dargestellt.

   ![Asset](assets/mz-to-sz1.png)


1. **Mehrzonenbildschirme erstellen**

   1. Wählen Sie den Ordner &quot; **Kanäle** &quot;aus und klicken Sie in der Aktionsleiste auf &quot; **Erstellen** &quot;, um den Assistenten zum Erstellen eines Kanals zu öffnen.
   1. Wählen Sie im Assistenten die Option &quot; **Linke Balkensplit Screen Channel** &quot;und erstellen Sie den Kanal mit dem Namen **MultiZoneLayout**.
   1. Fügen Sie dem Kanal Inhalte hinzu. Ziehen Sie die Assets per Drag &amp; Drop in die einzelnen Zonen. Das folgende Beispiel zeigt einen **MultiZoneLayout** -Kanal, der aus einem Video, einem Bild und einem Textbanner (in einer eingebetteten Sequenz) besteht, wie unten dargestellt.
   ![Asset](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Weitere Informationen zum Erstellen eines Layouts für mehrere Zonen in Ihrem Kanal finden Sie unter [Mehrzonenlayout](multi-zone-layout-aem-screens.md).


1. Erstellen Sie einen weiteren Kanal mit der Bezeichnung **TakeoverChannel** in Ihrem **Channels** -Ordner.

   ![Asset](assets/mz-to-sz3.png)

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten** , um diesem Kanal Inhalt hinzuzufügen. Fügen Sie eine **Kanalkomponente** und ein Bild-Asset hinzu, zu diesem Kanal hin zu wechseln, wie in der folgenden Abbildung gezeigt:

   ![Asset](assets/mz-to-sz4.png)

1. Öffnen Sie die Einstellungen für die Komponente &quot;Channel&quot;und verweisen Sie darauf, dass Sie den **MultiZoneLayout** -Kanal verwenden, den Sie in *Schritt 2* erstellt haben.

   ![Asset](assets/mz-to-sz5.png)

1. Legen Sie die Dauer des Felds &quot; **Sequenz** &quot;auf **10000 ms** fest.

   ![Asset](assets/mz-to-sz6.png)

1. Öffnen Sie auf ähnliche Weise die Einstellungen für das Bild (Asset, das Sie hinzugefügt haben) und legen Sie seine Dauer im Feld **Sequenz** auf **3000 ms** fest.

   ![Asset](assets/mz-to-sz7.png)

## Überprüfen der Vorschau {#checking-the-preview}

Sie können die gewünschte Ausgabe vom Player oder durch Klicken auf die **Vorschau** im Editor anzeigen.

Die Ausgabe zeigt an, wie ein Layout mit mehreren Zonen für *10000 ms* wiedergegeben wird, und wechselt dann zu einem Einzelzonenlayout mit einer Wiedergabedauer von *3000 ms* und wechselt dann zum Layout mit mehreren Zonen zurück.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>Sie können Ihren Kanalübergang entsprechend Ihren Anforderungen anpassen (von einem Mehrzonenlayout zum Einzelzonenlayout oder umgekehrt).