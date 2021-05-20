---
title: 'Nutzungsszenario: Übergang von mehreren zu einzelnen Zonen'
description: 'Auf dieser Seite erfahren Sie mehr über das Nutzungsszenario: Übergang von mehreren zu einzelnen Zonen.'
seo-description: 'Nutzungsszenario: Übergang von mehreren zu einzelnen Zonen.'
contentOwner: Jyotika Syal
feature: Inhaltserstellung in Screens
role: Developer, Business Practitioner
level: Intermediate
exl-id: 15632f31-1e92-40e5-b567-8705e27bdc93
source-git-commit: 60a6583dd3bf79ef09099506107705bf0bce1e07
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 100%

---

# Übergang von mehreren zu einzelnen Zonen {#multizone-to-singlezone-use-case}


## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Abschnitt wird ein Nutzungsszenario beschrieben, das erläutert, wie man einen Mehrzonen-Layout-Kanal im Wechsel mit einem Einzelzonen-Layout-Kanal einrichtet. Der Mehrzonenkanal verfügt über sequenzierende Bild-/Video-Assets und zeigt, wie Sie ein Projekt einrichten können, in dem zwischen Mehr- und Einzelzonen gewechselt werden kann.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Nutzungsszenario beginnen, sollten Sie sich mit den folgenden Themen vertraut machen:

* **[Erstellen und Verwalten von Kanälen](managing-channels.md)**
* **[Erstellen und Verwalten von Standorten](managing-locations.md)**
* **[Erstellen und Verwalten von Zeitplänen](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Autoren von Inhalten

## Einrichten des Projekts {#setting-up-the-project}

Gehen Sie wie folgt vor, um ein Projekt einzurichten:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Namen **TakeoverLoop** wie unten dargestellt.

   ![Asset](assets/mz-to-sz1.png)


1. **Erstellen eines Mehrzonenkanals in Screens**

   1. Wählen Sie den Ordner **Kanäle** aus und klicken Sie in der Aktionsleiste auf **Erstellen**, um den Assistenten zum Erstellen eines Kanals zu öffnen.
   1. Wählen Sie im Assistenten die Option **Splitscreen-Kanal mit L-Balken links** aus und erstellen Sie den Kanal mit dem Namen **MultiZoneLayout**.
   1. Fügen Sie dem Kanal Inhalt hinzu. Ziehen Sie die Assets in die einzelnen Zonen. Das folgende Beispiel zeigt einen **MultiZoneLayout**-Kanal, der aus einem Video, einem Bild und einem Textbanner (in einer eingebetteten Sequenz) besteht, wie unten dargestellt.

   ![Asset](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Weitere Informationen zum Erstellen eines Mehrzonen-Layouts in Ihrem Kanal finden Sie unter [Mehrzonen-Layout](multi-zone-layout-aem-screens.md).


1. Erstellen Sie einen weiteren Kanal mit der Bezeichnung **TakeoverChannel** in Ihrem Ordner **Kanäle**.

   ![Asset](assets/mz-to-sz3.png)

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um diesem Kanal Inhalt hinzuzufügen. Fügen Sie diesem Kanal eine Komponente **Kanal** und ein Bild-Asset hinzu, zu dem Sie wechseln möchten, wie in der folgenden Abbildung gezeigt:

   ![Asset](assets/mz-to-sz4.png)

1. Öffnen Sie die Einstellungen für die Komponente „Kanal“ und erstellen Sie einen Verweis auf den **MultiZoneLayout**-Kanal, den Sie in *Schritt 2* erstellt haben.

   ![Asset](assets/mz-to-sz5.png)

1. Legen Sie die Dauer im Feld **Sequenz** auf **10000 ms** fest.

   ![Asset](assets/mz-to-sz6.png)

1. Öffnen Sie auf ähnliche Weise die Einstellungen für das Bild (das von Ihnen hinzugefügte Asset) und legen Sie seine Dauer im Feld **Sequenz** auf **3000 ms** fest.

   ![Asset](assets/mz-to-sz7.png)

## Überprüfen der Vorschau {#checking-the-preview}

Sie können die gewünschte Ausgabe auf dem Player oder durch Klicken auf die **Vorschau** im Editor anzeigen.

Die Ausgabe zeigt an, wie ein Mehrzonen-Layout für *10000 ms* wiedergegeben wird, zu einem Einzelzonen-Layout mit einer Wiedergabedauer von *3000 ms* wechselt und dann wieder zurück zum Mehrzonen-Layout wechselt.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>Sie können Ihren Kanalübergang entsprechend Ihren Anforderungen (vom Mehrzonen- zum Einzelzonen-Layout oder umgekehrt) anpassen.
