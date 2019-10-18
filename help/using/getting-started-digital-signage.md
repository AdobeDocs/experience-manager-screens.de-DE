---
title: Grundlagen der digitalen Signatur für [!UICONTROL AEM-Bildschirme]
seo-title: Grundlagen der digitalen Signatur für [!UICONTROL AEM-Bildschirme]
description: Das Handbuch beschreibt die Grundlagen eines Projekts zur digitalen Signage
seo-description: Das Handbuch beschreibt die Grundlagen eines Projekts zur digitalen Signage
translation-type: tm+mt
source-git-commit: 30c724ea897fd2da5300bb5cad285d460af5de40

---


# Grundlagen eines Digital Signage-Projekts {#basics-digital-signage}

Bevor Sie sich mit den Best Practices für die Implementierung von AEM Screens vertraut machen, sollten Sie sich das Projekt nicht als herkömmliche Softwareentwicklung, sondern als Digitalsignaturprojekt vorstellen.

Dieser Abschnitt enthält Empfehlungen zu wichtigen Elementen, die vor der Implementierung eines AEM Screens-Projekts entscheidend sind.

## Schlüsselelemente der digitalen Signatur {#key-elements}

Die *Schlüsselelemente* eines Projekts zur digitalen Signatur sind:

![](/help/assets/Elements-Revised.png)

Die Definition der Schlüsselelemente ist vor der Implementierung eines digitalen Signage-Projekts unverzichtbar:

1. **Hardware**

   Die Hardware definiert, welche Hardwarekomponenten für die Implementierung des Digital Signage-Projekts geeignet sind:
   * Verfügt das Gerät über genügend Speicherplatz, um alle Varianten des Erlebnisses offline ausführen zu können?
   * Haben wir Videokabel-Typ und -Länge zugelassen? Unterstützt das Gerät beide gewünschten Auflösungen (HD, FullHD, 4K usw.) und Video-Codecs, die ich bereitstellen möchte (h.264, h.265 usw.)
   * Verwendung von Kupferdraht
   * Bildschirmgröße
   * Anzahl Bildschirme
      * orientation
      * Seitenverhältnis
      * Auflösungseinstellung

1. **Konnektivität**

   Konnektivität betont die folgenden Fragen:
   * Networked (cell oder wi-fi) oder standalone?
      * Müssen wir Updates für USB-Inhalte zulassen?
      * Müssen wir die Erfassung von Nutzungsdaten zulassen?

1. **Installation**

   Die Installation umfasst:
   * Zeigt: Querformat oder Hochformat
   * Wie wird der Bildschirm gemountet?
      * Hochformat oder Querformat
      * Volle Wohnung
      * Abdeckplatte
   * Fixierunterstützung
   * Personal: für die Installation und den Anschluss des Geräts an das Netzwerk verantwortlich
   * Wie weit ist die Stromquelle von der Vorrichtung entfernt?
   * Wie weit ist die physische Leiste vom eigentlichen Gerät entfernt?

1. **Inhalt**

   Der Inhalt umfasst:
   * Einzel- oder Mehrzonen?
      * Wie viele Medienelemente befinden sich gleichzeitig auf dem Bildschirm?
      * Wie viele Seiten für interaktive Anwendungen?
      * Definieren der UI-Schleife
      * Datengesteuerter Inhalt?
   * Versionssteuerung

1. **interaktiv**

   Interaktiv:
   * Bevorzugter Touchscreen-Typ?(resistive, kapazitive, multi-touch)?
      * Tastendruck
      * Geste
   * Datenauslösung (I/O)?
      * Senden/Empfangen von seriellen Befehlen (Kontaktschließung, PLC usw.)
      * Eingehende Daten werden auf dem Bildschirm (RSS) angezeigt oder lösen Inhalte aus
      * RFID/NFC/Bluetooth/iBeacon
      * Externe Dienstleistungen (Wetter, Verkehr usw.)

1. **Umgebung**

   Die Umwelt betont Folgendes:
   * Anzeigeposition?
      * Inside vs. Outside
      * Unerreichbar oder direkt exponiert
   * Spezielle Anforderungen an Temp?
   * Vandal-Beweis?
   * Hohe Umgebungslicht? Starke Kontraste?

1. **Wartung**

   Die Wartung konzentriert sich auf:

   * Sind detaillierte Installationsanleitungen/Benutzerhandbücher erforderlich?
   * Konfigurieren (programmieren) wir das Gerät vor dem Versand?
   * Müssen wir jede Seriennummer zu Tracking-Zwecken erfassen?
   * Gibt es Reserveanforderungen an die Stromversorgung (unterbrechungsfreie Stromversorgung)?
   * Wie werden Systemaktualisierungen bereitgestellt? Und wie werden Geräte remote überwacht? Ist eine MDM-Lösung erforderlich?
