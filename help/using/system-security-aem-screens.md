---
title: Sicherheits-Checkliste für AEM-Bildschirme
seo-title: Sicherheits-Checkliste für AEM-Bildschirme
description: Die Seite beschreibt die Sicherheitscheckliste für AEM-Bildschirme
seo-description: Die Seite beschreibt die Sicherheitscheckliste für AEM-Bildschirme
translation-type: tm+mt
source-git-commit: aa597424104880a79a8fcec4cfd08cd1a13a8aba

---


# Überlegungen zur Systemsicherheit für AEM Screens {#security-checklist}

Auf dieser Seite werden die Überlegungen zur Systemsicherheit für AEM Screens erläutert.


## White Paper zur Sicherheit von AEM Screens {#faqs-screens}

In diesem Abschnitt wird das Whitepaper beschrieben.


## Häufig gestellte Fragen zur Sicherheit von AEM Screens {#faqs-screens}

Bei den folgenden häufig gestellten Fragen wird von einer authentifizierten, registrierten Player-Architektur ausgegangen, bei der HTTPS als Kommunikationsprotokoll zwischen Player und AEM Server verwendet wird.

### FAQ 1 {#faq1}

Kann der Player-Traffic an einen böswilligen Server weitergeleitet und angewiesen werden, schädliche Medieninhalte herunterzuladen und wiederzugeben?

**Antwort** Es ist nicht möglich, da die HTTP-Verbindung beide Enden der Verbindung identifiziert und verschlüsselt. Wenn Sie versuchen, in der Mitte zu sein und abfangen, sehen Sie nur verschlüsselte Inhalte, und wenn Sie versuchen, die Identität des Servers zu imitieren, wird der Player Sie ablehnen, weil Ihr Zertifikat anders ist.


### FAQ 2 {#faq2}

Sollte ich HTTP oder HTTPs verwenden?
**Antwort** HTTPs verwenden Dies ist ein Muss, wenn Sie sich Sorgen um Sicherheit machen. Mit HTTPs wird die Kommunikation zwischen Player und Server verschlüsselt, und es wird fast unmöglich sein, den Inhalt abzufangen oder zu ändern.


### FAQ 3 {#faq3}

Gibt es beim Herunterladen von Inhalten irgendeine Art der Unterzeichnung des Inhalts oder Hashs?
**Antwort**Jedes Asset wird vom Server signiert (SHA) und anschließend vom Player für denselben Hash validiert, um die Integrität zu gewährleisten.
Wenn der Hash nicht übereinstimmt, versuchen wir, das 3-fache der Überprüfung erneut durchzuführen. Nach 3 Versuchen ist der Download-Befehl ungültig.


### FAQ 4 {#faq4}

Ist AEM Server sicher?
**Antwort** 4. Unter der Voraussetzung, dass Sie AMS verwenden, übernehmen wir die Sicherheit des Servers und verwenden die gleichen Funktionen wie Sites oder Assets.


### FAQ 5 {#faq5}

Ist das Gerät sicher?
**Antwort** Ein physisch beschädigter Spieler kann theoretisch manipuliert werden, um alle Inhalte wiederzugeben. Sie können den Player einfach ausschließen und einen USB/HDMI-Stick einstecken.

Daher empfehlen wir, die Geräte außer Reichweite zu bringen, vorzugsweise in einem gesicherten Container, wobei auch die Verkabelung gesichert ist. Deaktivieren Sie auch alle IR-Remote-Anschlüsse.

Wenn das Betriebssystem des Geräts nicht regelmäßig aktualisiert wird, kann das Betriebssystem Sicherheitslücken aufweisen und Remote-Angriffe über das Netzwerk zulassen.
[!NOTE]
>Es wird empfohlen, die Geräte mit geeigneten Remote-Update- und Steuerungsfunktionen (Remote-Desktop, MDM-Lösung usw.) zu instrumentieren.

Außerdem würde empfehlen, sie in ein privates Netzwerk zu setzen, nicht dem öffentlichen WLAN zum Beispiel ausgesetzt.


### FAQ 6 {#faq6}

Wie würde ein Hacker versuchen, einen Spieler zu kompromittieren?
**Antwort** Die einzige Möglichkeit, ein Player-Gerät zu kompromittieren, besteht darin,

1. Kompromittieren Sie das DNS, um die Identität des Servers in seinem Hostnamen zu imitieren, und
1. Kompromiss
   1. das Zertifikat serverseitig, um die Identität des Servers zu imitieren
   1. Gerät und imitieren Sie das Zertifikat clientseitig

1 und 2a sind meist unpraktisch in der Realität, und mit 2b benötigen Sie trotzdem Zugriff auf das Gerät, sodass Sie es auch austauschen können für Ihr eigenes Gerät, das gefälschte Inhalte ausführt.

Wir sind also nur so sicher wie ihr Netz und ihre Räumlichkeiten.

>[!IMPORTANT]
>Selbst wenn ein Gerät beschädigt ist, können Sie seine Anmeldeinformationen trotzdem ganz einfach widerrufen, damit es keine Verbindung mehr zu AEM herstellen kann.





