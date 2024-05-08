---
title: Konfiguration der Videowiedergabe und Problembehebung
description: Erfahren Sie, wie Sie die Videowiedergabe in Ihrem Kanal für AEM Screens debuggen und Fehler beheben können.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
feature: Channels, Interactive
role: Developer
level: Intermediate
exl-id: dfdd58b6-689b-47ca-9459-9c205f1841eb
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 35%

---

# Konfiguration der Videowiedergabe und Problembehebung {#video-playback-configuration-and-troubleshooting}

Beim Hochladen eines Videos in das DAM und Hinzufügen des Kanals treten möglicherweise Probleme auf, bei denen das Video nicht im AEM Screens-Player wiedergegeben wird.

In den folgenden Abschnitten wird beschrieben, wie Sie die Videowiedergabe in Ihrem Kanal debuggen und Fehler beheben können.

## DAM-Ausgaben {#dam-renditions}

Nachdem Sie das Video in den Kanal hochgeladen haben, sollten AEM damit beginnen, einige Ausgabeformate dafür zu erstellen. Sie können Ihre Videos unter „Assets“ anzeigen.

So zeigen Sie das Video an:

1. Navigieren Sie zu Ihrem Video, beispielsweise `http://localhost:4502/assets.html/content/dam/we-retail/en/videos`.
1. Klicken Sie auf das Video, erweitern Sie das Menü oben links und klicken Sie auf **Ausgabeformate**.

Es sollte verschiedene Ausgabedarstellungen geben (eine MP4- oder M4V-Datei).

Wenn keine Ausgabe verfügbar ist, überprüfen Sie, ob ffmpeg im Betriebssystem installiert ist, unter dem AEM ausgeführt wird.

