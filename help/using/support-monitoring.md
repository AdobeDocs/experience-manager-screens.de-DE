---
title: Support-Überwachung
seo-title: Support-Überwachung für AEM Screens
description: Auf dieser Seite werden die Best Practices für die Support-Überwachung von AEM Screens beschrieben.
seo-description: Auf dieser Seite werden die Best Practices für die Support-Überwachung von AEM Screens beschrieben.
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 100%

---


# Support-Überwachung {#support-monitoring}

Dieser Abschnitt enthält Best Practices zum Verwalten von Fehlern bei Geräten und Inhalten in Digital Signage-Projekten.

Support-Überwachung umfasst:

* **Geräteüberwachung**
* **Inhaltsüberwachung**

## Inhaltsüberwachung {#content-monitoring}

Per Inhaltsüberwachung können Sie Fehler in Zusammenhang mit Inhalten beheben, die auf dem Bildschirm nicht ordnungsgemäß dargestellt werden:

1. Wenn ein leerer (schwarzer) Bildschirm auftritt:

   * Überprüfen Sie die *Vorschau*, um zu ermitteln, ob der Kanal einen schwarzen Bildschirm anzeigt.
   * Registrieren Sie auf Ihrem Notebook einen *lokalen Chrome-Player* (als Erweiterung) für das Display, um zu sehen, ob ein schwarzer Bildschirm angezeigt wird.
   * Klicken Sie mit der rechten Maustaste und überprüfen Sie die *entsprechenden Protokolle*.

   Wenn das nicht beim lokalen Player, sondern nur auf dem Gerät geschieht:

   * Überprüfen Sie den (verwendeten) *Medientyp*, bei dem möglicherweise Probleme auf dem Gerät auftreten, und prüfen Sie, ob der Inhalt erfolgreich lokal heruntergeladen wurde (Administrator-UI: clear channel cache).
   * Schließen Sie alle *Geräteprotokolle* zur schnellen Fehlerbehebung in das Ticket ein.
   * *Erfassen Sie Protokolle* vom Gerät aus AEM.


## Geräteüberwachung {#device-monitoring}

Geräteüberwachung im Zusammenhang mit der Überwachung des physischen Geräts, wenn ein Problem mit schwarzem Bildschirm auftritt:

1. Wenn ein leerer (schwarzer) Bildschirm auftritt:

   * Überprüfen Sie, ob das *Display* eingeschaltet ist.
   * Überprüfen Sie, ob der *Computer* eingeschaltet ist und Signale sendet.
   * Klicken Sie mit der rechten Maustaste und prüfen Sie die *entsprechenden Protokolle*.

