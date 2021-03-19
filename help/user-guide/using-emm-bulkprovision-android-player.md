---
title: Verwenden von MDM oder EMM zur Massenbereitstellung von Android-Playern
seo-title: Massenbereitstellung von Android-Playern mit EMM oder MDM
description: Auf dieser Seite erfahren Sie mehr über die Massenbereitstellung von Android-Playern mit EMM oder MDM.
translation-type: ht
source-git-commit: 793507b266b99051544b377e4a7effb92dc6feb6
workflow-type: ht
source-wordcount: '334'
ht-degree: 100%

---


# Massenbereitstellung von Android-Playern mit Enterprise Mobility Management {#bulk-provisioning}

Bei der Massenbereitstellung von Android-Playern ist es mühsam, jeden einzelnen Player manuell bei AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) wie VMWare Airwatch, MobileIron oder Samsung Knox für die Remote-Bereitstellung und -Verwaltung Ihrer Bereitstellung zu verwenden. Der AEM Screens-Android-Player unterstützt den Branchenstandard EMM AppConfig, um eine Remote-Bereitstellung zu ermöglichen.

## Implementieren der Massenbereitstellung des Android-Players mit Enterprise Mobility Management {#implementation}

Gehen Sie wie folgt vor, um die Massenbereitstellung im Android-Player zuzulassen:

1. Stellen Sie sicher, dass Ihr Android-Gerät die Google Play-Services unterstützt.
1. Registrieren Sie Ihre Android-Player-Geräte bei Ihrer bevorzugten EMM-Lösung, die AppConfig unterstützt.
1. Melden Sie sich bei Ihrer EMM-Konsole an und rufen Sie das AEM Screens Player-Programm von Google Play ab.
1. Wählen Sie die verwaltete Konfiguration (oder die zugehörige Option) aus.
1. Sie sollten nun eine Liste der Player-Optionen sehen, die konfiguriert werden können (z. B. Server und Massenregistrierungs-Code).
1. Konfigurieren Sie diese Parameter, speichern Sie sie und stellen Sie die Richtlinie auf den Geräten bereit.

   >[!NOTE]
   >Die Geräte sollten das Programm zusammen mit der Konfiguration empfangen und auf den richtigen AEM-Server mit der ausgewählten Konfiguration verweisen. Wenn Sie den Massenregistrierungs-Code konfiguriert haben und ihn so belassen haben, wie er in AEM konfiguriert wurde, sollte sich der Player automatisch registrieren können. Wenn Sie eine Standardanzeige konfiguriert haben, kann er auch einige Standardinhalte herunterladen und anzeigen (die später nach Ihren Wünschen geändert werden können).

Darüber hinaus sollten Sie sich bei Ihrem EMM-Anbieter nach der AppConfig-Unterstützung erkundigen. Die meisten gängigen Anbieter wie [VMWare Airwatch](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [Mobile Iron](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [SOTI](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [Blackberry UEM](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [IBM Maas360](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm) und [Samsung Knox](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) unterstützen diesen Industriestandard.


