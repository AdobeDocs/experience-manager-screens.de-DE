---
title: 'Anwendungsfall: Übergang von mehreren zu einzelnen Zonen'
description: Auf dieser Seite erfahren Sie mehr über den Anwendungsfall „Übergang von mehreren zu einzelnen Zonen“.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer, User
level: Intermediate
exl-id: 15632f31-1e92-40e5-b567-8705e27bdc93
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 88%

---

# Übergang von mehreren zu einzelnen Zonen {#multizone-to-singlezone-use-case}

## Anwendungsfallbeschreibung {#use-case-description}

In diesem Abschnitt wird ein Anwendungsfall beschrieben, indem erläutert wird, wie man einen Mehrzonen-Layout-Kanal im Wechsel mit einem Einzelzonen-Layout-Kanal einrichtet. Der Mehrzonenkanal verfügt über sequenzierende Bild-/Video-Assets, und es wird gezeigt, wie Sie ein Projekt einrichten können, in dem zwischen Mehr- und Einzelzonen hin- und hergewechselt werden kann.

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

   1. Klicken Sie auf **Kanäle** Ordner und klicken Sie auf **Erstellen** in der Symbolleiste und öffnen Sie den Assistenten, damit Sie einen Kanal erstellen können.
   1. Klicks **Splitscreen-Kanal mit L-Balken links** Erstellen Sie im Assistenten den Kanal mit dem Titel **MultiZoneLayout**.
   1. Fügen Sie dem Kanal Inhalt hinzu. Ziehen Sie die Assets in die einzelnen Zonen. Das folgende Beispiel zeigt einen **MultiZoneLayout**-Kanal, der aus einem Video, einem Bild und einem Textbanner (in einer eingebetteten Sequenz) besteht, wie unten dargestellt.

   ![Asset](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Weitere Informationen zum Erstellen eines Mehrzonen-Layouts in Ihrem Kanal finden Sie unter [Mehrzonen-Layout](multi-zone-layout-aem-screens.md).


1. Erstellen Sie einen weiteren Kanal mit der Bezeichnung **TakeoverChannel** in Ihrem Ordner **Kanäle**.

   ![Asset](assets/mz-to-sz3.png)

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um Inhalte zu diesem Kanal hinzuzufügen. Fügen Sie dem Kanal eine Komponente **Kanal** und ein Bild-Asset hinzu, zu dem Sie wechseln möchten, wie in der folgenden Abbildung gezeigt:

   ![Asset](assets/mz-to-sz4.png)

1. Öffnen Sie die Einstellungen für die Komponente „Kanal“ und erstellen Sie einen Verweis auf den **MultiZoneLayout**-Kanal, den Sie in *Schritt 2* erstellt haben.

   ![Asset](assets/mz-to-sz5.png)

1. Legen Sie die Dauer im Feld **Sequenz** auf **10000 Millisekunden** fest.

   ![Asset](assets/mz-to-sz6.png)

1. Öffnen Sie auf ähnliche Weise die Einstellungen für das Bild (das von Ihnen hinzugefügte Asset) und legen Sie seine Dauer im Feld **Sequenz** auf **3000 Millisekunden** fest.

   ![Asset](assets/mz-to-sz7.png)

## Überprüfen der Vorschau {#checking-the-preview}

Sie können die gewünschte Ausgabe auf dem Player oder durch Auswählen der **Vorschau** im Editor anzeigen.

Die Ausgabe zeigt an, wie ein Mehrzonen-Layout für *10000 Millisekunden* wiedergegeben wird, zu einem Einzelzonen-Layout mit einer Wiedergabedauer von *3000 Millisekunden* wechselt und dann wieder zurück zum Mehrzonen-Layout wechselt.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>Sie können Ihren Kanalübergang entsprechend Ihren Anforderungen (vom Mehrzonen- zum Einzelzonen-Layout oder umgekehrt) anpassen.
