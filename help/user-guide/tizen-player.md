---
title: Tizen-Player
description: Erfahren Sie mehr über die Installation und Funktionsweise des Tizen-Players.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 45147959-b0ca-4d87-b89d-293e4b9af171
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 96%

---

# Implementieren des Tizen-Players {#tizen-player}

## Installieren des Tizen-Players {#installing-tizen-player}

Gehen Sie wie folgt vor, um den Tizen-Player für AEM Screens zu implementieren:

1. Navigieren Sie zur Seite [AEM Screens-Player-Downloads](https://download.macromedia.com/screens/), um den Tizen-Player herunterzuladen.

1. Installieren Sie die Tizen-Player-Datei *(.zip)* von Ihrem lokalen Gerät.

## Einrichten des HTTP-Servers {#setting-local-server}

>[!NOTE]
> Extrahieren Sie die ZIP-Datei und stellen Sie den Tizen-Player über einen `http server` zur Verfügung. (Der `http server` muss kein lokaler oder Apache-Server sein.)

Führen Sie dazu folgende Schritte durch:

1. Kopieren Sie die beiden extrahierten Dateien wie `AEMScreensPlayer.wgt` und `sssp_config.xml` in das Stammverzeichnis Ihres lokalen Apache-Webservers.

   >[!NOTE]
   >Die Datei `AEMScreensPlayer.wgt` ist das eigentliche Tizen-Player-Programm und `sssp_config.xml` enthält Informationen zu dieser Karte, die Ihnen bei der Installation auf dem Tizen-Gerät hilft.

1. Rufen Sie die IP oder URL Ihres lokalen HTTP-Servers ab (und den Pfad zu dem Ordner, der die in Schritt 2 extrahierten Dateien enthält, wenn diese in einen Unterordner und nicht in den Stammordner extrahiert wurden).

1. Der Tizen-Player lädt das Installationsprogramm vom lokalen Server herunter.

### Benennen des Tizen-Players {#name-tizen}

Sie können Ihrem Tizen-Player einen benutzerfreundlichen Gerätenamen zuweisen und so den zugewiesenen Gerätenamen an Adobe Experience Manager (AEM) senden. Mit dieser Funktion können Sie nicht nur Ihren Tizen-Player benennen, sondern auch mühelos geeignete Inhalte zuweisen.

>[!NOTE]
>Sie können den Player-Namen nur vor der Registrierung auswählen. Nachdem der Player registriert wurde, kann der Player-Name nicht mehr geändert werden.

Gehen Sie wie folgt vor, um den Namen im Tizen-Player zu konfigurieren:

1. Drücken Sie die Menütaste Ihrer Fernbedienung.
1. Navigieren Sie zu **Netzwerk** > **Gerätename**, um dem Player einen Namen zuzuweisen.

### Konfigurieren von Aktualisierungen auf dem Samsung-Gerät {#config-updates}

Führen Sie die folgenden Schritte auf dem Samsung-Gerät aus, um die Installation des AEM Screens-Players auf dem Gerät abzuschließen:

1. Navigieren Sie zu Ihrem Samsung-Gerät und schalten Sie es ein.
1. Drücken Sie auf der Fernbedienung des Geräts die Taste **MENU** und blättern Sie in der linken Navigationsleiste nach unten zu **System**.
1. Blättern Sie nach unten, wählen Sie die Option **Wiedergabe über** aus und ändern Sie sie in **URL-Starter**.
   ![Bild](/help/user-guide/assets/tizen/rms-2.png)
1. Sobald der URL-Starter eingestellt ist, drücken Sie die Taste **Home** auf Ihrer Fernbedienung.
1. Navigieren Sie zu den **URL-Starter-Einstellungen**, geben Sie die IP-Adresse des localhost-Servers ein und klicken Sie auf **Fertig**.

   >[!NOTE]
   >Der Tizen-Player sollte eine Verbindung zum HTTP-Server herstellen können.

1. Der AEM Screens-Player wird automatisch auf Ihrem Samsung-Gerät installiert und gestartet.

   >[!NOTE]
   >Sowohl das Tizen-Gerät als auch der `http`-Server sollten in der Lage sein, eine Verbindung zueinander herzustellen, d. h. der Server sollte für den Tizen-Player erreichbar sein.


## Ausschließen von Benutzeragenten mit dem SameSite-Cookie-Problem {#exempting-user-agents}

>[!IMPORTANT]
>**Dieser Abschnitt gilt für Adobe Experience Manager (AEM) 6.5.5 bis AEM 6.5.7**
>
>Es gibt einige Browser-Engines, die mit dem Attribut *`SameSite=None`*, das im von AEM 6.5 bis AEM 6.7 herausgegebenen Anmelde-Token verwendet wird, inkompatibel sind. In den meisten Fällen kann das Problem durch eine Aktualisierung des Browsers auf die neueste verfügbare Version behoben werden. Manchmal sind solche Aktualisierungen möglicherweise nicht möglich, z. B. bei intelligenten Displays, Set-Top-Boxen oder anderen Geräten mit eingebetteten Browsing-Engines.

Gehen Sie wie folgt vor, um diese inkompatiblen Clients auszuschließen, wenn Sie *SameSite=None* verwenden:

1. Aktualisieren Sie auf Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. Navigieren Sie nach dem Neustart von AEM zu `/system/console/configMgr` und suchen Sie nach **Adobe Granite Token Authentication Handler**. Setzen Sie den Wert für **SameSite** auf **None**.

1. Es sollte eine neue Option *`User agents to be exempted from samesite attribute`* sichtbar sein. Füllen Sie diese mit einem Regex, der den Benutzeragenten entspricht, die mit dem Attribut *SameSite=None* inkompatibel sind.

   >[!NOTE]
   >
   >Weitere Informationen finden Sie unter [SameSite=None: Bekannte inkompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients). Verwenden Sie folgenden Regex für den Tizen-Player: `(.*)Tizen(.*)`.

1. Registrieren Sie den Tizen-Player für Ihre Instanz von AEM 6.5.5 und höher. Er sollte sich registrieren und Inhalte normal anzeigen.

## Remote-Bereitstellung des Tizen-Players {#remote-provisioning}

Durch die Remote-Bereitstellung des Tizen-Players können Sie Tausende von Samsung Tizen-Anzeigen ohne großen Aufwand bereitstellen. Dadurch wird der manuelle Aufwand einer Konfiguration jedes Players mit der Server-URL und dem Massenregistrierungs-Code oder anderen Parametern vermieden. Und bei Vorhandensein von AEM Screens as a Cloud Service gilt dies auch für die Konfiguration des Cloud-Modus und Cloud-Tokens.

Mit dieser Funktion können Sie den Tizen-Player aus der Ferne konfigurieren und diese Konfigurationen bei Bedarf auch zentral aktualisieren. Sie benötigen lediglich den `HTTP`-Server, der zum Hosten des Tizen-Programms `(wgt and xml file)` verwendet wird, und einen Texteditor zum Speichern von `config.json` mit den entsprechenden Parametern.

Stellen Sie sicher, dass Sie die URL-Starter-Adresse auf dem Tizen-Gerät konfiguriert haben. Klicken Sie auf die Schaltfläche „Home“ > „URL-Starter-Einstellungen“.
Platzieren Sie auf dem `HTTP`-Server, der die Tizen-Anwendung hostet, die Datei `config.json` am selben Speicherort wie die Datei `wgt`. Der Dateiname muss `config.json` lauten.
Der Tizen-Player wird installiert und beim Start (und bei jedem Neustart) überprüft und wendet die Einstellungen in der Datei `config.json` an.

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
>Die Richtlinienkonfigurationen der Administrator-Benutzeroberfläche des Players werden streng durchgesetzt und können nicht manuell überschrieben werden. Um eine manuelle Player-Konfiguration für eine bestimmte Richtlinie zuzulassen, geben Sie die Richtlinie nicht in der Richtlinienkonfiguration an.
>>Wenn Sie beispielsweise eine manuelle Konfiguration für den Neustart-Zeitplan zulassen möchten, geben Sie den Schlüssel `rebootSchedule` nicht in der Richtlinienkonfiguration an. Richtlinienkonfigurationen werden jedes Mal gelesen, wenn der Player neu geladen wird.

| **Richtlinienname** | **Zweck** |
|---|---|
| Server | Die URL zum Adobe Experience Manager (AEM)-Server. |
| registrationKey | Wird für die Massenregistrierung von Geräten mit vorab freigegebenen Schlüsseln verwendet. |
| resolution | Die Auflösung des Geräts. |
| rebootSchedule | Der Zeitplan zum Neustarten des Players. |
| enableAdminUI | Aktivierung der Administrator-Benutzeroberfläche zum Konfigurieren des Geräts vor Ort. Stellen Sie diesen Wert auf „false“ ein, sobald die Benutzeroberfläche vollständig konfiguriert ist und in der Produktion verwendet wird. |
| enableOSD | Aktivierung der Kanalschalter-Benutzeroberfläche, damit Benutzende zwischen Kanälen auf dem Gerät wechseln können. Erwägen Sie, ihn auf „false“ festzulegen, sobald er vollständig konfiguriert und in der Produktion verfügbar ist. |
| enableActivityUI | Aktivieren Sie diese Option, um den Fortschritt von Aktivitäten wie Herunterladen und Synchronisieren anzuzeigen. Aktivieren Sie den Wert zwecks Fehlerbehebung und deaktivieren Sie ihn, sobald die Benutzeroberfläche vollständig konfiguriert ist und produktiv verwendet wird. |
| cloudMode | Setzen Sie dies auf „true“, wenn Sie möchten, dass der Tizen-Player eine Verbindung zu Screens as a Cloud Service herstellt. Legen Sie den Wert auf „false“ fest, um eine Verbindung zu AMS oder AEM On-Premise herzustellen. |
| cloudToken | Anmelde-Token zur Registrierung bei Screens as a Cloud Service. |


## Registrieren des Tizen-Geräts beim Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Führen Sie die folgenden Schritte aus, um das Tizen-Gerät beim Samsung Remote Management Service (RMS) zu registrieren und den URL-Starter remote zu konfigurieren:

>[!NOTE]
>Überprüfen Sie die Netzwerkeinstellungen und den Monitor.

1. Navigieren Sie zu **Menü** > **Netzwerk** > **Server-Netzwerkeinstellungen** und drücken Sie die **Eingabetaste**.

1. Navigieren Sie zur Server-Adresse, geben Sie den MagicInfo-URL-Zugriff ein und wählen Sie **Fertig**.

1. Richten Sie ggf. TLS ein. Navigieren Sie zum Port, wählen Sie die Port-Nummer vom Server aus und klicken Sie auf **Speichern**.

1. Navigieren Sie zur Registerkarte **Gerät** und suchen Sie nach dem konfigurierten Gerät. Wenn ein Gerät gefunden wird, aktivieren Sie das Kontrollkästchen und klicken Sie dann auf **Genehmigen**.

   >![Bild](/help/user-guide/assets/tizen/rms-3.png)

1. Füllen Sie die erforderlichen Informationen aus und klicken Sie auf eine Gerätegruppe. Klicken Sie auf **OK**.

   >![Bild](/help/user-guide/assets/tizen/rms-7.png)

1. Wenn das Gerät genehmigt wurde, wird es in der Geräteliste angezeigt.  Klicken Sie auf Ihrem Gerät auf *Informationen*, wie in der folgenden Abbildung dargestellt.

   >![Bild](/help/user-guide/assets/tizen/rms-6.png)

1. Das Dialogfeld „Geräteinformationen“ wird angezeigt. Klicken Sie auf die Registerkarte **Geräteinformationen** und dann auf **Bearbeiten**.

   >![Bild](/help/user-guide/assets/tizen/rms-5.png)

1. Bearbeiten Sie die Geräteoptionen und klicken Sie auf die Registerkarte **Einrichtung**. Navigieren Sie zum Abschnitt **URL-Starter** und geben Sie die URL ein, die als WGT-Host dient, und `SSSP config file`, um ein `SSSP`-Programm zu installieren, wie in der folgenden Abbildung dargestellt.

   ![Bild](/help/user-guide/assets/tizen/rms-9.png)

1. Klicken Sie auf **Speichern**.

### Verwenden der Fernbedienungs-Steuerung von Screens {#using-remote-control}

AEM Screens bietet Funktionen für die Steuerung per Fernbedienung. Mehr über diese Funktion erfahren Sie hier: [Fernbedienungs-Steuerung von Screens](implementing-remote-control.md)
