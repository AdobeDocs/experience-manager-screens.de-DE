---
title: Sicherheits-Checkliste für AEM Screens
description: Erfahren Sie mehr über die Sicherheitscheckliste für AEM Screens.
source-git-commit: b65e59473e175e7c1b31fba900bb7e47eff3a263
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 49%

---


# Überlegungen zur Systemsicherheit für AEM Screens {#security-checklist}

>[!IMPORTANT]
>Dies ist eine interne Git-Ressource.

Auf dieser Seite werden die Überlegungen zur Systemsicherheit für AEM Screens erläutert.


## Whitepaper zur Sicherheit von AEM Screens {#white-paper}

In diesem Abschnitt wird das Whitepaper beschrieben. (Ausstehender Whitepaper-Anhang)


## Häufig gestellte Fragen zur AEM Screens-Sicherheit {#faqs-screens}

Bei den folgenden häufig gestellten Fragen wird von einer authentifizierten, registrierten Player-Architektur ausgegangen, bei der HTTPS als Kommunikationsprotokoll zwischen Player und AEM-Server verwendet wird.

### Frage 1 {#faq1}

Kann der Player-Traffic an einen böswilligen Server umgeleitet und angewiesen werden, schädliche Medieninhalte herunterzuladen und wiederzugeben?

**Antwort**

Dies ist nicht möglich, da die HTTP-Verbindung beide Enden der Verbindung identifiziert und verschlüsselt. Wenn Sie versuchen, sich in der Mitte zu befinden und sie abzufangen, sehen Sie nur verschlüsselten Inhalt. Wenn Sie versuchen, die Identität des Servers zu imitieren, lehnt der Player Sie ab, da Ihr Zertifikat anders ist.


### Frage 2 {#faq2}

Sollte ich HTTP oder HTTPs verwenden?

**Antwort**

Verwenden Sie HTTPs. Dies ist unabdingbar, wenn Sie um die Sicherheit besorgt sind. Mit HTTPs wird die Kommunikation zwischen Player und Server verschlüsselt. Das Abfangen oder Ändern des Inhalts ist nicht möglich.


### Frage 3 {#faq3}

Gibt es beim Herunterladen von Inhalten irgendeine Art von Signierung des Inhalts oder des Hash?

**Antwort**

Jedes Asset wird vom Server signiert (SHA) und dann vom Player für denselben Hash validiert, um die Integrität zu gewährleisten.
Wenn der Hash nicht übereinstimmt, versucht die Software, dreimal erneut zu validieren. Nach drei Versuchen wird der Download-Befehl als ungültig betrachtet.


### Frage 4 {#faq4}

Ist der AEM-Server sicher?

**Antwort**

Wenn Sie AMS verwenden, übernimmt die Software die gesamte Server-Sicherheit und verwendet dieselben Funktionen wie Sites oder Assets.


### Frage 5 {#faq5}

Ist das Gerät sicher?

**Antwort**

Ein physisch kompromittierter Player kann theoretisch manipuliert werden, um beliebige Inhalte wiederzugeben. Sie können den Player auch abziehen und einen USB-/HDMI-Stick einstecken.

Schließen Sie die Geräte außer Reichweite, vorzugsweise in einen gesicherten Behälter, wobei auch die Verkabelung gesichert ist. Deaktivieren Sie auch alle IR-Remote-Anschlüsse.

Wenn das Betriebssystem des Geräts nicht regelmäßig aktualisiert wird, kann das Betriebssystem Sicherheitslücken aufweisen und Remote-Angriffe über das Netzwerk zulassen.

>[!NOTE]
>
>Es wird empfohlen, die Geräte mit angemessenen Remote-Update- und -Steuerungsfunktionen (Remote-Desktop, MDM-Lösung usw.) zu instrumentieren. Es wird auch empfohlen, ein privates Netzwerk zu verwenden, also kein öffentliches WLAN.


### Frage 6 {#faq6}

Wie würde ein Hacker versuchen, einen Player zu kompromittieren?

**Antwort**

Die einzige Möglichkeit, ein Player-Gerät zu kompromittieren, besteht darin,

1. das DNS zu kompromittieren, um den Server auf diesem Hostnamen zu stellvertreten, und
1. das
   1. Zertifikat Server-seitig zu kompromittieren, um sich als Server auszugeben
   1. und das Zertifikat auf der Client-Seite zu imitieren.

>[!IMPORTANT]
>Selbst wenn ein Gerät kompromittiert ist, können Sie seine Anmeldeinformationen dennoch einfach widerrufen, damit es keine Verbindung mehr zu AEM herstellen kann.





