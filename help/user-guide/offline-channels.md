---
title: Offline-Kanäle
seo-title: Offline Channels
description: Der AEM Screens Player bietet Offline-Unterstützung für Kanäle durch Nutzung der ContentSync-Technologie. Auf dieser Seite erfahren Sie mehr über Update-Handler und die Aktivierung der Offline-Konfiguration für einen Kanal.
seo-description: The AEM Screens player provides offline support for channels by leveraging the ContentSync technology. Follow this page to learn more about update handlers and enabling offline configuration for a channel.
uuid: 18b9d175-ff26-42db-86aa-5ea978909f71
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: bd572743-652f-4fc5-8b75-a3c4c74536f4
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 5ad1046f-8b64-490b-9966-ce9008180d54
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 59%

---

# Offline-Kanäle {#offline-channels}

Der Screens-Player bietet Offline-Unterstützung für die Kanäle durch Nutzung der ***ContentSync***-Technologie.

Die Player verwenden einen lokalen HTTP-Server, um die entpackten Inhalte bereitzustellen.

Wenn ein Kanal für die Ausführung konfiguriert ist *online*, stellt der Player die Kanalressourcen bereit, indem er auf den AEM-Server zugreift, aber wenn der Kanal für die Ausführung konfiguriert ist *offline*, stellt der Player die Kanalressourcen von einem lokalen HTTP-Server bereit.

Der Workflow für den Prozess sieht wie folgt aus:

1. Analyse der gewünschten Seite(n)
1. Sammeln aller zugehörigen Assets
1. Alles in einer ZIP-Datei verpacken
1. Laden Sie die ZIP-Datei herunter und extrahieren Sie sie lokal
1. Lokale Kopie des Inhalts anzeigen

## Update-Handler {#update-handlers}

***ContentSync*** verwendet Update-Handler, um alle erforderlichen Seiten und Assets für ein bestimmtes Projekt zu analysieren und zu sammeln. AEM Screens verwendet die folgenden Update-Handler:

### Allgemeine Optionen {#common-options}

* *type*: Der zu verwendende Update-Handler-Typ
* *path*: Pfad zur Ressource
* *[targetRootDirectory]*: Zielordner in der ZIP-Datei

<table>
 <tbody>
  <tr>
   <td><strong>Typ</strong></td> 
   <td><strong>Beschreibung</strong></td> 
   <td><strong>Optionen</strong></td> 
  </tr>
  <tr>
   <td>channels</td> 
   <td>erfasst einen Kanal</td> 
   <td>extension: Erweiterung der zu erfassenden Ressource<br /> [pathSuffix='']: Suffix zum Hinzufügen zum Kanalpfad<br /> </td> 
  </tr>
  <tr>
   <td>clientlib</td> 
   <td>erfasst die angegebene Client-Bibliothek</td> 
   <td>[extension='']: kann entweder css oder js sein, um nur das Erstere oder nur das Letztere zu sammeln</td> 
  </tr>
  <tr>
   <td>assetrenditions</td> 
   <td>erfasst die Asset-Wiedergaben</td> 
   <td>[renditions=[]]: Liste der zu erfassenden Wiedergaben. Standardmäßig wird die ursprüngliche Wiedergabe verwendet</td> 
  </tr>
  <tr>
   <td>copy</td> 
   <td>kopiert die angegebene Struktur aus dem Pfad</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Testen der ContentSync-Konfiguration {#testing-contentsync-configuration}

Befolgen Sie die folgenden Schritte, um die ContentSync-Konfiguration zu testen:

1. Öffnen Sie `https://localhost:4502/libs/cq/contentsync/content/console.html`
1. Wählen Sie Ihre Konfiguration in der Liste aus
1. Klicken Sie auf „Cache löschen“
1. Klicken Sie auf „Cache aktualisieren“
1. Klicken Sie auf „Vollständig herunterladen“
1. Entpacken Sie die ZIP-Datei
1. Starten Sie einen lokalen Server im extrahierten Ordner
1. Öffnen Sie Ihre Startseite und überprüfen Sie Ihren Anwendungsstatus

## Aktivieren der Offline-Konfiguration für einen Kanal {#enabling-offline-config-for-a-channel}

Gehen Sie wie folgt vor, um die Offline-Konfiguration für einen Kanal zu aktivieren:

1. Inspect Sie den Kanalinhalt und überprüfen Sie, ob er von einer AEM Instanz angefordert wird (Online).

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Navigieren Sie zum Kanal-Dashboard und klicken Sie auf **...** im Bedienfeld **KANALINFORMATIONEN**, um die Eigenschaften zu ändern.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Navigieren Sie zu den Kanaleigenschaften und stellen Sie sicher, dass das Kontrollkästchen auf der Registerkarte **Kanal** deaktiviert ist. Klicken Sie auf **Speichern und schließen**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Bevor der Inhalt ordnungsgemäß auf dem Gerät bereitgestellt wird, klicken Sie auf **Offline-Inhalt aktualisieren**.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   Der **Offline**-Status unter **EIGENSCHAFTEN** wird ebenfalls entsprechend aktualisiert.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Kontrollieren Sie den Inhalt des Kanals und überprüfen Sie, ob er vom lokalen Player-Cache angefordert wird.

   ![chlimage_1-26](assets/chlimage_1-26.png)

>[!NOTE]
>
>Weitere Informationen zur Vorlage für benutzerdefinierte Offline-Ressourcen-Handler und zu den Mindestanforderungen finden Sie in der `pom.xml` Informationen zu diesem spezifischen Projekt finden Sie unter [Vorlage für benutzerdefinierte Handler](/help/user-guide/developing-custom-component-tutorial-develop.md#custom-handlers) in **Entwickeln einer benutzerdefinierten Komponente für AEM Screens**.
