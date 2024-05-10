---
title: Sicherheits-Checkliste für AEM Screens
description: Erfahren Sie mehr über die Sicherheitscheckliste für AEM Screens.
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 80%

---


# Überlegungen zur Systemsicherheit für AEM Screens {#security-checklist}

>[!IMPORTANT]
>Eine interne Git-Ressource.

Auf dieser Seite werden Überlegungen zur Systemsicherheit für AEM Screens erläutert.


## Whitepaper zur Sicherheit von AEM Screens {#white-paper}

In diesem Abschnitt wird das Whitepaper beschrieben. (Ausstehender Whitepaper-Anhang)


## Häufig gestellte Fragen zur Sicherheit von AEM Screens {#faqs-screens}

Die folgenden häufig gestellten Fragen stellen eine authentifizierte, registrierte Player-Architektur dar. Es verwendet HTTPS als Kommunikationsprotokoll zwischen Player und AEM Server.

### Frage 1 {#faq1}

Kann der Player-Traffic an einen böswilligen Server umgeleitet und angewiesen werden, schädliche Medieninhalte herunterzuladen und wiederzugeben?

**Antwort**

Dies ist nicht möglich, da die HTTP-Verbindung beide Enden der Verbindung identifiziert und verschlüsselt. Wenn Sie versuchen, sich in der Mitte zu befinden und sie abzufangen, sehen Sie nur verschlüsselten Inhalt. Wenn Sie versuchen, die Identität des Servers zu imitieren, werden Sie vom Player abgelehnt, da Ihr Zertifikat abweicht.


### Frage 2 {#faq2}

Sollte ich HTTP oder HTTPs verwenden?

**Antwort**

Verwenden Sie HTTPs. Dieses Protokoll ist ein Muss, wenn es um Sicherheit geht. Mit HTTPs wird die Kommunikation zwischen Player und Server verschlüsselt. Damit ist es unmöglich, den Inhalt abzufangen oder zu ändern.


### Frage 3 {#faq3}

Gibt es beim Herunterladen von Inhalten irgendeine Art von Signierung des Inhalts oder des Hash?

**Antwort**

Jedes Asset wird vom Server signiert (SHA). Der Player überprüft ihn dann auf denselben Hash, um die Integrität zu gewährleisten.
Wenn der Hash nicht übereinstimmt, versucht die Software dreimal, erneut zu validieren. Nach drei Versuchen wird der Download-Befehl als ungültig betrachtet.


### Frage 4 {#faq4}

Ist der AEM-Server sicher?

**Antwort**

Unter der Voraussetzung, dass Sie AMS verwenden, kümmert sich die Software um die gesamte Server-Sicherheit mit denselben Funktionen wie Sites oder Assets.


### Frage 5 {#faq5}

Ist das Gerät sicher?

**Antwort**

Ein physisch kompromittierter Player kann theoretisch manipuliert werden, um beliebige Inhalte wiederzugeben. Sie könnten den Player auch ausstecken und einen USB-/HDMI-Stick einstecken.

Wahren Sie die Geräte unzugänglich auf – vorzugsweise in einem gesicherten Container – wobei die Verkabelung ebenfalls gesichert ist. Deaktivieren Sie auch alle IR-Remote-Anschlüsse.

Wenn das Betriebssystem des Geräts nicht regelmäßig aktualisiert wird, kann das Betriebssystem Sicherheitslücken aufweisen und Remote-Angriffe über das Netzwerk zulassen.

>[!NOTE]
>
>Es wird empfohlen, die Geräte mit geeigneten Fernaktualisierungs- und Fernsteuerungsfunktionen (Remote-Desktop, MDM-Lösung usw.) auszustatten. Es wird auch empfohlen, ein privates Netzwerk zu verwenden, also z. B. kein öffentliches WLAN.


### Frage 6 {#faq6}

Wie würde ein Hacker versuchen, einen Player zu kompromittieren?

**Antwort**

Die einzige Möglichkeit, ein Player-Gerät zu kompromittieren, besteht darin,

1. den DNS zu kompromittieren, um sich als Server auf seinem Host-Namen auszugeben, und
1. das
   1. Zertifikat Server-seitig zu kompromittieren, um sich als Server auszugeben
   1. und das Zertifikat auf der Client-Seite zu imitieren.

>[!IMPORTANT]
>Selbst wenn ein Gerät kompromittiert ist, können Sie seine Anmeldeinformationen problemlos widerrufen, sodass keine Verbindung mehr zu AEM hergestellt werden kann.





