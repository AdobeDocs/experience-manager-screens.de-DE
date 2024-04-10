---
title: Schnellstartanleitung
description: Erfahren Sie, wie Sie ein AEM Screens-Demoprojekt erstellen. Ein Demoprojekt unterstützt Sie beim Erstellen eines Digital-Signage-Erlebnisses – von der Installation und Konfiguration eines neuen Projekts bis hin zum Anzeigen von Inhalten mit dem AEM Screens-Player.
feature: Overview, Digital Signage
role: User
level: Beginner
exl-id: 9b7c7f50-2846-4727-a0ec-0220b4cd52c4
source-git-commit: 1e8beb9dfaf579250138d4a41eeec88cc81f2d39
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 69%

---

# Schnellstartanleitung {#kickstart-guide}

Die Schnellstartanleitung für AEM Screens zeigt, wie ein AEM Screens-Projekt eingerichtet und ausgeführt wird. Sie führt Sie durch die Einrichtung eines einfachen Digital-Signage-Erlebnisses, das Hinzufügen von Inhalten wie Assets und/oder Videos zu jedem Kanal und die weitere Veröffentlichung der Inhalte in einem AEM Screens-Player.

>[!NOTE]
>Bevor Sie an den Projektdetails arbeiten, stellen Sie sicher, dass Sie das neueste Feature Pack für AEM Screens installiert haben. Das neueste Feature Pack steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich).

## Voraussetzungen {#prerequisites}

Gehen Sie wie folgt vor, um ein Beispielprojekt für AEM Screens zu erstellen und Inhalte im Screens-Player zu veröffentlichen.

>[!NOTE]
>Im folgenden Tutorial wird die Wiedergabe des Inhalts Ihres Kanals im Chrome OS-Player gezeigt.

>[!IMPORTANT]
>**OSGi-Konfigurationseinstellungen**
>Sie müssen den leeren Referrer aktivieren, um dem Gerät das Bereitstellen von Daten auf dem Server zu erlauben. Wenn die Eigenschaft für den leeren Referrer deaktiviert ist, kann das Gerät keine Screenshots zurückgeben. Derzeit sind einige dieser Funktionen nur verfügbar, wenn der Apache Sling Referrer-Filter „Allow Empty“ in der OSGi-Konfiguration aktiviert ist. Im Dashboard wird ggf. eine Warnung angezeigt, dass einige dieser Funktionen aufgrund der Sicherheitseinstellungen nicht funktionieren.
>Führen Sie die nachfolgenden Schritte aus, um den ***Apache Sling Referrer-Filter „Allow Empty“*** zu aktivieren:


## Zulassen von leeren Referrer-Anforderungen {#allow-empty-referrer-requests}

1. Navigieren Sie zu **Konfiguration der Adobe Experience Manager-Web-Konsole** über AEM-Instanz > Hammersymbol > **Aktivitäten** > **Web-Konsole**.

   ![image](assets/config/empty-ref1.png)

1. Die **Konfiguration der Adobe Experience Manager-Web-Konsole** wird geöffnet. Suchen Sie nach „sling referrer“.

   Um nach der Eigenschaft „sling referrer“ zu suchen, drücken Sie **Befehl+F** für **Mac** und **Strg+F** für **Windows**.

1. Markieren Sie die Option **Leere erlauben**, wie in der folgenden Abbildung dargestellt.

   ![image](assets/config/empty-ref2.png)

1. Klicken Sie auf **Speichern**, um den Apache Sling Referrer-Filter „Leere erlauben“ zu aktivieren.

## Erstellen eines Digital-Signage-Erlebnisses in fünf Minuten {#creating-a-digital-signage-experience-in-minutes}

### Erstellen eines AEM Screens-Projekts {#creating-project}

Erstellen Sie zuerst ein AEM Screens-Projekt.

1. Navigieren Sie zu Ihrer Adobe Experience Manager-Instanz und klicken Sie auf **Screens**. Sie haben auch die Möglichkeit, direkt zur folgenden URL zu wechseln: `https://localhost:4502/screens.html/content/screens](https://localhost:4502/screens.html/content/screens`.

1. Klicks **Screens-Projekt erstellen** , damit Sie ein Screens-Projekt erstellen können.
1. Geben Sie den Titel als **DemoScreens** Klicken Sie auf **Speichern**.

   ![image](assets/kickstart/demo-1.png)

   >[!NOTE]
   >Nachdem Sie das Projekt erstellt haben, gelangen Sie zurück zur Screens-Projekt-Startseite. Sie können Ihr Projekt jetzt auswählen. In einem Projekt gibt es fünf verschiedene Ordner mit dem Titel **Anwendungen**, **Kanäle**, **Geräte**, **Standorte** und **Zeitpläne**.

### Erstellen eines Kanals {#creating-channel}

Nachdem Sie Ihr AEM Screens-Projekt erstellt haben, müssen Sie einen Kanal erstellen, in dem Sie den Inhalt verwalten.

