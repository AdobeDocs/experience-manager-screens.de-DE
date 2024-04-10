---
title: AEM Screens-Benachrichtigungs-Service
description: Erfahren Sie mehr darüber, wie Sie Geräteaktivität für AEM Screens überwachen können.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 205235d7-e621-4134-975c-257ae60939bc
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 16%

---

# AEM Screens-Benachrichtigungs-Service{#aem-screens-notifications-service}

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***AEM Screens-Benachrichtigungsdienst*** Beschreibt die Aktivität „Gerät überwachen„.

In diesem Abschnitt werden folgende Themen behandelt:

* **Überblick**
* **Konfigurieren der E-Mail-Einstellungen**
* **E-Mail-Benachrichtigung**
* **Anwendungsbeispiel**

<!-- OBSOLETE NOTE>
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3.2 Feature Pack 3 or AEM 6.4.1 Screens Feature Pack 1.
>
>To get access to this Feature Pack, you must contact Adobe Support and request access. Once you have permissions you can download it from Package Share. -->

## Übersicht {#overview}

***AEM Screens-Benachrichtigungsdienst*** Ermöglicht es Administratoren, eine E-Mail zu erhalten, wenn ein AEM Screens-Player eine konfigurierbare Zeit lang nicht gepingt hat.

Der Service lässt sich in der OSGi-Web-Konsole einrichten.

## Konfigurieren der E-Mail-Einstellungen {#configuring-email-settings}

Gehen Sie wie folgt vor, um die Einstellungen für E-Mail-Benachrichtigungen zu konfigurieren:

1. Öffnen Sie die **Konfiguration der Adobe Experience Manager-Web-Konsole**.
1. Öffnen Sie den **Screens-E-Mail-Überwachungs-Service für Geräte**.

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieren Sie die folgenden Felder, um Ihre Einstellungen für die E-Mail zu konfigurieren:

   **Gerätepfad** Geben Sie den Pfad zu den Screens-Projekten ein, die Sie überwachen möchten. Der Pfad heißt gewöhnlich `/home/users/screens/<Name of your project>`.

   Wenn Ihr Projekt beispielsweise **`We.Retail`** verwenden Sie den Projektpfad als ***/home/users/screens/we-retail***.

   >[!NOTE]
   >
   >Geben Sie den Projektpfad an, unter dem sich die Gerätebenutzer befinden.

   **Zeitplanfrequenz** - Geben Sie eine Zeit (z. B. 17.00 Uhr oder 23.00 Uhr) oder eine Häufigkeit in Stunden (z. B. 1) an, zu der dieser Monitor E-Mails senden soll.

   **Ping-Zeitüberschreitung** - Dies gibt das Intervall in Minuten an, nach dem ein Gerät als nicht erreichbar betrachtet wird.

   **SMTP-Server** : Gibt den SMTP-Server an, der zum Senden von E-Mails verwendet wird.

   **SMTP-Port** : Geben Sie den SMTP-Port ein.

   **Verwenden von TLS** - Transport Layer Security (TLS) ermöglicht die sichere Kommunikation mit dem SMTP-Server.

   Adobe empfiehlt die Verwendung von TLS für eine sichere Verbindung mit E-Mail-Servern des Unternehmens. Erkundigen Sie sich bei Ihrem E-Mail-Administrator nach den entsprechenden Werten.

   **Benutzername** : Geben Sie den Benutzernamen für das Senden von E-Mails an.

   **Passwort** : Geben Sie das Kennwort für den E-Mail-Versand an.

   **Empfängerin oder Empfänger** : Geben Sie die E-Mail-Adresse des Empfängers an.

   >[!NOTE]
   >
   >Sie können nur eine E-Mail-Adresse eingeben. Um eine Massen-E-Mail zu senden, erstellen Sie eine Gruppen- oder Verteilerliste mit den entsprechenden Benutzern.

1. Auswählen **Speichern** So konfigurieren Sie die Aktivität „Überwachen“ über eine E-Mail für Ihr AEM Screens-Gerät.

## E-Mail-Benachrichtigung {#email-notification}

Nachdem Sie die Konfiguration für Ihre E-Mail-Benachrichtigungen festgelegt haben, erhalten Sie eine E-Mail-Benachrichtigung, die den Link zum tatsächlichen Gerät enthält, über das Inaktivität gemeldet wird.

Durch den Zugriff auf diesen Link werden Sie direkt zum Geräte-Dashboard weitergeleitet.

E-Mails werden nur gesendet, wenn es mindestens ein Gerät gibt, das für die angegebene Ping-Zeitüberschreitung nicht angepingt hat und zum Zeitpunkt der E-Mail-Generierung immer noch nicht gepingt hat.

### Anwendungsbeispiele {#example-use-cases}

Im folgenden Beispiel werden einige Szenarien als Referenz beschrieben, um die Eigenschaften des E-Mail-Überwachungs-Service für Screens-Geräte zu konfigurieren.

**Szenario 1**

Sie legen die Zeitplanfrequenz auf 1:00 Uhr und die Ping-Zeitüberschreitung auf 60 Uhr fest. Wenn Ihr AEM Screens-Gerät dann zwischen 12:00 Uhr und 13:00 Uhr keinen Ping-Vorgang ausführt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.

**Szenario 2**

Sie legen die Zeitplanfrequenz als 1 und die Ping-Zeitüberschreitung als 60 fest. Wenn Ihr AEM Screens-Gerät dann nicht einmal zwischen zwei Pings zu einem bestimmten Tageszeitpunkt pingt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.
