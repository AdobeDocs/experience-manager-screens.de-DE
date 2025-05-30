---
title: Adobe Analytics-Integration mit AEM Screens
description: Erfahren Sie mehr über die vorkonfigurierte Integration von AEM Screens in Adobe Analytics und darüber, wie Sie einen Wiedergabenachweis erhalten.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: 92c8c42b-7c1e-4d4a-8662-18c99666e9c6
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 100%

---

# Adobe Analytics-Integration mit AEM Screens {#adobe-analytics-integration-with-aem-screens}

>[!CAUTION]
>
>Diese AEM Screens-Funktionalität ist nur verfügbar, wenn Sie mindestens AEM 6.4.2 Feature Pack 2 oder AEM 6.3.3 Feature Pack 4 installiert haben. Kundinnen und Kunden, die AEM Screens Cloud Service nutzen, sollten sich an das Adobe-Relationship-Management wenden, um Adobe Analytics in Screens Cloud aktivieren zu lassen.

>[!NOTE]
>
>Wenden Sie sich an den Adobe-Support, um Zugriff auf diese Feature Packs zu erhalten. Das neueste Feature Pack für AEM Screens steht auf dem [Software-Verteilungsportal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) zum Download zur Verfügung (Adobe ID erforderlich).

In diesem Abschnitt werden folgende Themen behandelt:

* **Überblick**
* **Architekturdetails**
* **Konfigurieren der Eigenschaften**

## Überblick {#overview}

***AEM Screens*** nutzt Adobe Analytics, um etwas Einzigartiges auf dem Markt erreichen: kanalübergreifende Analysen, die eine Korrelation von lokal angezeigten Inhalten mit anderen Datenquellen ermöglichen.

AEM Screens bietet eine vorkonfigurierte Integration mit Adobe Analytics und liefert Ihnen einen Wiedergabenachweis.

In diesem Abschnitt werden folgende Funktionen beschrieben, die beim Verbinden eines AEM Screens-Projekts mit Adobe Analytics genutzt werden:

* Berichte zum Nachweis der Wiedergabe nach Gerät
* Berichte zum Nachweis der Wiedergabe nach Asset
* Sicherstellung, dass alle Player-Ereignisse erfasst und mit einem Zeitstempel versehen werden
* Sicherstellung, dass alle Player-Ereignisse lokal gespeichert werden, wenn die Wiedergabe nicht mit einem Netzwerk verbunden ist
* Erstellung von Feedback-Schleifen zur Verfolgung von Wiedergabeereignissen im Laufe der Zeit
* Systemseitige Bearbeitung von Inhalten und Layouts anhand von Erfolgskriterien, die von der Inhaltsautorin bzw. dem Inhaltsautor definiert wurden

Eine Integration von Adobe Analytics mit AEM Screens hat somit folgende *Ziele*:

* Fördern des ROI bei der Implementierung von Digital Signage
* Integrieren von Analytics als Grundlage für die künftige Erfassung und Analyse von Nutzungsdaten

## Architekturdetails {#architectural-details}

AEM Screens-Kundinnen und -Kunden möchten wissen, welche Inhalte wann und wie lange (insgesamt) angezeigt wurden. Diese Anforderung gehört zu den gängigen Funktionen einer Signage-Lösung. Statt auf eine separate Analyseanwendung zu setzen, verwendet AEM Screens Adobe Analytics. Diese Kombination ermöglicht es uns, etwas Einzigartiges auf dem Markt erreichen: kanalübergreifende Analysen, die eine Korrelation von lokal angezeigten Inhalten mit anderen Datenquellen ermöglichen.

Im folgenden Architekturdiagramm wird die Integration von Adobe Analytics mit AEM Screens veranschaulicht:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Aktivieren von Adobe Analytics in AEM Screens {#enabling-adobe-analytics-in-aem-screens}

Die Einstellungen von Adobe Analytics können über die OSGi-Konsole konfiguriert werden.

Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**, um Adobe Analytics für AEM Screens zu konfigurieren.

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

## Screens Analytics: Aktivierungsablauf {#screens-analytics-enablement-flow}

>[!CAUTION]
>
>Wenden Sie sich vor der Konfiguration der Eigenschaften an das Adobe-Relationship-Management, um ein Ticket öffnen zu lassen und einen **Analytics-API-Schlüssel** sowie ein **Analytics-Projekt** zur Verwendung mit AEM Screens zu erhalten.

### Konfigurieren der Eigenschaften {#configuring-the-properties}

>[!CAUTION]
>
>Wenden Sie sich vor der Konfiguration der Eigenschaften an das Adobe-Relationship-Management, um ein Ticket öffnen zu lassen und einen **Analytics-API-Schlüssel** sowie ein **Analytics-Projekt** zur Verwendung mit AEM Screens zu erhalten.

In der folgenden Tabelle werden die Eigenschaften mit ihrer Beschreibung zur Konfiguration von Adobe Analytics für AEM Screens aufgeführt:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschaft</strong></td>
   <td><strong>Beschreibung</strong></td>
  </tr>
  <tr>
   <td><strong>Analytics-URL</strong></td>
   <td>URL zum Posten von Analysedaten aus dem Player. <br>
   Für Entwicklung/Staging</em>: https://cc-api-data-stage.adobe.io/ingest/<br /> <em>Für Produktion</em>: https://cc-api-data.adobe.io/ingest/<br /> <br /></td>
  </tr>
  <tr>
   <td><strong>Analytics-API-Schlüssel</strong></td>
   <td>API-Schlüssel für die Authentifizierung beim Adobe Analytics-Server (bereitgestellt vom Account Manager).</td>
  </tr>
  <tr>
   <td><strong>Analytics-Projekt</strong></td>
   <td>Das AEM Screens-Projekt, das in Ihrer Analyse für den Empfang von Daten konfiguriert wurde (bereitgestellt vom Account Manager).</td>
  </tr>
  <tr>
   <td><strong>Umgebung</strong></td>
   <td><p>Staging- oder Produktionsumgebung (wählen Sie entweder „Staging“ oder „Produktion“ aus).</p></td>
  </tr>
  <tr>
   <td><strong>Analytics-Sendefrequenz</strong></td>
   <td>Häufigkeit (in Minuten), mit der Analysedaten von den Playern gesendet werden. Standardmäßig ist der Wert auf 15 Minuten eingestellt.</td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Standardmäßig beträgt die **Analytics-Sendefrequenz** 15 Minuten.

#### Verwenden des Adobe Analytics-Service in AEM Screens {#using-adobe-analytics-service-in-aem-screens}

Dieses Szenario ruft die Analytics-API über REST-Aufrufe von einem Analytics-Dienst in der Firmware auf. Außerdem werden AEM Screens-Core-Komponenten zum Erstellen und Senden von für einen bestimmten Anwendungsfall spezifischen Ereignissen eingesetzt. All diese Funktionen sind erweiterbar, wobei jede benutzerdefinierte Nachricht von einem benutzerdefinierten Kanal an Analytics gesendet werden kann.

Analytics-Ereignisse werden in indexedDB offline gespeichert und später aufgeteilt und an die Cloud gesendet.

>[!NOTE]
>
>Weitere Informationen zum ***Sequenzieren*** und zum ***Standarddatenmodell für Ereignisse*** finden Sie unter **[Konfigurieren von Adobe Analytics für AEM Screens](configuring-adobe-analytics-aem-screens.md)**.