Gehen Sie wie folgt vor, um einen Kanal für Ihr Projekt zu erstellen:

1. Nachdem Sie ein Projekt erstellt haben, wählen Sie das Projekt **DemoScreens** aus und wählen Sie den Ordner **Kanäle** aus, wie in der folgenden Abbildung dargestellt. Klicken Sie in der Aktionsleiste auf **+ Erstellen**.

   ![image](assets/kickstart/demo-2.png)

1. Wählen Sie im Assistenten die Vorlage **Sequenz-Kanal** aus und klicken Sie auf **Weiter**.
   ![image](assets/kickstart/demo-3.png)

1. Geben Sie **TestChannel** als **Titel** ein und klicken Sie auf **Erstellen**.

   ![image](assets/kickstart/demo-4.png)

   Der **TestChannel** wird nun dem Ordner „Kanäle“ hinzugefügt, wie in der nachfolgenden Abbildung gezeigt.

   ![image](assets/kickstart/demo-5.png)

### Hinzufügen von Inhalten zu Kanälen {#adding-content}

Wenn Sie Ihren Kanal eingerichtet haben, fügen Sie Inhalte zu Ihrem Kanal hinzu, die vom AEM Screens-Player angezeigt werden können.

Gehen Sie wie folgt vor, um dem Kanal (**TestChannel**) Ihres Projekts Inhalte hinzuzufügen:

1. Navigieren Sie zum erstellten **DemoProject** und wählen Sie **TestChannel** aus dem Ordner **Kanäle** aus.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten** (siehe Abbildung unten). Der Editor für den **Testkanal** wird geöffnet.

   ![image](assets/kickstart/demo-6.png)

1. Klicken Sie auf das Symbol, das das seitliche Bedienfeld auf der linken Seite der Aktionsleiste umschaltet, um die Assets und Komponenten zu öffnen.

1. Ziehen Sie die Komponenten, die Sie hinzufügen möchten, in den Kanal.

   ![image](assets/kickstart/demo-7.png)

### Erstellen eines Standorts {#creating-location}

Wenn Sie Ihren Kanal eingerichtet haben, erstellen Sie einen Ort.

>[!NOTE]
>***Standorte*** gliedern Sie die verschiedenen Erlebnisse für digitale Beschilderung und enthalten die Konfigurationen der einzelnen Anzeigen, abhängig vom jeweiligen Standort.

Gehen Sie wie folgt vor, um einen Standort für Ihr Projekt zu erstellen:

1. Navigieren Sie zum erstellten **DemoProject** und wählen Sie den Ordner **Standorte** aus.
1. Klicken Sie in der Aktionsleiste auf **+ Erstellen**.
1. Wählen Sie im Assistenten **Standort** aus und klicken Sie auf **Weiter**.
1. Geben Sie den **Namen** und Titel für Ihren Standort ein (geben Sie als Titel **TestLocation** ein) und klicken Sie auf **Erstellen**.

Der Standort **TestLocation** wird erstellt und dem Ordner **Standorte** hinzugefügt.


### Erstellen einer Anzeige für einen Standort {#creating-display}

Wenn Sie einen Standort erstellt haben, erstellen Sie eine Anzeige für Ihren Standort.

>[!NOTE]
>***Anzeige*** stellt das digitale Erlebnis dar, das auf einem oder mehreren Bildschirmen dargestellt wird.

1. Navigieren Sie zur **TestLocation** und wählen Sie sie aus.
1. Klicken Sie in der Aktionsleiste auf **Erstellen**.

   ![image](assets/kickstart/demo-disp1.png)

1. Wählen Sie im Assistenten **Erstellen** die Option **Anzeige** aus und klicken Sie auf **Weiter**.

   ![image](assets/kickstart/demo-disp2.png)

1. Geben Sie unter **Titel** den Wert **LobbyDisplay** ein und klicken Sie auf **Erstellen**.

   ![image](assets/kickstart/demo-disp3.png)

   Eine neue Anzeige (**TestDisplay**) wird Ihrem Standort (**TestLocation**) hinzugefügt, wie in der nachfolgenden Abbildung gezeigt.

   ![image](assets/kickstart/demo-disp4.png)

### Zuweisen von Kanälen {#assigning-channel}

Nach Abschluss der Projekteinrichtung müssen Sie den Kanal einer Anzeige zuweisen, um den Inhalt anzuzeigen.

1. Navigieren Sie von zur gewünschten Anzeige **DemoScreens** > **Standorte** > **TestLocation** > **LobbyDisplay**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   ![image](assets/kickstart/demo-assign1.png)

   Oder

   Tippen/klicken Sie in der Aktionsleiste auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+ Kanal zuweisen**.

   ![image](assets/kickstart/demo-assign2.png)

1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.

