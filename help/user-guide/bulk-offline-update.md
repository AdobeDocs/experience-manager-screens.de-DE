---
title: Massen-Offline-Update
description: Erfahren Sie, wie Sie alle Kanäle stapelweise aktualisieren können.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d0a0b065-798e-4108-86ac-0a1f4e211cfc
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 74%

---

# Massen-Offline-Update {#bulk-offline-update}

In diesem Abschnitt werden die folgenden Themen zum Massen-Offline-Update behandelt:

* **Überblick**
* **Verwenden des Massen-Offline-Updates**

<!-- OBSOLETE VERSIONS
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, you must contact Adobe Support and request access. Once you have permissions you can download it from Package Share. -->

## Übersicht {#overview}

Bulk Offline Update ermöglicht die Massenaktualisierung aller Kanäle. Das vermeidet den Aufwand, zu einem bestimmten Kanal zu navigieren und den Inhalt zu aktualisieren. Stattdessen können Sie den gesamten Inhalt in den Kanälen für ein bestimmtes Projekt gemeinsam aktualisieren.

Sie können diese Aktivität auch für eine Zeit mit geringerem Netzwerk-Traffic planen.

>[!NOTE]
>
>Die Funktion für das Massen-Offline-Update wurde so optimiert, dass nur die geänderten Kanäle aktualisiert werden.

## Verwenden des Massen-Offline-Updates {#using-bulk-offline-update}

Sie können das Massen-Offline-Update manuell über die Benutzeroberfläche (UI) verwenden oder das Massen-Update über OSGi-Service planen.

### Verwenden der AEM Screens-Benutzeroberfläche {#using-aem-screens-user-interface}

Gehen Sie wie folgt vor, um das Massen-Offline-Update für ein AEM Screens-Projekt zu verwenden:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt.
1. Wählen Sie das Projekt aus und klicken Sie auf **Offline-Inhalt aktualisieren** in der Aktionsleiste aus, sodass Sie den Kanalinhalt manuell aktualisieren können.

   ![screen_shot_2018-04-24at122256pm](assets/screen_shot_2018-04-24at122256pm.png)

### Konfiguration der Adobe Experience Manager-Web-Konsole {#adobe-experience-manager-web-console-configuration}

Gehen Sie wie folgt vor, um das Massen-Offline-Update für ein AEM Screens-Projekt zu verwenden:

1. Konfiguration der Adobe Experience Manager-Web-Konsole.
1. Suchen Sie nach den Services für das Massen-Offline-Update.

   ![screen_shot_2018-04-24at121428pm](assets/screen_shot_2018-04-24at121428pm.png)

1. Fügen Sie die folgenden Eigenschaften hinzu:

   **Projektpfad** Geben Sie den Pfad Ihres AEM Screens-Projekts an. Der Pfad heißt gewöhnlich `/content/screens/<Name of your project>`.

   *Zum Beispiel* `/content/screens/we-retail`. Sie können diesen Pfad in der URL finden, indem Sie ein beliebiges Projekt unter AEM Screens auswählen (klicken Sie nicht auf das Symbol).

   >[!NOTE]
   >
   >Geben Sie den Projektpfad relativ zum Kanal an.

   **Zeitplanfrequenz** Geben Sie einen Zeitpunkt an, z. B. 17.00 Uhr, zu dem dieser Service Offline-Inhalte aktualisieren soll.

1. Auswählen **Speichern** um Ihre Einstellungen zu speichern. Ihr Inhalt wird zum angegebenen Zeitpunkt aktualisiert.
