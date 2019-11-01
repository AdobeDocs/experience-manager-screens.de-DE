---
title: Grundlagen von Digital Signage für [!UICONTROL AEM Screens]
seo-title: Grundlagen von Digital Signage für [!UICONTROL AEM Screens]
description: In diesem Handbuch werden die Grundlagen eines Digital Signage-Projekts beschrieben.
seo-description: In diesem Handbuch werden die Grundlagen eines Digital Signage-Projekts beschrieben.
translation-type: ht
source-git-commit: 30c724ea897fd2da5300bb5cad285d460af5de40

---


# Grundlagen eines Digital Signage-Projekts {#basics-digital-signage}

Bevor Sie sich mit Best Practices für die Implementierung von AEM Screens vertraut machen, sollten Sie sich das Projekt als Digital Signage-Projekt vorstellen – und nicht als herkömmliche Softwareentwicklung.

Dieser Abschnitt enthält Empfehlungen zu wichtigen Elementen, die vor der Implementierung eines AEM Screens-Projekts beachtet werden müssen.

## Schlüsselelemente von Digital Signage {#key-elements}

Die *Schlüsselelemente* eines Digital Signage-Projekts sind:

![](/help/assets/Elements-Revised.png)

Ein Definieren der Schlüsselelemente ist vor Implementierung eines Digital Signage-Projekts unerlässlich:

1. **Hardware**

   Die Hardware bestimmt darüber, welche Hardwarekomponenten sich zur Implementierung Ihres Digital Signage-Projekts eignen:
   * Verfügt das Gerät über ausreichend Speicherplatz, um alle Varianten der Erlebnisse offline ausführen zu können?
   * Wurden Art und Länge der Videokabel berücksichtigt? Unterstützt das Gerät sowohl die gewünschten Auflösungen (HD, FullHD, 4K usw.) als auch die bereitzustellenden Videocodecs (h.264, h.265 usw.)?
   * Einsatz von Kupferleitungen
   * Größe der Bildschirme
   * Anzahl der Bildschirme
      * Ausrichtung
      * Seitenverhältnis
      * Voreingestellte Auflösung

1. **Konnektivität**

   Beim Thema Konnektivität geht es um folgende Fragen:
   * Vernetzt (per Mobilfunk oder WLAN) bzw. eigenständig?
      * Müssen Inhaltsaktualisierungen über USB möglich sein?
      * Muss eine Erfassung von Nutzungsdaten möglich sein?

1. **Installation**

   Die Installation umfasst:
   * Displays: Querformat oder Hochformat
   * Wie wird der Bildschirm befestigt?
      * Hochformat oder Querformat
      * Komplettes Gehäuse
      * Abdeckplatte
   * Halterung
   * Personal: verantwortlich für Installation und Anschluss des Geräts an das Netzwerk
   * Wie weit ist die Stromquelle vom Gerät entfernt?
   * Wie weit ist das physische Bedienfeld vom betreffenden Gerät entfernt?

1. **Inhalt**

   Inhalt umfasst:
   * eine oder mehrere Zonen?
      * Wie viele Medien-Assets befinden sich gleichzeitig auf dem Bildschirm?
      * Wie viele Seiten für interaktive Anwendungen?
      * Definieren der UI-Schleife
      * Datengesteuerter Inhalt?
   * Versionskontrolle

1. **Interaktives**

   Interaktives beinhaltet:
   * bevorzugter Touchscreen? (resistiv, kapazitiv, Multi-Touch)
      * Tastendruck
      * Geste
   * Datenauslösung (I/O)?
      * Senden/Empfangen von seriellen Befehlen (Schließen von Kontakt, PLC usw.)
      * Eingehende Daten werden auf dem Bildschirm angezeigt (RSS) oder lösen Inhalt aus
      * RFID/NFC/Bluetooth/iBeacon
      * Externe Dienste (Wetter, Verkehr usw.)

1. **Umgebung**

   Bei der Umgebung geht es um Folgendes:
   * Displaystandort?
      * Drinnen vs. draußen
      * Unerreichbar oder direkter Kontakt
   * Spezielle Temperaturbedingungen?
   * Schutz vor Vandalismus?
   * Starkes Umgebungslicht? Starke Kontraste?

1. **Wartung**

   Bei der Wartung geht es um Folgendes:

   * Werden detaillierte Installationsanleitungen/Benutzerhandbücher benötigt?
   * Wird das Gerät vor dem Versand konfiguriert (programmiert)?
   * Müssen die einzelnen Seriennummern zu Verfolgungszwecken erfasst werden?
   * Gibt es Bedarf an einer Stromversorgungsreserve (unterbrechungsfreie Stromversorgung)?
   * Wie werden Systemaktualisierungen implementiert? Und wie werden Geräte remote überwacht? Ist eine MDM-Lösung erforderlich?
