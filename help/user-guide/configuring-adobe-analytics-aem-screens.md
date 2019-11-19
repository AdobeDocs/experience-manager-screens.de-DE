---
title: Konfigurieren von Adobe Analytics mit AEM Screens
seo-title: Konfigurieren von Adobe Analytics mit AEM Screens
description: 'In diesem Abschnitt erfahren Sie mehr über die Sequenzierung und das Senden benutzerspezifischer Ereignisse mit Offline-Adobe Analytics '
seo-description: 'In diesem Abschnitt erfahren Sie mehr über die Sequenzierung und das Senden benutzerspezifischer Ereignisse mit Offline-Adobe Analytics '
uuid: e685e553-c05b-4db4-8fa5-9ef45268b094
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: 3cec9266-4032-46b9-9c75-16da64bfea7d
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Konfigurieren von Adobe Analytics mit AEM Screens {#configuring-adobe-analytics-with-aem-screens}

>[!CAUTION]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.4.2 Feature Pack 2 und AEM 6.3.3 Feature Pack 4 installiert haben.

>Um Zugriff auf eines dieser Feature Packs zu erhalten, müssen Sie sich an den Adobe Support wenden und den Zugriff anfordern. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.
>
Dieser Abschnitt behandelt die folgenden Themen:

* **Sequenzierung in Adobe Analytics mit AEM Screens**
* **Senden benutzerspezifischer Ereignisse mit Offline-Adobe Analytics**

## Sequenzierung in Adobe Analytics mit AEM Screens {#sequencing-in-adobe-analytics-with-aem-screens}

Der ***Sequenzierungsprozess*** beginnt mit dem Datenspeicherdienst, der den Adobe Analytics-Dienst aktiviert. Kanalinhalt sendet Adobe Analytics-Ereignisse mit Payroll, d. h., die Datentesterfassung wird an die Windows-E/A gesendet, und es werden Aufenthaltsereignisse ausgelöst. Die Ereignisse werden im Index DB gespeichert und weiter in den Objektspeicher eingefügt. Je nach Zeitplan legt der Administrator fest, schneidet er die Daten aus dem Objektspeicher ab und überträgt sie dann weiter in den Stapelspeicher. Es versucht, die maximale Datenmenge zu senden, wenn eine Verbindung besteht.

### Sequenzierendes Diagramm {#sequencing-diagram}

Im folgenden Sequenzierungdiagramm wird die Adobe Analytics-Integration mit AEM Screens beschrieben:

![analytics_chunking](assets/analytics_chunking.png)

## Senden benutzerspezifischer Ereignisse mit Offline-Adobe Analytics {#sending-custom-events-using-offline-adobe-analytics}

Die folgende Tabelle fasst das Standarddatenmodell für Ereignisse zusammen. Es werden alle Felder aufgelistet, die an Adobe Analytics gesendet werden:

<table>
 <tbody>
  <tr>
   <td><strong>Abschnitt</strong></td> 
   <td><strong>Eigenschaftsbeschriftung</strong></td> 
   <td><strong>Eigenschaftsname/Schlüssel</strong></td> 
   <td><strong>Erforderlich</strong></td> 
   <td><strong>Datentyp</strong></td> 
   <td><strong>Eigenschaftstyp</strong><br /> </td> 
   <td><strong>Beschreibung</strong></td> 
  </tr>
  <tr>
   <td><strong><em>Core/Event</em></strong></td> 
   <td>Ereignis-GUID</td> 
   <td>event.guid</td> 
   <td>empfohlen</td> 
   <td>String</td> 
   <td>UUID</td> 
   <td>Eindeutige ID, die die Instanz eines Ereignisses identifiziert</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum der Erfassung des Ereignisses</td> 
   <td>event.coll_dts</td> 
   <td>optional</td> 
   <td>String</td> 
   <td>timestamp - UTC</td> 
   <td>Erfassungsdatum</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum des Ereignisses (Start)</td> 
   <td>event.dts_start</td> 
   <td>empfohlen</td> 
   <td>String</td> 
   <td>timestamp - UTC</td> 
   <td>Startzeitpunkt des Ereignisses, wenn Sie dies NICHT angeben, wird die Ereigniszeit als Empfangszeit des Servers angenommen</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum des Ereignisses (Ende)</td> 
   <td>event.dts_end</td> 
   <td>optional</td> 
   <td>String</td> 
   <td>timestamp - UTC</td> 
   <td>Abschlussdatum</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Workflow</td> 
   <td>event.workflow</td> 
   <td>empfohlen</td> 
   <td>String</td> 
   <td> </td> 
   <td>Workflow-Name (Bildschirme)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Haupt-DMe-Kategorie</td> 
   <td>event.category</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>Hauptkategorie (DESKTOP, MOBILE, WEB, PROZESS, SDK, SERVICE, ECOSYSTEM) - Gruppierung von Ereignistypen - <strong>Wir senden Player anWir senden Spieler</strong></td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Unterkategorie</td> 
   <td>event.subcategory</td> 
   <td>empfohlen</td> 
   <td>String</td> 
   <td> </td> 
   <td>Unterkategorie - Abschnitt eines Workflows oder Bereich eines Bildschirms usw. (Zuletzt verwendete Dateien, CC-Dateien, mobile Kreationen usw.)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Ereignis-/Aktionstyp</td> 
   <td>event.type</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>Ereignistyp (Rendering, Klicken, Pinch, Zoom) - Primäre Benutzeraktion</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Subtype</td> 
   <td>event.subtype</td> 
   <td>empfohlen</td> 
   <td>String</td> 
   <td> </td> 
   <td>Ereignisteiltyp (erstellen, aktualisieren, löschen, veröffentlichen usw.) - Zusätzliche Details der Benutzeraktion</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Offline</td> 
   <td>event.offline</td> 
   <td>optional</td> 
   <td>Boolesch</td> 
   <td> </td> 
   <td>Das Ereignis wurde generiert, während die Aktion offline/online war (true/false)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>User Agent</td> 
   <td>event.user_agent</td> 
   <td>empfohlen (Webeigenschaften)</td> 
   <td>String</td> 
   <td> </td> 
   <td>Benutzeragent</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Sprache/Sprache</td> 
   <td>event.language</td> 
   <td>empfohlen</td> 
   <td>String</td> 
   <td> </td> 
   <td>User locale ist eine Zeichenfolge, die auf den Sprach-Tagging-Konventionen von RFC 3066 basiert (z. B. en-US, fr-FR oder es-ES).</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Geräte-GUID</td> 
   <td>event.device_guid</td> 
   <td>optional</td> 
   <td>string<br /> </td> 
   <td>UUID</td> 
   <td>Identifiziert die Geräte-GUID (z.B. Computer-ID oder Hash der IP-Adresse + Subnet-Maske + Netzwerk-ID + Benutzeragent) - Hier senden wir den Benutzernamen des Players generiert zur Registrierungszeit.</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Count</td> 
   <td>event.count</td> 
   <td>optional</td> 
   <td>number</td> 
   <td> </td> 
   <td>Anzahl der aufgetretenen Ereignisse - hier senden wir die Videodauer</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Wert</td> 
   <td>event.value</td> 
   <td>optional</td> 
   <td>String</td> 
   <td> </td> 
   <td>Wert des Ereignisses (z. B. Einstellungen ein-/ausschalten)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>pageName</td> 
   <td>event.pagename</td> 
   <td>für AA</td> 
   <td>String</td> 
   <td> </td> 
   <td>Adobe Analytics-Unterstützung für benutzerdefinierten Seitennamen</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>URL</td> 
   <td>event.url</td> 
   <td>optional</td> 
   <td>String</td> 
   <td> </td> 
   <td>URL der Webeigenschaft oder des Mobilschemas - muss vollständig qualifizierte URL enthalten</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Error Code</td> 
   <td>event.error_code</td> 
   <td> </td> 
   <td>String</td> 
   <td> </td> 
   <td>Fehlercode</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Fehlertyp</td> 
   <td>event.error_type</td> 
   <td> </td> 
   <td>String</td> 
   <td> </td> 
   <td>Fehlertyp</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Fehlerbeschreibung</td> 
   <td>event.error_description</td> 
   <td> </td> 
   <td>String</td> 
   <td> </td> 
   <td>Fehlerbeschreibung<br /> </td> 
  </tr>
  <tr>
   <td><strong><em>Quelle/Ursprungserzeugnis</em></strong></td> 
   <td>Name</td> 
   <td>source.name</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>App-Name (AEM Screens)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Version</td> 
   <td>source.version</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>Firmware-Version</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Plattform</td> 
   <td>source.platform</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>navigator.platform</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Gerät</td> 
   <td>source.device</td> 
   <td>Erforderliche ohne Ausnahmen</td> 
   <td>String</td> 
   <td> </td> 
   <td>Player-Name</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Betriebssystemversion</td> 
   <td>source.os_version</td> 
   <td>Erforderliche ohne Ausnahmen</td> 
   <td>String</td> 
   <td> </td> 
   <td>O/S-Version</td> 
  </tr>
  <tr>
   <td><strong><em>Inhalt</em></strong></td> 
   <td>Aktion</td> 
   <td>content.action</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>Die URL zum Asset, einschließlich der tatsächlich wiedergegebenen Darstellung</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Mime Type</td> 
   <td>content.mimetype</td> 
   <td>optional</td> 
   <td>String</td> 
   <td> </td> 
   <td>Mime-Typ des Inhalts</td> 
  </tr>
  <tr>
   <td><strong><em>Transaktion</em></strong></td> 
   <td>Transaktionsnummer</td> 
   <td>trn.number</td> 
   <td>required</td> 
   <td>String</td> 
   <td>UUID</td> 
   <td>Eindeutige ID, die vorzugsweise UUID v4 entspricht</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Produktbeschreibung</td> 
   <td>trn.product</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>Die URL zum Asset (ohne Darstellung)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Menge</td> 
   <td>trn.quantity</td> 
   <td>required</td> 
   <td>String</td> 
   <td> </td> 
   <td>Die Dauer der Wiedergabe</td> 
  </tr>
 </tbody>
</table>

