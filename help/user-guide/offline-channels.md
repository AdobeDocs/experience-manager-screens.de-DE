---
title: Offline-Kanäle
description: Erfahren Sie mehr darüber, wie AEM Screens Player mithilfe der ContentSync-Technologie Offline-Unterstützung für Kanäle bietet.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 5ad1046f-8b64-490b-9966-ce9008180d54
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 45%

---

# Offline-Kanäle {#offline-channels}

Der Screens-Player bietet Offline-Unterstützung für die Kanäle durch Verwendung der ***ContentSync*** Technologie.

Die Player verwenden einen lokalen HTTP-Server, um die entpackten Inhalte bereitzustellen.

Wenn ein Kanal für die Ausführung konfiguriert ist *online*, stellt der Player die Kanalressourcen durch Zugriff auf den AEM bereit. Wenn der Kanal jedoch für die Ausführung konfiguriert ist *offline*, stellt der Player die Kanalressourcen von einem lokalen HTTP-Server bereit.

Der Workflow für den Prozess ist der folgende:

1. Analysieren Sie die gewünschten Seiten.
1. Sammeln Sie alle zugehörigen Assets.
1. Verpacken Sie alles in einer ZIP-Datei.
1. Laden Sie die ZIP-Datei herunter und extrahieren Sie sie lokal.
1. Anzeige einer lokalen Kopie des Inhalts.

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
   <td><code>channels</code></td> 
   <td>erfasst einen Kanal</td> 
   <td>extension: Erweiterung der zu erfassenden Ressource<br /> [pathSuffix='']: Suffix zum Hinzufügen zum Kanalpfad<br /> </td> 
  </tr>
  <tr>
   <td><code>clientlib</code></td> 
   <td>erfasst die angegebene Client-Bibliothek</td> 
   <td>[extension='']: kann entweder css oder js sein, um nur das Erstere oder nur das Letztere zu sammeln</td> 
  </tr>
  <tr>
   <td><code>assetrenditions</code></td> 
   <td>erfasst die Asset-Wiedergaben</td> 
   <td>[renditions=[]]: Liste der zu erfassenden Wiedergaben. Standardmäßig wird die ursprüngliche Wiedergabe verwendet</td> 
  </tr>
  <tr>
   <td><code>copy</code></td> 
   <td>kopiert die angegebene Struktur aus dem Pfad</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Testen der ContentSync-Konfiguration {#testing-contentsync-configuration}

Befolgen Sie die folgenden Schritte, um die ContentSync-Konfiguration zu testen:

1. Öffnen Sie `https://localhost:4502/libs/cq/contentsync/content/console.html`
1. Klicken Sie in der Liste auf Ihre Konfiguration .
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

1. Navigieren Sie zum Kanal-Dashboard.
1. Klicks **...** im **KANALINFORMATIONEN** Bedienfeld.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Navigieren Sie zu den Kanaleigenschaften.
1. Vergewissern Sie sich auf der Registerkarte (Kanal), dass das Kontrollkästchen deaktiviert ist, und klicken Sie dann auf **Speichern und schließen**.

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
