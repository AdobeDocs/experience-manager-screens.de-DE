---
title: Konfiguration und Fehlerbehebung bei der Videowiedergabe
seo-title: Beheben von Videoproblemen
description: null
seo-description: Auf dieser Seite erfahren Sie, wie Sie Videoprobleme beheben. Wenn Sie ein Video zu DAM hochladen und zu Ihrem Kanal hinzufügen, kann möglicherweise das Problem auftreten, dass das Video im Screens-Player nicht wiedergegeben wird. In diesem Abschnitt werden das Debugging und die Problembehebung für die Videowiedergabe in Ihrem Kanal erläutert.
uuid: 825b2440-5626-40d5-8c93-7689c24474d4
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
discoiquuid: 65ecc6f1-ba0e-443f-85a1-ac19f9a52c2c
translation-type: tm+mt
source-git-commit: 66c741bb73bd5deb2bb5b06dd46f2e407d9c4b7e

---


# Konfiguration und Fehlerbehebung bei der Videowiedergabe {#video-playback-configuration-and-troubleshooting}

Wenn Sie ein Video zu DAM hochladen und zu Ihrem Kanal hinzufügen, kann möglicherweise das Problem auftreten, dass das Video im Screens-Player nicht wiedergegeben wird.

In den folgenden Abschnitten werden das Debugging und die Problembehebung für die Videowiedergabe in Ihrem Kanal beschrieben.

## DAM-Ausgaben {#dam-renditions}

Wenn Sie das Video in den Kanal hochgeladen haben, sollte AEM damit beginnen, einige Ausgaben dafür zu erzeugen. Sie können Ihre Videos unter Assets anzeigen.

So zeigen Sie das Video an:

1. Navigieren Sie beispielsweise zu Ihrem Video `http://localhost:4502/assets.html/content/dam/we-retail/en/videos`.
1. Click the video and expand the top left menu and click **Renditions**.

Es sollten unterschiedliche Ausgaben vorliegen (ein MP4- oder M4V-Video).

Wenn keine Darstellung vorhanden ist, stellen Sie sicher, dass auf dem Betriebssystem, auf dem AEM ausgeführt wird, ffmpeg installiert ist.

