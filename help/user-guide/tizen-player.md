---
title: Tizen-Player
description: Auf dieser Seite wird die Installation und Funktionsweise des Tizen-Players beschrieben.
translation-type: tm+mt
source-git-commit: 4c005ace7b1da94ed527164d6cfa09666d746273
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 21%

---


# Implementieren des Tizen-Players {#tizen-player}

## Installieren des Tizen-Players {#installing-tizen-player}

Gehen Sie wie folgt vor, um den Tizen-Player für AEM Screens zu implementieren:

1. Navigieren Sie zur Seite [AEM 6.5-Player-Downloads](https://download.macromedia.com/screens/), um den Tizen-Player herunterzuladen.

1. Installieren Sie die Zehn-Player-Datei *(.zip)* vom lokalen Computer.

## Ausnahme von Benutzeragenten mit dem Problem mit dem Samesite-Cookie {#exempting-user-agents}

>[!IMPORTANT]
>**Dieser Abschnitt gilt für AEM 6.5.5 bis AEM 6.5.7**
>Es gibt einige Browser-Engines, die mit dem Attribut *SameSite=None* inkompatibel sind, das im Anmeldetoken verwendet wird, das von AEM 6.5 bis AEM 6.7 herausgegeben wurde. In den meisten Fällen kann das Problem durch ein Upgrade des Browsers auf die neueste verfügbare Version behoben werden. In einigen Fällen sind solche Upgrades möglicherweise nicht möglich, z. B. mit intelligenten Displays, Set-Top-Boxen oder anderen Geräten mit eingebetteten Browsing-Engines. Gehen Sie wie folgt vor, um diese inkompatiblen Clients bei Verwendung von SameSite=None auszunehmen.

1. Laden Sie den Patch *jar file* von `https://artifactory.corp.adobe.com/artifactory/maven-aem-release-local/com/adobe/granite/crx-auth-token/2.6.10/` herunter.

1. Navigieren Sie in AEM zu `/system/console/bundles` und klicken Sie auf die Schaltfläche `install/update`.

1. Installieren Sie die JAR-Datei `crx-auth-token`. Nach der Installation dieser JAR-Datei müssen Sie möglicherweise den Vorgang beenden und AEM neu starten, da es sich um eine Authentifizierung handelt.

1. Gehen Sie nach AEM Neustart zu `/system/console/configMgr` und suchen Sie nach **Adobe Granite Token Authentication Handler**. Legen Sie für die Einstellung &quot;GleichSite&quot;den Wert &quot;Ohne&quot;fest.

1. Es sollte eine neue Option *Benutzeragenten angezeigt werden, die von demselben Site-Attribut* ausgenommen werden sollen. Füllen Sie diesen mit einem Regex entsprechend dem Benutzeragent/den Benutzeragenten, der/die nicht mit dem Attribut *SameSite=None* kompatibel ist/sind.
   >[!NOTE]
   >Siehe [SameSite=None: Bekannte inkompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients) finden Sie weitere Informationen.

1. Für den Zehn-Player verwenden Sie den regex: `(.*)Tizen (4|5)(.*)` Registrieren Sie den Tizen Player gegen Ihre AEM 6.5.5 und höher Instanz und es sollte sich registrieren und Inhalte normal anzeigen.


## Einrichten des lokalen Servers und Extrahieren der ZIP-Dateien {#setting-local-server}

Gehen Sie wie folgt vor, um den lokalen Server einzurichten und die extrahierten Dateien zu kopieren:

1. Rufen Sie die IP-Adresse Ihres lokalen Geräts ab.
   >[!NOTE]
   >In der offiziellen Dokumentation erfahren Sie, wie Sie den lokalen Server auf Ihrer Plattform aktivieren.

1. Navigieren Sie vom Terminal zum selben Verzeichnis des entpackten Installationsordners und überprüfen Sie, ob der lokale Host funktioniert.

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

1. Kopieren Sie die beiden extrahierten Dateien wie `AEMScreensPlayer.wgt` und `sssp_config.xml` in den Stammordner Ihres lokalen Apache-Webservers.

   >[!NOTE]
   >Die `AEMScreensPlayer.wgt`ist die eigentliche Tizen Player-Anwendung und `sssp_config.xml` enthält Informationen zu dieser Karte, die Ihnen bei der Installation auf dem Tizen-Gerät hilft.

### Konfigurieren von Aktualisierungen auf dem Samsung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, um die Installation des AEM Screens-Players auf dem Gerät abzuschließen:

1. Navigieren Sie zu Ihrem Samsung-Gerät und schalten Sie es ein.

1. Klicken Sie auf die Schaltfläche **MENU** aus der Remote-Umgebung des Geräts und blättern Sie von der linken Navigationsleiste nach unten zu **System**.

1. Blättern Sie nach unten und wählen Sie die Option **Über URL-Starter abspielen**.
   ![image](/help/user-guide/assets/tizen/rms-2.png)

1. Drücken Sie die Taste **Home** von Ihrer Remote-Site.

1. Geben Sie die IP-Adresse Ihres localhost-Servers ein.

1. Wählen Sie **Remote** im **Entwicklermodus** aus.

1. Klicken Sie auf der Fernbedienung des Geräts auf die Schaltfläche **Home** und wählen Sie **URL-Starter** aus.

1. Der AEM Screens-Player sollte jetzt automatisch auf Ihrem Samsung-Gerät installiert und gestartet werden.

## Massenbereitstellung des ZIP-Players {#bulk-provisioning-tizen-player}

>[!NOTE]
>Es kann eine mühsame Anstrengung sein, die Adresse Ihres AEM-Servers manuell in die Admin-Benutzeroberfläche jedes einzelnen Geräts für eine große Anzahl von Geräten einzugeben. Es wird empfohlen, die Samsung Remote Management (RMS)-Lösung für die Bereitstellung und Verwaltung der Lösung zu verwenden. Weitere Informationen finden Sie unter [Aktivieren des Tizen-Geräts beim Samsung Remote Management Service (RMS)](#enroll-tizen-device-rm).

Führen Sie die folgenden Schritte aus, um eine Massenbereitstellung durchzuführen, damit die Anwendung beim Starten auf Ihre AEM Autoreninstanz verweist:

1. Laden Sie das [Tizen Studio](https://developer.tizen.org/development/tizen-studio/download) herunter und installieren Sie es.
1. Öffnen Sie die Datei `wgt` mit dem Tizen-Studio.
1. Öffnen Sie die Datei `firmware-platform.js`, suchen Sie nach `DEFAULT_PREFERENCES` und ändern Sie die Server-URL in die AEM Autor-URL und speichern Sie sie.
1. Erstellen Sie die neue Datei `wgt`.

   >[!NOTE]
   >Möglicherweise müssen Sie ein Unterschriftszertifikat erstellen oder einrichten.

1. Stellen Sie diese neue `wgt` Datei-RMS bereit. Wenn der Player startet, sollte sie automatisch auf Ihren Server verweisen, damit Sie sie nicht für jedes Gerät manuell eingeben müssen.

### Aktivieren des Tizen-Geräts für den Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Gehen Sie wie folgt vor, um das Tizen-Gerät beim Samsung Remote Management Service (RMS) anzumelden und den URL Launcher remote zu konfigurieren:

>[!NOTE]
>Überprüfen Sie die Netzwerkeinstellungen und den Monitor.

1. Navigieren Sie zu **Menü** -> **Netzwerk** -> **Servernetzwerkeinstellungen** und drücken Sie **Eingabetaste**.

   >[!NOTE]
   >Überprüfen Sie, ob der Bildschirm auf &quot;Über URL-Starter abspielen&quot;eingerichtet ist.
   >![image](/help/user-guide/assets/tizen/rms-2.png)

1. Navigieren Sie zur Serveradresse und geben Sie den Zugriff auf die MagicInfo-URL ein und drücken Sie Fertig.

1. Richten Sie ggf. TLS ein. Navigieren Sie zum Anschluss und wählen Sie die Anschlussnummer vom Server aus. Klicken Sie auf **Speichern**.

1. Navigieren Sie zur Registerkarte &quot;Gerät&quot;und suchen Sie nach dem Gerät, das Sie gerade konfiguriert haben.

1. Sobald ein Gerät gefunden wurde, klicken Sie auf das Kontrollkästchen und wählen Sie **Genehmigen**.

1. Füllen Sie die erforderlichen Informationen aus und wählen Sie eine Gerätegruppe aus. Klicken Sie auf **OK**, um den Genehmigungsprozess abzuschließen.

   >![image](/help/user-guide/assets/tizen/rms-7.png)

1. Sobald das Gerät genehmigt wurde, sollte es auf der Liste des Geräts angezeigt werden. Klicken Sie auf die Schaltfläche *Informationen* in Ihrem Gerätefeld **i**.

   >![image](/help/user-guide/assets/tizen/rms-6.png)

1. Das Dialogfeld &quot;Geräteinformationen&quot;wird angezeigt. Wählen Sie die Registerkarte **Geräteinformationen** und klicken Sie auf **Bearbeiten**.

1. Bearbeiten Sie die Geräteoptionen und wählen Sie die Registerkarte **Setup**. Navigieren Sie zum Abschnitt **URL-Starter** und geben Sie die URL ein, die als Host für die WGT dient, und `SSSP config file`, um eine `SSSP`-Anwendung zu installieren, wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/tizen/rms-9.png)

1. Klicken Sie auf **Speichern**, damit die Änderungen auf dem Anzeigebereich angezeigt werden.




