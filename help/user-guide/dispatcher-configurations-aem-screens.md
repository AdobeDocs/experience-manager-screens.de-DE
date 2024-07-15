---
title: Dispatcher-Konfigurationen für AEM Screens
description: Auf dieser Seite werden Richtlinien zur Dispatcher-Konfiguration für ein AEM Screens-Projekt beschrieben.
feature: Administering Screens
role: Developer, User
level: Intermediate
exl-id: 8b281488-f54d-4f8a-acef-ca60fa2315ed
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 100%

---

# Dispatcher-Konfigurationen für AEM Screens{#dispatcher-configurations-for-aem-screens}

Der Dispatcher ist das Caching- und/oder Lastenausgleichs-Tool von Adobe Experience Manager.

Die folgende Seite enthält die Richtlinien zum Konfigurieren eines Dispatchers für ein AEM Screens-Projekt.

>[!NOTE]
>
>Bei vorhandenem Dispatcher können Verbindungen zum Registrierungs-Servlet durch Filtern in den Dispatcher-Regeln verhindert werden.
>
>Ist kein Dispatcher vorhanden, deaktivieren Sie das Registrierungs-Servlet in der Liste der OSGi-Komponenten.

Um den Dispatcher für ein AEM Screens-Projekt konfigurieren zu können, benötigen Sie entsprechende Dispatcher-Vorkenntnisse.
Weitere Informationen finden Sie unter [Konfigurieren von Dispatcher](https://experienceleague.adobe.com/de/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration).

## Konfigurieren von Dispatcher für die Manifest-Version v2 {#configuring-dispatcher}

>[!IMPORTANT]
>Die folgenden Dispatcher-Konfigurationen gelten nur für die Manifest-Version v2. Informationen zur Manifest-Version v3 finden Sie unter [Dispatcher-Konfigurationen für Manifest-Version v3](#configuring-dispatcherv3).

AEM Screens-Player oder -Geräte verwenden ebenfalls authentifizierte Sitzungen, um auf die Ressourcen in den Veröffentlichungsinstanzen zuzugreifen. Wenn Sie also über mehrere Veröffentlichungsinstanzen verfügen, sollten die Anfragen immer an dieselbe Veröffentlichungsinstanz gesendet werden, damit die authentifizierte Sitzung für alle Anfragen von den AEM Screens-Playern/-Geräten gültig ist.

Gehen Sie wie folgt vor, um den Dispatcher für ein AEM Screens-Projekt zu konfigurieren.

### Aktivieren von fixierbaren Sitzungen {#enable-sticky-session}

Wenn Sie mehrere Veröffentlichungsinstanzen mit nur einem Dispatcher verwenden möchten, aktualisieren Sie die Datei `dispatcher.any` so, dass das Sticky-Verhalten aktiviert ist.

```xml
/stickyConnections {
  /paths
  {
    "/"
  }
 }
```

Wenn Sie eine Veröffentlichungsinstanz mit einem Dispatcher verwenden, ist die Aktivierung des Sticky-Verhaltens am Dispatcher nicht nötig, da der Load-Balancer jede Anfrage an den Dispatcher senden kann. In diesem Fall wählen Sie im Feld für das **Sticky-Verhalten** die Option **Aktivieren** aus, um es auf Load-Balancer-Ebene zu aktivieren, wie in der folgenden Abbildung dargestellt:

![Bild](/help/user-guide/assets/dispatcher/dispatcher-enable.png)

Wenn Sie z. B. AWS ALB verwenden, finden Sie unter [Zielgruppen für Ihre Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) Informationen dazu, wie Sie das Sticky-Verhalten auf ALB-Ebene aktivieren. Aktivieren Sie das Sticky-Verhalten für einen Tag.

### Schritt 1: Konfigurieren von Client-Kopfzeilen {#step-configuring-client-headers}

Fügen Sie dem Abschnitt `/clientheaders` Folgendes hinzu:

**X-Requested-With**

**X-SET-HEARTBEAT**

**X-REQUEST-COMMAND**

### Schritt 2: Konfigurieren von Screens-Filtern {#step-configure-screens-filters}

Fügen Sie Folgendes zu ***`/filter`*** hinzu, um Screens-Filter zu konfigurieren.

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

### Schritt 3: Deaktivieren des Dispatcher-Caches {#step-disabling-dispatcher-cache}

Deaktivieren Sie das Dispatcher-Caching für ***/content/screens path***.

Screens-Player verwenden die authentifizierte Sitzung, sodass der Dispatcher keine Anfragen von Screens-Playern für `channels/assets` im Cache speichert.

Um den Cache für die Assets zu aktivieren, damit die Assets aus dem Dispatcher-Cache bereitgestellt werden, gehen Sie wie folgt vor:

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

Stellen Sie sicher, dass diese Filter und Cache-Regeln in Dispatchern von Veröffentlichungsinstanzen zugelassen sind, damit Screens funktioniert.

### Voraussetzungen für die Manifest-Version v3 {#prerequisites3}

Achten Sie darauf, dass diese beiden Voraussetzungen erfüllt sind, bevor Sie einen Dispatcher (Manifest-Version v3) für AEM Screens konfigurieren:

* Stellen Sie sicher, dass Sie `v3 manifests` verwenden. Navigieren Sie zu `https://<server:port>/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` und stellen Sie sicher, dass `Enable ContentSync Cache` deaktiviert ist.

* Stellen Sie sicher, dass der Dispatcher Flush-Agent in der Veröffentlichungsinstanz unter `/etc/replication/agents.publish/dispatcher1useast1Agent` konfiguriert ist.

  ![image](/help/user-guide/assets/dispatcher/dispatcher-1.png)

  ![Bild](/help/user-guide/assets/dispatcher/dispatcher-3.png)

### Filter {#filter-v3}

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

* Alle AEM Screens-Player verwenden eine authentifizierte Sitzung, um eine Verbindung zu AEM (Author/Publish) herzustellen. Da ein vorkonfigurierter Dispatcher diese URLs nicht zwischenspeichert, sollten Sie diese aktivieren.

* Fügen Sie `statfileslevel "10"` zum Abschnitt `/cache` in `publish_farm.any` hinzu.
Dies unterstützt das Caching von bis zu 10 Ebenen aus dem Cache-Basisverzeichnis und die entsprechende Invalidierung bei der Veröffentlichung von Inhalten, anstatt alles zu invalidieren. Sie können diese Ebene ändern, je nachdem, wie tief Ihre Inhaltsstruktur ist.

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

### Hinzufügen der Invalidierungsregel für segment.js {#invalidsegmentjs}

Wenn Sie zielgerichtete Kampagnen mit AEM Screens verwenden, muss die Datei `segments.js file`, die vom Dispatcher bereitgestellt wird, invalidiert werden, wenn Sie neue Segmente hinzufügen und in AEM veröffentlichen. Ohne diese Invalidierungsregel funktionieren neue zielgerichtete Kampagnen im AEM Screens-Player nicht (stattdessen wird der Standardinhalt angezeigt).

* Fügen Sie eine Invalidierungsregel zu `/etc/httpd/conf.dispatcher.d/available_farms/999_ams_publish_farm.any` hinzu. Folgende Regel soll hinzugefügt werden:

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

* Diese Regel stellt sicher, dass die `segments.js`-Datei invalidiert wird und die neueste Datei abgerufen wird, wenn sie geändert wird.
