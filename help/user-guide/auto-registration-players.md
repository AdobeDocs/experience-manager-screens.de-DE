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
ht-degree: 62%

---

# Automatische Registrierung von Playern {#auto-registration}

Die manuelle Massenregistrierung von Tausenden von Playern kann mühsam sein und zusätzliche Zeitanforderungen und Kosten verursachen. Um diesen Prozess zu vereinfachen, können Sie mit der Massenregistrierungsfunktion einen vorinstallierten Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

## Implementieren der automatischen Registrierung von Playern {#bulk-registering-implementation}

Führen Sie die folgenden Schritte aus, um die automatische Registrierung von Playern zu implementieren:

1. Melden Sie sich bei Ihrer AEM-Instanz an, klicken Sie auf Ihr AEM Screens-Projekt und klicken Sie auf **Eigenschaften** in der Aktionsleiste aus.
1. Klicken Sie auf **Erweitert** -Registerkarte, damit Sie die **Geräteregistrierung** Abschnitt.

1. Geben Sie im Abschnitt **Massenregistrierungscode** -Feld. Anschließend wird eine optionale Standardanzeige in der **Standardmäßige Anzeigezuweisung** , um den Player zuzuweisen, der automatisch registriert ist.

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

* Sie können den Pfad konfigurieren `/bin/screens/registration` , damit sie nach Möglichkeit nur über bekannte IP-Bereiche zugänglich ist.

* Erwägen Sie die Verwendung eines MDM, um dem Player die Konfiguration bereitzustellen.

* Verwenden Sie immer `HTTPS` und nicht `HTTP` für die Player-Kommunikation mit AEM.

  >[!NOTE]
  >Die standardmäßige Anzeigezuweisung funktioniert derzeit nur bei der Massenregistrierung. Es funktioniert nicht für die manuelle Registrierung, wenn kein Registrierungscode verfügbar ist.