1. Wählen Sie unter **Einstellungen** den Kanal **nach Pfad** und bei **unterstützte Ereignisse** die Optionen **erstes Laden** und **inaktiver Bildschirm** aus.

   >[!NOTE]
   >
   >Die Felder **Kanal-Rolle**, **Priorität** und **Unterbrechungsmethoden** werden standardmäßig ausgefüllt. Siehe [Kanaleigenschaften](/help/user-guide/channel-assignment-latest-fp.md#channel-properties) für weitere Informationen zu den Kanalzuweisungseigenschaften.

   ![Bild](assets/kickstart/demo-assign3.png)

   Außerdem können Sie die **Aktivierungsfenster** und **Wiederholungsplan**.

   >[!NOTE]
   >Die *Wiederholungsplan* ermöglicht Ihnen, einen Zeitplan für Ihren Kanal festzulegen. Sie richten mehrere Intervallzeitpläne für einen Kanal ein.
   >Weitere Informationen finden Sie unter [Intervallzeitplan](/help/user-guide/channel-assignment-latest-fp.md#recurrence-schedule).

1. Klicken Sie auf **Speichern**, nachdem Sie Ihre Voreinstellungen konfiguriert haben.

### Registrieren eines Geräts und Zuweisen eines Geräts zu einer Anzeige {#registering-device}

Registrieren Sie Ihr Gerät über das AEM Dashboard.

>[!IMPORTANT]
>Im Entwicklermodus kann der Chrome OS-Player als Chrome-Browser-Plug-in installiert werden, ohne dass ein echtes Chrome-Player-Gerät erforderlich ist. Gehen Sie zur Installation wie folgt vor:
>
>1. Klicken Sie [hier](https://download.macromedia.com/screens/), um den neuesten Chrome-Player herunterzuladen.
>1. Entpacken Sie die Datei und speichern Sie sie auf der Festplatte.
>1. Öffnen Sie den Chrome-Browser und wählen Sie im Menü die Option **Erweiterungen** oder navigieren Sie direkt zu ***chrome://extensions***.
>1. Schalten Sie die **Entwicklermodus** oben rechts.
>1. Klicks **Entpacktes Laden** oben links und laden Sie den entpackten Chrome-Player.
>1. Überprüfen **AEM Screens Chrome-Player** -Plug-in, wenn es in der Liste der Erweiterungen verfügbar ist.
>1. Öffnen Sie eine neue Registerkarte und klicken Sie auf **Apps** Symbol oben links oder navigieren Sie direkt zu ***chrome://apps***.
>1. Klicks **AEM Screens** Plug-in, damit Sie den Chrome-Player starten können. Standardmäßig wird der Player im Vollbildmodus gestartet. Presse **Esc** , um den Vollbildmodus zu beenden.

Sobald Ihr Chrome OS-Player eingerichtet ist, führen Sie die folgenden Schritte aus, um ein Chrome-Gerät zu registrieren.

1. Navigieren Sie von Ihrer AEM-Instanz zum Ordner **Geräte** Ihres Projekts.

1. Tippen/klicken Sie in der Aktionsleiste auf die Option **Geräte-Manager**.

   ![image](assets/kickstart/demo-register1.png)

1. Tippen/klicken Sie oben rechts auf die Option **Geräteregistrierung**.

1. Wählen Sie das erforderliche Gerät aus und tippen/klicken Sie auf **Gerät registrieren**.

   ![image](assets/kickstart/demo-register2.png)

1. Warten Sie, bis das Gerät seinen Registrierungs-Code sendet, und überprüfen Sie gleichzeitig von Ihrem Chrome-Gerät aus den **Registrierungs-Code**.
   ![image](assets/kickstart/demo-register3.png)

1. Wenn der **Registrierungs-Code** auf beiden Geräten identisch ist, tippen/klicken Sie in AEM auf die Option **Bestätigen**.

1. Legen Sie den gewünschten Namen für das Gerät als **ChromeDeviceforDemo** fest und klicken Sie auf **Registrieren**.

   ![image](assets/kickstart/demo-register4.png)

1. Klicken Sie im Dialogfeld **Geräteregistrierung erfolgreich** auf **Anzeige zuweisen**.

   ![image](assets/kickstart/demo-register5.png)

1. Wählen Sie den Pfad zu Ihrer Anzeige als **DemoScreens** > **Standorte** > **TestLocation** > **LobbyDisplay** und klicken **Zuweisen**.

   ![Bild](assets/kickstart/demo-device6.png)

1. Wenn das Gerät erfolgreich zugewiesen wurde, sehen Sie die folgende Bestätigung.

   ![Bild](assets/kickstart/demo-register8.png)

1. Auswählen **Beenden** , um den Registrierungsprozess abzuschließen. Sie können Ihr registriertes Gerät jetzt über das Anzeigen-Dashboard anzeigen.

   ![Bild](assets/kickstart/demo-register9.png)

### Anzeigen von Inhalten im Chrome-Player {#viewing-content-output}

Alle Assets in Ihrem Kanal werden jetzt auf Ihrem Chrome OS-Player wiedergegeben.

Herzlichen Glückwunsch! Jetzt spielen Sie Inhalte in einem AEM Screens-Kanal ab!

![image](assets/kickstart/demo-video-screens.gif)
