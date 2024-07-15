---
title: Support-Überwachung
description: Erfahren Sie mehr über die Best Practices für die Support-Überwachung von AEM Screens.
exl-id: b9d6f713-e26d-4f56-bedb-2d419a19a05c
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%

---

# Support-Überwachung {#support-monitoring}

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
