---
title: Dispatcher-Konfigurationen für AEM Screens
seo-title: Dispatcher-Konfigurationen für AEM Screens
description: Auf dieser Seite werden Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt hervorgehoben.
seo-description: Auf dieser Seite werden Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt hervorgehoben.
uuid: ec5219b7-73f9-4026-99e5-e4a02201b128
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
discoiquuid: 1b1a36a4-4f95-41e3-b0a8-74249efb0119
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Dispatcher-Konfigurationen für AEM Screens{#dispatcher-configurations-for-aem-screens}

Der Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich.

Die folgende Seite enthält die Richtlinien zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt.

## Voraussetzungen {#pre-requisites}

Bevor Sie Dispatcher für ein AEM Screens-Projekt konfigurieren, müssen Sie über vorherige Kenntnisse von Dispatcher verfügen.

Weitere Informationen finden Sie unter ** [Konfigurieren von Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html)**.

## Konfigurieren des Dispatchers {#configuring-dispatcher}

Gehen Sie wie folgt vor, um Dispatcher für ein AEM Screens-Projekt zu konfigurieren.

### Schritt 1: Client-Header konfigurieren {#step-configuring-client-headers}

Fügen Sie dem `/clientheaders`Abschnitt Folgendes hinzu:

**X-Requested-With**

**X-SET-HEARTBEAT**

**X-REQUEST-COMMAND**

### Schritt 2: Konfigurieren von Bildschirmfiltern {#step-configuring-screens-filters}

Fügen Sie zum Konfigurieren von Bildschirmfiltern Folgendes hinzu ***/filtern***.

```
## AEM Screens Filters
## # Login, Ping and Device Configurations
/0200 { /type "allow" /method "POST" /url "/libs/granite/core/content/login.validate/j_security_check" }
/0201 { /type "allow" /method "GET" /url "/content/screens/svc.json" }
/0202 { /type "allow" /method "GET" /url "/content/screens/svc.ping.json" }
/0203 { /type "allow" /method "GET" /url "/content/screens/svc.config.json" }
## # Device Dashboard Configurations
/0204 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.preferences.json" }
/0205 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.logs.json" }
/0206 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.statusinfo.json" }
/0207 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.screenshot.json" }
## # Content Configurations
/0208 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*" }
/0209 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*/jcr:content/*/offline-config_*.zip" }
/0210 { /type "allow" /method '(GET|HEAD)' /url '/var/contentsync/content/screens/.+/jcr:content/.+/offline-config_.*\.[0-9]+\.zip' }
```

### Schritt 3: Dispatcher-Cache deaktivieren {#step-disabling-dispatcher-cache}

Deaktivieren Sie die Dispatcher-Zwischenspeicherung für ***/content/screens-Pfad***.
