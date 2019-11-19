---
title: AEM Screens-Benachrichtigungsdienst
seo-title: AEM Screens-Benachrichtigungsdienst
description: Auf dieser Seite erfahren Sie mehr darüber, wie Sie die Geräteaktivität überwachen können.
seo-description: Auf dieser Seite erfahren Sie mehr darüber, wie Sie die Geräteaktivität überwachen können.
uuid: 9843219d-ed39-4e4f-bef4-e500528ff9f1
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 8879e510-4f0e-46da-87d2-77c5aaacb26e
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# AEM Screens-Benachrichtigungsdienst{#aem-screens-notifications-service}

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***Der AEM Screens-Benachrichtigungsdienst*** beschreibt die Funktion, mit der Sie die Geräteaktivität überwachen können.

Dieser Abschnitt behandelt die folgenden Themen:

* **Überblick**
* **E-Mail-Einstellungen konfigurieren**
* **Email Notification**
* **Verwendungsfall**

>[!CAUTION]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.3.2 Feature Pack 3 oder AEM 6.4.1 Screens Feature Pack 1 installiert haben.
>
>Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

## Überblick {#overview}

***AEM Screens-Benachrichtigungsdienst*** ermöglicht Administratoren den Empfang einer E-Mail, wenn ein AEM-Bildschirmplayer für einen konfigurierbaren Zeitraum nicht ping.

Dieser Dienst kann in der OSGi-Webkonsole konfiguriert werden.

## Configuring Email Settings {#configuring-email-settings}

Gehen Sie wie folgt vor, um die Einstellungen für E-Mail-Benachrichtigungen zu konfigurieren:

1. Open **Adobe Experience Manager Web Console Configuration**.
1. Öffnen Sie den **Anzeigebereich "Geräte-E-Mail-Überwachungsdienst**".

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieren Sie die folgenden Felder, um Ihre Einstellungen für die E-Mail zu konfigurieren:

   **Gerätepfad** Geben Sie den Pfad zu den Bildschirmen ein, die Sie überwachen möchten. Der Pfad ist gewöhnlich `/home/users/screens/<Name of your project>`.

   Wenn Ihr Projekt beispielsweise **We.Retail** ist, verwenden Sie den Projektpfad als ***/home/users/screens/we-trading***.

   >[!NOTE]
   >
   >Geben Sie den Projektpfad an, unter dem sich die Gerätebenutzer befinden.

   **Häufigkeit** planen Geben Sie eine Zeit (z. B. 17.00 Uhr oder 23.00 Uhr) oder Häufigkeit in Stunden (z. B. 1) an, zu der dieser Monitor E-Mails senden soll.

   **Ping-Timeout** : Gibt das Intervall in Minuten an, nach dem ein Gerät als nicht erreichbar betrachtet werden sollte.

   **SMTP-Server** Gibt den SMTP-Server an, der zum Senden von E-Mails verwendet wird.

   **SMTP-Anschluss** Geben Sie den SMTP-Anschluss ein.

   **Mit TLS** Transport Layer Security (TLS) können Sie eine sichere Kommunikation mit dem SMTP-Server nutzen.

   Es wird empfohlen, TLS für eine sichere Verbindung mit den E-Mail-Servern des Unternehmens zu verwenden. Bitte fragen Sie bei Ihrem E-Mail-Administrator nach entsprechenden Werten.

   **Benutzername** Geben Sie den Benutzernamen zum Senden von E-Mails an.

   **password** Geben Sie das Kennwort zum Senden von E-Mails an.

   **Empfänger** Geben Sie die E-Mail-Adresse des Empfängers an.

   >[!NOTE]
   >
   >Sie können nur eine E-Mail-Adresse eingeben. Um eine Massen-E-Mail zu senden, erstellen Sie eine Gruppen- oder Verteilerliste mit den entsprechenden Benutzern.

1. Klicken Sie auf **Speichern** , um die Monitoraktivität über eine E-Mail für Ihr AEM Screens-Gerät zu konfigurieren.

## Email Notification {#email-notification}

Nachdem Sie die Konfiguration für Ihre E-Mail-Benachrichtigungen festgelegt haben, erhalten Sie eine E-Mail-Benachrichtigung, die den Link zum Gerät enthält, auf dem die Inaktivität gemeldet wird.

Durch Zugriff auf diesen Link gelangen Sie direkt zum Geräte-Dashboard.

E-Mails werden nur gesendet, wenn mindestens ein Gerät vorhanden ist, das für den angegebenen Ping-Timeout nicht gepingt hat und zum Zeitpunkt der Generierung der E-Mail noch nicht pingelt.

### Beispiel-Anwendungsfälle {#example-use-cases}

Im folgenden Beispiel werden einige Szenarien beschrieben, in denen Sie die Eigenschaften von Bildschirmgerät-E-Mail-Überwachungsdienst konfigurieren können.

**Szenario 1**:

Wenn Sie die Häufigkeit des Zeitplans auf 1:00 Uhr und den Ping-Timeout auf 60 festlegen und Ihr Bildschirmgerät nicht zwischen 22:00 Uhr und 13:00 Uhr pinkt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.

**Szenario 2**:

Wenn Sie die Zeitintervallfrequenz auf 1 und den Ping-Timeout auf 60 einstellen und das Bildschirmgerät zu keiner bestimmten Tageszeit zwischen den Pfaden pinkelt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.
