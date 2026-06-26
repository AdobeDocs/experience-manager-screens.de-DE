---
title: Support-Überwachung
description: Erfahren Sie mehr über die Best Practices für die Support-Überwachung von AEM Screens.
exl-id: b9d6f713-e26d-4f56-bedb-2d419a19a05c
TQID: https://experienceleague.adobe.com/uqtkwa1zcJ58tJOxWT0gWkOhAM-C-5zEdcFLjrHa1-Q
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 6ffdfa02d948d50b544f6fa5164dc6dca8bff638
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 82%

---

# Support-Überwachung {#support-monitoring}

>[!IMPORTANT]
>Dieser Inhalt gilt für AEM On-Premise/AMS (AEM 6.5LTS und AEM 6.5). Informationen zu AEM as a Cloud Service Screens-Inhalten finden Sie im [AEM as a Cloud Service-Handbuch](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

Dieser Abschnitt enthält Best Practices zum Verwalten von Fehlern bei Geräten und Inhalten in Digital-Signage-Projekten.

Support-Überwachung umfasst:

* **Geräteüberwachung**
* **Inhaltsüberwachung**

## Inhaltsüberwachung {#content-monitoring}

Durch die Inhaltsüberwachung können Sie Fehler in Zusammenhang mit Inhalten beheben, die auf dem Bildschirm nicht ordnungsgemäß dargestellt werden:

1. Wenn ein leerer (schwarzer) Bildschirm angezeigt wird:

   * Überprüfen Sie die *Vorschau*, um zu ermitteln, ob der Kanal einen schwarzen Bildschirm anzeigt.
   * Registrieren Sie auf Ihrem Laptop einen *lokalen Chrome-Player* (als Erweiterung) für die Anzeige, um festzustellen, ob ein schwarzer Bildschirm angezeigt wird.
   * Klicken Sie mit der rechten Maustaste und überprüfen Sie die *entsprechenden Protokolle*.

   Wenn das Problem nicht beim lokalen Player auftritt, sondern nur auf dem Gerät:

   * Überprüfen Sie den (verwendeten) *Medientyp*, bei dem möglicherweise Probleme auf dem Gerät auftreten, und prüfen Sie, ob der Inhalt erfolgreich lokal heruntergeladen wurde (Administrator-Benutzeroberfläche: Kanal-Cache löschen).
   * Schließen Sie alle *Geräteprotokolle* zur schnellen Fehlerbehebung in das Ticket ein.
   * *Erfassen Sie Protokolle* vom Gerät aus AEM.

## Geräteüberwachung {#device-monitoring}

Geräteüberwachung im Zusammenhang mit der Überwachung des physischen Geräts, wenn ein Problem mit schwarzem Bildschirm auftritt:

1. Wenn ein leerer (schwarzer) Bildschirm angezeigt wird:

   * Überprüfen Sie, ob das *Display* eingeschaltet ist.
   * Überprüfen Sie, ob der *Computer* eingeschaltet ist und ein Signal sendet.
   * Klicken Sie mit der rechten Maustaste und prüfen Sie die *entsprechenden Protokolle*.

