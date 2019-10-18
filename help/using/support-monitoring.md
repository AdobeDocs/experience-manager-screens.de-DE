---
title: Unterstützungsüberwachung
seo-title: Support-Überwachung für AEM-Bildschirme
description: Die Seite beschreibt den Leitfaden zur Support-Überwachung für AEM Screens - Best Practices
seo-description: Die Seite beschreibt den Leitfaden zur Support-Überwachung für AEM Screens - Best Practices
translation-type: tm+mt
source-git-commit: 3c91e0ec80b29bebcc066f45a1eef1fd74e00a13

---


# Unterstützungsüberwachung {#support-monitoring}

Dieser Abschnitt enthält Best Practices zum Verwalten von Geräte- und Inhaltsanomalien in einem Projekt für digitale Signaturen.

Die Unterstützungsüberwachung umfasst:

* **Geräteüberwachung**
* **Inhaltsüberwachung**

## Inhaltsüberwachung {#content-monitoring}

Mit der Inhaltsüberwachung können Sie Fehler in Zusammenhang mit Inhalten beheben, die nicht ordnungsgemäß auf dem Bildschirm angezeigt werden:

1. Wenn ein Problem mit dem leeren Bildschirm auftritt:

   * Überprüfen Sie die *Vorschau* , um zu sehen, ob der Kanal einen schwarzen Bildschirm anzeigt.
   * Registrieren Sie einen *lokalen Chrome-Player* (als Erweiterung) auf Ihrem Laptop, um zu sehen, ob dies einen schwarzen Bildschirm zeigt.
   * Klicken Sie mit der rechten Maustaste und überprüfen Sie die *entsprechenden Protokolle*.
   Wenn dies nicht auf dem lokalen Player, sondern nur auf dem Gerät geschieht:

   * Überprüfen Sie den *Medientyp* (der verwendet wird), bei dem Probleme auf dem Gerät auftreten können, und überprüfen Sie, ob der Inhalt lokal heruntergeladen wurde (Administrator-UI: Clear Channel Cache).
   * Schließen Sie alle *Geräteprotokolle* zur schnellen Fehlerbehebung in das Ticket ein.
   * *Erfassen von Protokollen* vom Gerät aus AEM


## Geräteüberwachung {#device-monitoring}

Geräteüberwachung bei der Überwachung des physischen Geräts, wenn ein Problem mit dem leeren Bildschirm auftritt:

1. Wenn ein Problem mit dem leeren Bildschirm auftritt:

   * Überprüfen Sie, ob das *Display* eingeschaltet ist.
   * Überprüfen Sie, ob der *Computer* eingeschaltet ist und das Signal sendet.
   * Klicken Sie mit der rechten Maustaste, überprüfen Sie die *entsprechenden Protokolle*.

