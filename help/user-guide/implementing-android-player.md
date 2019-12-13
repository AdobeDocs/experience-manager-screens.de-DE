---
title: Implementierung von Android Player
seo-title: Implementierung des Android-Players
description: Befolgen Sie die Anweisungen auf dieser Seite, um mehr über die Implementierung von Android Watchdog zu erfahren, einer Lösung zur Wiederherstellung des Players nach Abstürzen.
seo-description: Befolgen Sie die Anweisungen auf dieser Seite, um mehr über die Implementierung von Android Watchdog zu erfahren, einer Lösung zur Wiederherstellung des Players nach Abstürzen.
uuid: 17edd093-f1b1-479e-9f25-28c64f1a7223
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 77fe9d4e-e1bb-42f7-b563-dc03e3af8a60
docset: aem65
translation-type: tm+mt
source-git-commit: 209a9a833957d9a8bb7c7ec70ff421514f5b974c

---


# Implementierung von Android Player {#implementing-android-player}

In diesem Abschnitt wird die Konfiguration des Android-Players beschrieben. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

Additionally, **Watchdog** is a solution to recover the player from crashes. Eine Anwendung muss sich selbst beim Watchdog-Dienst registrieren und dann regelmäßig Nachrichten zur Bestätigung ihrer Aktivität an den Dienst senden. Falls der Watchdog-Dienst innerhalb der geforderten Zeit keine Keep-Alive-Nachricht erhält, versucht der Dienst das Gerät neu zu starten, um eine saubere Wiederherstellung durchzuführen (bei ausreichenden Rechten) oder die Anwendung neu zu starten.

## Installieren von Android Player {#installing-android-player}

Installieren Sie Android Player für AEM Screens, um den Android Player für AEM Screens zu implementieren.

Rufen Sie die Seite [**AEM 6.4 Player-Downloads**](https://download.macromedia.com/screens/) auf.

### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-hoc-Methode können Sie den neuesten Android Player (*.exe*) installieren. Besuchen Sie die Seite [**AEM 6.4 Player-Downloads**](https://download.macromedia.com/screens/) .

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte auf dem Player aus, um die Ad-hoc-Installation abzuschließen:

1. Drücken Sie die lange Taste oben links, um das Admin-Bedienfeld zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration** , geben Sie den Speicherort (die Adresse) der AEM-Instanz ein, mit der Sie eine Verbindung herstellen möchten, und klicken Sie auf **Speichern**.

1. Navigieren Sie im linken Aktionsmenü zum Link **Geräteregistrierung** , um den Status des Geräteregistrierungsprozesses zu prüfen ****.

>[!NOTE]
>
>Wenn der **Bundesstaat** **REGISTRIERT** ist, wird das Feld **Geräte-ID** ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Implementieren von Android Watchdog {#implementing-android-watchdog}

Aufgrund der Architektur von Android erfordert der Neustart des Geräts, dass die Anwendung über Systemrechte verfügt. Hierzu müssen Sie die apk mithilfe der Signierungsschlüssel des Herstellers signieren. Andernfalls startet Watchdog die Player-Anwendung neu und nicht das Gerät.

### Signieren von Android-apks mithilfe von Herstellerschlüsseln {#signage-of-android-apks-using-manufacturer-keys}

To access some of the privileged APIs of Android such as *PowerManager* or *HDMIControlServices*, you need to signtheandroid apk using the manufacturer's keys.

>[!CAUTION]
>
>Voraussetzungen:
>
>Die Android SDK sollte installiert sein, bevor Sie die folgenden Schritte durchführen.

Gehen Sie wie folgt vor, um die Android-apk mithilfe von Herstellerschlüsseln zu signieren:

1. Download the apk from Google Play or from [AEM Screens Player Downloads](https://download.macromedia.com/screens/) page
1. Obtain the platform keys from the manufacturer to get a *pk8* and a *pem* file

1. Suchen Sie nach dem apksigner-Tool in Android SDK mithilfe von find ~/Library/Android/sdk/build-tools -name "apksigner"
1. &lt;Pfad&gt; /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk
1. Suchen Sie den Pfad zum Werkzeug für die ZIP-Ausrichtung in android sdk
1. &lt;Pfad&gt; /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk
1. Installieren Sie ***aemscreensaligned.apk**mithilfe von adb install auf dem Gerät*

## Implementierung von Android Watchdog {#android-watchdog-implementation}

The cross-Android watchdog service is implemented as a cordova plugin using *AlarmManager*.

Das folgende Diagramm zeigt die Implementierung des Watchdog-Diensts:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialization** At the time of initialization of the cordova plugin, permissions are checked to see if we have system privileges and thus the Reboot permission. Sind diese beiden Kriterien erfüllt, wird eine Pending-Intent für den Neustart erstellt. Andernfalls wird eine Pending-Intent für den Neustart der Anwendung (basierend auf ihrer Startaktivität) erstellt.

**2. Keep Alive Timer** A keep alive timer is used to trigger an event every 15 seconds. In diesem Fall müssen Sie die vorhandene Pending-Intent abbrechen (um die App neu zu starten) und eine neue Pending-Intent für die gleichen 60 Sekunden in der Zukunft registrieren (also im Grunde den Neustart verschieben).

>[!NOTE]
>
>In Android wird der *AlarmManager* für die Registrierung von *pendingIntents* verwendet, die auch dann noch ausgeführt werden können, wenn die App abgestürzt ist und die Alarmbereitstellung von API 19 (Kitkat) ungenau ist. Behalten Sie etwas Abstand zwischen dem Intervall des Timers und dem *AlarmManager*-Alarm *pendingIntent* bei.

**3. Application Crash** In case of a crash, the pendingIntent for Reboot registered with AlarmManager is no longer reset and thus it executes a reboot or restart of app (depending on permissions available at the time of initialization of the cordova plugin).
