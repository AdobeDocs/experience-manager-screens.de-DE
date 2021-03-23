---
title: Automatische Registrierung von Playern
seo-title: Automatische Registrierung von Playern
description: Auf dieser Seite erfahren Sie mehr über die automatische Registrierung von Playern mit AMS/On-Premise Screens.
feature: Verwaltungsbildschirme, Player
role: 'Administrator  '
level: Zwischenschaltung
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 98%

---


# Automatische Registrierung von Playern {#auto-registration}

Die manuelle Massenregistrierung von Tausenden von Playern kann sehr mühsam sein und zusätzliche Zeitanforderungen und Kosten verursachen. Um diesen Prozess zu vereinfachen, können Sie mit der Massenregistrierungsfunktion einen vorinstallierten Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

## Implementieren der automatischen Registrierung von Playern {#bulk-registering-implementation}

Führen Sie die folgenden Schritte aus, um die automatische Registrierung von Playern zu implementieren:

1. Melden Sie sich bei Ihrer AEM-Instanz an, wählen Sie Ihr AEM Screens-Projekt aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.
1. Wählen Sie die Registerkarte **Erweitert** aus, um den Abschnitt **Geräteregistrierung** anzuzeigen.

1. Geben Sie im Feld **Bulk registration code** (Massenregistrierungs-Code) einen Code für die automatische Registrierung und in **Default display assignment** (Standardmäßige Anzeigenzuweisung) eine optionale Standardanzeige an, die dem Player zugewiesen werden soll, der automatisch registriert wird.
   >[!NOTE]
   >Geben Sie einen Code Ihrer Wahl ein und wählen Sie bei Bedarf eine Standardanzeige aus.

   ![image](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Stellen Sie Ihren Playern die entsprechende Server-URL und den Registrierungs-Code mithilfe einer MDM- oder Konfigurations-JSON-Datei zur Verfügung.

   >[!NOTE]
   >Weitere Informationen finden Sie auf der Implementierungsseite des jeweiligen Players für Ihr Betriebssystem. Sie können die Admin-Benutzeroberfläche auch zur Eingabe des Registrierungs-Codes verwenden.

1. Wenn das `registrationKey`-Attribut mit dem in AEM konfigurierten Attribut übereinstimmt, registriert sich der Player automatisch. Wenn eine Standardanzeige konfiguriert ist, wird dieser Inhalt heruntergeladen und wiedergegeben.

   ![image](/help/user-guide/assets/auto-registration/auto-register2.png)

## Best Practices für die Sicherheit {#security-best-practices}

Im folgenden Abschnitt finden Sie einige der Best Practices für die Sicherheit:

* Um sicherzustellen, dass der Registrierungs-Code nicht kompromittiert wird, konfigurieren Sie den Code in AEM kurz vor dem Start der Massenregistrierung und löschen Sie das Feld, wenn Sie fertig sind.

* Sie können den Pfad `/bin/screens/registration` so konfigurieren, dass er nur aus bekannten IP-Bereichen zugänglich ist, wenn möglich.

* Erwägen Sie die Verwendung eines MDM, um dem Player die Konfiguration bereitzustellen.

* Verwenden Sie immer `HTTPS` und nicht `HTTP` für die Player-Kommunikation mit AEM.

   >[!NOTE]
   >Die standardmäßige Anzeigenzuweisung funktioniert derzeit nur für die Massenregistrierung und nicht für die manuelle Registrierung ohne Registrierungs-Code.