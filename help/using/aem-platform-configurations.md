---
title: AEM-Plattformkonfigurationen
description: Auf dieser Seite werden AEM Platform-Konfigurationen beschrieben.
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
TQID: https://experienceleague.adobe.com/qsJ-vj45WoTXXdBU5zsNQYoB7g4HnNTLwwfFSBL-wwI
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 592
ht-degree: 80%

---

# AEM-Plattformkonfigurationen {#platform-configurations}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

>[!NOTE]
>
>Ein typischer Stakeholder für diese Aktivität ist eine Person, die AEM implementiert.

Beginnen Sie mit AEM Screens, indem den Abschnitten unten folgen, um AEM-Plattformkonfigurationen einzurichten.

## Server-Konfigurationen {#server-configurations}

Informationen zum Einrichten von Server-Konfigurationen finden Sie unter [Server-Konfigurationen](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction#ServerConfiguration).

## Author-Publish {#author-publish}

Siehe [Konfigurieren von Author und Publish in AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish).

>[!NOTE]
>
>Wenn es nur je eine Autoren- und Veröffentlichungsinstanz gibt, können Sie auf der Seite [Konfigurieren von Autoren- und Veröffentlichungsinstanzen in AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish) nur die Schritte unter **Einrichten von Replikationsagenten in der Autoreninstanz** ausführen.

## Dispatcher-Konfigurationen {#dispatcher-configurations}

Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und den Lastenausgleich. Die Verwendung des AEM-Dispatchers trägt außerdem dazu bei, Ihren AEM-Server vor Angriffen zu schützen. Somit können Sie die Sicherheit Ihrer AEM-Instanz verbessern, indem Sie den Dispatcher in Verbindung mit einem Webserver der Unternehmensklasse verwenden.

Weitere Informationen dazu finden Sie unter **[Dispatcher-Konfigurationen für AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens)**. Hier finden Sie Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt.

## Installieren von FFMpeg- und Video-Ausgabedarstellungen {#installing-ffmpeg}

Installieren Sie FFmpeg gemäß den Schritten für das entsprechende Betriebssystem (normalerweise RHEL):

1. Bei Installation durch Aktivierung von EPEL und RPMFusion können Sie alle gstreamer-Codecs installieren, um die Unterstützung für FFmpeg-Konvertierungen zu erweitern.
1. Wenn der AAC-Codec als experimentell markiert ist, schlagen FFMpeg-Konvertierungen fehl. Um dieses Problem zu vermeiden, fügen Sie den Videoprofilen `-strict -2` hinzu (in AEM 6.3 `/etc/dam/video` und nach `/libs/settings/dam/video in AEM 6.4` verschoben)

   >[!NOTE]
   >
   >`-strict -2` muss der letzte Parameter in der Parameterliste sein. Kopieren Sie außerdem in AEM 6.4 die Knoten unter */libs/settings/dam/video* nach */conf/global/settings/dam/video*, wie unter [Video-Ausgabedarstellungen](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/authoring/product-features/generating-renditions) beschrieben.
1. Prüfen Sie, ob Videokonvertierungen stattfinden und Ausgabedarstellungen erstellt werden.

## Kennworteinschränkungen {#password-restrictions}

Die Kennwortrichtlinie von AEM muss bei der AMS-Instanz deaktiviert sein. Sie kann auch alternativ in der Web-Konsole mithilfe des Screens-Gerätedienstes *com.adobe.cq.screens.device.impl.DeviceService konfiguriert werden*
Siehe **Kennworteinschränkungen** im Abschnitt [Konfigurieren von Autoren- und Veröffentlichungsinstanz in AEM Screens](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish)

## Einrichten der Umgebungen {#setting-up-environments}

Installieren Sie die aktuellsten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager (AEM) und führen Sie sie aus:

* AEM Service Pack
* Screens Feature Pack
* AEM Cumulative Fix Pack

Identifizieren Sie zusätzlich zu den obigen Angaben alle Entwicklungspakete (z. B. WCM Core).
Komponenten) oder Drittanbieter-Toolkits (z. B. SAP Hybris), die erforderlich sind.Installieren Sie die gleichen Software-Pakete in Ihren lokalen Entwicklungsumgebungen. Weisen Sie Ihren Client an, dieselbe Konfiguration auf allen QA-, Staging- und Produktions-Servern zu verwenden. Nicht übereinstimmende Server-Konfigurationen verursachen Probleme bei Bereitstellung und Tests.

>[!NOTE]
>
>Informationen zum Installieren des neuesten Feature Packs für AEM Screens finden Sie in den [Versionshinweisen](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/aem-screens-introduction).

## Einrichten von ACLs {#setting-up-acls}

Unter „Einrichten von ACLs“ wird erläutert, wie Projekte getrennt werden können, damit jede Person bzw. jedes Team ein eigenes Projekt erhält.

Weitere Informationen finden Sie unter [Einrichten von ACLs](https://experienceleague.adobe.com/de/docs/experience-manager-screens/user-guide/administering/setting-up-acls).

