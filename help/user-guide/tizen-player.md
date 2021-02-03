---
title: Tizen-Player
description: Auf dieser Seite wird die Installation und Funktionsweise des Tizen-Players beschrieben.
translation-type: ht
source-git-commit: 2ace2f926900304377afcd6187462545a60784d3
workflow-type: ht
source-wordcount: '905'
ht-degree: 100%

---


# Implementieren des Tizen-Players {#tizen-player}

## Installieren des Tizen-Players {#installing-tizen-player}

Gehen Sie wie folgt vor, um den Tizen-Player für AEM Screens zu implementieren:

1. Navigieren Sie zur Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/), um den Tizen-Player herunterzuladen.

1. Installieren Sie die Tizen-Player-Datei *(.zip)* vom lokalen Gerät.

## Einrichten des lokalen Servers und Extrahieren der ZIP-Dateien {#setting-local-server}

>[!NOTE]
> Extrahieren Sie die ZIP-Datei und stellen Sie den Tizen-Player über einen `http server` zur Verfügung. (Der `http server` muss kein lokaler oder Apache-Server sein.)

Führen Sie dazu folgende Schritte durch:

1. Kopieren Sie die beiden extrahierten Dateien wie `AEMScreensPlayer.wgt` und `sssp_config.xml` in das Stammverzeichnis Ihres lokalen Apache-Webservers.

   >[!NOTE]
   >Die Datei `AEMScreensPlayer.wgt` ist das eigentliche Tizen-Player-Programm und `sssp_config.xml` enthält Informationen zu dieser Karte, die Ihnen bei der Installation auf dem Tizen-Gerät hilft.

1. Rufen Sie die IP oder URL Ihres lokalen HTTP-Servers ab (und den Pfad zu dem Ordner, der die in Schritt 2 extrahierten Dateien enthält, wenn diese in einen Unterordner und nicht in den Stammordner extrahiert wurden).

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

### Konfigurieren von Aktualisierungen auf dem Samsung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, um die Installation des AEM Screens-Players auf dem Gerät abzuschließen:

1. Navigieren Sie zu Ihrem Samsung-Gerät und schalten Sie es ein.

1. Drücken Sie auf der Fernbedienung des Geräts die Taste **MENU** und blättern Sie in der linken Navigationsleiste nach unten zu **System**.

1. Blättern Sie nach unten und wählen Sie die Option **Wiedergabe über** aus und ändern Sie sie in **URL-Starter**.
   ![image](/help/user-guide/assets/tizen/rms-2.png)

1. Sobald der URL-Starter eingestellt ist, drücken Sie die Taste **Home** auf Ihrer Fernbedienung.

1. Navigieren Sie zu den **URL-Starter-Einstellungen**, geben Sie die IP-Adresse des localhost-Servers ein und wählen Sie **Fertig**.
   >[!NOTE]
   >Der Tizen-Player sollte eine Verbindung zum HTTP-Server herstellen können.

1. Der AEM Screens-Player sollte jetzt automatisch auf Ihrem Samsung-Gerät installiert und gestartet werden.

   >[!NOTE]
   >Sowohl das Tizen-Gerät als auch der `http`-Server sollten in der Lage sein, eine Verbindung zueinander herzustellen, d. h. der Server sollte für den Tizen-Player erreichbar sein.


## Ausschließen von Benutzeragenten mit dem SameSite-Cookie-Problem {#exempting-user-agents}

>[!IMPORTANT]
>**Dieser Abschnitt gilt für Adobe Experience Manager (AEM) 6.5.5 bis AEM 6.5.7**
>Es gibt einige Browser-Engines, die mit dem Attribut *SameSite=None* inkompatibel sind, das im Anmelde-Token verwendet wird, das von AEM 6.5 bis AEM 6.7 herausgegeben wurde. In den meisten Fällen kann das Problem durch eine Aktualisierung des Browsers auf die neueste verfügbare Version behoben werden. In einigen Fällen sind solche Aktualisierungen möglicherweise nicht möglich, z. B. bei intelligenten Displays, Set-Top-Boxen oder anderen Geräten mit eingebetteten Browsing-Engines.

Gehen Sie wie folgt vor, um diese inkompatiblen Clients auszuschließen, wenn Sie *SameSite=None* verwenden:

1. Aktualisieren Sie auf Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. Gehen Sie nach dem Neustart von AEM zu `/system/console/configMgr` und suchen Sie nach **Adobe Granite Token Authentication Handler**. Setzen Sie den Wert für **SameSite** auf **None**.

