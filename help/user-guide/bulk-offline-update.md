---
title: Bulk Offline Update
seo-title: Bulk Offline Update
description: Auf dieser Seite erfahren Sie, wie Sie alle Kanäle stapelweise aktualisieren können.
seo-description: Auf dieser Seite erfahren Sie, wie Sie alle Kanäle stapelweise aktualisieren können.
uuid: 9b52c5e7-aa6d-4f55-b23c-8bd923723552
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 5d4ca652-d918-4b2b-b239-a2be9255ef0d
noindex: true
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Bulk Offline Update {#bulk-offline-update}

In diesem Abschnitt werden die folgenden Themen zur Massenaktualisierung von Offlinedokumenten behandelt:

* **Überblick**
* **Verwenden der Offline-Massenaktualisierung**

>[!CAUTION]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.3 Feature Pack 3 oder AEM 6.4 Screens Feature Pack 1 installiert haben.
>
>Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

## Überblick {#overview}

Bulk Offline Update, ermöglicht Ihnen, den gesamten Kanal in großen Mengen zu aktualisieren. Dadurch wird die einfache Navigation zu einem bestimmten Kanal und die Aktualisierung des Inhalts vermieden. Stattdessen können Sie den gesamten Inhalt in Kanälen für ein bestimmtes Projekt in einem Moment aktualisieren.

Sie können diese Aktivität auch für eine Zeit geringeren Netzwerkverkehrs planen.

>[!NOTE]
>
>Die Funktion für die Offline-Aktualisierung von Massen wurde optimiert, um nur die Kanäle zu aktualisieren, die geändert wurden.

## Verwenden der Offline-Massenaktualisierung {#using-bulk-offline-update}

Sie können Bulk Offline Update über die Benutzeroberfläche (UI) manuell verwenden oder die Massenaktualisierung über OSGi-Dienste planen.

### Verwenden der AEM Screens-Benutzeroberfläche {#using-aem-screens-user-interface}

Gehen Sie wie folgt vor, um eine Bulk-Offline-Aktualisierung für ein AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt.
1. Wählen Sie das Projekt aus und klicken Sie in der Aktionsleiste auf "Offline-Inhalt **** aktualisieren", um den Kanalinhalt manuell zu aktualisieren.

   ![screen_shot_2018-04-24at12256pm](assets/screen_shot_2018-04-24at122256pm.png)

### Konfiguration von Adobe Experience Manager Web Console {#adobe-experience-manager-web-console-configuration}

Gehen Sie wie folgt vor, um eine Bulk-Offline-Aktualisierung für ein AEM Screens-Projekt zu verwenden:

1. Konfiguration von Adobe Experience Manager Web Console.
1. Suchen Sie nach Bulk Offline-Updateservices.

   ![screen_shot_2018-04-24at121428pm](assets/screen_shot_2018-04-24at121428pm.png)

1. Fügen Sie die folgenden Eigenschaften hinzu:

   **Projektpfad** Geben Sie den Pfad Ihres AEM Screens-Projekts an. Der Pfad ist gewöhnlich `/content/screens/<Name of your project>`.

   *Beispiel*, `/content/screens/we-retail`. Sie können diesen Pfad in der URL finden, indem Sie ein beliebiges Projekt unter AEM Screens auswählen (klicken Sie nicht auf das Symbol).

   >[!NOTE]
   >
   >Geben Sie den Projektpfad relativ zum Kanal an.

   **Häufigkeit** des Planens Geben Sie einen Zeitpunkt an, z. B. 17.00 Uhr oder 17.00 Uhr, zu dem dieser Dienst Offlineinhalte aktualisieren soll.

1. Klicken Sie auf **Speichern** , um Ihre Einstellungen zu speichern, und Ihre Inhalte werden zum festgelegten Zeitpunkt aktualisiert.

