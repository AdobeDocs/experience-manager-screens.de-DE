---
title: Automatische Registrierung von Spielern
seo-title: Automatische Registrierung von Spielern
description: Folgen Sie dieser Seite, um mehr über die automatische Registrierung von Spielern mit AMS/On-Prem-Bildschirmen zu erfahren.
translation-type: tm+mt
source-git-commit: f94eac66b6372e9f3e4cfc28693c4ba61d1b9ab1
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Automatische Registrierung von Spielern {#auto-registration}

Bulk Registering Tausenden von Playern manuell kann sehr schwerfällig werden und zusätzliche Zeit und Kosten. Um diesen Vorgang zu vereinfachen, können Sie mit der Massenregistrierungsfunktion einen vorab freigegebenen Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

## Implementierung der automatischen Registrierung von Spielern {#bulk-registering-implementation}

Gehen Sie wie folgt vor, um die automatische Registrierung von Playern zu implementieren:

1. Melden Sie sich bei Ihrer AEM an, wählen Sie Ihr AEM-Screenprojekt aus und klicken Sie auf Eigenschaften und die Registerkarte Erweitert.
1. Sie sollten einen Abschnitt zur Massenregistrierung sehen, in dem Sie einen Massenregistrierungscode und eine optionale Standardanzeige angeben können, die dem Player, der als Massenregistrierter fungiert, zugewiesen werden soll
1. Geben Sie einen Code Ihrer Wahl ein und wählen Sie bei Bedarf eine Standardanzeige aus.
1. Stellen Sie Ihren Playern die entsprechende Server-URL und den Registrierungscode mit einer MDM- oder Konfigurations-JSON-Datei zur Verfügung. Genauere Informationen finden Sie auf der Implementierungsseite für den jeweiligen Player für Ihr Betriebssystem. Sie können die Admin-Benutzeroberfläche auch zur Eingabe des Registrierungscodes verwenden.
1. Wenn das `registrationKey`-Attribut mit dem in AEM konfigurierten Attribut übereinstimmt, registriert sich der Player automatisch, und wenn eine Standardanzeige konfiguriert ist, wird dieser Inhalt heruntergeladen und abgespielt.

## Best Practices für die Sicherheit {#security-best-practices}

Befolgen Sie den folgenden Abschnitt, um einige der Best Practices für die Sicherheit zu erwägen:

* Um sicherzustellen, dass der Registrierungscode nicht beschädigt wird, konfigurieren Sie den Code in AEM, bevor Sie die Massenregistrierung starten. Wenn Sie fertig sind, löschen Sie bitte dieses Feld und speichern Sie AEM.

* Sie können konfigurieren, dass der Pfad `/bin/screens/`Registrierung nur von bekannten IP-Bereichen aus aufgerufen werden kann, wenn dies möglich ist.

* Erwägen Sie die Verwendung eines MDM, um dem Player die Konfiguration bereitzustellen.

* Verwenden Sie immer `HTTPS` und nicht `HTTP` für die Player-Kommunikation mit AEM.

   >[!NOTE]
   >Die Standardzuweisung zur Anzeige funktioniert derzeit nur bei der Massenregistrierung und nicht bei der manuellen Registrierung ohne Registrierungscode.