---
title: Support-Überwachung
description: Erfahren Sie mehr über das Handbuch zur Support-Überwachung für AEM Screens Best Practices .
exl-id: b9d6f713-e26d-4f56-bedb-2d419a19a05c
source-git-commit: 1e8beb9dfaf579250138d4a41eeec88cc81f2d39
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 65%

---

# Support-Überwachung {#support-monitoring}

Dieser Abschnitt enthält Best Practices zum Verwalten von Fehlern bei Geräten und Inhalten in Digital-Signage-Projekten.

Support-Überwachung umfasst:

* **Geräteüberwachung**
* **Inhaltsüberwachung**

## Inhaltsüberwachung {#content-monitoring}

Mit der Inhaltsüberwachung können Sie Probleme im Zusammenhang mit Inhalten beheben, die nicht ordnungsgemäß auf dem Bildschirm angezeigt werden:

1. Wenn ein leerer (schwarzer) Bildschirm auftritt:

   * Überprüfen *Vorschau* damit Sie sehen können, ob der Kanal einen schwarzen Bildschirm anzeigt.
   * Registrieren Sie auf Ihrem Notebook einen *lokalen Chrome-Player* (als Erweiterung) für das Display, um zu sehen, ob ein schwarzer Bildschirm angezeigt wird.
   * Rechtsklicken und überprüfen *Gültige Protokolle*.

   Wenn dies nicht im lokalen Player, sondern nur auf dem Gerät geschieht:

   * Überprüfen Sie den (verwendeten) *Medientyp*, bei dem möglicherweise Probleme auf dem Gerät auftreten, und prüfen Sie, ob der Inhalt erfolgreich lokal heruntergeladen wurde (Administrator-UI: clear channel cache).
   * Schließen Sie alle *Geräteprotokolle* zur schnellen Fehlerbehebung in das Ticket ein.
   * *Erfassen Sie Protokolle* vom Gerät aus AEM.

## Geräteüberwachung {#device-monitoring}

Geräteüberwachung im Zusammenhang mit der Überwachung des physischen Geräts, wenn ein Problem mit schwarzem Bildschirm auftritt:

1. Wenn ein leerer (schwarzer) Bildschirm auftritt:

   * Überprüfen Sie, ob das *Display* eingeschaltet ist.
   * Überprüfen Sie, ob der *Computer* eingeschaltet ist und Signale sendet.
   * Rechtsklick, Überprüfung und Prüfung *Gültige Protokolle*.
