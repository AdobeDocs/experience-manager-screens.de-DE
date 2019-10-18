---
title: AEM-Plattformkonfigurationen
seo-title: AEM-Plattformkonfigurationen
description: Auf der Seite werden AEM Platform-Konfigurationen beschrieben.
seo-description: Auf der Seite werden AEM Platform-Konfigurationen beschrieben.
translation-type: tm+mt
source-git-commit: 5c83a2b59769dfd3736a830f7d7d3cc35137c182

---

# AEM-Plattformkonfigurationen {#platform-configurations}

>[!NOTE]
>
>Typischer Stakeholder für diese Aktivität ist ein AEM-Implementor.

Gehen Sie wie folgt vor, um AEM-Plattformkonfigurationen einzurichten, um mit AEM Screens zu beginnen.

## Serverkonfigurationen {#server-configurations}

Informationen zum Einrichten von Serverkonfigurationen finden Sie unter [Serverkonfigurationen](https://helpx.adobe.com/experience-manager/6-5/screens/using/configuring-screens-introduction.html#ServerConfiguration).

## Autor veröffentlichen {#author-publish}

Informationen zum Einrichten der Autoren-Veröffentlichung finden Sie unter Authoring und Veröffentlichung in AEM Screens [konfigurieren.](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html)

>[!NOTE]
>
> Wenn es nur einen Autor und einen Veröffentlichungsvorgang gibt, müssen Sie nur die Schritte unter **Einrichten von Replizierungsagenten beim Autor** unter [Konfigurieren von Authoring und Veröffentlichen in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html) ausführen.

## Dispatcherkonfigurationen {#dispatcher-configurations}

Der Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich. Mit dem Dispatcher von AEM können Sie außerdem Ihren AEM-Server vor Angriffen schützen. Daher können Sie die Sicherheit Ihrer AEM-Instanz verbessern, indem Sie den Dispatcher in Verbindung mit einem Webserver der Unternehmensklasse verwenden.

Lesen Sie die Informationen zu **[Dispatcher-Konfigurationen für AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/dispatcher-configurations-aem-screens.html)** , die Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt enthalten.

## Installieren von FFMpeg- und Videowiedergaben {#installing-ffmpeg}

Installieren Sie FFMpeg gemäß den Schritten für das entsprechende Betriebssystem (normalerweise RHEL):

1. Bei der Installation durch Aktivierung von EPEL und RPMFusion können Sie alle Gstreamer-Codecs installieren, um die Unterstützung für FFmpeg-Konvertierungen zu erweitern
1. Wenn der AAC-Codec als experimentell markiert ist, schlagen die ffmpeg-Konvertierungen fehl. Um dies zu vermeiden, fügen Sie den Videoprofilen (/etc/dam/video in AEM 6.3 und in AEM 6.4 nach /libs/settings/dam/video)"strikt -2 hinzu.
   >[!NOTE]
   >
   > Bitte beachten Sie, dass -strikt -2 die letzten Parameter in der Liste der Parameter sein muss. Zusätzlich müssen Sie in AEM 6.4 die Knoten unter */libs/settings/dam/video* nach */conf/global/settings/dam/video* kopieren, wie in den [Videowiedergaben](https://helpx.adobe.com/experience-manager/6-5/screens/using/generating-renditions.html)erwähnt.
1. Überprüfen Sie, ob Videokonvertierungen stattfinden und ob Darstellungen erstellt werden.

## Kennwortbeschränkungen {#password-restrictions}

Die Kennwortrichtlinie von AEM muss auf der AMS-Instanz deaktiviert werden. Dies kann alternativ in der Webkonsole mithilfe des Bildschirmgerätediensts *com.adobe.cq.screens.device.impl.DeviceService* Siehe Abschnitt **Kennwortbeschränkungen**[in Konfigurieren von Authoring und Veröffentlichung in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html)

## Setting up the Environments {#setting-up-environments}

Installieren und führen Sie die aktuellsten Versionen der folgenden Pakete für Ihre Version von Adobe Experience Manager (AEM) aus:

* AEM Service Pack 
* Screens Feature Pack
* AEM  Cumulative Fix Pack 

Zusätzlich zu den oben genannten, identifizieren Sie alle erforderlichen Entwicklungspakete (z. B. WCM Corecomponents) oder Drittanbieter-Toolkits (z. B. SAP Hybris).
Installieren Sie dieselben Softwarepakete auf Ihren lokalen Entwicklungsumgebungen. Weisen Sie Ihren Client an, dieselbe Konfiguration auf allen QA-, Stage- und Production-Servern zu verwenden. Nicht übereinstimmende Serverkonfigurationen verursachen Probleme bei der Bereitstellung und beim Testen.

>[!NOTE]
> Informationen zum Installieren des neuesten Feature Pack für AEM Screens finden Sie in den [Versionshinweisen](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html?topic=/experience-manager/6-5/screens/morehelp/release-notes.ug.js).

## Einrichten von ACLs {#setting-up-acls}

Durch die Einrichtung von ACLs wird erklärt, wie Projekte so getrennt werden, dass jedes einzelne oder Team sein eigenes Projekt bearbeitet.

Weitere Informationen finden Sie unter [Einrichten von ACLs](https://helpx.adobe.com/experience-manager/6-5/screens/using/setting-up-acls.html) .