>[!CAUTION]
>
>Wenn keine Darstellung vorhanden ist, stellen Sie sicher, dass auf dem Betriebssystem, auf dem AEM ausgeführt wird, ffmpeg installiert ist.
>
>Klicken Sie [hier](https://evermeet.cx/ffmpeg/), um ffmpeg zu installieren.

## Video-Assets {#video-assets}

Wenn unter dem Video kein Quellattribut angezeigt wird, wurde das Video möglicherweise nicht transkodiert. Wenn das Video ordnungsgemäß transkodiert wurde, wird es im Dashboard angezeigt (siehe nachfolgende Abbildung).

Überprüfen Sie, ob ffmpeg installiert ist und die Videoprofile.

![chlimage_1-2](assets/chlimage_1-2.png)

### Prüfen des Videoprofils {#checking-video-profile}

1. Navigate to the **Video Profile**, that is, `http://localhost:4502/etc/dam/video.html` and click **Upload Test Video**.

   ![chlimage_1-3](assets/chlimage_1-3.png)

1. Upload a test video and click **Ok** to begin the transcoding.

   Falls die Transkodierung fehlschlägt, erweitern Sie die ffmpeg-Ausgabe, um die Fehler in der Konsolenausgabe von ffmpeg zu verstehen.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Wenn das Video erfolgreich transkodiert wurde, können Sie die transkodierte Datei herunterladen.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >Stellen Sie sicher, dass Sie lange genug warten, bis das Video transkodiert wurde (es sollte das Tag „neu“ aufweisen statt „in Bearbeitung“), bevor Sie es zu einem Kanal hinzufügen.

### Testen des Profils mit einer Videokomponente {#checking-profile-with-a-video-component}

Prüfen Sie die Liste der Profile über die Design-Seite, wenn die Videokomponente nicht korrekt konfiguriert ist.

1. Navigieren Sie zu Ihrem Kanal. Wählen Sie dort den Modus **Design** aus.

   ![chlimage_1-6](assets/chlimage_1-6.png)

1. Wählen Sie das Video aus und öffnen Sie das Dialogfeld **Bearbeiten**. Öffnen Sie die Registerkarte **Profile**.

   Wählen Sie unterschiedliche Profile aus. (Es sollte wenigstens das Profil „Hohe Qualität H.264“ vorhanden sein.)

   ![chlimage_1-7](assets/chlimage_1-7.png)

### Prüfen des Videos im Web-Player {#checking-the-video-in-the-web-player}

Use the **Web Player** `http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html/content/screens/we-retail/locations/demo/flagship/single/device0` to validate playback in browsers (Chrome and Safari). Chrome wird auf Android-Geräten genutzt, Safari ist der Browser unter OSX und iOS.

Wenn das Video in Safari nicht läuft, funktioniert es auch nicht bei den OSX- und iOS-Playern. Das liegt wahrscheinlich an einem Kodierungsfehler. Das Video muss also neu kodiert werden.

Führen Sie die folgenden Schritte durch, um mit einem DAM-Workflow FullHD-Ausgaben zu erstellen:

1. Navigate to the *workflow model admin*, that is `http://localhost:4502/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models`.
1. Wählen Sie das Modell **Screens – Asset aktualisieren** aus.
1. Klicken Sie in der Aktionsleiste auf **Workflow starten**, um das Dialogfeld **Workflow ausführen** zu öffnen.

1. Wählen Sie das Video-Asset in der **Nutzlast** aus.
1. Klicken Sie auf **Ausführen**.

>[!NOTE]
>
>Warten Sie eine Weile, während die Ausgaben erstellt werden. Laden Sie nach einigen Sekunden/Minuten (je nach Videogröße) den Web-Player in Safari neu.

#### Fehlerbehebung für das Flag "Autoplay Policy" {#troubleshooting-autoplay-policy-flag}

Falls der AEM Screens Player das Video zwar abruft, aber nicht anzeigt, müssen Sie die Fehlerbehebung für das Flag "Autoplay Policy"durchführen.

Führen Sie die folgenden Schritte aus, um das Problem mit der autoplay Policy-Kennzeichnung von Google zu beheben:

1. Navigieren Sie zu ***chrome://flags/#autoplay-policy***
1. Die **Autoplay-Richtlinie** muss von " **Standard** "in " **Keine Benutzergeste"geändert werden**

1. Starten Sie den Webbrowser neu und aktualisieren Sie den Player

>[!NOTE]
>
>Weitere Informationen zu den Best Practices für gute Benutzererfahrungen mit den neuen Autoplay-Richtlinien in Chrome finden Sie in der Dokumentation zu Änderungen *der* Autoplay-Richtlinie, das heißt `https://developers.google.com/web/updates/2017/09/autoplay-policy-changes#webaudio`.

### Synchronisieren von Videos über mehrere Player hinweg {#syncing-video-across-multiple-players}

Um Videos synchron auf mehreren Geräten wiederzugeben, sollten Sie die absolute Strategie für die Sequenz verwenden, zu der das Video gehört.

#### Voraussetzungen {#requirements}

* identische 2+ Player
* im Idealfall ähnliche Hardware
* identische Netzwerktopologie (Player sind mit einem NTP-Server verbunden, der ihre internen Systemuhren ausrichtet)

#### Einrichten der absoluten Strategie {#setting-up-the-absolute-strategy}

Die absolute Strategie:

* berechnet eine Ankerzeit (Mitternacht des aktuellen Tages)
* berechnet die Dauer der Sequenz (Summe der Dauer aller Elemente)
* zu einem beliebigen Zeitpunkt berechnet es, welches Element derzeit wiedergegeben werden soll, und das nächste Element durch Lösen der Sequenz _rest_time = (current_time - anker_time) % sequence_duration.

Führen Sie die folgenden Schritte durch, um eine absolute Strategie einzurichten:

1. Navigieren Sie zu Ihrem Kanalautor und wählen Sie die Sequenzkomponenten wie in der nachfolgenden Abbildung gezeigt aus.
1. Öffnen Sie das Konfigurations-Dialogfeld .
1. Edit the **Strategy** and add absolute.

![chlimage_1-8](assets/chlimage_1-8.png)

>[!NOTE]
>
>Die Betriebssysteme der Player müssen über dieselbe Uhr verfügen.

**Ausrichten der Uhren unter OS X** Gehen Sie wie folgt vor, um die Uhren an OSX auszurichten:

1. Open **Date &amp; Time** preferences on each OSX box
1. Check** Datum und Uhrzeit automatisch einstellen**
1. Paste value 0.pool.ntp.org, 1.pool.ntp.org, 2.pool.ntp.org, 3.pool.ntp.org, time.apple.com in the dropdown or simply run *sudo ntpdate -u -v 0.pool.ntp.org*
1. Starten Sie alle Player (mind. zwei).

Es kann eine Weile dauern, bis die Player eine neue synchronisierte Sequenz beginnen.

