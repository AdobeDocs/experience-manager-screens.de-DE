---
title: Implementieren von Android&trade;-Player
description: Erfahren Sie mehr über die Implementierung von Android&trade; Watchdog, einer Lösung, mit der Sie den Android&trade;-Player nach Abstürzen wiederherstellen können.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
feature: Administering Screens, Android Player
role: Admin
level: Intermediate
exl-id: d1331cb8-8bf6-4742-9525-acf18707b4d8
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '1464'
ht-degree: 37%

---

# Implementieren von Android™ Player {#implementing-android-player}

In diesem Abschnitt wird die Konfiguration des Android™-Players beschrieben. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

Außerdem **Wachhund** ist eine Lösung, um den Player von Abstürzen zu erholen. Eine Anwendung muss sich selbst beim Watchdog-Service registrieren und dann regelmäßig Meldungen an den Service senden, dass er aktiv ist. Falls der Watchdog-Service innerhalb der geforderten Zeit keine Keep-Alive-Nachricht erhält, versucht der Service das Gerät neu zu starten, um eine saubere Wiederherstellung durchzuführen (bei ausreichenden Rechten) oder die Anwendung neu zu starten.

## Installieren des Android™-Players {#installing-android-player}

Um den Android™-Player für AEM Screens zu implementieren, installieren Sie den Android™-Player für AEM Screens.

Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

### Einrichten der Umgebung für das AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Richten Sie eine Umgebung für den Android™-Player ein, wenn Sie das AEM Screens 6.5.5 Service Pack verwenden.

Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** in der **Konfiguration der Adobe Experience Manager-Web-Konsole** in allen AEM-Autoren- und Veröffentlichungsinstanzen von **Lax** (Gering) auf **None** (Keine) fest.

Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole** über `http://localhost:4502/system/console/configMgr`.

1. Suchen Sie nach *Adobe Granite Token Authentication Handler*.

1. Legen Sie das **Attribut „SameSite“ für die Anmelde-Token-Cookies** von **Lax** (Gering) auf **None** (Keine) fest.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Klicken Sie auf **Speichern**.


### Ad-hoc-Methode {#ad-hoc-method}

Mit der Ad-hoc-Methode können Sie den neuesten Android™-Player installieren (*.exe*). Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:

1. Drücken Sie die Taste lange in der oberen linken Ecke, um das Admin-Bedienfeld zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.

1. Navigieren Sie zu . **Gerät** **Registrierung** über den Link im linken Aktionsmenü, um den Status des Geräteregistrierungsprozesses zu überprüfen.

>[!NOTE]
>
>Wenn die **Bundesland** ist **REGISTRIERT**, können Sie sehen, dass die **Geräte-ID** Feld ist ausgefüllt.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Implementieren von Android™ Watchdog {#implementing-android-watchdog}

Aufgrund der Android™-Architektur erfordert ein Neustart des Geräts, dass die Anwendung über Systemberechtigungen verfügt. Signieren Sie dazu die APK mit den Signierschlüsseln des Herstellers, andernfalls startet Watchdog die Player-Anwendung neu und nicht das Gerät neu.

### Signage von Android™ `apks` Verwenden von Herstellerschlüsseln {#signage-of-android-apks-using-manufacturer-keys}

So greifen Sie auf einige der privilegierten APIs von Android zu™ z. B. *PowerManager* oder *HDMIControlServices*, signieren Sie das Android™ `apk` mithilfe der Herstellerschlüssel.

>[!CAUTION]
>
>Voraussetzungen:
>
>Sie sollten das Android™-SDK installiert haben, bevor Sie die folgenden Schritte ausführen.

Gehen Sie wie folgt vor, um die Android™-APK mit den Herstellerschlüsseln zu signieren:

1. Laden Sie die apk von Google Play oder von der Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/) herunter
1. Beschaffen Sie sich die Plattformschlüssel vom Hersteller, damit Sie eine *pk8* und ein *PEM* Datei

1. Suchen Sie das . `apksigner` Tool im Android™-SDK mit „Suchen“ `~/Library/Android/sdk/build-tools -name "apksigner"`
1. `<pathto> /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk`
1. Suchen des Pfads zum Zip Align Tool im Android™ SDK
1. `<pathto> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk`
1. Installieren Sie ***aemscreensaligned.apk*** mithilfe von adb install auf dem Gerät

