---
title: Grundlagen von Digital Signage für [!UICONTROL AEM Screens]
description: Erfahren Sie mehr über die Grundlagen eines Digital Signage-Projekts.
exl-id: e3913be2-9028-4773-a034-e16924a71e04
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 98%

---

# Grundlagen eines Digital Signage-Projekts {#basics-digital-signage}

Bevor Sie sich mit Best Practices für die Implementierung von AEM Screens vertraut machen, sollten Sie sich das Projekt als Digital-Signage-Projekt vorstellen – und nicht als herkömmliche Softwareentwicklung.

Dieser Abschnitt enthält Empfehlungen zu wichtigen Elementen, die vor der Implementierung eines AEM Screens-Projekts beachtet werden müssen.

## Schlüsselelemente von Digital Signage {#key-elements}

Die *Schlüsselelemente* eines Digital-Signage-Projekts sind:

![](/help/assets/Elements-Revised.png)

Ein Definieren der Schlüsselelemente ist vor Implementierung eines Digital-Signage-Projekts unerlässlich:

1. **Hardware**

   Die Hardware bestimmt darüber, welche Hardwarekomponenten sich zur Implementierung Ihres Digital-Signage-Projekts eignen:
   * Verfügt das Gerät über ausreichend Speicherplatz, um alle Varianten der Erlebnisse offline ausführen zu können?
   * Wurden Art und Länge der Videokabel berücksichtigt? Unterstützt das Gerät sowohl die gewünschten Auflösungen (HD, FullHD, `4K`) und Video-Codecs, die ich bereitstellen möchte (h.264, h.265 )?
   * Einsatz von Kupferleitungen
   * Größe der Bildschirme
   * Anzahl der Bildschirme
      * Ausrichtung
      * Seitenverhältnis
      * Voreingestellte Auflösung

1. **Konnektivität**

   Die Konnektivität wirft folgende Fragen auf:
   * Vernetzt (per Mobilfunk oder WLAN) bzw. eigenständig?
      * Müssen Sie Aktualisierungen von USB-Inhalten zulassen?
      * Müssen Sie die Erfassung von Nutzungsdaten zulassen?

1. **Installation**

   Die Installation umfasst:
   * Displays: Querformat oder Hochformat
   * Wie wird der Bildschirm montiert?
      * Ausrichtung im Hochformat im Vergleich zur Ausrichtung im Querformat
      * Komplettes Gehäuse
      * Abdeckplatte
   * Halterung
   * Personal: verantwortlich für Installation und Anschluss des Geräts an das Netzwerk
   * Wie weit ist die Stromquelle vom Gerät entfernt?
   * Wie weit ist das physische Bedienfeld vom betreffenden Gerät entfernt?

1. **Inhalt**

   Inhalt umfasst:
   * Einzelzone oder Mehrzonen?
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
      * Senden/Empfangen von seriellen Befehlen (Schließen von Kontakt und PLC)
      * Eingehende Daten werden auf dem Bildschirm angezeigt (RSS) oder lösen Inhalt aus
      * RFID/NFC/Bluetooth/iBeacon
      * Externe Services (Wetter, Verkehr)

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

   * Sind Installationsanleitungen und Benutzerhandbücher erforderlich?
   * Konfigurieren (programmieren) Sie das Gerät vor dem Versand?
   * Müssen Sie jede Seriennummer zu Tracking-Zwecken erfassen?
   * Gibt es Bedarf an einer Reservestromversorgung (unterbrechungsfreien Stromversorgung)?
   * Wie werden Systemaktualisierungen bereitgestellt? Und wie werden Geräte remote überwacht? Ist eine MDM-Lösung erforderlich?
