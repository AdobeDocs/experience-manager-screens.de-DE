---
title: REST-APIs
seo-title: REST-API
description: AEM Screens stellt eine einfache RESTful-API bereit, die der Siren-Spezifikation entspricht. Auf dieser Seite erfahren Sie, wie Sie in der Inhaltsstruktur navigieren und Befehle an Geräte in der Umgebung senden können.
seo-description: AEM Screens stellt eine einfache RESTful-API bereit, die der Siren-Spezifikation entspricht. Auf dieser Seite erfahren Sie, wie Sie in der Inhaltsstruktur navigieren und Befehle an Geräte in der Umgebung senden können.
uuid: 5988fdcb-cda5-4d3e-a2ab-f9ee4179e568
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: c07b6e4f-c0a4-4151-a543-76dabd6d5146
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# REST-APIs{#rest-apis}

AEM Screens provides a simple RESTful API that follows the [Siren](https://github.com/kevinswiber/siren) specification. Sie ermöglicht die Navigation in der Inhaltsstruktur und das Senden von Befehlen an Geräte in der Umgebung.

The API is accessible at [*http://localhost:4502/api/screens.json*](http://localhost:4502/api/screens.json).

## Navigieren in der Inhaltsstruktur {#navigating-content-structure}

Die von den API-Aufrufen zurückgegebene JSON-Datei listet die Entitäten auf, die im Zusammenhang mit der aktuellen Ressource stehen. Nach der aufgelisteten Selbstverknüpfung ist jede dieser Entitäten erneut als REST-Ressource verfügbar.

Um beispielsweise auf die Bildschirme an unserem Demo-Flagship-Standort zuzugreifen, können Sie Folgendes aufrufen:

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship.json HTTP/1.1
Host: http://localhost:4502
```

Oder verwenden Sie curl:

```xml
curl -u admin:admin http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship.json
```

Das Ergebnis sieht dann wie folgt aus:

```xml
{
  "class": [
    "aem-io/screens/location"
  ],
  "links": [
    {
      "rel": [
        "self"
      ],
      "href": "http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship.json"
    },
    {
      "rel": [
        "parent"
      ],
      "href": "http://localhost:4502/api/screens/content/screens/we-retail/locations/demo.json"
    }
  ],
  "properties": {…},
  "entities": [
    {
      "class": [
        "aem-io/screens/display"
      ],
      "links": [
        {
          "rel": [
            "self"
          ],
          "href": "http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json"
        }
      ],
      "rel": [
        "child"
      ],
      "properties": {
        "title": "Single Screen Display",
        "height": 1440,
        "description": "Demo location of a single screen display.",
        "name": "single",
        "width": 2560,
        "idletimeout": 300,
        "layoutrows": 1,
        "layoutcols": 1
      }
    },
    …
  ]
}
```

Um dann auf die Einzelbildanzeige zuzugreifen, können Sie folgende Telefonanrufe ausführen:

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502
```

## Ausführen von Aktionen auf Ressourcen {#executing-actions-on-the-resource}

Die von den API-Aufrufen zurückgegebene JSON-Datei kann eine Liste von Aktionen enthalten, die für die Ressource verfügbar sind.

The display, for instance, lists a *broadcast-command* action that allows to send a command to all the devices assigned to that display.

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502
```

Oder verwenden Sie curl:

```xml
curl -u admin:admin http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json
```

***Ergebnis:***

```xml
{
  "class": [
    "aem-io/screens/display"
  ],
  "links": […],
  "properties": {…},
  "entities": […],
  "actions": [
    {
      "title": "",
      "name": "broadcast-command",
      "method": "POST",
      "href": "/api/screens/content/screens/we-retail/locations/demo/flagship/single",
      "fields": [
        {
          "name": ":operation",
          "value": "broadcast-command",
          "type": "hidden"
        },
        {
          "name": "msg",
          "type": "text"
        }
      ]
    }
  ]
}
```

Um diese Aktion auslösen, muss Folgendes aufgerufen werden:

```xml
POST /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502

:operation=broadcast-command&msg=reboot
```

Oder verwenden Sie curl:

```xml
curl -u admin:admin -X POST -d ':operation=broadcast-command&msg=reboot' http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json
```