## Grundlegendes zu Android™ Watchdog-Services {#android-watchdog-services}

Der Android-übergreifende Watchdog-Service wird mithilfe von als Cordova-Plug-in implementiert. *AlarmManager*.

Das folgende Diagramm zeigt die Implementierung des Watchdog-Service:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialisierung** - Zum Zeitpunkt der Initialisierung des Cordova-Plug-ins werden die Berechtigungen überprüft, um festzustellen, ob Sie Systemberechtigungen und damit die Berechtigung zum Neustart haben. Sind diese beiden Kriterien erfüllt, wird ein Pending-Intent für den Neustart erstellt. Andernfalls wird ein Pending-Intent für den Neustart der Anwendung (basierend auf ihrer Startaktivität) erstellt.

**2. Keep Alive-Timer** - Ein Keep-Alive-Timer wird verwendet, um alle 15 Sekunden ein Ereignis Trigger. Brechen Sie in diesem Fall die bestehende ausstehende Absicht ab (zum Neustart oder Neustart der App) und registrieren Sie eine neue ausstehende Absicht für dieselben 60 Sekunden in der Zukunft (und verschieben Sie im Wesentlichen den Neustart).

>[!NOTE]
>
>In Android™ wird die *AlarmManager* wird verwendet, um zu registrieren *PendingIntents* die auch dann ausgeführt werden kann, wenn die App abgestürzt ist und die Alarmausgabe von API 19 (Kitkat) nicht genau ist. Abstand zwischen dem Zeitgeberintervall und dem *AlarmManager* *von PendingIntent* Alarm.

**3. Anwendungsabsturz** - Bei einem Absturz wird die bei AlarmManager registrierte PendingIntent für Neustart nicht mehr zurückgesetzt. Daher wird ein Neustart oder Neustart der App ausgeführt (abhängig von den zum Zeitpunkt der Initialisierung des Cordova-Plug-ins verfügbaren Berechtigungen).

## Massenbereitstellung des Android™-Players {#bulk-provision-android-player}

Beim Massenrollout des Android™-Players muss der Player so bereitgestellt werden, dass er auf eine AEM-Instanz verweist und andere Eigenschaften konfiguriert, ohne diese manuell in die Admin-Benutzeroberfläche einzugeben.

>[!NOTE]
>Diese Funktion ist über den Android™-Player 42.0.372 verfügbar.

Gehen Sie wie folgt vor, um die Massenbereitstellung im Android™-Player zuzulassen:

