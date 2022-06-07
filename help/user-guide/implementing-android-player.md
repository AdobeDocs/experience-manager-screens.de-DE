---
title: Implementieren des Android-Players
seo-title: Implementation of Android Player
description: Auf dieser Seite erfahren Sie mehr über die Implementierung von Android Watchdog, einer Lösung zur Wiederherstellung des Players nach Abstürzen.
seo-description: Follow this page to learn implementation of Android Watchdog, a solution to recover the player from crashes.
uuid: 17edd093-f1b1-479e-9f25-28c64f1a7223
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 77fe9d4e-e1bb-42f7-b563-dc03e3af8a60
docset: aem65
feature: Administering Screens, Android Player
role: Admin
level: Intermediate
exl-id: d1331cb8-8bf6-4742-9525-acf18707b4d8
source-git-commit: 8d4a7b2bc436d822c673a00437ee895c8ef5cb6f
workflow-type: ht
source-wordcount: '1529'
ht-degree: 100%

---

# Implementieren des Android-Players {#implementing-android-player}

In diesem Abschnitt wird die Konfiguration des Android-Players beschrieben. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

Außerdem ist **Watchdog** eine Lösung zur Wiederherstellung des Players nach Abstürzen. Eine Anwendung muss sich selbst beim Watchdog-Service registrieren und dann regelmäßig Nachrichten zur Bestätigung ihrer Aktivität an den Service senden. Falls der Watchdog-Service innerhalb der geforderten Zeit keine Keep-Alive-Nachricht erhält, versucht der Service das Gerät neu zu starten, um eine saubere Wiederherstellung durchzuführen (bei ausreichenden Rechten) oder die Anwendung neu zu starten.

## Installieren des Android-Players {#installing-android-player}

Installieren Sie Android-Player für AEM Screens, um den Android-Player für AEM Screens zu implementieren.

Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

### Einrichten der Umgebung für das AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Wenn Sie das AEM Screens 6.5.5 Service Pack verwenden, müssen Sie eine Umgebung für den Android-Player einrichten.

Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** in der **Konfiguration der Adobe Experience Manager-Web-Konsole** in allen AEM-Autoren- und Veröffentlichungsinstanzen von **Lax** (Gering) auf **None** (Keine) fest.

Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole** über `http://localhost:4502/system/console/configMgr`.

1. Suchen Sie nach *Adobe Granite Token Authentication Handler*.

1. Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** von **Lax** (Gering) auf **None** (Keine) fest.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Klicken Sie auf **Speichern**.


### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-hoc-Methode können Sie den aktuellen Android-Player (*.exe*) installieren. Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:

1. Halten Sie die linke obere Ecke gedrückt, um den Admin-Bereich zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.

1. Navigieren Sie im linken Aktionsmenü zum Link **Geräteregistrierung**, um den Status des Prozesses zur Geräteregistrierung zu prüfen **.**

>[!NOTE]
>
>Wenn der **Status** **REGISTRIERT** ist, wird das Feld **Geräte-ID** ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Implementieren von Android Watchdog {#implementing-android-watchdog}

Aufgrund der Architektur von Android erfordert der Neustart des Geräts, dass die Anwendung über Systemrechte verfügt. Hierzu müssen Sie die APK mithilfe der Signierungsschlüssel des Herstellers signieren. Andernfalls startet Watchdog die Player-App neu, statt das Gerät neu zu starten.

### Signieren von Android-APKs mithilfe von Herstellerschlüsseln {#signage-of-android-apks-using-manufacturer-keys}

Zum Zugreifen auf die berechtigten APIs von Android, wie zum Beispiel *PowerManager* oder *HDMIControlServices*, müssen Sie die Android-apk mithilfe der Herstellerschlüssel signieren.

>[!CAUTION]
>
>Voraussetzungen:
>
>Die Android SDK sollte installiert sein, bevor Sie die folgenden Schritte durchführen.

Gehen Sie wie folgt vor, um die Android-apk mithilfe von Herstellerschlüsseln zu signieren:

1. Laden Sie die apk von Google Play oder von der Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/) herunter
1. Rufen Sie die Plattformschlüssel des Herstellers ab, um eine *pk8*- und eine *pem*-Datei zu erhalten

