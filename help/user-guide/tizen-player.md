---
title: Tizen-Player
description: Auf dieser Seite wird die Installation und Funktionsweise des Tizen-Players beschrieben.
translation-type: tm+mt
source-git-commit: dc2fedaa5726e1013e1b51f429ba19e4a709de28
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 27%

---


# Implementieren des Tizen-Players {#tizen-player}

## Installieren des Tizen-Players {#installing-tizen-player}

Gehen Sie wie folgt vor, um den Tizen-Player für AEM Screens zu implementieren:

1. Navigieren Sie zur Seite [AEM 6.5-Player-Downloads](https://download.macromedia.com/screens/), um den Tizen-Player herunterzuladen.

1. Installieren Sie die Zehn-Player-Datei *(.zip)* vom lokalen Computer.

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
   ![image](/help/user-guide/assets/tizen/url-launcher.png)

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

Gehen Sie wie folgt vor, um das Tizen-Gerät beim Samsung Remote Management Service (RMS) zu registrieren und den URL Launcher remote zu konfigurieren:

>[!NOTE]
>Überprüfen Sie die Netzwerkeinstellungen und den Monitor.

1. Navigieren Sie zu **Menü** -> **Netzwerk** -> **Servernetzwerkeinstellungen** und drücken Sie **Eingabetaste**.

   >[!NOTE]
   >Überprüfen Sie, ob der Bildschirm auf &quot;Über URL-Starter abspielen&quot;eingerichtet ist.

1. Navigieren Sie zur Serveradresse und geben Sie den Zugriff auf die MagicInfo-URL ein und drücken Sie Fertig.

1. TLS je nach Fall verwenden oder nicht verwenden
   1. Wechseln Sie zum Anschluss und wählen Sie die Anschlussnummer vom Server aus.
   1. Treten Sie auf Speichern, sobald die Optionen bereit sind.

1. Navigieren Sie zur Registerkarte &quot;Gerät&quot;, sobald Sie sich bei MIS angemeldet haben.
   1. Suchen Sie nach dem Gerät, das Sie gerade konfiguriert haben, indem Sie die IP-Adresse und/oder die Mac-Adresse ansehen.
   1. Sobald ein Gerät gefunden wurde, klicken Sie auf das Kontrollkästchen und wählen Sie Genehmigen.

1. Wenn Sie auf die Schaltfläche Genehmigt geklickt haben, wird das folgende Popup angezeigt
   1. Füllen Sie die erforderlichen Informationen aus
   1. Gerätegruppe auswählen
   1. Klicken Sie auf OK, um den Genehmigungsprozess abzuschließen.

1. Sobald das Gerät genehmigt wurde, sollte es wie folgt auf der Liste des Geräts angezeigt werden.
   1. Klicken Sie auf die Schaltfläche &quot;Informationen&quot;im Feld &quot;i&quot;.

1. Das Popup für Geräteinformationen erscheint wie folgt und klicken Sie auf die Schaltfläche &quot;Bearbeiten&quot;.

1. Die Optionen zum Bearbeiten des Geräts werden wie folgt angezeigt und wählen Sie die Registerkarte &quot;Einstellungen&quot;.

1. Suchen Sie den Abschnitt &quot;URL-Starter&quot;und geben Sie die URL ein, die als Host für den Wgt dient, und `SSSP config file`, um eine SSSP-Anwendung zu installieren.




