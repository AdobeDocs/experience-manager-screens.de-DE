---
title: Automatische Registrierung von Spielern
seo-title: Automatische Registrierung von Spielern
description: Folgen Sie dieser Seite, um mehr über die automatische Registrierung von Spielern mit AMS/On-Prem-Bildschirmen zu erfahren.
translation-type: tm+mt
source-git-commit: 56432654d0895b892223677c8a03f10181864271
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---


# Automatische Registrierung von Spielern {#auto-registration}

Bulk Registering Tausenden von Playern manuell kann sehr schwerfällig werden und zusätzliche Zeit und Kosten. Um diesen Vorgang zu vereinfachen, können Sie mit der Massenregistrierungsfunktion einen vorab freigegebenen Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

## Implementierung der automatischen Registrierung von Spielern {#bulk-registering-implementation}

Gehen Sie wie folgt vor, um die automatische Registrierung von Playern zu implementieren:

1. Melden Sie sich bei Ihrer AEM an, wählen Sie Ihr AEM-Screenprojekt aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.
1. Klicken Sie auf die Registerkarte **Erweitert**, um den Abschnitt **Geräteregistrierung** Ansicht, wie unten dargestellt.

   ![image](/help/user-guide/assets/auto-registration/auto-register1.png)

1. Geben Sie im Feld **Massenregistrierungscode** einen Code für die automatische Registrierung und in der optionalen Standardanzeige unter **Standardmäßige Anzeigenzuweisung** einen Code für die automatische Registrierung an, der dem Player zugewiesen werden soll, der automatisch registriert ist.
   >[!NOTE]
   >Geben Sie einen Code Ihrer Wahl ein und wählen Sie bei Bedarf eine Standardanzeige aus.
1. Stellen Sie Ihren Playern die entsprechende Server-URL und den Registrierungscode mit einer MDM- oder Konfigurations-JSON-Datei zur Verfügung.

   >[!NOTE]
   >Weitere Informationen finden Sie auf der Implementierungsseite für den jeweiligen Player für Ihr Betriebssystem. Sie können die Admin-Benutzeroberfläche auch zur Eingabe des Registrierungscodes verwenden.

1. Wenn das `registrationKey`-Attribut mit dem in AEM konfigurierten Attribut übereinstimmt, registriert sich der Player automatisch, und wenn eine Standardanzeige konfiguriert ist, wird dieser Inhalt heruntergeladen und abgespielt.

   ![image](/help/user-guide/assets/auto-registration/auto-register2.png)

## Best Practices für die Sicherheit {#security-best-practices}

Befolgen Sie den folgenden Abschnitt, um einige der Best Practices für die Sicherheit zu erwägen:

* Um sicherzustellen, dass der Registrierungscode nicht beschädigt wird, konfigurieren Sie den Code in AEM, bevor Sie die Massenregistrierung starten. Wenn Sie fertig sind, löschen Sie bitte dieses Feld und speichern Sie AEM.

* Sie können konfigurieren, dass der Pfad `/bin/screens/`Registrierung nur von bekannten IP-Bereichen aus aufgerufen werden kann, wenn dies möglich ist.

* Erwägen Sie die Verwendung eines MDM, um dem Player die Konfiguration bereitzustellen.

* Verwenden Sie immer `HTTPS` und nicht `HTTP` für die Player-Kommunikation mit AEM.

   >[!NOTE]
   >Die Standardzuweisung zur Anzeige funktioniert derzeit nur bei der Massenregistrierung und nicht bei der manuellen Registrierung ohne Registrierungscode.