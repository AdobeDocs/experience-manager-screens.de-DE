---
title: Konfiguration der Videowiedergabe und Fehlerbehebung
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
ht-degree: 83%

---

# Konfiguration der Videowiedergabe und Fehlerbehebung {#video-playback-configuration-and-troubleshooting}

Beim Hochladen eines Videos in das DAM und Hinzufügen des Kanals treten möglicherweise Probleme auf, bei denen das Video nicht im AEM Screens-Player wiedergegeben wird.

In den folgenden Abschnitten werden das Debugging und die Problembehebung für die Videowiedergabe in Ihrem Kanal beschrieben.

## DAM-Ausgaben {#dam-renditions}

Nachdem Sie das Video in den Kanal hochgeladen haben, sollten AEM damit beginnen, einige Ausgabeformate dafür zu erstellen. Sie können Ihre Videos unter „Assets“ anzeigen.

So zeigen Sie das Video an:

1. Navigieren Sie zu Ihrem Video, beispielsweise `http://localhost:4502/assets.html/content/dam/we-retail/en/videos`.
1. Klicken Sie auf das Video. Erweitern Sie das obere linke Menü und klicken Sie auf **Ausgabedarstellungen**.

Es sollten unterschiedliche Ausgabedarstellungen vorliegen (ein MP4- oder M4V-Video).

Wenn keine Ausgabe verfügbar ist, überprüfen Sie, ob ffmpeg im Betriebssystem installiert ist, unter dem AEM ausgeführt wird.

