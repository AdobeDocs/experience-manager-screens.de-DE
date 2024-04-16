---
title: Automatische Registrierung von Playern
description: Auf dieser Seite erfahren Sie mehr über die automatische Registrierung von Playern mit AMS/On-Premise Screens.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 28449523-a44d-4260-9771-f1987686cbb6
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 45%

---

# Automatische Registrierung von Playern {#auto-registration}

Das manuelle Registrieren von Tausenden von Playern kann umständlich werden und Zeit und Kosten erhöhen. Um diesen Prozess zu vereinfachen, können Sie mit der Massenregistrierung einen vorab freigegebenen Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

## Implementieren der automatischen Registrierung von Playern {#bulk-registering-implementation}

Führen Sie die folgenden Schritte aus, um die automatische Registrierung von Playern zu implementieren:

1. Melden Sie sich bei Ihrer AEM-Instanz an, klicken Sie auf Ihr AEM Screens-Projekt und klicken Sie auf **Eigenschaften** in der Aktionsleiste aus.
1. Klicken Sie auf **Erweitert** -Registerkarte, damit Sie die **Geräteregistrierung** Abschnitt.

1. Geben Sie im Feld **Bulk registration code** (Massenregistrierungs-Code) einen Code für die automatische Registrierung und in **Default display assignment** (Standardmäßige Anzeigenzuweisung) eine optionale Standardanzeige an, die dem Player zugewiesen werden soll, der automatisch registriert wird.

   >[!NOTE]
   >Geben Sie einen Code Ihrer Wahl ein und klicken Sie bei Bedarf auf eine Standardanzeige.

   ![image](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Stellen Sie Ihren Playern die entsprechende Server-URL und den Registrierungs-Code mithilfe einer MDM- oder Konfigurations-JSON-Datei zur Verfügung.

   >[!NOTE]
   >Weitere Informationen finden Sie auf der Implementierungsseite für den jeweiligen Player für Ihr Betriebssystem. Sie können die Admin-Benutzeroberfläche auch zur Eingabe des Registrierungs-Codes verwenden.

1. Wenn die Variable `registrationKey` -Attribut mit dem in AEM konfigurierten Attribut übereinstimmt, registriert sich der Player automatisch. Wenn eine Standardanzeige konfiguriert ist, wird dieser Inhalt heruntergeladen und wiedergegeben.

   ![Bild](/help/user-guide/assets/auto-registration/auto-register2.png)

## Best Practices für die Sicherheit {#security-best-practices}

Im folgenden Abschnitt finden Sie einige der Best Practices für die Sicherheit:

* Stellen Sie sicher, dass der Registrierungs-Code nicht kompromittiert ist: Konfigurieren Sie den Code in AEM unmittelbar vor dem Start der Massenregistrierung. Wenn Sie fertig sind, löschen Sie dieses Feld und speichern Sie in AEM.

* Sie können den Pfad `/bin/screens/registration` so konfigurieren, dass er nur aus bekannten IP-Bereichen zugänglich ist, wenn möglich.

* Erwägen Sie die Verwendung eines MDM, um dem Player die Konfiguration bereitzustellen.

* Verwenden Sie immer `HTTPS` und nicht `HTTP` für die Player-Kommunikation mit AEM.

  >[!NOTE]
  >Die standardmäßige Anzeigenzuweisung funktioniert derzeit nur für die Massenregistrierung und nicht für die manuelle Registrierung ohne Registrierungs-Code.
