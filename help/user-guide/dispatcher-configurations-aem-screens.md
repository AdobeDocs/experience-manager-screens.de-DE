---
title: Dispatcher-Konfigurationen für AEM Screens
seo-title: Dispatcher Configurations for AEM Screens
description: Auf dieser Seite werden Richtlinien zum Konfigurieren von Dispatcher für ein AEM Screens-Projekt hervorgehoben.
seo-description: This page highlights guidelines for configuring dispatcher for an AEM Screens project.
feature: Administering Screens
role: Developer, User
level: Intermediate
exl-id: 8b281488-f54d-4f8a-acef-ca60fa2315ed
source-git-commit: 01d2245cca5757441ef2bd4e2c05c231b678ce48
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 87%

---

# Dispatcher-Konfigurationen für AEM Screens {#dispatcher-configurations-for-aem-screens}

Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich.

Die folgende Seite enthält die Richtlinien zum Konfigurieren von Dispatcher für ein AEM Screens-Projekt.

>[!NOTE]
>
>Wenn ein Dispatcher verfügbar ist, können Verbindungen zum Registrierungs-Servlet durch Filtern in den Dispatcher-Regeln verhindert werden.
>
>Wenn kein Dispatcher vorhanden ist, deaktivieren Sie das Registrierungs-Servlet in der Liste der OSGi-Komponenten.

