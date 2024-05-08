---
title: Tizen-Player
description: Auf dieser Seite wird die Installation und Funktionsweise des Tizen-Players beschrieben.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 45147959-b0ca-4d87-b89d-293e4b9af171
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 53%

---

# Implementieren des Tizen-Players {#tizen-player}

## Installieren des Tizen-Players {#installing-tizen-player}

Gehen Sie wie folgt vor, um den Tizen-Player für AEM Screens zu implementieren:

1. Navigieren Sie zum [AEM Screens Player-Downloads](https://download.macromedia.com/screens/) -Seite, damit Sie den Tizen-Player herunterladen können.

1. Installieren Sie die Tizen-Player-Datei *(.zip)* vom lokalen Gerät.

## Einrichten des HTTP-Servers {#setting-local-server}

>[!NOTE]
> Extrahieren Sie die ZIP-Datei und stellen Sie den Tizen-Player über einen `http server` zur Verfügung. (Der `http server` muss kein lokaler oder Apache-Server sein.)

Führen Sie dazu folgende Schritte durch:

1. Kopieren Sie die beiden extrahierten Dateien wie `AEMScreensPlayer.wgt` und `sssp_config.xml` in das Stammverzeichnis Ihres lokalen Apache-Webservers.

   >[!NOTE]
   >Die Datei `AEMScreensPlayer.wgt` ist das eigentliche Tizen-Player-Programm und `sssp_config.xml` enthält Informationen zu dieser Karte, die Ihnen bei der Installation auf dem Tizen-Gerät hilft.

1. Rufen Sie die IP- oder URL-Adresse Ihres lokalen HTTP-Servers ab (und den Pfad zu dem Ordner, der die in Schritt 2 extrahierten Dateien enthält, wenn er in einen Unterordner und nicht in den Stammordner extrahiert wird).

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

### Benennen des Tizen-Players {#name-tizen}

Sie können Ihrem Tizen-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Tizen-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Nachdem der Player registriert wurde, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Tizen-Player zu konfigurieren:

1. Drücken Sie die Menü-Taste Ihrer Fernbedienung.
1. Navigieren Sie zu **network** > **Gerätename** damit Sie dem Player einen Namen zuweisen können.

### Konfigurieren von Aktualisierungen auf dem Samsung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, damit Sie die Installation des AEM Screens-Players auf dem Gerät durchführen können:

1. Navigieren Sie zu Ihrem Samsung-Gerät und schalten Sie es ein.
1. Drücken Sie auf der Fernbedienung des Geräts die Taste **MENU** und blättern Sie in der linken Navigationsleiste nach unten zu **System**.
1. Scrollen Sie nach unten und klicken Sie auf **Wiedergabe über** und ändern Sie sie in **URL-Starter** -Option.
   ![Bild](/help/user-guide/assets/tizen/rms-2.png)
1. Wenn der URL-Starter festgelegt ist, drücken Sie die **Startseite** -Schaltfläche von Ihrem Remote-Standort aus.
1. Navigieren Sie zu den **URL-Starter-Einstellungen**, geben Sie die IP-Adresse des localhost-Servers ein und wählen Sie **Fertig**.

   >[!NOTE]
   >Der Tizen-Player sollte eine Verbindung zum HTTP-Server herstellen können.

1. Der AEM Screens Player installiert und startet automatisch auf Ihrem Samsung-Gerät.

   >[!NOTE]
   >Sowohl das Tizen-Gerät als auch der `http`-Server sollten in der Lage sein, eine Verbindung zueinander herzustellen, d. h. der Server sollte für den Tizen-Player erreichbar sein.


## Ausschließen von Benutzeragenten mit dem SameSite-Cookie-Problem {#exempting-user-agents}

>[!IMPORTANT]
>**Dieser Abschnitt gilt für Adobe Experience Manager (AEM 6.5.5 bis AEM 6.5.7.**
>
>Es gibt einige Browser-Engines, die mit dem *`SameSite=None`* Attribut, das im Anmeldetoken verwendet wird, das von AEM 6.5.5 bis AEM 6.5.7 herausgegeben wurde. Normalerweise kann das Problem durch ein Upgrade des Browsers auf die neueste verfügbare Version behoben werden. Manchmal sind solche Upgrades nicht möglich, z. B. bei intelligenten Displays, Set-Top-Boxen oder anderen Geräten mit eingebetteten Browsing-Engines.

Gehen Sie wie folgt vor, um diese inkompatiblen Clients auszuschließen, wenn Sie *SameSite=None* verwenden:

1. Aktualisieren Sie auf Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. Gehen Sie nach AEM Neustart zu `/system/console/configMgr` und suchen Sie nach **Adobe Granite Token Authentication Handler**. Setzen Sie den Wert für **SameSite** auf **None**.

1. Es sollte eine neue Option angezeigt werden *`User agents to be exempted from samesite attribute`*. Füllen Sie diese mit einem Regex, der dem/den Benutzeragenten entspricht, der/die mit dem *SameSite=None*-Attribut inkompatibel ist/sind.

   >[!NOTE]
   >
   >Weitere Informationen finden Sie unter [SameSite=None: Bekannte inkompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients). Verwenden Sie für den Tizen-Player den Regex: `(.*)Tizen(.*)`.

1. Registrieren Sie den Tizen-Player für Ihre Instanz von AEM 6.5.5 und höher. Er sollte sich registrieren und Inhalte normal anzeigen.

## Remote-Bereitstellung des Tizen-Players {#remote-provisioning}

Durch die Remote-Bereitstellung des Tizen-Players können Sie Hunderte und Tausende von Samsung Tizen-Anzeigen ohne großen Aufwand bereitstellen. Dadurch wird der manuelle Aufwand bei der Konfiguration jedes Players mit der Server-URL und dem Bulk-Registrierungs-Code oder anderen Parametern vermieden. Wenn AEM Screens as a Cloud Service ist, konfigurieren Sie den Cloud-Modus und das Cloud-Token.

Mit dieser Funktion können Sie den Tizen-Player remote konfigurieren und bei Bedarf auch zentral diese Konfigurationen aktualisieren. Sie benötigen lediglich den `HTTP`-Server, der zum Hosten des Tizen-Programms `(wgt and xml file)` verwendet wird, und einen Texteditor zum Speichern der `config.json` mit den entsprechenden Parametern.

Stellen Sie sicher, dass Sie die URL-Starter-Adresse auf dem Tizen-Gerät konfiguriert haben, d. h. Startseite > URL-Starter-Einstellungen.
Platzieren Sie auf dem `HTTP`-Server, der die Tizen-Anwendung hostet, die Datei `config.json` am selben Speicherort wie die Datei `wgt`. Der Dateiname muss `config.json` lauten.
Der Tizen-Player installiert und beim Start (und bei jedem Neustart) überprüft und wendet die Einstellungen in der `config.json` -Datei.

### Beispiel für eine JSON-Richtlinie {#example-json}

```java
{
  "server":  "http://your-aem-instance.com:4502",
  "registrationKey": "AdobeRocks!!",
  "enableAdminUI": true,
  "enableOSD": true,
  "enableActivityUI": true
}
```

### Richtlinienattribute und Zweck {#policy-attributes}

In der folgenden Tabelle sind die Richtlinien und deren Funktionen aufgeführt.

>[!NOTE]
>Richtlinienkonfigurationen werden streng durchgesetzt und können nicht manuell auf der Admin-Benutzeroberfläche des Players überschrieben werden. Um eine manuelle Player-Konfiguration für eine bestimmte Richtlinie zu ermöglichen, geben Sie die Richtlinie nicht in der Richtlinienkonfiguration an.
>Wenn Sie beispielsweise eine manuelle Konfiguration für den Neustart-Zeitplan zulassen möchten, geben Sie den Schlüssel nicht an `rebootSchedule` in der Richtlinienkonfiguration. Richtlinienkonfigurationen werden jedes Mal gelesen, wenn der Player neu geladen wird.

| **Richtlinienname** | **Zweck** |
|---|---|
| Server | Die URL zum Adobe Experience Manager (AEM)-Server. |
| registrationKey | Wird für die Massenregistrierung von Geräten mit vorab freigegebenen Schlüsseln verwendet. |
| resolution | Die Auflösung des Geräts. |
| rebootSchedule | Der Zeitplan zum Neustarten des Players. |
| enableAdminUI | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzer zwischen Kanälen auf dem Gerät wechseln können. Stellen Sie den Wert ggf. auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableActivityUI | Aktivieren Sie diese Option, damit Sie den Fortschritt von Aktivitäten wie Download und Synchronisierung anzeigen können. Aktivieren Sie diese Option zur Fehlerbehebung und deaktivieren Sie sie, sobald sie vollständig konfiguriert ist und sich in der Produktion befindet. |
| cloudMode | Setzen Sie dies auf „true“, wenn Sie möchten, dass der Tizen-Player eine Verbindung zu Screens as a Cloud Service herstellt. Auf &quot;false&quot;setzen, um eine Verbindung zu AMS oder On-Premise-AEM herzustellen. |
| cloudToken | Anmelde-Token zur Registrierung bei Screens as a Cloud Service. |


## Registrieren des Tizen-Geräts beim Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Führen Sie die folgenden Schritte aus, um das Tizen-Gerät beim Samsung Remote Management Service (RMS) zu registrieren und den URL-Starter remote zu konfigurieren:

>[!NOTE]
>Überprüfen Sie die Netzwerkeinstellungen und den Monitor.

1. Navigieren Sie zu **Menü** > **Netzwerk** > **Server-Netzwerkeinstellungen** und drücken Sie die **Eingabetaste**.

1. Navigieren Sie zur Server-Adresse, geben Sie den MagicInfo-URL-Zugriff ein und wählen Sie **Fertig**.

1. Richten Sie bei Bedarf TLS ein. Navigieren Sie zum Port, klicken Sie auf die Portnummer vom Server und klicken Sie auf **Speichern**.

1. Navigieren Sie zum **Gerät** und suchen Sie nach dem konfigurierten Gerät. Wenn ein Gerät gefunden wird, klicken Sie auf das Kontrollkästchen und dann auf **Genehmigen**.

   >![Bild](/help/user-guide/assets/tizen/rms-3.png)

1. Füllen Sie die erforderlichen Informationen aus und klicken Sie auf eine Gerätegruppe. Klicken Sie auf **OK**.

   >![Bild](/help/user-guide/assets/tizen/rms-7.png)

1. Wenn das Gerät genehmigt wurde, wird es in der Geräteliste angezeigt. Klicks *Informationen* auf Ihrem Gerät, wie im Folgenden gezeigt.

   >![Bild](/help/user-guide/assets/tizen/rms-6.png)

1. Das Dialogfeld „Geräteinformationen“ wird angezeigt. Klicken Sie auf **Geräteinformationen** Registerkarte und klicken Sie auf **Bearbeiten**.

   >![Bild](/help/user-guide/assets/tizen/rms-5.png)

1. Bearbeiten Sie die Geräteoptionen und klicken Sie auf die Schaltfläche **Einrichtung** Registerkarte. Navigieren Sie zu **URL-Starter** und geben Sie die URL ein, über die WGT gehostet wird, und `SSSP config file` damit Sie eine `SSSP` wie in der folgenden Abbildung dargestellt.

   ![image](/help/user-guide/assets/tizen/rms-9.png)

1. Klicken Sie auf **Speichern**.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
