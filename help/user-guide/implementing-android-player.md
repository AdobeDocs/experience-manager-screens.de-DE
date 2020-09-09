---
title: Implementieren des Android-Players
seo-title: Implementieren des Android-Players
description: Auf dieser Seite erfahren Sie mehr über die Implementierung von Android Watchdog, einer Lösung zur Wiederherstellung des Players nach Abstürzen.
seo-description: Auf dieser Seite erfahren Sie mehr über die Implementierung von Android Watchdog, einer Lösung zur Wiederherstellung des Players nach Abstürzen.
uuid: 17edd093-f1b1-479e-9f25-28c64f1a7223
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 77fe9d4e-e1bb-42f7-b563-dc03e3af8a60
docset: aem65
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 90%

---


# Implementieren des Android-Players {#implementing-android-player}

In diesem Abschnitt wird die Konfiguration des Android-Players beschrieben. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

Außerdem ist **Watchdog** eine Lösung zur Wiederherstellung des Players nach Abstürzen. Eine Anwendung muss sich selbst beim Watchdog-Dienst registrieren und dann regelmäßig Nachrichten zur Bestätigung ihrer Aktivität an den Dienst senden. Falls der Watchdog-Dienst innerhalb der geforderten Zeit keine Keep-Alive-Nachricht erhält, versucht der Dienst das Gerät neu zu starten, um eine saubere Wiederherstellung durchzuführen (bei ausreichenden Rechten) oder die Anwendung neu zu starten.

## Installieren des Android-Players {#installing-android-player}

Installieren Sie Android-Player für AEM Screens, um den Android-Player für AEM Screens zu implementieren.

Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

### Einrichten der Umgebung für AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Wenn Sie AEM Screens 6.5.5 Service Pack verwenden, müssen Sie eine Umgebung für den Android-Player einrichten.

Setzen Sie das **Attribut SameSite für die Cookies** login-token von **Lax** auf **None** aus **Adobe Experience Manager Web ConsoleConfiguration** in allen AEM Autor- und Veröffentlichungsinstanzen.

Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zu **Konfiguration der Adobe Experience Manager-Web-Konsole** über `http://localhost:4502/system/console/configMgr`.

1. Suchen Sie nach *Adobe Granite Token Authentication Handler*.

1. Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** von **Lax** auf **Keine** fest.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Klicken Sie auf **Speichern**.


### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-hoc-Methode können Sie den aktuellen Android-Player (*.exe*) installieren. Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:

1. Halten Sie die linke obere Ecke gedrückt, um den Admin-Bereich zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.

1. Navigieren Sie im linken Aktionsmenü zum Link **Geräteregistrierung******, um den Status des Prozesses zur Geräteregistrierung zu prüfen.

>[!NOTE]
>
>Wenn der **Status** **REGISTRIERT** ist, wird das Feld **Geräte-ID** ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Implementieren von Android Watchdog {#implementing-android-watchdog}

Aufgrund der Architektur von Android erfordert der Neustart des Geräts, dass die Anwendung über Systemrechte verfügt. Hierzu müssen Sie die apk mithilfe der Signierungsschlüssel des Herstellers signieren. Andernfalls startet Watchdog die Player-Anwendung neu und nicht das Gerät.

### Signieren von Android-apks mithilfe von Herstellerschlüsseln         {#signage-of-android-apks-using-manufacturer-keys}

To access some of the privileged APIs of Android such as *PowerManager* or *HDMIControlServices*, you need to sign the android apk using the manufacturer&#39;s keys.

>[!CAUTION]
>
>Voraussetzungen:
>
>Die Android SDK sollte installiert sein, bevor Sie die folgenden Schritte durchführen.

Gehen Sie wie folgt vor, um die Android-apk mithilfe von Herstellerschlüsseln zu signieren:

1. Laden Sie die apk von Google Play oder von der Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/) herunter
1. Rufen Sie die Plattformschlüssel des Herstellers ab, um eine *pk8*- und eine *pem*-Datei zu erhalten

1. Suchen Sie nach dem apksigner-Tool in Android SDK mithilfe von find ~/Library/Android/sdk/build-tools -name &quot;apksigner&quot;
1. &lt;Pfad> /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk
1. Suchen Sie den Pfad zum Zipalign-Tool in Android SDK
1. &lt;Pfad> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk
1. Installieren Sie ***aemscreensaligned.apk*** mithilfe von adb install auf dem Gerät

## Implementierung von Android Watchdog {#android-watchdog-implementation}

Der Android Watchdog-übergreifende Dienst wird mithilfe von *AlarmManager* als Cordova-Plug-in implementiert.

Das folgende Diagramm zeigt die Implementierung des Watchdog-Diensts:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialisierung** Zum Zeitpunkt der Initialisierung des Cordova-Plug-ins werden die Berechtigungen geprüft, um zu ermitteln, ob wir über Systemrechte und damit über die Berechtigung zum Neustart verfügen. Sind diese beiden Kriterien erfüllt, wird ein Pending-Intent für den Neustart erstellt. Andernfalls wird ein Pending-Intent für den Neustart der Anwendung (basierend auf ihrer Startaktivität) erstellt.

**2. Keep-Alive-Timer** Ein Keep-Alive-Timer wird verwendet, um alle 15 Sekunden ein Ereignis auszulösen. In diesem Fall müssen Sie den vorhandenen Pending-Intent abbrechen (um die App neu zu starten) und einen neuen Pending-Intent für dieselben 60 Sekunden in der Zukunft registrieren (also im Grunde den Neustart verschieben).

>[!NOTE]
>
>In Android wird der *AlarmManager* für die Registrierung von *pendingIntents* verwendet, die auch dann noch ausgeführt werden können, wenn die App abgestürzt ist und die Alarmbereitstellung von API 19 (Kitkat) ungenau ist. Behalten Sie etwas Abstand zwischen dem Intervall des Timers und dem *AlarmManager*-Alarm *pendingIntent* bei.

**3. Anwendungsabsturz** Im Fall eines Absturzes wird der pendingIntent für den Neustart, der beim AlarmManager registriert ist, nicht mehr zurückgesetzt. Daher führt er (je nach den zum Zeitpunkt der Initialisierung des Cordova-Plug-ins verfügbaren Berechtigungen) einen Neustart der App durch.
