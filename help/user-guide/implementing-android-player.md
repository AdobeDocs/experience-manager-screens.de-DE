---
title: Implementieren des Android-Players
description: Erfahren Sie mehr über die Implementierung von Android Watchdog, einer Lösung, mit der Sie den Android-Player nach Abstürzen wiederherstellen können.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
feature: Administering Screens, Android Player
role: Admin
level: Intermediate
exl-id: d1331cb8-8bf6-4742-9525-acf18707b4d8
source-git-commit: e82cfee5ecc6b639b7b2b65553d1635943b356ea
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 25%

---

# Implementieren von Android™ Player {#implementing-android-player}

In diesem Abschnitt wird die Konfiguration des Android™-Players beschrieben. Er enthält Informationen zur Konfigurationsdatei und präsentiert die verfügbaren Optionen und Empfehlungen zu den zum Entwickeln und Testen zu verwendenden Einstellungen.

Außerdem **Watchdog** ist eine Lösung, um den Player nach Abstürzen wiederherzustellen. Eine Anwendung muss sich beim Watchdog-Dienst registrieren und dann regelmäßig Nachrichten an den Dienst senden, dass er aktiv ist. Falls der Watchdog-Dienst nicht innerhalb einer festgelegten Zeit eine Keep-Alive-Meldung erhält, versucht der Dienst, das Gerät neu zu starten. Dies geschieht für eine saubere Wiederherstellung (wenn es über die nötigen Berechtigungen verfügt) oder startet die Anwendung neu.

## Installieren des Android™-Players {#installing-android-player}

Installieren Sie Android™ Player für AEM Screens, um den Android™ Player für AEM Screens zu implementieren.

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

