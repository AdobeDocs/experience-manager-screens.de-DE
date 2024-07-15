---
title: Automatische Registrierung von Playern
description: Auf dieser Seite erfahren Sie mehr über die automatische Registrierung von Playern mit AMS/On-Premise Screens.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 28449523-a44d-4260-9771-f1987686cbb6
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 100%

---

# Automatische Registrierung von Playern {#auto-registration}

Die manuelle Massenregistrierung von Tausenden von Playern kann mühsam sein und zusätzliche Zeitanforderungen und Kosten verursachen. Um diesen Prozess zu vereinfachen, können Sie mit der Massenregistrierungsfunktion einen vorinstallierten Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

## Implementieren der automatischen Registrierung von Playern {#bulk-registering-implementation}

Führen Sie die folgenden Schritte aus, um die automatische Registrierung von Playern zu implementieren:

1. Melden Sie sich bei Ihrer AEM-Instanz an, wählen Sie Ihr AEM Screens-Projekt aus und klicken Sie in der Aktionsleiste auf **Eigenschaften**.
1. Klicken Sie auf die Registerkarte **Erweitert**, um den Abschnitt **Geräteregistrierung** anzuzeigen.

1. Geben Sie im Feld **Massenregistrierungs-Code** einen Code für die automatische Registrierung ein. Legen Sie anschließend unter **Standardanzeigezuweisung** eine optionale Standardanzeige fest, der dem automatisch registrierten Player zugewiesen werden soll.

   >[!NOTE]
   >Geben Sie einen Code Ihrer Wahl ein und klicken Sie bei Bedarf auf eine Standardanzeige.

   ![image](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Stellen Sie Ihren Playern die entsprechende Server-URL und den Registrierungs-Code mithilfe einer MDM- oder Konfigurations-JSON-Datei zur Verfügung.

   >[!NOTE]
   >Weitere Informationen finden Sie auf der Implementierungsseite des jeweiligen Players für Ihr Betriebssystem. Sie können die Admin-Benutzeroberfläche auch zur Eingabe des Registrierungs-Codes verwenden.

1. Wenn das `registrationKey`-Attribut mit dem in AEM konfigurierten Attribut übereinstimmt, registriert sich der Player automatisch. Wenn eine Standardanzeige konfiguriert ist, wird dieser Inhalt heruntergeladen und wiedergegeben.

   ![Bild](/help/user-guide/assets/auto-registration/auto-register2.png)

## Best Practices für die Sicherheit {#security-best-practices}

Im folgenden Abschnitt finden Sie einige der Best Practices für die Sicherheit:

* Um sicherzustellen, dass der Registrierungs-Code nicht kompromittiert wird, konfigurieren Sie den Code in AEM kurz vor dem Start der Massenregistrierung und löschen Sie das Feld, wenn Sie fertig sind.

* Sie können den Pfad `/bin/screens/registration` so konfigurieren, dass er nur über bekannte IP-Bereiche zugänglich ist, sofern möglich.

* Erwägen Sie die Verwendung eines MDM, um dem Player die Konfiguration bereitzustellen.

* Verwenden Sie immer `HTTPS` und nicht `HTTP` für die Player-Kommunikation mit AEM.

  >[!NOTE]
  >Die Standardanzeigezuweisung funktioniert derzeit nur bei der Massenregistrierung. Sie kann nicht für manuelle Registrierungen verwendet werden, wenn kein Registrierungs-Code verfügbar ist.
