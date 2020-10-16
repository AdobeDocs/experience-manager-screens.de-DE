---
title: AEM-Plattformkonfigurationen
seo-title: AEM-Plattformkonfigurationen
description: Auf dieser Seite werden AEM-Plattformkonfigurationen beschrieben.
seo-description: Auf dieser Seite werden AEM-Plattformkonfigurationen beschrieben.
translation-type: tm+mt
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---

# AEM-Plattformkonfigurationen {#platform-configurations}

>[!NOTE]
>
>Typische Verantwortliche für diese Aktivität sind AEM-Implementoren.

Gehen Sie wie folgt vor, um AEM-Plattformkonfigurationen einzurichten und erste Schritte mit AEM Screens zu machen.

## Serverkonfigurationen {#server-configurations}

Informationen zum Einrichten von Serverkonfigurationen finden Sie unter [Serverkonfigurationen](https://helpx.adobe.com/experience-manager/6-5/screens/using/configuring-screens-introduction.html#ServerConfiguration).

## Author-Publish {#author-publish}

Informationen zum Einrichten von author-publish finden Sie unter [Konfigurieren von Author und Publish in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html).

>[!NOTE]
>
>Wenn es nur einen Autor und eine Veröffentlichung gibt, müssen Sie lediglich auf der Seite [Konfigurieren von Author und Publish in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html) die Schritte unter **Einrichten von Replikationsagenten für Author** ausführen.

## Dispatcher-Konfigurationen {#dispatcher-configurations}

Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich. Mit dem Dispatcher von AEM können Sie außerdem Ihren AEM-Server vor Angriffen schützen. Daher können Sie die Sicherheit Ihrer AEM-Instanz verbessern, indem Sie den Dispatcher in Verbindung mit einem Webserver der Unternehmensklasse verwenden.

Weitere Informationen dazu finden Sie unter **[Dispatcher-Konfigurationen für AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/dispatcher-configurations-aem-screens.html)**; hier finden Sie Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt.

## Installieren von FFmpeg- und Videoausgaben {#installing-ffmpeg}

Installieren Sie FFmpeg gemäß den Schritten für das entsprechende Betriebssystem (normalerweise RHEL):

1. Bei Installation durch Aktivierung von EPEL und RPMFusion können Sie alle gstreamer-Codecs installieren, um die Unterstützung für FFmpeg-Konvertierungen zu erweitern.
1. Wenn der AAC-Codec als experimentell markiert ist, schlagen FFmpeg-Konvertierungen fehl. Um das zu verhindern, fügen Sie den Videoprofilen (/etc/dam/video in AEM 6.3 und /libs/settings/dam/video in AEM 6.4) -strict -2 hinzu.
   >[!NOTE]
   >
   > Beachten Sie, dass -strict -2 die letzten Parameter in der Parameterliste sein müssen. Außerdem müssen Sie in AEM 6.4 die Knoten unter */libs/settings/dam/video* nach */conf/global/settings/dam/video* kopieren, wie in [Videoausgaben](https://helpx.adobe.com/experience-manager/6-5/screens/using/generating-renditions.html) dargestellt.
1. Prüfen Sie, ob Videokonvertierungen stattfinden und Ausgaben erstellt werden.

## Kennworteinschränkungen {#password-restrictions}

Die Kennwortrichtlinie von AEM muss bei der AMS-Instanz deaktiviert werden. Dies kann alternativ in der Webkonsole mithilfe des Screens-Gerätediensts *com.adobe.cq.screens.device.impl.DeviceService* konfiguriert werden.
Weitere Informationen dazu finden Sie im Abschnitt **Kennwortbeschränkungen** unter [Konfigurieren von Author und Publish in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html).

## Einrichten der Umgebungen {#setting-up-environments}

Installieren Sie die aktuellsten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager (AEM) und führen Sie sie aus:

* AEM Service Pack
* Screens Feature Pack
* AEM Cumulative Fix Pack

Ermitteln Sie außerdem alle erforderlichen Entwicklungspakete (z. B. zentrale
WCM-Komponenten) oder Toolkits von Drittanbietern (z. B. SAP Hybris).
Installieren Sie dieselben Softwarepakete in Ihren lokalen Entwicklungsumgebungen. Weisen Sie Ihren Klienten an, dieselbe Konfiguration auf allen QA-, Staging- und Produktionsservern zu verwenden. Nicht übereinstimmende Serverkonfigurationen verursachen Probleme bei Bereitstellung und Tests.

>[!NOTE]
>
>Informationen zum Installieren des neuesten Feature Pack für AEM Screens finden Sie in den [Versionshinweisen](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html?topic=/experience-manager/6-5/screens/morehelp/release-notes.ug.js).

## Einrichten von ACLs {#setting-up-acls}

Unter „Einrichten von ACLs“ wird erläutert, wie Sie Projekte separieren können, damit jede Person bzw. jedes Team ein eigenes Projekt erhält.

Weitere Informationen finden Sie unter [Einrichten von ACLs](https://helpx.adobe.com/experience-manager/6-5/screens/using/setting-up-acls.html).
