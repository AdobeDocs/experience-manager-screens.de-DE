---
title: Offline-Kanäle
description: Erfahren Sie mehr darüber, wie der AEM Screens-Player mithilfe der ContentSync-Technologie eine Offline-Unterstützung für Kanäle bietet.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 5ad1046f-8b64-490b-9966-ce9008180d54
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: ht
source-wordcount: '427'
ht-degree: 100%

---

# Offline-Kanäle {#offline-channels}

Der Screens-Player bietet eine Offline-Unterstützung für die Kanäle mithilfe der Technologie ***ContentSync***.

Die Player verwenden einen lokalen HTTP-Server, um den entpackten Inhalt bereitzustellen.

Wenn ein Kanal so konfiguriert ist, dass er *online* läuft, stellt der Player die Kanal-Ressourcen durch Zugriff auf den AEM-Server bereit. Wenn der Kanal jedoch so konfiguriert ist, dass er *offline* läuft, stellt der Player die Kanalressourcen von einem lokalen HTTP-Server bereit.

Der Workflow für den Prozess ist wie folgt:

1. Analysieren der gewünschten Seiten.
1. Sammeln aller zugehörigen Assets.
1. Verpacken aller Elemente in einer ZIP-Datei.
1. Herunterladen und lokales Extrahieren der ZIP-Datei.
1. Anzeigen einer lokalen Kopie des Inhalts.

## Update-Handler {#update-handlers}

***ContentSync*** verwendet Update-Handler, um alle erforderlichen Seiten und Assets für ein bestimmtes Projekt zu analysieren und zu sammeln. AEM Screens verwendet die folgenden Update-Handler:

### Allgemeine Optionen {#common-options}

* *type*: der zu verwendende Update-Handler-Typ
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
   <td>Kopiert die angegebene Struktur aus dem Pfad</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Testen der ContentSync-Konfiguration {#testing-contentsync-configuration}

Befolgen Sie die folgenden Schritte, um die ContentSync-Konfiguration zu testen:

1. Öffnen Sie `https://localhost:4502/libs/cq/contentsync/content/console.html`.
1. Klicken Sie auf Ihre Konfiguration in der Liste.
1. Klicken Sie auf **Zwischenspeicher löschen**.
1. Klicken Sie auf **Cache aktualisieren**.
1. Klicken Sie auf **Alles herunterladen**.
1. Entpacken Sie die ZIP-Datei.
1. Starten Sie einen lokalen Server im extrahierten Ordner.
1. Öffnen Sie Ihre Startseite und überprüfen Sie Ihren App-Status.

## Aktivieren der Offline-Konfiguration für einen Kanal {#enabling-offline-config-for-a-channel}

Befolgen Sie die folgenden Schritte, um die Offline-Konfiguration für einen Kanal zu aktivieren:

1. Überprüfen Sie den Kanalinhalt und ermitteln Sie, ob dieser von einer AEM-Instanz (online) angefordert wurde.

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Navigieren Sie zum Kanal-Dashboard.
1. Klicken Sie im Bedienfeld **KANALINFORMATIONEN** auf **…**.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Navigieren Sie zu den Kanaleigenschaften.
1. Vergewissern Sie sich auf der Registerkarte ((Kanal)), dass das Kontrollkästchen deaktiviert ist, und klicken Sie dann auf **Speichern und schließen**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Bevor der Inhalt ordnungsgemäß auf dem Gerät bereitgestellt wird, klicken Sie auf **Offline-Inhalt aktualisieren**.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   Der **Offline**-Status unter **EIGENSCHAFTEN** wird ebenfalls entsprechend aktualisiert.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Kontrollieren Sie den Inhalt des Kanals und überprüfen Sie, ob er vom lokalen Player-Cache angefordert wird.

   ![chlimage_1-26](assets/chlimage_1-26.png)

>[!NOTE]
>
>Weitere Informationen zur Vorlage für benutzerdefinierte Offline-Ressourcen-Handler. und zu den Mindestanforderungen in der Datei `pom.xml` für das Projekt. finden Sie unter **Entwickeln einer benutzerdefinierten Komponente für AEM Screens** im Abschnitt [Vorlage für benutzerdefinierte Handler](/help/user-guide/developing-custom-component-tutorial-develop.md#custom-handlers).
