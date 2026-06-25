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
TQID: https://experienceleague.adobe.com/9BVI-WKkjiL-vY57T-GMir-4Dll552q-30LDHF20BxU
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
subfeature_v2:
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: d4664dd5678eaccabe656398c437dca264d4675e
workflow-type: tm+mt
source-wordcount: 538
ht-degree: 77%

---

# AEM Screens-Benachrichtigungsdienst{#aem-screens-notifications-service}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***AEM Screens-Benachrichtigungsdienst*** beschreibt die Geräteaktivität.

In diesem Abschnitt werden folgende Themen behandelt:

* **Überblick**
* **Konfigurieren der E-Mail-Einstellungen**
* **E-Mail-Benachrichtigung**
* **Anwendungsbeispiel**

<!-- 
OBSOLETE NOTE>
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3.2 Feature Pack 3 or AEM 6.4.1 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. After you have permissions you can download it from Package Share. 
-->

## Überblick {#overview}

Der ***AEM Screens-Benachrichtigungsdienst*** bietet Admins die Möglichkeit, sich eine E-Mail schicken zu lassen, wenn ein AEM Screens-Player in einem konfigurierbaren Zeitraum nicht gepingt hat.

Der Service lässt sich in der OSGi-Web-Konsole einrichten.

## Konfigurieren der E-Mail-Einstellungen {#configuring-email-settings}

Gehen Sie wie folgt vor, um die Einstellungen für E-Mail-Benachrichtigungen zu konfigurieren:

1. Öffnen Sie die **Konfiguration der Adobe Experience Manager-Web-Konsole**.
1. Öffnen Sie den **Screens-E-Mail-Überwachungs-Service für Geräte**.

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieren Sie die folgenden Felder, um Ihre Einstellungen für E-Mail zu konfigurieren:

   **Gerätepfad** - Geben Sie den Pfad zu den Screens-Projekten ein, die Sie überwachen möchten. Der Pfad heißt gewöhnlich `/home/users/screens/<Name of your project>`.

   Wenn Ihr Projekt beispielsweise **`We.Retail`** lautet, verwenden Sie ***/home/users/screens/we-retail*** als Projektpfad.

   >[!NOTE]
   >
   >Geben Sie den Projektpfad an, unter dem sich die Gerätebenutzerinnen und -benutzer befinden.

   **Häufigkeit** - Geben Sie eine Zeit (z. B. 17 :00 Uhr oder 17 :00) oder eine Häufigkeit in Stunden (z. B. 1) an, zu der der Service E-Mails senden soll.

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

Sie haben die Zeitplanfrequenz auf 1 :00 und die Ping-Zeitüberschreitung auf 60 festgelegt. Wenn Ihr AEM Screens-Gerät dann zwischen 12:00 :00 und 13:00 :00 keinen Ping durchführt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.

**Szenario 2**

Sie legen die Zeitplanfrequenz auf 1 und das Ping-Timeout auf 60 fest. Wenn Ihr AEM Screens-Gerät dann zur gegebenen Zeit des Tages nicht pingt, erhalten Sie eine E-Mail-Benachrichtigung, die die Inaktivität des Geräts bestätigt.
