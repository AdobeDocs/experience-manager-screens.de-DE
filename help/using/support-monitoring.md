---
title: Support-Überwachung
description: Erfahren Sie mehr über die Best Practices für die Support-Überwachung von AEM Screens.
exl-id: b9d6f713-e26d-4f56-bedb-2d419a19a05c
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 40%

---

# Support-Überwachung {#support-monitoring}

Dieser Abschnitt enthält Best Practices zum Verwalten von Fehlern bei Geräten und Inhalten in Digital-Signage-Projekten.

Support-Überwachung umfasst:

* **Geräteüberwachung**
* **Inhaltsüberwachung**

## Inhaltsüberwachung {#content-monitoring}

Durch die Inhaltsüberwachung können Sie Fehler in Zusammenhang mit Inhalten beheben, die auf dem Bildschirm nicht ordnungsgemäß dargestellt werden:

1. Wenn ein Problem mit einem leeren Bildschirm auftritt:

   * Überprüfen Sie die *Vorschau* damit Sie sehen können, ob der Kanal einen schwarzen Bildschirm anzeigt.
   * Registrieren Sie eine *lokaler Chrome-Player* (als Erweiterung) auf Ihrem Laptop zu dieser Anzeige und sehen, ob dies einen schwarzen Bildschirm zeigt.
   * Klicken Sie mit der rechten Maustaste und überprüfen Sie die *Gültige Protokolle*.

   Wenn das Problem nicht im lokalen Player, sondern nur auf dem Gerät auftritt:

   * Überprüfen Sie die *Medientyp* (wird verwendet), die möglicherweise Probleme auf diesem Gerät haben, und auch überprüfen, ob der Inhalt erfolgreich lokal heruntergeladen wurde (Administrator-UI: clear channel cache).
   * Schließen Sie alle *Geräteprotokolle* zur schnellen Fehlerbehebung in das Ticket ein.
   * *Erfassen Sie Protokolle* vom Gerät aus AEM.

## Geräteüberwachung {#device-monitoring}

Geräteüberwachung im Zusammenhang mit der Überwachung des physischen Geräts, wenn ein Problem mit einem leeren Bildschirm auftritt:

1. Wenn ein Problem mit einem leeren Bildschirm auftritt:

   * Überprüfen Sie, ob das *Display* eingeschaltet ist.
   * Überprüfen Sie, ob die *Computer* eingeschaltet ist und ein Signal sendet.
   * Klicken Sie mit der rechten Maustaste und prüfen Sie die *entsprechenden Protokolle*.
