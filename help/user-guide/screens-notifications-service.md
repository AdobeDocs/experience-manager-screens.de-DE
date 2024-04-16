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
source-git-commit: b65e59473e175e7c1b31fba900bb7e47eff3a263
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 16%

---

# AEM Screens-Benachrichtigungs-Service{#aem-screens-notifications-service}

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***AEM Screens-Benachrichtigungsdienst*** beschreibt die Geräteaktivität.

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
>To get access to this Feature Pack, contact Adobe Support and request access. After you have permissions you can download it from Package Share. -->

## Übersicht {#overview}

***AEM Screens-Benachrichtigungsdienst*** ermöglicht es Administratoren, eine E-Mail zu erhalten, wenn ein AEM Screens-Player während einer konfigurierbaren Zeit nicht pingt.

Der Service lässt sich in der OSGi-Web-Konsole einrichten.

## Konfigurieren der E-Mail-Einstellungen {#configuring-email-settings}

Gehen Sie wie folgt vor, um die E-Mail-Benachrichtigungseinstellungen zu konfigurieren:

1. Öffnen Sie die **Konfiguration der Adobe Experience Manager-Web-Konsole**.
1. Öffnen Sie den **Screens-E-Mail-Überwachungs-Service für Geräte**.

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieren Sie die folgenden Felder, damit Sie Ihre Einstellungen für die E-Mail konfigurieren können:

   **Gerätepfad** Geben Sie den Pfad zu den Screens-Projekten ein, die Sie überwachen möchten. Der Pfad heißt gewöhnlich `/home/users/screens/<Name of your project>`.

   Wenn Ihr Projekt beispielsweise **`We.Retail`**, verwenden Sie den Projektpfad als ***/home/users/screens/we-retail***.

   >[!NOTE]
   >
   >Geben Sie den Projektpfad an, unter dem sich die Gerätebenutzer befinden.

   **Planfrequenz** - Geben Sie eine Zeit (z. B. 17:00 Uhr oder 17:00 Uhr) oder eine Häufigkeit in Stunden (z. B. 1) an, zu der dieser Monitor E-Mails senden soll.

   **Ping Time Out** - Gibt das Intervall in Minuten an, nach dem ein Gerät als nicht erreichbar betrachtet werden soll.

   **SMTP-Server** - Gibt den SMTP-Server an, der zum Senden von E-Mails verwendet wird.

   **SMTP-Port** - Geben Sie den SMTP-Port ein.

   **Verwenden von TLS** - Transport Layer Security (TLS) ermöglicht die Verwendung einer sicheren Kommunikation mit dem SMTP-Server.

   Adobe empfiehlt die Verwendung von TLS für eine sichere Verbindung zu Unternehmens-E-Mail-Servern. Erkundigen Sie sich bei Ihrem E-Mail-Administrator nach geeigneten Werten.

   **Benutzername** - Geben Sie den Benutzernamen zum Senden von E-Mails an.

   **password** - Geben Sie das Kennwort zum Senden von E-Mails an.

   **Empfänger** - Geben Sie die E-Mail-Adresse des Empfängers an.

   >[!NOTE]
   >
   >Sie können nur eine E-Mail-Adresse eingeben. Um eine Massen-E-Mail zu senden, erstellen Sie eine Gruppen- oder Verteilerliste mit den entsprechenden Benutzern.

1. Auswählen **Speichern** , um die Überwachungsaktivität per E-Mail für Ihr AEM Screens-Gerät zu konfigurieren.

## E-Mail-Benachrichtigung {#email-notification}

Nachdem Sie die Konfiguration für Ihre E-Mail-Benachrichtigungen festgelegt haben, erhalten Sie eine E-Mail-Benachrichtigung, die den Link zum Gerät enthält, auf dem die Inaktivität gemeldet wird.

Durch Zugriff auf diesen Link gelangen Sie direkt zum Geräte-Dashboard.

E-Mails werden nur gesendet, wenn mindestens ein Gerät vorhanden ist, das während des angegebenen Ping-Timeouts nicht gepingt hat und zum Zeitpunkt der Generierung der E-Mail noch nicht pingt.

### Anwendungsbeispiele {#example-use-cases}

Im folgenden Beispiel werden einige Szenarien beschrieben, in denen Sie die Eigenschaften über den E-Mail-Überwachungsdienst für Screens-Geräte konfigurieren können.

**Szenario 1**

Sie legen die Häufigkeit auf 1:00 Uhr und das Ping-Timeout auf 60 fest. Wenn Ihr AEM Screens-Gerät dann nicht zwischen 12:00 Uhr und 13:00 Uhr ping, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.

**Szenario 2**

Sie legen die Häufigkeit auf 1 und das Ping-Timeout auf 60 fest. Wenn Ihr AEM Screens-Gerät dann zu keiner Tageszeit zwischen einem Ping pingt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.
