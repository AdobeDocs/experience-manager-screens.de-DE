---
title: Dispatcher-Konfigurationen für AEM Screens
seo-title: Dispatcher-Konfigurationen für AEM Screens
description: Auf dieser Seite werden Richtlinien zum Konfigurieren von Dispatcher für ein AEM Screens-Projekt hervorgehoben.
seo-description: Auf dieser Seite werden Richtlinien zum Konfigurieren von Dispatcher für ein AEM Screens-Projekt hervorgehoben.
translation-type: tm+mt
source-git-commit: 37025002d02603ab8a5c571086524be858389557
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 71%

---


# Dispatcher-Konfigurationen für AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich.

Die folgende Seite enthält die Richtlinien zum Konfigurieren von Dispatcher für ein AEM Screens-Projekt.

>[!NOTE]
>
>Wenn ein Dispatcher verfügbar ist, können Verbindungen zum Registrierungs-Servlet durch Filtern in den Dispatcher-Regeln verhindert werden.
>
>Wenn kein Dispatcher vorhanden ist, deaktivieren Sie das Registrierungs-Servlet in der Liste der OSGi-Komponenten.

## Voraussetzungen {#pre-requisites}

Bevor Sie Dispatcher für ein AEM Screens-Projekt konfigurieren, müssen Sie über Vorkenntnisse in Dispatcher verfügen.

Weitere Informationen finden Sie unter [Konfigurieren von Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html).

## Konfigurieren von Dispatcher {#configuring-dispatcher}

Gehen Sie wie folgt vor, um Dispatcher für ein AEM Screens-Projekt zu konfigurieren.

### Aktivieren von fixierbaren Sitzungen {#enable-sticky-session}

Wenn jemand mehr als eine Instanz im Veröffentlichungsmodus mit Dispatcher verwenden möchte, muss er die Datei &quot;dispatcher.any&quot;in seinem Dispatcher aktualisieren.

```xml
/stickyConnections {
  /paths
  {
    "/content/screens"
    "/home/users/screens"
    "/libs/granite/csrf/token.json"
  }
}
```

### Schritt 1: Konfigurieren von Client-Kopfzeilen {#step-configuring-client-headers}

Fügen Sie dem Abschnitt `/clientheaders` Folgendes hinzu:

**X-Requested-With**

**X-SET-HEARTBEAT**

**X-REQUEST-COMMAND**

### Schritt 2: Konfigurieren von Screens-Filtern {#step-configuring-screens-filters}

Fügen Sie ***/filter*** Folgendes hinzu, um Screens-Filter zu konfigurieren.

```
## AEM Screens Filters
## # Login, Ping and Device Configurations
/0200 { /type "allow" /method "POST" /url "/libs/granite/core/content/login.validate/j_security_check" }
/0201 { /type "allow" /method "GET" /url "/libs/granite/csrf/token.json" }
/0202 { /type "allow" /method "GET" /url "/content/screens/svc.json" }
/0203 { /type "allow" /method "GET" /url "/content/screens/svc.ping.json" }
/0204 { /type "allow" /method "GET" /url "/content/screens/svc.config.json" }
## # Device Dashboard Configurations
/0210 { /type "allow" /method '(GET|POST)' /url "/home/users/screens/*/devices/*/profile_screens.preferences.json" }
/0211 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.logs.json" }
/0212 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.statusinfo.json" }
/0213 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.screenshot.json" }
## # Content Configurations
/0220 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*" }
/0221 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*/jcr:content/*/offline-config_*.zip" }
/0222 { /type "allow" /method '(GET|HEAD)' /url '/var/contentsync/content/screens/.+/jcr:content/.+/offline-config_.*\.[0-9]+\.zip' }
```

### Schritt 3: Deaktivieren von Dispatcher-Cache {#step-disabling-dispatcher-cache}

Deaktivieren Sie die Dispatcher-Zwischenspeicherung für ***/content/screens path***.

Screens Player verwenden authentifizierte Sitzung, sodass der Dispatcher keine der Bildschirmanforderungen von Playern zwischenspeichert `channels/assets`.

Um den Cache für die Assets zu aktivieren, damit die Assets aus dem Dispatcher-Cache bereitgestellt werden, müssen Sie:

* hinzufügen `/allowAuthorization 1` im `/cache` Abschnitt
* hinzufügen die folgenden Regeln in `/rules` Abschnitt `/cache`

```xml
/0000
    {
        /glob "*"
        /type "allow"
    }   

/0001
    {
        # Disable Dispatcher Cache for Screens channels
        /glob "/content/screens/*.html"
        /type "deny" 
    }

/0002
    {
    # Disable Dispatcher Cache for Screens offline manifests
    /glob "/content/screens/*.json"
    /type "deny"
    }

/0003
    { # Disable Dispatcher Cache for Screens devices json 
    /glob "/home/users/screens/*.json"
    /type "deny"
    }
```