Um Dispatcher für ein AEM Screens-Projekt konfigurieren zu können, müssen Sie über Vorkenntnisse in Dispatcher verfügen.
Weitere Informationen finden Sie unter [Konfigurieren von Dispatcher](https://docs.adobe.com/content/help/de-DE/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html).

## Konfigurieren von Dispatcher für die Manifest-Version v2 {#configuring-dispatcher}

>[!IMPORTANT]
>Die folgenden Dispatcher-Konfigurationen gelten nur für die Manifest-Version v2. Informationen zur Manifest-Version v3 finden Sie unter [Dispatcher-Konfigurationen für Manifest-Version v3](#configuring-dispatcherv3).

AEM Screens-Player oder -Geräte verwenden ebenfalls authentifizierte Sitzungen, um auf die Ressourcen in den Veröffentlichungsinstanzen zuzugreifen. Wenn Sie also über mehrere Veröffentlichungsinstanzen verfügen, sollten die Anfragen immer an dieselbe Veröffentlichungsinstanz gesendet werden, damit die authentifizierte Sitzung für alle Anfragen von den AEM Screens-Playern/Geräten gültig ist.

Gehen Sie wie folgt vor, um Dispatcher für ein AEM Screens-Projekt zu konfigurieren.

### Aktivieren von fixierbaren Sitzungen {#enable-sticky-session}

Wenn Sie mehrere Veröffentlichungsinstanzen mit nur einem Dispatcher verwenden möchten, müssen Sie die Datei `dispatcher.any` so aktualisieren, dass das Sticky-Verhalten aktiviert ist.

```xml
/stickyConnections {
  /paths
  {
    "/"
  }
 }
```

Wenn Sie eine Veröffentlichungsinstanz mit einem Dispatcher verwenden, ist die Aktivierung des Sticky-Verhaltens am Dispatcher nicht nötig, da der Load-Balancer jede Anfrage an den Dispatcher senden kann. In diesem Fall klicken Sie im Feld **Sticky-Verhalten** auf **Aktivieren**, um es auf der Ebene des Load-Balancers zu aktivieren, wie in der folgenden Abbildung gezeigt:

![image](/help/user-guide/assets/dispatcher/dispatcher-enable.png)

Wenn Sie z. B. AWS ALB verwenden, finden Sie unter [Zielgruppen für Ihre Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) Informationen dazu, wie Sie das Sticky-Verhalten auf ALB-Ebene aktivieren. Aktivieren Sie das Sticky-Verhalten für 1 Tag.

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

## Konfigurieren von Dispatcher für die Manifest-Version v3 {#configuring-dispatcherv3}

Stellen Sie sicher, dass diese Filter und Cache-Regeln in Dispatchern zugelassen sind, die sich vor den Veröffentlichungsinstanzen befinden, damit Screens funktioniert.

### Voraussetzungen für Manifest-Version v3 {#prerequisites3}

Stellen Sie sicher, dass diese beiden Voraussetzungen erfüllt sind, bevor Sie Dispatcher (Manifest-Version v3) für AEM Screens konfigurieren:

* Stellen Sie sicher, dass Sie `v3 manifests` verwenden. Navigieren Sie zu `https://<server:port>/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` und stellen Sie sicher, dass `Enable ContentSync Cache` deaktiviert ist.

* Stellen Sie sicher, dass der Dispatcher-Flush-Agent in der Veröffentlichungsinstanz unter `/etc/replication/agents.publish/dispatcher1useast1Agent` konfiguriert ist.

   ![Bild](/help/user-guide/assets/dispatcher/dispatcher-1.png)

   ![Bild](/help/user-guide/assets/dispatcher/dispatcher-3.png)

### Filter  {#filter-v3}

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
#/0221 { /type "allow" /method '(GET|HEAD)' /url "/content/experience-fragments/*" } ## uncomment this, if you're using experience-fragments
/0222 { /type "allow" /extension '(css|eot|gif|ico|jpeg|jpg|js|gif|pdf|png|svg|swf|ttf|woff|woff2|html|mp4|mov|m4v)' /path "/content/dam/*" } ## add any other formats required for your project here
 
## # Enable clientlibs proxy servlet
/0230 { /type "allow" /method "GET" /url "/etc.clientlibs/*" }
```

### Cache-Regeln {#cache-rules-v3}

* Fügen Sie `/allowAuthorized "1"` zum Abschnitt `/cache` in `publish_farm.any` hinzu.

* Alle Screens-Player verwenden eine authentifizierte Sitzung, um eine Verbindung zu AEM (Autor/Veröffentlichung) herzustellen. Dispatcher ist so vorkonfiguriert, dass diese URLs nicht zwischengespeichert werden. Daher müssen wir diese aktivieren.

* Fügen Sie `statfileslevel "10"` zum Abschnitt `/cache` in `publish_farm.any` hinzu.
Dies unterstützt die Zwischenspeicherung von bis zu 10 Ebenen aus dem Cache-Basisverzeichnis und die entsprechende Invalidierung bei der Veröffentlichung von Inhalten, anstatt alles zu invalidieren. Sie können diese Ebene ändern, je nachdem, wie tief Ihre Inhaltsstruktur ist.

* Hinzufügen von Folgendem zu `/invalidate section in publish_farm.any`

   ```
   /0003 {
       /glob "*.json"
       /type "allow"
   }
   ```

* Fügen Sie die folgenden Regeln zum Abschnitt `/rules` in `/cache` in `publish_farm.any` oder einer Datei hinzu, die in `publish_farm.any` enthalten ist:

   ```
   ## Don't cache CSRF login tokens
   /0001
       {
       /glob "/libs/granite/csrf/token.json"
       /type "deny"
       }
   ## Allow Dispatcher Cache for Screens channels
   /0002
       {
           /glob "/content/screens/*.html"
           /type "allow"
       }
   ## Allow Dispatcher Cache for Screens offline manifests
   /0003
       {
       /glob "/content/screens/*.manifest.json"
       /type "allow"
       }
   ## Allow Dispatcher Cache for Assets
   /0004
       {
   
       /glob "/content/dam/*"
       /type "allow"
       }
   ## Disable Dispatcher Cache for Screens devices json
   /0005
       {
       /glob "/home/users/screens/*.json"
       /type "deny"
       }
   ## Disable Dispatcher Cache for Screens svc json
   /0006
       {
       /glob "/content/screens/svc.json"
       /type "deny"
       }
   ```

### Invalidierungsregel für segment.js hinzufügen {#invalidsegmentjs}

Wenn Sie zielgerichtete Kampagnen mit AEM Screens verwenden, wird die `segments.js file` vom Dispatcher bereitgestellt wird, muss invalidiert werden, wenn Sie neue Segmente hinzufügen und auf AEM veröffentlichen. Ohne diese Invalidierungsregel funktionieren neue zielgerichtete Kampagnen nicht auf dem Screens-Player (stattdessen wird der Standardinhalt angezeigt).

* Hinzufügen einer Invalidierungsregel zu `/etc/httpd/conf.dispatcher.d/available_farms/999_ams_publish_farm.any`. Folgende Regel wird hinzugefügt:

```
    /invalidate {
                        .
                        .
                        /0004 {
                               /glob "conf/<project-name>/settings/wcm/.js"
                               /type "allow"
                        }
                }
```

* Diese Regel stellt sicher, dass `segments.js` wird ungültig gemacht und die neueste Datei wird abgerufen, wenn sie geändert wird.
