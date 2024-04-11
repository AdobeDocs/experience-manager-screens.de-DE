---
title: REST-APIs
description: Erfahren Sie, wie AEM Screens eine einfache RESTful-API bereitstellt, die der Siren-Spezifikation entspricht. Erfahren Sie auch, wie Sie in der Inhaltsstruktur navigieren und Befehle an Geräte in der Umgebung senden.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: ac01935a-c3ff-485a-b60e-227fb94c75b0
source-git-commit: 43e89ddc3eb6baffca75d730a978e60e234aaee4
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 57%

---

# REST-APIs{#rest-apis}

AEM Screens stellt eine einfache RESTful-API bereit, die der [Siren](https://github.com/kevinswiber/siren)-Spezifikation entspricht. Damit können Sie in der Inhaltsstruktur navigieren und Befehle an Geräte in der Umgebung senden.

Die API steht unter [*http://localhost:4502/api/screens.json*](http://localhost:4502/api/screens.json) zur Verfügung.

## Navigieren in der Inhaltsstruktur {#navigating-content-structure}

Die von den API-Aufrufen zurückgegebene JSON-Datei listet die Entitäten auf, die im Zusammenhang mit der aktuellen Ressource stehen. Nach dem aufgelisteten Selbstlink ist jede dieser Entitäten wieder als REST-Ressource verfügbar.

Um beispielsweise auf die Anzeigen im Demo-Flagship-Speicherort zuzugreifen, können Sie Folgendes aufrufen:

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship.json HTTP/1.1
Host: http://localhost:4502
```

Oder mithilfe von cURL:

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

Und um dann auf den einzelnen Bildschirm zuzugreifen, können Sie Folgendes aufrufen:

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502
```

## Ausführen von Aktionen auf Ressourcen {#executing-actions-on-the-resource}

Die von den API-Aufrufen zurückgegebene JSON-Datei kann eine Liste von Aktionen enthalten, die für die Ressource verfügbar sind.

Auf dem Bildschirm wird beispielsweise eine Aktion *broadcast-command* aufgeführt, die es erlaubt, einen Befehl an alle diesem Bildschirm zugeordneten Geräte zu senden.

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502
```

Oder mithilfe von cURL:

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

Rufen Sie Folgendes auf, um diese Aktion Trigger:

```xml
POST /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502

:operation=broadcast-command&msg=reboot
```

Oder mithilfe von cURL:

```xml
curl -u admin:admin -X POST -d ':operation=broadcast-command&msg=reboot' http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json
```
