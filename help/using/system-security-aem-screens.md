---
title: Sicherheits-Checkliste für AEM-Bildschirme
seo-title: Sicherheits-Checkliste für AEM-Bildschirme
description: Die Seite beschreibt die Sicherheitscheckliste für AEM-Bildschirme
seo-description: Die Seite beschreibt die Sicherheitscheckliste für AEM-Bildschirme
translation-type: tm+mt
source-git-commit: 72551a4b56d1db851cad71abd2ce8c0b02bbbc30

---


# Überlegungen zur Systemsicherheit für AEM Screens {#security-checklist}

Auf dieser Seite werden die Überlegungen zur Systemsicherheit für AEM Screens erläutert.


## White Paper zur Sicherheit von AEM Screens {#white-paper}

In diesem Abschnitt wird das Whitepaper beschrieben. (Ausstehende Anlage zum Weißbuch)


## Häufig gestellte Fragen zur Sicherheit von AEM Screens {#faqs-screens}

Bei den folgenden häufig gestellten Fragen wird von einer authentifizierten, registrierten Player-Architektur ausgegangen, bei der HTTPS als Kommunikationsprotokoll zwischen Player und AEM Server verwendet wird.

### FAQ 1 {#faq1}

Kann der Player-Traffic an einen böswilligen Server weitergeleitet und angewiesen werden, schädliche Medieninhalte herunterzuladen und wiederzugeben?

**Antwort**

Dies ist nicht möglich, da die HTTP-Verbindung beide Enden der Verbindung identifiziert und verschlüsselt. Wenn Sie versuchen, in der Mitte zu sein und abfangen, sehen Sie nur verschlüsselte Inhalte, und wenn Sie versuchen, die Identität des Servers zu imitieren, wird der Player Sie ablehnen, weil Ihr Zertifikat anders ist.


### FAQ 2 {#faq2}

Sollte ich HTTP oder HTTPs verwenden?

**Antwort**

Verwenden Sie HTTPs. Dies ist ein Muss, wenn Sie sich Sorgen um Sicherheit machen. Mit HTTPs wird die Kommunikation zwischen Player und Server verschlüsselt, und es wird fast unmöglich sein, den Inhalt abzufangen oder zu ändern.


### FAQ 3 {#faq3}

Gibt es beim Herunterladen von Inhalten irgendeine Art der Unterzeichnung des Inhalts oder Hashs?

**Antwort**

Jedes Asset wird vom Server signiert (SHA) und anschließend vom Player für denselben Hash validiert, um die Integrität zu gewährleisten.
Wenn der Hash nicht übereinstimmt, versuchen wir, das 3-fache der Überprüfung erneut durchzuführen. Nach 3 Versuchen ist der Download-Befehl ungültig.


### FAQ 4 {#faq4}

Ist AEM Server sicher?

**Antwort**

s 4. Unter der Voraussetzung, dass Sie AMS verwenden, übernehmen wir die Sicherheit des Servers und verwenden die gleichen Funktionen wie Sites oder Assets.


### FAQ 5 {#faq5}

Ist das Gerät sicher?

**Antwort**

Ein physisch kompromittierter Spieler kann theoretisch manipuliert werden, um jeden Inhalt wiederzugeben. Sie können den Player einfach ausschließen und einen USB/HDMI-Stick einstecken.

Es wird daher empfohlen, die Geräte außer Reichweite zu bringen, vorzugsweise in einem gesicherten Container, wobei auch die Verkabelung gesichert ist. Deaktivieren Sie auch alle IR-Remote-Anschlüsse.

Wenn das Betriebssystem des Geräts nicht regelmäßig aktualisiert wird, kann das Betriebssystem Sicherheitslücken aufweisen und Remote-Angriffe über das Netzwerk zulassen.
>[!NOTE]
>Es wird empfohlen, die Geräte mit geeigneten Remote-Update- und Steuerungsfunktionen (Remote-Desktop, MDM-Lösung usw.) zu instrumentieren. Es wird auch empfohlen, ein privates Netzwerk zu verwenden, das beispielsweise nicht dem öffentlichen WIFI ausgesetzt ist.


### FAQ 6 {#faq6}

Wie würde ein Hacker versuchen, einen Spieler zu kompromittieren?

**Antwort**

Die einzige Möglichkeit, ein Player-Gerät zu kompromittieren, besteht darin,

1. den DNS zu gefährden, um den Server auf seinem Hostnamen zu imitieren, und
1. Kompromiss
   1. das Zertifikat serverseitig, um die Identität des Servers zu imitieren
   1. Gerät und imitieren Sie das Zertifikat clientseitig

>[!IMPORTANT]
>Auch wenn ein Gerät beschädigt ist, können Sie seine Anmeldeinformationen trotzdem ganz einfach widerrufen, damit es keine Verbindung mehr zu AEM herstellen kann.





