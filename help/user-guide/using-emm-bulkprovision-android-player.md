---
title: Verwenden von MDM oder EMM zur Bereitstellung von Android Player als Massenspeicher
seo-title: Massenbereitstellung von Android Player mit EMM oder MDM
description: Auf dieser Seite erfahren Sie mehr über die Massenbereitstellung von Android Player mit EMM oder MDM
translation-type: tm+mt
source-git-commit: 793507b266b99051544b377e4a7effb92dc6feb6
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# Massenbereitstellung von Android Player mit Enterprise Mobility Management {#bulk-provisioning}

Bei der Massenbereitstellung des Android-Players wird es mühsam, jeden einzelnen Player manuell mit AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) wie VMWare Airwatch, MobileIron oder Samsung Knox zu verwenden, um Ihre Bereitstellung remote bereitzustellen und zu verwalten. AEM Screens Android Player unterstützt den Branchenstandard EMM AppConfig, um die Bereitstellung per Remote-Zugriff zu ermöglichen.

## Implementierung der Massenbereitstellung von Android Player mithilfe von Enterprise Mobility Management {#implementation}

Gehen Sie wie folgt vor, um die Massenbereitstellung in Android Player zuzulassen:

1. Stellen Sie sicher, dass Ihr Android-Gerät Google Play-Dienste unterstützt.
1. Registrieren Sie Ihre Android-Player-Geräte mit Ihrer bevorzugten EMM-Lösung, die AppConfig unterstützt.
1. Melden Sie sich bei Ihrer EMM-Konsole an und rufen Sie die AEM Screens Player-Anwendung von Google Play ab.
1. Wählen Sie die verwaltete Konfiguration (oder die zugehörige Option).
1. Sie sollten nun eine Liste der Player-Optionen sehen, die konfiguriert werden können (z. B. Server- und Massenregistrierungscode).
1. Konfigurieren Sie diese Parameter, speichern Sie die Richtlinie und stellen Sie sie auf den Geräten bereit.

   >[!NOTE]
   >Die Geräte sollten die Anwendung zusammen mit der Konfiguration empfangen und mit der ausgewählten Konfiguration auf den richtigen AEM Server verweisen. Wenn Sie sich dafür entschieden haben, den Massenregistrierungscode zu konfigurieren und ihn so wie in AEM konfiguriert zu halten, sollte der Player automatisch in der Lage sein, sich selbst zu registrieren. Wenn Sie eine Standardanzeige konfiguriert haben, können Sie auch einige Standardinhalte herunterladen und anzeigen (die später nach Belieben geändert werden können).

Darüber hinaus sollten Sie sich mit Ihrem EMM-Anbieter über die AppConfig-Unterstützung in Verbindung setzen. Am häufigsten werden solche Programme wie [VMWare Airwatch](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [Mobile Iron](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [SOTI](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [Blackberry UEM](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [IBM Maas360](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm) und [Samsung Knox&lt;a101000000000000000000000000000000000000000000000000000000000000000000000000 11/> unterstützen unter anderem diesen Industriestandard.](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm)

