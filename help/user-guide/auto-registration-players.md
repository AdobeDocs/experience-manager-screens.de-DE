---
title: Automatische Registrierung von Playern
description: Auf dieser Seite erfahren Sie mehr über die automatische Registrierung von Playern mit AMS/On-Premise Screens.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 28449523-a44d-4260-9771-f1987686cbb6
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 49%

---

# Automatische Registrierung von Playern {#auto-registration}

Die Massenregistrierung Tausender Player kann mühsam werden und Zeit und Kosten verursachen. Um diesen Prozess zu vereinfachen, können Sie mit der Massenregistrierungsfunktion einen vorab freigegebenen Schlüssel in AEM angeben, der entweder über eine Konfigurationsdatei oder eine MDM-Lösung (Mobile Device Management) für einen Player bereitgestellt werden kann.

## Implementieren der automatischen Registrierung von Playern {#bulk-registering-implementation}

Führen Sie die folgenden Schritte aus, um die automatische Registrierung von Playern zu implementieren:

1. Melden Sie sich bei Ihrer AEM-Instanz an, wählen Sie Ihr AEM Screens-Projekt aus und klicken Sie auf **Eigenschaften** in der Aktionsleiste aus.
1. Wählen Sie die **Erweitert** Registerkarte , auf der Sie die **Geräteregistrierung** -Abschnitt.

1. Geben Sie im Feld **Bulk registration code** (Massenregistrierungs-Code) einen Code für die automatische Registrierung und in **Default display assignment** (Standardmäßige Anzeigenzuweisung) eine optionale Standardanzeige an, die dem Player zugewiesen werden soll, der automatisch registriert wird.

   >[!NOTE]
   >Geben Sie einen Code Ihrer Wahl ein und wählen Sie bei Bedarf eine Standardanzeige aus.

   ![image](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Stellen Sie Ihren Playern die entsprechende Server-URL und den Registrierungs-Code mithilfe einer MDM- oder Konfigurations-JSON-Datei zur Verfügung.

   >[!NOTE]
   >Weitere Informationen finden Sie auf der Implementierungsseite für den jeweiligen Player für Ihr Betriebssystem. Sie können die Admin-Benutzeroberfläche auch zur Eingabe des Registrierungs-Codes verwenden.

1. Wenn die `registrationKey` das Attribut mit dem in AEM konfigurierten übereinstimmt, registriert sich der Player automatisch selbst und wenn eine Standardanzeige konfiguriert ist, lädt dieser Inhalt herunter und wird wiedergegeben.

   ![Bild](/help/user-guide/assets/auto-registration/auto-register2.png)

## Best Practices für die Sicherheit {#security-best-practices}

Im folgenden Abschnitt finden Sie einige der Best Practices für die Sicherheit:

* Stellen Sie sicher, dass der Registrierungs-Code nicht kompromittiert wird: Konfigurieren Sie den Code in AEM, unmittelbar bevor Sie mit der Massenregistrierung beginnen. Löschen Sie anschließend dieses Feld, und speichern Sie ihn in AEM.

* Sie können den Pfad `/bin/screens/registration` so konfigurieren, dass er nur aus bekannten IP-Bereichen zugänglich ist, wenn möglich.

* Erwägen Sie die Verwendung eines MDM, um dem Player die Konfiguration bereitzustellen.

* Verwenden Sie immer `HTTPS` und nicht `HTTP` für die Player-Kommunikation mit AEM.

  >[!NOTE]
  >Die standardmäßige Anzeigenzuweisung funktioniert derzeit nur für die Massenregistrierung und nicht für die manuelle Registrierung ohne Registrierungs-Code.
