---
title: 'Nutzungsszenario: Übergang von mehreren zu einzelnen Zonen'
description: Auf dieser Seite erfahren Sie mehr über den Anwendungsfall Übergang von mehreren zu einzelnen Zonen.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer, User
level: Intermediate
exl-id: 15632f31-1e92-40e5-b567-8705e27bdc93
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 36%

---

# Übergang von mehreren zu einzelnen Zonen {#multizone-to-singlezone-use-case}

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Abschnitt wird ein Anwendungsbeispiel beschrieben, in dem erläutert wird, wie ein Mehrzonen-Layout-Kanal eingerichtet wird, der mit einem Einzelzonen-Layout-Kanal wechselt. Der Mehrzonen-Kanal verfügt über sequenzierende Bild-/Video-Assets und zeigt, wie Sie ein Projekt einrichten können, das von einer Mehrzonen- zur Einzonen-Zone und umgekehrt wechselt.

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

   1. Wählen Sie die **Kanäle** Ordner und auswählen **Erstellen** in der Symbolleiste und öffnen Sie den Assistenten, damit Sie einen Kanal erstellen können.
   1. Wählen Sie im Assistenten die Option **Splitscreen-Kanal mit L-Balken links** aus und erstellen Sie den Kanal mit dem Namen **MultiZoneLayout**.
   1. Fügen Sie dem Kanal Inhalt hinzu. Ziehen Sie die Assets in die einzelnen Zonen. Das folgende Beispiel zeigt eine **MultiZoneLayout** Kanal, der ein Video, ein Bild und ein Textbanner (in einer eingebetteten Sequenz) umfasst, wie unten dargestellt.

   ![Asset](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Weitere Informationen zum Erstellen eines Mehrzonen-Layouts in Ihrem Kanal finden Sie unter [Mehrzonen-Layout](multi-zone-layout-aem-screens.md).


1. Erstellen Sie einen weiteren Kanal mit der Bezeichnung **TakeoverChannel** in Ihrem Ordner **Kanäle**.

   ![Asset](assets/mz-to-sz3.png)

1. Auswählen **Bearbeiten** in der Aktionsleiste, damit Sie diesem Kanal Inhalte hinzufügen können. Hinzufügen einer **Kanal** -Komponente und ein Bild-Asset, zu dem Sie für diesen Kanal wechseln möchten, wie in der folgenden Abbildung dargestellt:

   ![Asset](assets/mz-to-sz4.png)

1. Öffnen Sie die Einstellungen für die Komponente „Kanal“ und erstellen Sie einen Verweis auf den **MultiZoneLayout**-Kanal, den Sie in *Schritt 2* erstellt haben.

   ![Asset](assets/mz-to-sz5.png)

1. Legen Sie die Dauer aus der **Sequenz** -Feld zu **10000 Millisekunden**.

   ![Asset](assets/mz-to-sz6.png)

1. Öffnen Sie auf ähnliche Weise die Einstellungen für das Bild (Asset, das Sie hinzugefügt haben) und legen Sie die Dauer über die **Sequenz** -Feld zu **3000 Millisekunden**.

   ![Asset](assets/mz-to-sz7.png)

## Überprüfen der Vorschau {#checking-the-preview}

Sie können die gewünschte Ausgabe im Player anzeigen oder einfach durch Auswahl von **Vorschau** aus dem Editor aus.

Die Ausgabe zeigt, wie ein Mehrzonen-Layout für *10000 Millisekunden* und wechselt dann zu einem Einzelzonen-Layout mit der Wiedergabedauer von *3000 Millisekunden* und wechselt dann zurück zum Mehrzonen-Layout.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>Sie können Ihren Kanalübergang (von Mehrzonen- zu Einzelzonen-Layout oder umgekehrt) entsprechend Ihren Anforderungen anpassen.
