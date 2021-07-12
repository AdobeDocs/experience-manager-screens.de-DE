---
title: Inhaltsaktualisierung als Dienst
seo-title: Inhaltsaktualisierung als Dienst
description: Auf dieser Seite erhalten Sie Informationen zur Inhaltsaktualisierung als Dienst.
seo-description: Auf dieser Seite erhalten Sie Informationen zur Inhaltsaktualisierung als Dienst.
uuid: c73126ca-18d0-45b4-bdde-a3653082bfc4
contentOwner: Jyotika syal
feature: Inhaltserstellung in Screens
role: Admin, Developer
level: Intermediate
exl-id: de9f669b-9ce7-4d70-99b4-0b69ef3c1af5
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 100%

---

# Inhaltsaktualisierung als Dienst {#content-update-as-a-service}

In diesem Abschnitt werden folgende Themen zum Aktualisieren von Content-as-a-Service behandelt:

* **Überblick**
* **Verwenden des Massen-Offline-Updates**

>[!CAUTION]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.3 Feature Pack 3 oder AEM 6.4 Screens Feature Pack 1 installiert haben.
>
>Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

## Überblick {#overview}

Das Massen-Offline-Update ermöglicht es Ihnen, alle Kanäle gemeinsam zu aktualisieren. Das vermeidet den Aufwand, zu einem bestimmten Kanal zu navigieren und den Inhalt zu aktualisieren. Stattdessen können Sie den gesamten Inhalt in den Kanälen für ein bestimmtes Projekt gemeinsam aktualisieren.

Sie können diese Aktivität auch für eine Zeit mit geringerem Netzwerk-Traffic planen.

>[!NOTE]
>
>Die Funktion für das Massen-Offline-Update wurde so optimiert, dass nur die geänderten Kanäle aktualisiert werden.

## Verwenden des Massen-Offline-Updates {#using-bulk-offline-update}

Sie können das Massen-Offline-Update manuell über die Benutzeroberfläche (UI) verwenden oder das Massen-Update über OSGi-Dienste planen.

### Verwenden der AEM Screens-Benutzeroberfläche {#using-aem-screens-user-interface}

Gehen Sie wie folgt vor, um das Massen-Offline-Update für ein AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt.
1. Wählen Sie das Projekt aus und klicken Sie in der Aktionsleiste auf **Offline-Inhalt aktualisieren**, um den Kanalinhalt manuell zu aktualisieren.

   ![screen_shot_2018-04-24at122256pm](assets/screen_shot_2018-04-24at122256pm.png)

### Konfiguration der Adobe Experience Manager-Web-Konsole {#adobe-experience-manager-web-console-configuration}

Gehen Sie wie folgt vor, um das Massen-Offline-Update für ein AEM Screens-Projekt zu verwenden:

1. Konfiguration der Adobe Experience Manager-Web-Konsole.
1. Suchen Sie nach den Diensten für das Massen-Offline-Update.

   ![screen_shot_2018-04-24at121428pm](assets/screen_shot_2018-04-24at121428pm.png)

1. Fügen Sie die folgenden Eigenschaften hinzu:

   **Projektpfad** Geben Sie den Pfad Ihres AEM Screens-Projekts an. Der Pfad heißt gewöhnlich `/content/screens/<Name of your project>`.

   *Zum Beispiel* `/content/screens/we-retail`. Sie können diesen Pfad in der URL finden, indem Sie ein beliebiges Projekt unter AEM Screens auswählen (klicken Sie nicht auf das Symbol).

   >[!NOTE]
   >
   >Geben Sie den Projektpfad relativ zum Kanal an.

   **Zeitplanfrequenz** Geben Sie einen Zeitpunkt an, z. B. 17.00 Uhr, zu dem dieser Dienst Offline-Inhalte aktualisieren soll.

1. Klicken Sie auf **Speichern**, um Ihre Einstellungen zu speichern. Ihre Inhalte werden zum festgelegten Zeitpunkt aktualisiert.
