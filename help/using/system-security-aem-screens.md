---
title: Sicherheits-Checkliste für AEM Screens
seo-title: Sicherheits-Checkliste für AEM Screens
description: Auf dieser Seite wird die Sicherheits-Checkliste für AEM Screens beschrieben.
seo-description: Auf dieser Seite wird die Sicherheits-Checkliste für AEM Screens beschrieben.
translation-type: ht
source-git-commit: f25176be89424059b8c51296969f069687328536
workflow-type: ht
source-wordcount: '473'
ht-degree: 100%

---


# Überlegungen zur Systemsicherheit für AEM Screens {#security-checklist}

>[!IMPORTANT]
>
>Dies ist eine interne Git-Ressource.

Auf dieser Seite werden die Überlegungen zur Systemsicherheit für AEM Screens erläutert.


## Whitepaper zur Sicherheit von AEM Screens {#white-paper}

In diesem Abschnitt wird das Whitepaper beschrieben. (Ausstehender Whitepaper-Anhang)


## Häufig gestellte Fragen zur Sicherheit von AEM Screens {#faqs-screens}

Bei den folgenden häufig gestellten Fragen wird von einer authentifizierten, registrierten Player-Architektur ausgegangen, bei der HTTPS als Kommunikationsprotokoll zwischen Player und AEM-Server verwendet wird.

### Frage 1 {#faq1}

Kann der Player-Traffic an einen böswilligen Server umgeleitet und angewiesen werden, schädliche Medieninhalte herunterzuladen und wiederzugeben?

**Antwort**

Dies ist nicht möglich, da die HTTP-Verbindung beide Enden der Verbindung identifiziert und verschlüsselt. Wenn Sie versuchen, den Traffic in der Mitte abzufangen, sehen Sie nur verschlüsselte Inhalte. Wenn Sie versuchen, sich als Server auszugeben, lehnt der Player Sie ab, da Ihr Zertifikat anders ist.


### Frage 2 {#faq2}

Sollte ich HTTP oder HTTPs verwenden?

**Antwort**

Verwenden Sie HTTPs. Dies ist unabdingbar, wenn Sie um die Sicherheit besorgt sind. Mit HTTPs wird die Kommunikation zwischen Player und Server verschlüsselt. Damit ist es fast unmöglich, den Inhalt abzufangen oder zu ändern.


### Frage 3 {#faq3}

Gibt es beim Herunterladen von Inhalten irgendeine Art von Signierung des Inhalts oder des Hash?

**Antwort**

Jedes Asset wird vom Server signiert (SHA) und dann vom Player für denselben Hash validiert, um die Integrität zu gewährleisten.
Wenn der Hash nicht übereinstimmt, versuchen wir dreimal, erneut zu validieren. Nach 3 Versuchen betrachten wir den Download-Befehl als ungültig.


### Frage 4 {#faq4}

Ist der AEM-Server sicher?

**Antwort**

Antwort 4. Unter der Voraussetzung, dass Sie AMS verwenden, kümmern wir uns um die gesamte Server-Sicherheit mit denselben Funktionen wie Sites oder Assets.


### Frage 5 {#faq5}

Ist das Gerät sicher?

**Antwort**

Ein physisch kompromittierter Player kann theoretisch manipuliert werden, um beliebige Inhalte wiederzugeben. Sie könnten den Player auch einfach ausstecken und einen USB-/HDMI-Stick einstecken.

Es wird daher empfohlen, die Geräte unzugänglich – vorzugsweise in einem gesicherten Container – aufzubewahren, wobei die Verkabelung ebenfalls gesichert ist. Deaktivieren Sie auch alle IR-Remote-Anschlüsse.

Wenn das Betriebssystem des Geräts nicht regelmäßig aktualisiert wird, kann das Betriebssystem Sicherheitslücken aufweisen und Remote-Angriffe über das Netzwerk zulassen.

>[!NOTE]
>
>Es wird empfohlen, die Geräte mit geeigneten Fernaktualisierungs- und Fernsteuerungsfunktionen (Remote-Desktop, MDM-Lösung usw.) auszustatten. Es wird auch empfohlen, ein privates Netzwerk zu verwenden, also kein öffentliches WLAN.


### Frage 6 {#faq6}

Wie würde ein Hacker versuchen, einen Player zu kompromittieren?

**Antwort**

Die einzige Möglichkeit, ein Player-Gerät zu kompromittieren, besteht darin,

1. den DNS zu kompromittieren, um sich als Server auf seinem Host-Namen auszugeben, und
1. das
   1. Zertifikat Server-seitig zu kompromittieren, um sich als Server auszugeben
   1. und das Zertifikat auf der Client-Seite zu imitieren.

>[!IMPORTANT]
>Selbst wenn ein Gerät kompromittiert ist, können Sie seine Anmeldeinformationen problemlos widerrufen, sodass keine Verbindung mehr zu AEM hergestellt werden kann.





