---
title: Adobe Analytics-Integration mit AEM Screens
seo-title: Adobe Analytics-Integration mit AEM Screens
description: Auf dieser Seite erfahren Sie mehr über die Integration von AEM Screens mit Adobe Analytics und erhalten einen Spielnachweis.
seo-description: Auf dieser Seite erfahren Sie mehr über die Integration von AEM Screens mit Adobe Analytics und erhalten einen Spielnachweis.
uuid: 80d61af7-bf4d-46ca-a026-99a666c2e1a0
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: b1a0e00e-0368-42c9-8bcd-5f00b4d0990c
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Adobe Analytics-Integration mit AEM Screens {#adobe-analytics-integration-with-aem-screens}

>[!CAUTION]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.4.2 Feature Pack 2 und AEM 6.3.3 Feature Pack 4 installiert haben.

>Um Zugriff auf eines dieser Feature Packs zu erhalten, müssen Sie sich an den Adobe Support wenden und den Zugriff anfordern. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.
>
Dieser Abschnitt behandelt die folgenden Themen:

* **Überblick**
* **Architekturdetails**
* **Eigenschaften konfigurieren**

## Überblick {#overview}

***AEM Screens*** nutzt Adobe Analytics, und damit können Sie etwas Besonderes auf dem Markt erreichen - kanalübergreifende Analysen, die dazu beitragen, die lokal angezeigten Inhalte mit anderen Datenquellen zu korrelieren.

AEM Screens bietet eine Out-of-the-Box-Integration mit Adobe Analytics und einen Spielnachweis.

In diesem Abschnitt werden die folgenden Funktionen beim Verbinden eines AEM Screens-Projekts mit Adobe Analytics beschrieben:

* Ermöglicht die Berichterstellung zum Nachweis der Wiedergabe nach Gerät
* Ermöglicht die Berichterstellung zum Nachweis der Wiedergabe nach Asset
* Stellt sicher, dass alle Player-Ereignisse erfasst und mit einem Zeitstempel versehen werden
* Stellt sicher, dass alle Player-Ereignisse lokal gespeichert werden, wenn die Wiedergabe nicht mit einem Netzwerk verbunden ist
* Ermöglicht die Erstellung von Feedback-Schleifen zur Verfolgung von Wiedergabeereignissen im Zeitverlauf
* Ermöglicht das Ändern von Inhalt und Layouts anhand von Erfolgskriterien, die vom Inhaltsautor definiert wurden

Die Integration von Adobe Analytics in AEM Screens setzt daher folgende *Ziele*:

* Aktivieren der ROI aus Digital Signage-Implementierungen
* Analytics als Grundlage für die künftige Aktivierung der Erfassung und Analyse von Nutzungsinformationen integrieren

## Architekturdetails {#architectural-details}

Kunden mit AEM Screens möchten verstehen, welche Inhalte zu welcher Zeit und für wie lange (aggregiert) angezeigt wurden. Dies ist die übliche Fähigkeit der Signage-Lösung. Statt eigene Analysen zu erstellen, nutzt AEM Screens Adobe Analytics, und damit können wir etwas Besonderes auf dem Markt erreichen - kanalübergreifende Analysen, die dazu beitragen, die lokalisierten Inhalte mit anderen Datenquellen zu korrelieren.

Im folgenden Architekturdiagramm wird die Integration von Adobe Analytics mit AEM Screens erläutert:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Aktivieren von Adobe Analytics in AEM-Bildschirmen {#enabling-adobe-analytics-in-aem-screens}

Die Adobe Analytics-Einstellungen können über die OSGi-Konsole konfiguriert werden.

Navigieren Sie zur **Adobe Experience Manager Web-Konsolenkonfiguration** , um Adobe Analytics für AEM-Bildschirme zu konfigurieren, wie in der folgenden Abbildung dargestellt:

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

## Screenanalysen: Aktivierungsfluss {#screens-analytics-enablement-flow}

>[!CAUTION]
Bevor Sie die Eigenschaften konfigurieren, wenden Sie sich an Ihren Adobe Relationship Manager, um ein Ticket zu erstellen, um einen **Analytics-API-Schlüssel** und ein **Analyseprojekt** für die Verwendung mit AEM Screens zu erhalten.

![]()

### Eigenschaften konfigurieren {#configuring-the-properties}

>[!CAUTION]
Bevor Sie die Eigenschaften konfigurieren, wenden Sie sich an Ihren Adobe Relationship Manager, um ein Ticket zu erstellen, um einen **Analytics-API-Schlüssel** und ein **Analyseprojekt** für die Verwendung mit AEM Screens zu erhalten.

In der folgenden Tabelle werden die Eigenschaften mit ihrer Beschreibung zur Konfiguration von Adobe Analytics für AEM Screens aufgeführt:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><strong>Analytics-URL</strong></td>
   <td>URL zum Posten von Analysedaten vom Player<br /> </td>
  </tr>
  <tr>
   <td><strong>Analytics-API-Schlüssel</strong></td>
   <td>API-Schlüssel für die Authentifizierung beim Adobe Analytics-Server (vom Konten-Manager bereitgestellt)</td>
  </tr>
  <tr>
   <td><strong>Analytics-Projekt</strong></td>
   <td>AEM Screens-Projekt, das in Ihrer Analyse für den Empfang von Daten konfiguriert wurde (bereitgestellt vom Accounts Manager)</td>
  </tr>
  <tr>
   <td><strong>Umgebung</strong></td>
   <td><p>Stage- oder Produktionsumgebung.</p> <p><em>Entwicklungs-/Bereitstellungs</em> - https://cc-api-data-stage.adobe.io/ingest/<br /> <em>für die Produktion</em> - https://cc-api-data.adobe.io/ingest/</p> </td>
  </tr>
  <tr>
   <td><strong>Analytics-Senden-Frequenz</strong></td>
   <td>Häufigkeit in Minuten, mit der Analysedaten von den Playern gesendet werden. Standardmäßig ist er auf 15 Minuten eingestellt.</td>
  </tr>
 </tbody>
</table>

>[!NOTE]
Standardmäßig beträgt die **Analytics-Senden-Frequenz **15 Minuten.

#### Verwenden des Adobe Analytics-Dienstes in AEM Screens {#using-adobe-analytics-service-in-aem-screens}

Dieses Szenario ruft die Analytics-API über REST-Aufrufe eines Analytics-Dienstes in den Komponenten "Firmware"und "Instrument"auf, um explizit Ereignisse zu erstellen und zu senden, die für einen bestimmten Anwendungsfall spezifisch sind, während gleichzeitig die Erweiterbarkeit ermöglicht wird, bei der benutzerdefinierte Nachrichten von einem benutzerdefinierten entwickelten Kanal an Analytics gesendet werden können.

Analytics-Ereignisse werden offline in indexedDB und später chunked gespeichert und an die Cloud gesendet.

>[!NOTE]
Weitere Informationen zum ***Sequenzieren*** und zum ***Standarddatenmodell für Ereignisse*** finden Sie unter Adobe Analytics für AEM-Bildschirme **[konfigurieren](configuring-adobe-analytics-aem-screens.md)**.