1. Suchen Sie nach dem apksigner-Tool in Android SDK mithilfe von find ~/Library/Android/sdk/build-tools -name &quot;apksigner&quot;
1. &lt;pathto> /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk
1. Suchen Sie den Pfad zum Zipalign-Tool in Android SDK
1. &lt;pathto> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk
1. Installieren Sie ***aemscreensaligned.apk*** mithilfe von adb install auf dem Gerät

## Einführung zu Android Watchdog-Services {#android-watchdog-services}

Der Android-übergreifende Watchdog-Service wird mithilfe von *AlarmManager* als Cordova-Plug-in implementiert.

Das folgende Diagramm zeigt die Implementierung des Watchdog-Service:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialisierung** Zum Zeitpunkt der Initialisierung des Cordova-Plug-ins werden die Berechtigungen geprüft, um zu ermitteln, ob wir über Systemrechte und damit über die Berechtigung zum Neustart verfügen. Sind diese beiden Kriterien erfüllt, wird ein Pending-Intent für den Neustart erstellt. Andernfalls wird ein Pending-Intent für den Neustart der Anwendung (basierend auf ihrer Startaktivität) erstellt.

**2. Keep-Alive-Timer** Ein Keep-Alive-Timer wird verwendet, um alle 15 Sekunden ein Ereignis auszulösen. In diesem Fall müssen Sie den vorhandenen Pending-Intent abbrechen (um die App neu zu starten) und einen neuen Pending-Intent für dieselben 60 Sekunden in der Zukunft registrieren (also im Grunde den Neustart verschieben).

>[!NOTE]
>
>In Android wird der *AlarmManager* für die Registrierung von *pendingIntents* verwendet, die auch dann noch ausgeführt werden können, wenn die App abgestürzt ist und die Alarmbereitstellung von API 19 (Kitkat) ungenau ist. Behalten Sie etwas Abstand zwischen dem Intervall des Timers und dem *AlarmManager*-Alarm *pendingIntent* bei.

**3. Anwendungsabsturz** Im Fall eines Absturzes wird der pendingIntent für den Neustart, der beim AlarmManager registriert ist, nicht mehr zurückgesetzt. Daher führt er (je nach den zum Zeitpunkt der Initialisierung des Cordova-Plug-ins verfügbaren Berechtigungen) einen Neustart der App durch.

## Massenbereitstellung von Android-Player {#bulk-provision-android-player}

Wenn der Android-Player in Massen bereitgestellt wird, muss der Player auf eine AEM-Instanz verweisen und andere Eigenschaften konfigurieren, ohne dass diese manuell in der Admin-Benutzeroberfläche eingegeben werden müssen.

>[!NOTE]
>Diese Funktion ist ab der Android-Player-Version 42.0.372 verfügbar.

Gehen Sie wie folgt vor, um die Massenbereitstellung im Android-Player zuzulassen:

