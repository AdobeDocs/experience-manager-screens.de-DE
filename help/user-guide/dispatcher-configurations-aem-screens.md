---
title: Dispatcher-Konfigurationen für AEM Screens
seo-title: Dispatcher-Konfigurationen für AEM Screens
description: Auf dieser Seite werden Richtlinien zum Konfigurieren von Dispatcher für ein AEM Screens-Projekt hervorgehoben.
seo-description: Auf dieser Seite werden Richtlinien zum Konfigurieren von Dispatcher für ein AEM Screens-Projekt hervorgehoben.
translation-type: tm+mt
source-git-commit: 43aca405707625fe5a132beaed82dbb9a4513129
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

AEM Screens-Player/-Geräte verwenden authentifizierte Sitzungen, um auf die Ressourcen in den Veröffentlichungsinstanzen zuzugreifen. Wenn Sie also mehrere Instanzen im Veröffentlichungsmodus haben, sollten die Anforderungen immer an dieselbe Instanz im Veröffentlichungsmodus gesendet werden, damit die authentifizierte Sitzung für alle Anforderungen von AEM Screens-Playern/Geräten gültig ist.

Gehen Sie wie folgt vor, um Dispatcher für ein AEM Screens-Projekt zu konfigurieren.

### Aktivieren von fixierbaren Sitzungen {#enable-sticky-session}

Wenn Sie mehrere Instanzen im Veröffentlichungsmodus verwenden möchten, die von einem Dispatcher vorgestellt werden, müssen Sie die `dispatcher.any`-Datei aktualisieren, um die Stickiness zu aktivieren

```xml
/stickyConnections {
  /paths
  {
    "/"
  }
 }
```

Wenn eine Instanz im Veröffentlichungsmodus von einem Dispatcher frontiert ist, hilft die Aktivierung der Stickiness am Dispatcher nicht, da der Lastenausgleich jede Anforderung an den Dispatcher senden kann. In diesem Fall klicken Sie auf **Aktivieren** im Feld **Stickiness**, um es auf der Ebene des Lastenausgleichs zu aktivieren, wie in der folgenden Abbildung gezeigt:

![image](/help/user-guide/assets/dispatcher/dispatcher-enable.png)

Wenn Sie z. B. AWS ALB verwenden, lesen Sie die [Zielpopulationen für Ihren Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html), um die Stickiness auf ALB-Ebene zu aktivieren. Die Stickiness 1 Tag lang aktivieren.

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

Screens-Player verwenden die authentifizierte Sitzung, sodass der Dispatcher keine der Anforderungen von Screens-Playern für `channels/assets` im Cache zwischenspeichert.

Um den Cache für die Assets zu aktivieren, damit die Assets aus dem Dispatcher-Cache bereitgestellt werden, müssen Sie:

* `/allowAuthorization 1` im Abschnitt `/cache` hinzufügen,
* die folgenden Regeln zum Abschnitt `/rules` von `/cache` hinzufügen.

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