1. Sie sollten eine neue Option sehen: *Benutzeragenten, die vom SameSite-Attribut ausgenommen werden sollen*. Füllen Sie diese mit einem Regex, der dem/den Benutzeragenten entspricht, der/die mit dem *SameSite=None*-Attribut inkompatibel ist/sind.
   >[!NOTE]
   >Weitere Informationen finden Sie unter [SameSite=None: Bekannte inkompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients). Verwenden Sie folgenden Regex für den Tizen-Player: `(.*)Tizen(.*)`.

1. Registrieren Sie den Tizen-Player für Ihre Instanz von AEM 6.5.5 und höher. Er sollte sich registrieren und Inhalte normal anzeigen.

## Massenbereitstellung von Tizen-Player {#bulk-provisioning-tizen-player}

>[!NOTE]
>Es kann mühsam sein, die Adresse Ihres AEM-Servers für eine große Anzahl von Geräten manuell in die Administrator-Benutzeroberfläche jedes einzelnen Geräts einzugeben. Es wird empfohlen, die Samsung Remote Management (RMS)-Lösung für die Bereitstellung und Verwaltung größerer Lösungen zu verwenden. Weitere Informationen finden Sie unter [Registrieren des Tizen-Geräts beim Samsung Remote Management Service (RMS)](#enroll-tizen-device-rm).

Befolgen Sie die folgenden Schritte zur Massenbereitstellung des Programms, damit sie beim Start auf Ihre AEM-Autoreninstanz verweist:

1. Laden und installieren Sie [Tizen Studio](https://developer.tizen.org/development/tizen-studio/download).
1. Öffnen Sie die Datei `wgt` mit Tizen Studio.
1. Öffnen Sie die Datei `firmware-platform.js`, suchen Sie nach `DEFAULT_PREFERENCES` und ändern Sie die Server-URL in die AEM Author-URL und speichern Sie sie.
1. Erstellen Sie die neue `wgt`-Datei.

   >[!NOTE]
   >Möglicherweise müssen Sie ein Signaturzertifikat erstellen oder einrichten.

1. Stellen Sie diese neue `wgt`-Datei mit RMS oder URL-Starter bereit. Wenn der Player gestartet wird, sollte sie automatisch auf Ihren Server verweisen, damit Sie sie nicht für jedes Gerät manuell eingeben müssen.

### Registrieren des Tizen-Geräts beim Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Führen Sie die folgenden Schritte aus, um das Tizen-Gerät beim Samsung Remote Management Service (RMS) zu registrieren und den URL-Starter remote zu konfigurieren:

>[!NOTE]
>Überprüfen Sie die Netzwerkeinstellungen und den Monitor.

1. Navigieren Sie zu **Menü** > **Netzwerk** > **Server-Netzwerkeinstellungen** und drücken Sie die **Eingabetaste**.

1. Navigieren Sie zur Server-Adresse, geben Sie den MagicInfo-URL-Zugriff ein und wählen Sie **Fertig**.

1. Richten Sie ggf. TLS ein. Navigieren Sie zum Port, wählen Sie die Port-Nummer vom Server aus und klicken Sie auf **Speichern**.

1. Navigieren Sie zur Registerkarte **Gerät** und suchen Sie nach dem konfigurierten Gerät. Sobald ein Gerät gefunden wurde, klicken Sie auf das Kontrollkästchen und wählen Sie **Genehmigen** aus.

   >![image](/help/user-guide/assets/tizen/rms-3.png)

1. Füllen Sie die erforderlichen Informationen aus und wählen Sie eine Gerätegruppe aus. Klicken Sie auf **OK**, um den Genehmigungsprozess abzuschließen.

   >![image](/help/user-guide/assets/tizen/rms-7.png)

1. Sobald das Gerät genehmigt wurde, sollte es in der Geräteliste angezeigt werden. Klicken Sie auf die Schaltfläche *Informationen* in Ihrem Gerätefeld, d. h. auf **i**, wie in der Abbildung unten dargestellt.

   >![image](/help/user-guide/assets/tizen/rms-6.png)

1. Das Dialogfeld „Geräteinformationen“ wird angezeigt. Wählen Sie die Registerkarte **Geräteinformationen** aus und klicken Sie auf **Bearbeiten**.

   >![image](/help/user-guide/assets/tizen/rms-5.png)

1. Bearbeiten Sie die Geräteoptionen und wählen Sie die Registerkarte **Einrichtung** aus. Navigieren Sie zum Abschnitt **URL-Starter** und geben Sie die URL ein, die als WGT-Host dient, und `SSSP config file`, um ein `SSSP`-Programm zu installieren, wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/tizen/rms-9.png)

1. Klicken Sie auf **Speichern**, damit die Änderungen auf dem Bildschirm angezeigt werden.