1. Erstellen Sie eine JSON-Konfigurationsdatei mit dem Namen `player-config.default.json`.
Nutzen Sie dazu eine [Beispiel-JSON-Richtlinie](#example-json) sowie eine Tabelle, die die Verwendung der verschiedenen [Richtlinienattribute](#policy-attributes) beschreibt.

1. Verwenden Sie einen MDM- oder ADB- oder Android Studio-Datei-Explorer, um diese JSON-Richtliniendatei im Ordner *sdcard* auf dem Android-Gerät abzulegen.

1. Nachdem die Datei bereitgestellt wurde, installieren Sie die Player-App mit dem MDM.

1. Wenn die Player-App gestartet wird, liest sie diese Konfigurationsdatei und verweist auf den entsprechenden AEM-Server, auf dem sie registriert und anschließend gesteuert werden kann.

   >[!NOTE]
   >Diese Datei ist *schreibgeschützt*, wenn die App zum ersten Mal gestartet wird, und kann nicht für nachfolgende Konfigurationen verwendet werden. Wenn der Player vor dem Ablegen der Konfigurationsdatei gestartet wird, deinstallieren Sie die App und installieren Sie sie erneut auf dem Gerät.

### Richtlinienattribute {#policy-attributes}

In der folgenden Tabelle finden Sie eine Zusammenfassung der Richtlinienattribute mit einer beispielhaften JSON-Richtliniendatei als Referenz:

| **Richtlinienname** | **Zweck** |
|---|---|
| *server* | Die URL zum Adobe Experience Manager-Server. |
| *resolution* | Die Auflösung des Geräts. |
| *rebootSchedule* | Der Zeitplan für den Neustart gilt für alle Plattformen. |
| *enableAdminUI* | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf *false* ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| *enableOSD* | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf *false* ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird |
| *enableActivityUI* | Aktivierung zum Anzeigen des Fortschritts von Aktivitäten wie Downloads und Synchronisierungen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| *enableNativeVideo* | Aktivieren Sie diese Option, um die native Hardware-Beschleunigung für die Videowiedergabe zu verwenden (nur Android). |

### Beispiel für eine JSON-Richtlinie {#example-json}

```java
{
  "server": "https://author-screensdemo.adobecqms.net",
"device": "",
"user": "",
"password": "",
"resolution": "auto",
"rebootSchedule": "at 4:00 am",
"maxNumberOfLogFilesToKeep": 10,
"logLevel": 3,
"enableAdminUI": true,
"enableOSD": true,
"enableActivityUI": false,
"enableNativeVideo": false,
"enableAutoScreenshot": false,
"cloudMode": false,
"cloudUrl": "https://screens.adobeioruntime.net",
"cloudToken": "",
"enableDeveloperMode": true
}
```

>[!NOTE]
>Alle Android-Geräte haben einen Ordner *sdcard*, unabhängig davon, ob tatsächlich eine *sdcard* eingelegt wurde oder nicht. Diese Datei befindet sich bei Bereitstellung auf derselben Ebene wie der Ordner „Downloads“. Einige MDMs wie Samsung Knox verweisen möglicherweise auf diesen Ordner *sdcard* als *Interner Datenspeicher*.

## Massenbereitstellung von Android-Playern mit Enterprise Mobility Management {#bulk-provisioning}

Bei der Massenbereitstellung von Android-Playern ist es mühsam, jeden einzelnen Player manuell bei AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) wie VMWare Airwatch, MobileIron oder Samsung Knox für die Remote-Bereitstellung und -Verwaltung Ihrer Bereitstellung zu verwenden. Der AEM Screens-Android-Player unterstützt den Branchenstandard EMM AppConfig, um eine Remote-Bereitstellung zu ermöglichen.

## Benennen des Android-Players {#name-android}

Sie können Ihrem Android-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Android-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Sobald der Player registriert ist, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Android-Player zu konfigurieren:

1. Navigieren Sie zu **Einstellungen** > **Über das Gerät**
1. Bearbeiten Sie den Gerätenamen und legen Sie ihn fest, um den Android-Player zu benennen.

### Implementieren der Massenbereitstellung des Android-Players mit Enterprise Mobility Management {#implementation}

Gehen Sie wie folgt vor, um die Massenbereitstellung im Android-Player zuzulassen:

1. Stellen Sie sicher, dass Ihr Android-Gerät die Google Play-Services unterstützt.
1. Registrieren Sie Ihre Android-Player-Geräte bei Ihrer bevorzugten EMM-Lösung, die AppConfig unterstützt.
1. Melden Sie sich bei Ihrer EMM-Konsole an und rufen Sie das AEM Screens Player-Programm von Google Play ab.
1. Wählen Sie die verwaltete Konfiguration oder die zugehörige Option aus.
1. Sie sollten nun eine Liste der Player-Optionen sehen, die konfiguriert werden können, wie z. B. Server und Massenregistrierungs-Code.
1. Konfigurieren Sie diese Parameter, speichern Sie sie und stellen Sie die Richtlinie auf den Geräten bereit.

   >[!NOTE]
   >Die Geräte sollten das Programm zusammen mit der Konfiguration empfangen und auf den richtigen AEM-Server mit der ausgewählten Konfiguration verweisen. Wenn Sie den Massenregistrierungs-Code konfiguriert haben und ihn so belassen haben, wie er in AEM konfiguriert wurde, sollte sich der Player automatisch registrieren können. Wenn Sie eine Standardanzeige konfiguriert haben, kann er auch einige Standardinhalte herunterladen und anzeigen (die später nach Ihren Wünschen geändert werden können).

Darüber hinaus sollten Sie sich bei Ihrem EMM-Anbieter nach der AppConfig-Unterstützung erkundigen. Die meisten gängigen Anbieter wie [VMWare Airwatch](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [Mobile Iron](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [SOTI](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [Blackberry UEM](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [IBM Maas360](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm) und [Samsung Knox](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) unterstützen diesen Industriestandard.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Weitere Informationen zu dieser Funktion finden Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
