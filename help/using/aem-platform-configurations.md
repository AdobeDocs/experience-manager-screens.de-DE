---
title: AEM-Plattformkonfigurationen
description: Auf dieser Seite werden AEM Platform-Konfigurationen beschrieben.
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 75%

---

# AEM-Plattformkonfigurationen {#platform-configurations}

>[!NOTE]
>
>Ein typischer Verantwortlicher für diese Aktivität ist ein AEM-Implementor.

Beginnen Sie mit AEM Screens, indem den Abschnitten unten folgen, um AEM-Plattformkonfigurationen einzurichten.

## Server-Konfigurationen {#server-configurations}

Informationen zum Einrichten von Server-Konfigurationen finden Sie unter [Server-Konfigurationen](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction#ServerConfiguration).

## Author-Publish {#author-publish}

Siehe [Konfigurieren von Author und Publish in AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish).

>[!NOTE]
>
>Wenn es nur einen Autor und eine Veröffentlichung gibt, können Sie nur die Schritte unter **Einrichten von Replikationsagenten auf der Autoreninstanz** in [Konfigurieren von Autoren- und Veröffentlichungsinstanz in AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish) Seite.

## Dispatcher-Konfigurationen {#dispatcher-configurations}

Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und den Lastenausgleich. Die Verwendung des AEM-Dispatchers trägt außerdem dazu bei, Ihren AEM-Server vor Angriffen zu schützen. Somit können Sie die Sicherheit Ihrer AEM-Instanz verbessern, indem Sie den Dispatcher in Verbindung mit einem Webserver der Unternehmensklasse verwenden.

Weitere Informationen dazu finden Sie unter **[Dispatcher-Konfigurationen für AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens)**. Hier finden Sie Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt.

## Installieren von FFMpeg- und Video-Ausgabedarstellungen {#installing-ffmpeg}

Installieren Sie FFmpeg gemäß den Schritten für das entsprechende Betriebssystem (normalerweise RHEL):

1. Bei Installation durch Aktivierung von EPEL und RPMFusion können Sie alle gstreamer-Codecs installieren, um die Unterstützung für FFmpeg-Konvertierungen zu erweitern.
1. Wenn der AAC-Codec als experimentell markiert ist, schlagen FFMpeg-Konvertierungen fehl. Um das zu verhindern, fügen Sie den Videoprofilen (/etc/dam/video in AEM 6.3 und /libs/settings/dam/video in AEM 6.4) `-strict -2` hinzu.

   >[!NOTE]
   >
   >`-strict -2` muss der letzte Parameter in der Parameterliste sein. Kopieren Sie außerdem in AEM 6.4 die Knoten unter */libs/settings/dam/video* nach */conf/global/settings/dam/video* gemäß [Videoausgaben](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/authoring/product-features/generating-renditions).
1. Prüfen Sie, ob Videokonvertierungen stattfinden und Ausgabedarstellungen erstellt werden.

## Kennworteinschränkungen {#password-restrictions}

Die Kennwortrichtlinie von AEM muss bei der AMS-Instanz deaktiviert sein. Es kann auch alternativ in der Web-Konsole mithilfe des Screens-Gerätedienstes konfiguriert werden. *com.adobe.cq.screens.device.impl.DeviceService*
Siehe **Kennwortbeschränkungen** Abschnitt in[Konfigurieren von Autoren- und Veröffentlichungsinstanz in AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish)

## Einrichten der Umgebungen {#setting-up-environments}

Installieren Sie die aktuellsten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager (AEM) und führen Sie sie aus:

* AEM Service Pack
* Screens Feature Pack
* AEM Cumulative Fix Pack

Ermitteln Sie außerdem alle erforderlichen Entwicklungspakete (z. B. zentrale
WCM-Komponenten) oder Toolkits von Drittanbietern (z. B. SAP Hybris).
Installieren Sie dieselben Softwarepakete in Ihrer lokalen Entwicklungsumgebung. Weisen Sie Ihren Client an, dieselbe Konfiguration auf allen QA-, Staging- und Produktions-Servern zu verwenden. Nicht übereinstimmende Server-Konfigurationen verursachen Probleme bei Bereitstellung und Tests.

>[!NOTE]
>
>Informationen zum Installieren des neuesten Feature Packs für AEM Screens finden Sie in den [Versionshinweisen](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/aem-screens-introduction).

## Einrichten von ACLs {#setting-up-acls}

Unter „Einrichten von ACLs“ wird erläutert, wie Sie Projekte separieren können, damit jede Person bzw. jedes Team ein eigenes Projekt erhält.

Siehe [Einrichten von ACLs](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/setting-up-acls) für weitere Details.