1. Erstellen Sie eine JSON-Konfigurationsdatei mit dem Namen `player-config.default.json`.
Siehe ein [Beispiel einer JSON-Richtlinie](#example-json) und eine Tabelle, die die Verwendung der verschiedenen [Richtlinienattribute](#policy-attributes).

1. Verwenden Sie einen MDM- oder ADB- oder Android™ Studio-Datei-Explorer, um diese JSON-Richtliniendatei in abzulegen. *SDcard* Ordner auf dem Android™-Gerät.

1. Nachdem die Datei bereitgestellt wurde, installieren Sie die Player-App mit dem MDM.

1. Wenn die Player-Anwendung gestartet wird, wird diese Konfigurationsdatei gelesen und verweist auf den entsprechenden AEM-Server, auf dem sie registriert und dann gesteuert wird.

   >[!NOTE]
   >Diese Datei ist *Schreibgeschützt* Das erste Mal, dass die Anwendung gestartet wird und nicht für nachfolgende Konfigurationen verwendet werden kann. Wenn der Player gestartet wird, bevor die Konfigurationsdatei abgelegt wurde, deinstallieren Sie die Anwendung einfach und installieren Sie sie erneut auf dem Gerät.

### Richtlinienattribute {#policy-attributes}

Die folgende Tabelle fasst zur Referenz die Richtlinienattribute mit einer JSON-Beispielrichtlinie zusammen:

| **Richtlinienname** | **Zweck** |
|---|---|
| *Aufschläger* | Die URL zum Adobe Experience Manager-Server. |
| *resolution* | Die Auflösung des Geräts. |
| *rebootSchedule* | Der Zeitplan für den Neustart gilt für alle Plattformen. |
| *enableAdminUI* | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf *false* ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| *enableOSD* | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf *false* ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird |
| *enableActivityUI* | Aktivieren Sie diese Option, wenn Sie den Fortschritt von Aktivitäten wie Herunterladen und Synchronisieren anzeigen möchten. Aktivieren Sie diese Option zur Fehlerbehebung und deaktivieren Sie sie, sobald sie vollständig konfiguriert ist und sich in der Produktion befindet. |
| *enableNativeVideo* | Aktivieren Sie diese Option, wenn Sie die native Hardwarebeschleunigung für die Videowiedergabe verwenden möchten (nur Android™). |

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
>Alle Android™-Geräte haben eine `*sdcard*` Ordner, ob ein tatsächlicher `*sdcard*` wird eingefügt oder nicht. Diese Datei befindet sich bei Bereitstellung auf derselben Ebene wie der Ordner „Downloads“. Einige MDMs wie Samsung Knox verweisen möglicherweise auf diesen Ordner *sdcard* als *Interner Datenspeicher*.

## Massenbereitstellung von Android™-Playern mit Enterprise Mobility Management {#bulk-provisioning}

Wenn Sie den Android™-Player stapelweise bereitstellen, wird es mühsam, jeden Player manuell bei AEM zu registrieren. Es wird dringend empfohlen, eine EMM-Lösung (Enterprise Mobility Management) zu verwenden, z. B. [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), MobileIron oder Samsung Knox zur Remote-Bereitstellung und -Verwaltung Ihrer Bereitstellung. Der AEM Screens Android™-Player unterstützt die branchenübliche EMM AppConfig, um die Remote-Bereitstellung zu ermöglichen.

## Benennen des Android™-Players {#name-android}

Sie können Ihrem Android™-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an AEM (Adobe Experience Manager) senden. Mit dieser Funktion können Sie nicht nur Ihren Android™-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Sobald der Player registriert ist, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Android™-Player zu konfigurieren:

1. Navigieren zu **Einstellungen** > **Über das Gerät**
1. Bearbeiten Sie den Gerätenamen und legen Sie ihn fest, um Ihren Android™-Player zu benennen

### Implementieren der Massenbereitstellung des Android™-Players mit Enterprise Mobility Management {#implementation}

Gehen Sie wie folgt vor, um die Massenbereitstellung in Android™ Player zuzulassen:

1. Stellen Sie sicher, dass Ihr Android™-Gerät Google Play-Services unterstützt.
1. Registrieren Sie Ihre Android™-Player-Geräte mit Ihrer bevorzugten EMM-Lösung, die AppConfig unterstützt.
1. Melden Sie sich bei Ihrer EMM-Konsole an und rufen Sie die AEM Screens Player-Anwendung von Google Play ab.
1. Wählen Sie die verwaltete Konfiguration oder die zugehörige Option aus.
1. Sie sollten nun eine Liste der Player-Optionen sehen, die konfiguriert werden können, wie z. B. Server und Massenregistrierungs-Code.
1. Konfigurieren Sie diese Parameter, speichern Sie sie und stellen Sie die Richtlinie auf den Geräten bereit.

   >[!NOTE]
   >Die Geräte sollten das Programm zusammen mit der Konfiguration empfangen und auf den richtigen AEM-Server mit der ausgewählten Konfiguration verweisen. Wenn Sie den Massenregistrierungs-Code konfiguriert haben und ihn so belassen haben, wie er in AEM konfiguriert wurde, sollte sich der Player automatisch registrieren können. Wenn Sie ein Standarddisplay konfiguriert haben, können Standardinhalte heruntergeladen und angezeigt werden (die später nach Bedarf geändert werden können).

Sie sollten sich auch an Ihren EMM-Anbieter wenden, um Informationen zur AppConfig-Unterstützung zu erhalten. Die beliebtesten wie [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [`Mobile Iron`](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [`SOTI`](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [`BlackBerry&reg; UEM`](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [`IBM&reg; Maas360`](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm), und [`Samsung Knox`](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) Dieser Branchenstandard wird unter anderem unterstützt.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