>[!CAUTION]
>
>Wenn keine Ausgabe verfügbar ist, überprüfen Sie, ob ffmpeg im Betriebssystem installiert ist, unter dem AEM ausgeführt wird.
>
>Klicken Sie [hier](https://www.ffmpeg.org/download.html), um ffmpeg zu installieren.

## Video-Assets {#video-assets}

Wenn unter dem Video kein Quellattribut angezeigt wird, wurde das Video möglicherweise nicht transkodiert. Wenn das Video ordnungsgemäß transkodiert wurde, wird es im Dashboard angezeigt, wie im Folgenden gezeigt:

Vergewissern Sie sich, dass ffmpeg installiert ist, und prüfen Sie die Videoprofile.

![chlimage_1-2](assets/chlimage_1-2.png)

### Prüfen des Videoprofils {#checking-video-profile}

1. Navigieren Sie zum **Videoprofil**, d. h. `http://localhost:4502/etc/dam/video.html`, und klicken Sie auf **Test-Video hochladen**.

   ![chlimage_1-3](assets/chlimage_1-3.png)

1. Laden Sie ein Testvideo hoch und klicken Sie auf **Ok** damit Sie mit der Transkodierung beginnen können.

   Wenn das transkodierte Video fehlschlägt, erweitern Sie die ffmpeg-Ausgabe, um Fehler in der Konsolenausgabe von ffmpeg zu verstehen.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Wenn das Video erfolgreich transkodiert wurde, können Sie die transkodierte Datei herunterladen.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >Stellen Sie sicher, dass Sie ausreichend Zeit für die Transkodierung des Videos geben (es sollte das neue Tag anstelle der Verarbeitung zeigen), bevor Sie es zu einem Kanal hinzufügen.

### Testen des Profils mit einer Videokomponente {#checking-profile-with-a-video-component}

Überprüfen Sie die Liste der Profile aus dem Seitenentwurf, wenn die Videokomponente nicht ordnungsgemäß konfiguriert ist.

1. Navigieren Sie zu Ihrem Kanal und klicken Sie auf das **Design** -Modus.

   ![chlimage_1-6](assets/chlimage_1-6.png)

1. Klicken Sie auf das Video und öffnen Sie das **Bearbeiten** angezeigt. Öffnen Sie die **Profile** Registerkarte.

   >[!NOTE]
   >Klicken Sie auf verschiedene Profile (mindestens sollte das Profil &quot;Hohe Qualität H.264&quot;vorhanden sein).

### Prüfen des Videos im Web-Player {#checking-the-video-in-the-web-player}

Mit dem **Web-Player** `http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html/content/screens/we-retail/locations/demo/flagship/single/device0` können Sie die Wiedergabe in Browsern (Chrome und Safari) testen. Chrome wird auf Android™-Geräten verwendet, während Safari der OS X- und iOS-Browser ist.

Wenn das Video nicht in Safari ausgeführt wird, wird es auch nicht in den OS X- und iOS-Playern ausgeführt. Dies ist wahrscheinlich ein Kodierungsproblem und das Video muss neu kodiert werden.

Gehen Sie wie folgt vor, um einen DAM-Workflow zum Erstellen von FullHD-Wiedergaben zu verwenden:

1. Navigieren Sie zum *Workflow-Modelladministrator* , `http://localhost:4502/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models`.
1. Klicken Sie auf **Screens-Asset aktualisieren** -Modell.
1. Klicks **Workflow starten** in der Aktionsleiste aus.
1. Aus dem **Workflow ausführen** Klicken Sie im Dialogfeld auf Ihr Video-Asset im **Nutzlast**.
1. Klicken Sie auf **Ausführen**.

>[!NOTE]
>
>Warten Sie einige Zeit, um die Ausgabedarstellungen zu erstellen. Laden Sie den Webplayer jedoch nach einigen Sekunden/Minuten (abhängig von der Videogröße) in Safari neu.

#### Fehlerbehebung für die automatische Wiedergaberichtlinie {#troubleshooting-autoplay-policy-flag}

Wenn der AEM Screens-Player das Video zwar abruft, aber nicht anzeigt, führen Sie eine Fehlerbehebung für das Flag Autoplay-Richtlinie durch.

Führen Sie die folgenden Schritte aus, um das Problem mit der Kennzeichnung der Autoplay-Richtlinie in Google zu beheben:

1. Navigieren Sie zu ***chrome://flags/#autoplay-policy***
1. Die **Autoplay-Richtlinie** muss von **Standard** in **Keine Benutzergeste erforderlich** geändert werden

1. Starten Sie den Webbrowser neu und aktualisieren Sie den Player

>[!NOTE]
>
>Weitere Informationen zu Best Practices für gute Benutzererlebnisse mit den neuen Autoplay-Richtlinien in Chrome finden Sie in der Dokumentation für *Änderungen an der Autoplay-Richtlinie* at `https://developers.google.com/web/updates/2017/09/autoplay-policy-changes#webaudio`.

### Synchronisieren von Videos über mehrere Player hinweg {#syncing-video-across-multiple-players}

Um Videos synchron auf mehreren Geräten wiederzugeben, sollten Sie die absolute Strategie für die Sequenz nutzen, zu der das Video gehört.

#### Voraussetzungen {#requirements}

* zwei oder mehr identische Player
* im Idealfall ähnliche Hardware
* identische Netzwerktopologie (die Player sind mit einem NTP-Server verbunden, der ihre internen Systemuhren synchronisiert)

#### Einrichten der absoluten Strategie {#setting-up-the-absolute-strategy}

Die absolute Strategie:

* Berechnet eine Ankerzeit (Mitternacht des aktuellen Tages).
* Berechnet die Dauer der Sequenz (Summe der Dauer aller zugehörigen Elemente).
* Sie berechnet zu jedem Zeitpunkt, welches Element gerade abgespielt werden soll, und das nächste Element, indem sie die Sequenz _rest_time = (current_time - anchor_time) % sequence_duration löst.

Gehen Sie wie folgt vor, um eine absolute Strategie einzurichten:

1. Navigieren Sie zu Ihrem Kanalautor und klicken Sie auf die Sequenzkomponente , wie in der folgenden Abbildung dargestellt.
1. Öffnen Sie das Konfigurations-Dialogfeld.
1. Bearbeiten Sie die **Strategie** und fügen Sie „absolut“ hinzu.

   ![chlimage_1-8](assets/chlimage_1-8.png)

   >[!NOTE]
   >Die Betriebssysteme der Player müssen über dieselbe Uhr verfügen.

**Synchronisieren von Uhren unter OS X** Gehen Sie wie folgt vor, um die Uhren unter OS X auszurichten:

1. Öffnen **Datum und Uhrzeit** Voreinstellungen für jedes OS X-Feld
1. Aktivieren Sie **Datum und Uhrzeit automatisch festlegen**.
1. Kopieren Sie den Wert 0.pool.ntp.org, 1.pool.ntp.org, 2.pool.ntp.org, 3.pool.ntp.org, time.apple.com in das Dropdown-Feld. Sie können auch einfach den Befehl *sudo ntpdate -u -v 0.pool.ntp.org* ausführen.
1. Starten Sie alle Player (mind. zwei).

Es kann eine Weile dauern, bis die Player eine neue synchronisierte Sequenz beginnen.
