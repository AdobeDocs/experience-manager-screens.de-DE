---
title: Adobe Analytics-Integration mit AEM Screens
seo-title: Adobe Analytics-Integration mit AEM Screens
description: Folgen Sie dieser Seite, um mehr über die vorkonfigurierte Integration von AEM Screens mit Adobe Analytics zu erfahren und einen Wiedergabenachweis zu erhalten.
seo-description: Folgen Sie dieser Seite, um mehr über die vorkonfigurierte Integration von AEM Screens mit Adobe Analytics zu erfahren und einen Wiedergabenachweis zu erhalten.
uuid: 80d61af7-bf4d-46ca-a026-99a666c2e1a0
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: b1a0e00e-0368-42c9-8bcd-5f00b4d0990c
docset: aem65
translation-type: ht
source-git-commit: f25176be89424059b8c51296969f069687328536
workflow-type: ht
source-wordcount: '684'
ht-degree: 100%

---


# Adobe Analytics-Integration mit AEM Screens{#adobe-analytics-integration-with-aem-screens}

>[!CAUTION]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie das Feature Pack 2 für AEM 6.4.2 und das Feature Pack 4 für AEM 6.3.3 installiert haben.

>[!NOTE]
>
>Wenden Sie sich an den Adobe-Support, um Zugriff auf diese Feature Packs zu erhalten. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

In diesem Abschnitt werden folgende Themen behandelt:

* **Überblick**
* **Architekturdetails**
* **Konfigurieren der Eigenschaften**

## Überblick {#overview}

***AEM Screens*** nutzt Adobe Analytics, um etwas Einzigartiges auf dem Markt erreichen: kanalübergreifende Analysen, die die Korrelation von lokal angezeigten Inhalten mit anderen Datenquellen ermöglichen.

AEM Screens bietet eine vorkonfigurierte Integration mit Adobe Analytics und liefert Ihnen einen Wiedergabenachweis.

In diesem Abschnitt werden folgende Funktionen beschrieben, die beim Verbinden eines AEM Screens-Projekts mit Adobe Analytics genutzt werden:

* Berichte zum Nachweis der Wiedergabe nach Gerät
* Berichte zum Nachweis der Wiedergabe nach Asset
* Sicherstellung, dass alle Player-Ereignisse erfasst und mit einem Zeitstempel versehen werden
* Sicherstellung, dass alle Player-Ereignisse lokal gespeichert werden, wenn die Wiedergabe nicht mit einem Netzwerk verbunden ist
* Erstellung von Feedback-Schleifen zur Verfolgung von Wiedergabeereignissen im Zeitverlauf
* Ändern von Inhalten und Layouts anhand von Erfolgskriterien, die vom Inhaltsautor definiert wurden

Eine Integration von Adobe Analytics mit AEM Screens hat somit folgende *Ziele*:

* Fördern des ROI bei der Implementierung digitaler Beschilderungen
* Integrieren von Analytics als Grundlage für die künftige Erfassung und Analyse von Nutzungsdaten

## Architekturdetails {#architectural-details}

Ein AEM Screens-Kunde möchte wissen, welche Inhalte wann wie lange angezeigt wurden (aggregiert). Dies ist eine gebräuchliche Funktion einer Beschilderungslösung. Statt eigene Analysen zu erstellen, nutzt AEM Screens Adobe Analytics, um etwas branchenweit Einzigartiges zu ermöglichen: kanalübergreifende Analysen, die dabei helfen, lokale angezeigte Inhalte mit anderen Datenquellen zu korrelieren.

Im folgenden Architekturdiagramm wird die Integration von Adobe Analytics mit AEM Screens veranschaulicht:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Aktivieren von Adobe Analytics in AEM Screens {#enabling-adobe-analytics-in-aem-screens}

Die Einstellungen von Adobe Analytics können über die OSGi-Konsole konfiguriert werden.

Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole**, um Adobe Analytics für AEM Screens zu konfigurieren (wie in der folgenden Abbildung gezeigt):

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

## Screens Analytics: Aktivierungsablauf {#screens-analytics-enablement-flow}

>[!CAUTION]
>
>Wenden Sie sich vor der Konfiguration der Eigenschaften an Ihren Adobe Relationship Manager, damit dieser ein Ticket erstellt und Sie einen **Analytics-API-Schlüssel** sowie ein **Analytics-Projekt** zur Verwendung mit AEM Screens erhalten.

![]()

### Konfigurieren der Eigenschaften {#configuring-the-properties}

>[!CAUTION]
>
>Wenden Sie sich vor der Konfiguration der Eigenschaften an Ihren Adobe Relationship Manager, damit dieser ein Ticket erstellt und Sie einen **Analytics-API-Schlüssel** sowie ein **Analytics-Projekt** zur Verwendung mit AEM Screens erhalten.

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
   Für Entwicklung/Staging</em>: https://cc-api-data-stage.adobe.io/ingest/<br /> <em>Für Produktion</em>: https://cc-api-data.adobe.io/ingest/</em><br /> <br /></td>
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

#### Verwenden des Adobe Analytics-Dienstes in AEM Screens {#using-adobe-analytics-service-in-aem-screens}

In diesem Szenario wird die Analytics-API über REST-Aufrufe aus einem Analytics-Dienst in den Kernkomponenten „Firmware“ und „Instrumentenbildschirme“ aufgerufen, um explizit Ereignisse zu erstellen und zu senden, die für ein bestimmtes Nutzungsszenario spezifisch sind. Gleichzeitig ist eine Erweiterung möglich, bei der sich benutzerdefinierte Nachrichten von einem benutzerdefinierten Kanal an Analytics senden lassen.

Analytics-Ereignisse werden in indexedDB offline gespeichert und später aufgeteilt und an die Cloud gesendet.

>[!NOTE]
>
>Weitere Informationen zum ***Sequenzieren*** und zum ***Standarddatenmodell für Ereignisse*** finden Sie unter **[Konfigurieren von Adobe Analytics für AEM Screens](configuring-adobe-analytics-aem-screens.md)**.

