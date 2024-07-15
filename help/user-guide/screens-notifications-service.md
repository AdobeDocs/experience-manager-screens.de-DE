---
title: AEM Screens-Benachrichtigungsdienst
description: Erfahren Sie mehr darüber, wie Sie die Geräteaktivität für AEM Screens überwachen können.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 205235d7-e621-4134-975c-257ae60939bc
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 100%

---

# AEM Screens-Benachrichtigungsdienst{#aem-screens-notifications-service}

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

## Überblick {#overview}

Der ***AEM Screens-Benachrichtigungsdienst*** bietet Admins die Möglichkeit, sich eine E-Mail schicken zu lassen, wenn ein AEM Screens-Player in einem konfigurierbaren Zeitraum nicht gepingt hat.

Der Service lässt sich in der OSGi-Web-Konsole einrichten.

## Konfigurieren der E-Mail-Einstellungen {#configuring-email-settings}

Gehen Sie wie folgt vor, um die Einstellungen für E-Mail-Benachrichtigungen zu konfigurieren:

1. Öffnen Sie die **Konfiguration der Adobe Experience Manager-Web-Konsole**.
1. Öffnen Sie den **Screens-E-Mail-Überwachungs-Service für Geräte**.

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieren Sie die folgenden Felder, um Ihre Einstellungen für E-Mail zu konfigurieren:

   **Gerätepfad**: Geben Sie den Pfad zu den Screens-Projekten ein, die Sie überwachen möchten. Der Pfad heißt gewöhnlich `/home/users/screens/<Name of your project>`.

   Wenn Ihr Projekt beispielsweise **`We.Retail`** lautet, verwenden Sie ***/home/users/screens/we-retail*** als Projektpfad.

   >[!NOTE]
   >
   >Geben Sie den Projektpfad an, unter dem sich die Gerätebenutzerinnen und -benutzer befinden.

   **Häufigkeit**: Geben Sie eine Zeit (z. B. 17.00 Uhr) oder eine Häufigkeit in Stunden (z. B. 1) an, zu der der Service E-Mails senden soll.

   **Ping-Timeout**: Dieses Feld gibt das Intervall in Minuten an, nach dem ein Gerät als nicht erreichbar betrachtet werden soll.

   **SMTP-Server** Gibt den SMTP-Server an, der zum Senden von E-Mails verwendet werden soll.

   **SMTP-Port** Gibt den SMTP-Port an.

   **TLS verwenden**: Mit Transport Layer Security (TLS) können Sie für eine sichere Kommunikation mit dem SMTP-Server sorgen.

   Adobe empfiehlt, für sichere Verbindungen mit Unternehmens-E-Mail-Servern TLS zu verwenden. Fragen Sie Ihre E-Mail-Admins nach geeigneten Werten.

   **Benutzername**: Geben Sie den Benutzernamen zum Senden von E-Mails an.

   **Kennwort**: Geben Sie das Kennwort zum Senden von E-Mails an.

   **Empfänger**: Geben Sie die E-Mail-Adresse der Empfängerin bzw. des Empfängers an.

   >[!NOTE]
   >
   >Sie können nur eine E-Mail-Adresse eingeben. Um eine Massen-E-Mail zu senden, erstellen Sie eine Gruppenliste oder einen Verteiler mit den gewünschten Personen.

1. Klicken Sie auf **Speichern**, um die Überwachungsaktivität per E-Mail für Ihr AEM Screens-Gerät zu konfigurieren.

## E-Mail-Benachrichtigung {#email-notification}

Nachdem Sie die E-Mail-Benachrichtigungen konfiguriert haben, erhalten Sie eine E-Mail-Benachrichtigung, die den Link zum eigentlichen Gerät enthält, auf dem die Inaktivität gemeldet wurde.

Durch Zugriff auf diesen Link gelangen Sie direkt zum Geräte-Dashboard.

E-Mails werden nur gesendet, wenn:

* es mindestens ein Gerät gibt, das während des angegebenen Ping-Timeouts nicht gepingt hat, und
* dieses Gerät zum Zeitpunkt der Generierung der E-Mail nach wie vor nicht pingt.

### Beispiel-Anwendungsfälle {#example-use-cases}

Im folgenden Beispiel werden zur Referenz einige Szenarien beschrieben, in denen die Eigenschaften des E-Mail-Überwachungs-Services für Screens-Geräte konfiguriert werden.

**Szenario 1**

Sie legen die Zeitplanfrequenz auf 1:00 Uhr morgens und das Ping-Timeout auf 60 fest. Wenn Ihr AEM Screens-Gerät dann nicht zwischen 12:00 Uhr und 13:00 Uhr pingt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.

**Szenario 2**

Sie legen die Zeitplanfrequenz auf 1 und das Ping-Timeout auf 60 fest. Wenn Ihr AEM Screens-Gerät dann zur gegebenen Zeit des Tages nicht pingt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.
