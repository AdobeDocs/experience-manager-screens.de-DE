---
title: REST-APIs
description: Erfahren Sie, wie AEM Screens eine einfache RESTful-API bereitstellt, die der Siren-Spezifikation entspricht. Lernen Sie zudem, wie Sie in der Inhaltsstruktur navigieren und Befehle an Geräte in der Umgebung senden.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: ac01935a-c3ff-485a-b60e-227fb94c75b0
TQID: https://experienceleague.adobe.com/qh3gh-3IzKyUA4fr79v7JAT5WAq2Q2eZTqTlOAC7yN0
product_v2: id: a27b4747-2f72-4fb7-9936-be5d11dd2c4aid: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ce44533e-8ec8-4e11-a9e9-78b0fe561832
source-git-commit: 0b0bfcd803c3da9298122200a0a1715fc2d5e49c
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 95%

---

# REST-APIs{#rest-apis}

AEM Screens stellt eine einfache RESTful-API bereit, die der [Siren](https://github.com/kevinswiber/siren)-Spezifikation entspricht. Damit können Sie in der Inhaltsstruktur navigieren und Befehle an Geräte in der Umgebung senden.

Auf die API kann unter [*http://localhost:4502/api/screens.json zugegriffen*](http://localhost:4502/api/screens.json).

## Navigieren in der Inhaltsstruktur {#navigating-content-structure}

Die von den API-Aufrufen zurückgegebene JSON-Datei listet die Entitäten auf, die im Zusammenhang mit der aktuellen Ressource stehen. Über den aufgeführten Selbst-Link kann auf jede dieser Entitäten wieder als REST-Ressource zugegriffen werden.

Um beispielsweise auf die Bildschirme an dem Flagship-Standort der Demo zuzugreifen, können Sie Folgendes aufrufen:

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

Um diese Aktion auszulösen, rufen Sie Folgendes auf:

```xml
POST /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502

:operation=broadcast-command&msg=reboot
```

Oder mithilfe von cURL:

```xml
curl -u admin:admin -X POST -d ':operation=broadcast-command&msg=reboot' http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json
```