>[!CAUTION]
>
>Wenn keine Ausgabe verfügbar ist, überprüfen Sie, ob ffmpeg im Betriebssystem installiert ist, unter dem AEM ausgeführt wird.
>
>Klicken Sie [hier](https://www.ffmpeg.org/download.html), um ffmpeg zu installieren.

## Video-Assets {#video-assets}

Wenn unter dem Video kein Quellattribut angezeigt wird, wurde das Video möglicherweise nicht transkodiert. Wenn das Video ordnungsgemäß transkodiert wurde, wird es im Dashboard angezeigt (wie nachfolgend dargestellt).

Vergewissern Sie sich, dass ffmpeg installiert ist, und prüfen Sie die Videoprofile.

![chlimage_1-2](assets/chlimage_1-2.png)

### Prüfen des Videoprofils {#checking-video-profile}

1. Navigieren Sie zum **Videoprofil**, d. h. `http://localhost:4502/etc/dam/video.html`, und klicken Sie auf **Test-Video hochladen**.

   ![chlimage_1-3](assets/chlimage_1-3.png)

1. Laden Sie ein Testvideo hoch und klicken Sie auf **OK**, um die Transkodierung zu starten.

   Falls das transkodierte Video fehlschlägt, erweitern Sie die ffmpeg-Ausgabe, um die Fehler in der Konsolenausgabe von ffmpeg zu verstehen.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Wenn das Video erfolgreich transkodiert wurde, können Sie die transkodierte Datei herunterladen.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >Stellen Sie sicher, dass Sie lange genug warten, bis das Video transkodiert wurde (es sollte das Tag „neu“ aufweisen statt „in Bearbeitung“), bevor Sie es zu einem Kanal hinzufügen.

### Testen des Profils mit einer Videokomponente {#checking-profile-with-a-video-component}

Prüfen Sie die Liste der Profile über die Design-Seite, wenn die Videokomponente nicht korrekt konfiguriert ist.

1. Navigieren Sie zu Ihrem Kanal und klicken Sie auf das **Design** -Modus.

   ![chlimage_1-6](assets/chlimage_1-6.png)

1. Klicken Sie auf das Video und öffnen Sie das **Bearbeiten** angezeigt. Öffnen Sie die Registerkarte **Profile**.

   >[!NOTE]
   >Klicken Sie auf verschiedene Profile (mindestens sollte das Profil &quot;Hohe Qualität H.264&quot;vorhanden sein).

### Prüfen des Videos im Web-Player {#checking-the-video-in-the-web-player}

Mit dem **Web-Player** `http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html/content/screens/we-retail/locations/demo/flagship/single/device0` können Sie die Wiedergabe in Browsern (Chrome und Safari) testen. Chrome wird auf Android™-Geräten genutzt, Safari ist der Browser unter OS X und iOS.

Wenn das Video in Safari nicht läuft, funktioniert es auch nicht bei den OS X- und iOS-Playern.  Das liegt wahrscheinlich an einem Kodierungsfehler. Das Video muss also neu kodiert werden.

Gehen Sie wie folgt vor, um einen DAM-Workflow zum Erstellen von FullHD-Wiedergaben zu verwenden:

1. Navigieren Sie zur *Workflow-Modelladministration*, d. h. `http://localhost:4502/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models`.
1. Klicken Sie auf **Screens-Asset aktualisieren** -Modell.
1. Klicks **Workflow starten** in der Aktionsleiste aus.
1. Aus dem **Workflow ausführen** Klicken Sie im Dialogfeld auf Ihr Video-Asset im **Nutzlast**.
1. Klicken Sie auf **Ausführen**.

>[!NOTE]
>
>Warten Sie eine Weile, während die Ausgabedarstellungen erstellt werden. Laden Sie nach einigen Sekunden/Minuten (je nach Videogröße) den Web-Player in Safari neu.

#### Problembehebung für das Flag „Autoplay-Richtlinie“ {#troubleshooting-autoplay-policy-flag}

Wenn der AEM Screens-Player das Video zwar abruft, aber nicht anzeigt, führen Sie eine Fehlerbehebung für das Flag Autoplay-Richtlinie durch.

Führen Sie folgende Schritte aus, um das Problem mit dem Flag „Autoplay-Richtlinie“ von Google zu beheben:

1. Navigieren Sie zu ***chrome://flags/#autoplay-policy***
1. Die **Autoplay-Richtlinie** muss von **Standard** in **Keine Benutzergeste erforderlich** geändert werden

1. Starten Sie den Webbrowser neu und aktualisieren Sie den Player

>[!NOTE]
>
>Weitere Informationen zu bewährten Verfahren für gute Benutzererlebnisse mit den neuen Autoplay-Richtlinien in Chrome finden Sie in der Dokumentation zu *Änderungen der Autoplay-Richtlinie* auf `https://developers.google.com/web/updates/2017/09/autoplay-policy-changes#webaudio`.

### Synchronisieren von Videos über mehrere Player hinweg {#syncing-video-across-multiple-players}

Um Videos synchron auf mehreren Geräten wiederzugeben, sollten Sie die absolute Strategie für die Sequenz nutzen, zu der das Video gehört.

#### Voraussetzungen {#requirements}

* zwei oder mehr identische Player
* im Idealfall ähnliche Hardware
* identische Netzwerktopologie (die Player sind mit einem NTP-Server verbunden, der ihre internen Systemuhren synchronisiert)

#### Einrichten der absoluten Strategie {#setting-up-the-absolute-strategy}

Die absolute Strategie:

* berechnet eine Ankerzeit (Mitternacht des aktuellen Tages).
* berechnet die Dauer der Sequenz (Summe der Dauer aller Elemente).
* berechnet zu jedem beliebigen Zeitpunkt mit der Formel „verbleibende_Sequenzzeit = (aktuelle_Zeit – Ankerzeit) % Sequenzdauer“, welches Element aktuell und als nächstes wiedergegeben werden soll.

Führen Sie die folgenden Schritte durch, um eine absolute Strategie einzurichten:

1. Navigieren Sie zu Ihrem Kanalautor und klicken Sie auf die Sequenzkomponente , wie in der folgenden Abbildung dargestellt.
1. Öffnen Sie das Konfigurations-Dialogfeld.
1. Bearbeiten Sie die **Strategie** und fügen Sie „absolut“ hinzu.

   ![chlimage_1-8](assets/chlimage_1-8.png)

   >[!NOTE]
   >Die Betriebssysteme der Player müssen über dieselbe Uhr verfügen.

**Synchronisieren der Uhren unter OS X** Gehen Sie wie folgt vor, um die Uhren unter OS X zu synchronisieren:

1. Öffnen Sie in jeder OS X-Box die Einstellungen für **Datum und Uhrzeit**.
1. Aktivieren Sie **Datum und Uhrzeit automatisch festlegen**.
1. Kopieren Sie den Wert 0.pool.ntp.org, 1.pool.ntp.org, 2.pool.ntp.org, 3.pool.ntp.org, time.apple.com in das Dropdown-Feld. Sie können auch einfach den Befehl *sudo ntpdate -u -v 0.pool.ntp.org* ausführen.
1. Starten Sie alle Player (mind. zwei).

Es kann eine Weile dauern, bis die Player eine neue synchronisierte Sequenz beginnen.