Mit der Ad-hoc-Methode können Sie den neuesten Android™ Player (*.exe*). Rufen Sie die Seite [**AEM 6.5 Player-Downloads**](https://download.macromedia.com/screens/) auf.

Nachdem Sie die Anwendung heruntergeladen haben, führen Sie die Schritte auf dem Player aus, um die Ad-hoc-Installation abzuschließen:

1. Halten Sie die linke obere Ecke gedrückt, um das Admin-Bedienfeld zu öffnen.
1. Navigieren Sie im linken Aktionsmenü zu **Konfiguration**, geben Sie den Standort (die Adresse) der AEM-Instanz ein, zu der Sie eine Verbindung aufbauen möchten, und klicken Sie auf **Speichern**.

1. Navigieren Sie zum **Gerät** **Registrierung** im linken Aktionsmenü, damit Sie den Status des Prozesses zur Geräteregistrierung überprüfen können.

>[!NOTE]
>
>Wenn die Variable **Bundesland** is **REGISTRIERT**, können Sie sehen, dass die Variable **Geräte-ID** -Feld gefüllt wird.
>
>Wenn der **Status** **UNREGISTRIERT** ist, können Sie das Gerät mithilfe des **Tokens** registrieren.

## Implementieren von Android™ Watchdog {#implementing-android-watchdog}

Aufgrund der Architektur von Android™ muss das neu starten des Geräts über Systemberechtigungen verfügen. Signieren Sie die apk mit den Signaturschlüsseln des Herstellers. Andernfalls kann der Watchdog die Player-Anwendung neu starten und das Gerät nicht neu starten.

### Signage von Android™ `apks` Verwenden von Herstellerschlüsseln {#signage-of-android-apks-using-manufacturer-keys}

So greifen Sie auf die berechtigten APIs von Android™ zu, z. B. *PowerManager* oder *HDMIControlServices*, unterschreiben Sie Android™. `apk` unter Verwendung der Herstellerschlüssel.

>[!CAUTION]
>
>Voraussetzungen:
>
>Sie sollten das Android™ SDK installiert haben, bevor Sie die folgenden Schritte ausführen.

Gehen Sie wie folgt vor, um die Android™-apk mithilfe der Herstellerschlüssel zu signieren:

1. Laden Sie die apk aus Google Play oder aus dem [AEM Screens Player-Downloads](https://download.macromedia.com/screens/) page
1. Besorgen Sie sich die Plattformschlüssel vom Hersteller, damit Sie eine *pk8* und *pem* file

1. Suchen Sie die `apksigner` Tool in Android™ SDK mit der Suchfunktion `~/Library/Android/sdk/build-tools -name "apksigner"`
1. `<pathto> /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk`
1. Suchen Sie den Pfad zum Zip-Graph-Tool im Android™ SDK.
1. `<pathto> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk`
1. Installieren Sie ***aemscreensaligned.apk*** mithilfe von adb install auf dem Gerät

## Grundlegendes zu Android™ Watchdog-Services {#android-watchdog-services}

Der Android-Watchdog-übergreifende Dienst wird als Cordova-Plug-in implementiert, indem er *AlarmManager*.

Das folgende Diagramm zeigt die Implementierung des Watchdog-Dienstes:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialisierung** - Zum Zeitpunkt der Initialisierung des Cordova-Plug-ins werden die Berechtigungen überprüft, um festzustellen, ob Sie über Systemberechtigungen und somit über die Berechtigung zum Neustart verfügen. Sind diese beiden Kriterien erfüllt, wird ein Pending-Intent für den Neustart erstellt. Andernfalls wird ein Pending-Intent für den Neustart der Anwendung (basierend auf ihrer Startaktivität) erstellt.

**2. Keep-Alive-Timer** - Ein Keep-Alive-Timer wird verwendet, um alle 15 Sekunden ein Ereignis Trigger. In diesem Fall brechen Sie den vorhandenen Pending-Intent ab (um die App neu zu starten) und registrieren Sie einen neuen Pending-Intent für dieselben 60 Sekunden in der Zukunft (im Wesentlichen wird der Neustart verschoben).

>[!NOTE]
>
>In Android™ wird die *AlarmManager* wird verwendet, um die *pendingIntents* kann auch dann ausgeführt werden, wenn die App abgestürzt ist und die Alarmbereitstellung von API 19 (Kitkat) ungenau ist. Zwischen dem Timer-Intervall und dem *AlarmManager* *pendingIntent&#39;s* Alarm.

**3. Anwendungsabsturz** - Bei einem Absturz wird der pendingIntent für den Neustart, der beim AlarmManager registriert ist, nicht mehr zurückgesetzt. Daher wird ein Neustart des Programms ausgeführt (abhängig von den zum Zeitpunkt der Initialisierung des Cordova-Plug-ins verfügbaren Berechtigungen).

## Massenbereitstellung von Android™ Player {#bulk-provision-android-player}

Wenn der Android™-Player stapelweise eingeführt wird, muss der Player auf eine AEM Instanz verweisen und andere Eigenschaften konfigurieren, ohne sie manuell in der Admin-Benutzeroberfläche einzugeben.

>[!NOTE]
>Diese Funktion ist ab Android™ Player 42.0.372 verfügbar.

Gehen Sie wie folgt vor, um die Massenbereitstellung im Android™-Player zuzulassen:

1. Erstellen Sie eine JSON-Konfigurationsdatei mit dem Namen `player-config.default.json`.
Anzeigen einer [Beispiel-JSON-Richtlinie](#example-json) und einer Tabelle, die die Verwendung der verschiedenen [Richtlinienattribute](#policy-attributes).

1. Verwenden Sie einen MDM- oder ADB- oder Android™ Studio-Datei-Explorer, um diese JSON-Richtliniendatei im *sdcard* auf dem Android™-Gerät.

1. Wenn die Datei bereitgestellt ist, verwenden Sie das MDM, um die Player-Anwendung zu installieren.

1. Wenn die Player-Anwendung gestartet wird, wird diese Konfigurationsdatei gelesen und auf den entsprechenden AEM-Server verwiesen, auf dem sie registriert und dann gesteuert wird.

   >[!NOTE]
   >Diese Datei ist *schreibgeschützt* wenn die Anwendung zum ersten Mal gestartet wird und nicht für nachfolgende Konfigurationen verwendet werden kann. Wenn der Player vor dem Ablegen der Konfigurationsdatei gestartet wird, deinstallieren Sie die Anwendung einfach und installieren Sie sie erneut auf dem Gerät.

### Richtlinienattribute {#policy-attributes}

Die folgende Tabelle fasst zur Referenz die Richtlinienattribute mit einer JSON-Beispielrichtlinie zusammen:

| **Richtlinienname** | **Zweck** |
|---|---|
| *server* | Die URL zum Adobe Experience Manager-Server. |
| *resolution* | Die Auflösung des Geräts. |
| *rebootSchedule* | Der Zeitplan für den Neustart gilt für alle Plattformen. |
| *enableAdminUI* | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf *false* ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| *enableOSD* | Aktivieren Sie die Benutzeroberfläche für den Kanalschalter, damit Benutzer die Kanäle auf dem Gerät wechseln können. Legen Sie dafür fest, dass *false* nach der vollständigen Konfiguration und in der Produktion. |
| *enableActivityUI* | Aktivieren Sie diese Option, wenn Sie den Fortschritt von Aktivitäten wie Download und Synchronisierung anzeigen möchten. Aktivieren Sie diese Option zur Fehlerbehebung und deaktivieren Sie sie, sobald sie vollständig konfiguriert ist und sich in der Produktion befindet. |
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
>Alle Android™-Geräte verfügen über eine `*sdcard*` Ordner, ob ein tatsächlicher `*sdcard*` wird eingefügt oder nicht. Diese Datei befindet sich bei Bereitstellung auf derselben Ebene wie der Ordner „Downloads“. Einige MDMs, wie Samsung Knox, sehen dies möglicherweise *sdcard* Ordnerspeicherort als *Interner Speicher*.

## Massenbereitstellung von Android™-Player mithilfe von Enterprise Mobility Management {#bulk-provisioning}

Bei der Massenbereitstellung des Android™-Players wird es mühsam, jeden Player manuell bei AEM zu registrieren. Verwenden Sie eine EMM-Lösung (Enterprise Mobility Management) wie [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), MobileIron oder Samsung Knox verwenden, damit Sie Ihre Implementierung remote bereitstellen und verwalten können. Der AEM Screens Android™ Player unterstützt die standardmäßige EMM AppConfig-Lösung, die die Remote-Bereitstellung ermöglicht.

## Benennen von Android™ Player {#name-android}

Sie können Ihrem Android™-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an AEM (Adobe Experience Manager) senden. Mit dieser Funktion können Sie nicht nur Ihren Android™-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Nachdem der Player registriert wurde, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Android™-Player zu konfigurieren:

1. Navigieren Sie zu **settings** > **Über Geräte**
1. Bearbeiten Sie den Gerätenamen und legen Sie ihn fest, um den Android™-Player zu benennen.

### Implementieren der Massenbereitstellung von Android™ Player mithilfe von Enterprise Mobility Management {#implementation}

Gehen Sie wie folgt vor, um die Massenbereitstellung im Android™-Player zuzulassen:

1. Stellen Sie sicher, dass Ihr Android™-Gerät Google Play-Dienste unterstützt.
1. Registrieren Sie Ihre Android™-Player-Geräte mit Ihrer bevorzugten EMM-Lösung, die AppConfig unterstützt.
1. Melden Sie sich bei Ihrer EMM-Konsole an und rufen Sie die AEM Screens Player-Anwendung von Google Play ab.
1. Klicken Sie auf die Option &quot;Verwaltete Konfiguration&quot;oder &quot;Zugehörige&quot;.
1. Sie sollten nun eine Liste der Player-Optionen sehen, die konfiguriert werden können, wie z. B. Server und Massenregistrierungs-Code.
1. Konfigurieren Sie diese Parameter, speichern Sie sie und stellen Sie die Richtlinie auf den Geräten bereit.

   >[!NOTE]
   >Die Geräte sollten die Anwendung zusammen mit der Konfiguration erhalten. Er sollte auf den richtigen AEM-Server mit der ausgewählten Konfiguration verweisen. Wenn Sie sich dafür entschieden haben, den Massenregistrierungscode zu konfigurieren und ihn so zu halten, wie in AEM konfiguriert, sollte der Player sich automatisch registrieren können. Wenn Sie eine Standardanzeige konfiguriert haben, kann sie auch einige Standardinhalte herunterladen und anzeigen (die später nach Belieben geändert werden können).

Wenden Sie sich außerdem an Ihren EMM-Anbieter, wenn Sie Fragen zur AppConfig-Unterstützung haben. Am häufigsten verwendete [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [`Mobile Iron`](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [`SOTI`](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [`BlackBerry&reg; UEM`](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [`IBM&reg; Maas360`](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm), und [`Samsung Knox`](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) unterstützen unter anderem diesen Industriestandard.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
