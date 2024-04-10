---
title: AEM Platform-Konfigurationen
description: Auf dieser Seite werden AEM Platform-Konfigurationen beschrieben.
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 44%

---

# AEM Platform-Konfigurationen  {#platform-configurations}

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind AEM-Implementoren.

Beginnen Sie mit AEM Screens, indem Sie die folgenden Abschnitte ausführen, um AEM Plattformkonfigurationen einzurichten.

## Serverkonfigurationen {#server-configurations}

Informationen zum Einrichten von Serverkonfigurationen finden Sie unter [Serverkonfigurationen](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction#ServerConfiguration).

## Author-Publish {#author-publish}

Siehe [Konfigurieren von Autoren- und Veröffentlichungsinstanz in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish).

>[!NOTE]
>
>Wenn es nur einen Autor und eine Veröffentlichung gibt, führen Sie nur die Schritte unter **Einrichten von Replikationsagenten auf der Autoreninstanz** in [Konfigurieren von Autoren- und Veröffentlichungsinstanz in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish) Seite.

## Dispatcher-Konfigurationen {#dispatcher-configurations}

Der Dispatcher ist das Caching- und Lastenausgleichstool von Adobe Experience Manager. Die Verwendung des AEM-Dispatchers trägt außerdem dazu bei, Ihren AEM-Server vor Angriffen zu schützen. Somit können Sie die Sicherheit Ihrer AEM-Instanz verbessern, indem Sie den Dispatcher in Verbindung mit einem Webserver der Unternehmensklasse verwenden.

Siehe **[Dispatcher-Konfigurationen für AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens)** , der Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt hervorhebt.

## Installieren von FFMpeg- und Videoausgaben {#installing-ffmpeg}

Installieren Sie FFmpeg gemäß den Schritten für das entsprechende Betriebssystem (normalerweise RHEL):

1. Bei Installation durch Aktivierung von EPEL und RPMFusion können Sie alle gstreamer-Codecs installieren, um die Unterstützung für FFmpeg-Konvertierungen zu erweitern.
1. Wenn der AAC-Codec als experimentell markiert ist, schlagen FFmpeg-Konvertierungen fehl. Um dies zu vermeiden, fügen Sie `-strict -2` zu den Videoprofilen (/etc/dam/video in AEM 6.3 und in AEM 6.4 zu /libs/settings/dam/video verschoben.

   >[!NOTE]
   >
   >Die `-strict -2` muss der letzte Parameter in der Parameterliste sein. Außerdem müssen Sie in AEM 6.4 die Knoten unter */libs/settings/dam/video* nach */conf/global/settings/dam/video* gemäß [Videoausgaben](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/generating-renditions).
1. Prüfen Sie, ob Videokonvertierungen stattfinden und Ausgaben erstellt werden.

## Kennworteinschränkungen {#password-restrictions}

Die Kennwortrichtlinie von AEM muss in der AMS-Instanz deaktiviert sein. Dies kann alternativ in der Web-Konsole mithilfe des Screens-Gerätedienstes konfiguriert werden. *com.adobe.cq.screens.device.impl.DeviceService*
Siehe **Kennwortbeschränkungen** Abschnitt in[Konfigurieren von Autoren- und Veröffentlichungsinstanz in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish)

## Einrichten der Umgebungen {#setting-up-environments}

Installieren Sie die aktuellsten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager (AEM) und führen Sie sie aus:

* AEM Service Pack
* Screens Feature Pack
* AEM Cumulative Fix Pack

Ermitteln Sie außerdem alle erforderlichen Entwicklungspakete (z. B. zentrale
WCM-Komponenten) oder Toolkits von Drittanbietern (z. B. SAP Hybris).
Installieren Sie dieselben Softwarepakete in Ihrer lokalen Entwicklungsumgebung. Weisen Sie Ihren Klienten an, dieselbe Konfiguration auf allen QA-, Staging- und Produktionsservern zu verwenden. Nicht übereinstimmende Serverkonfigurationen verursachen Probleme bei der Bereitstellung und beim Testen.

>[!NOTE]
>
>Informationen zum Installieren des neuesten Feature Packs für AEM Screens finden Sie unter [Versionshinweise](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/aem-screens-introduction).

## Einrichten von ACLs {#setting-up-acls}

Unter „Einrichten von ACLs“ wird erläutert, wie Sie Projekte separieren können, damit jede Person bzw. jedes Team ein eigenes Projekt erhält.

Weitere Informationen finden Sie unter [Einrichten von ACLs](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/setting-up-acls).
