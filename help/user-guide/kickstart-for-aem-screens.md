---
title: Schnellstartanleitung
seo-title: Schnellstartanleitung
description: Befolgen Sie die Anweisungen auf dieser Seite, um ein Demoprojekt für AEM Screens zu erstellen. Ein Demoprojekt unterstützt Sie beim Erstellen eines digitalen Beschilderungserlebnisses – von der Installation und Konfiguration eines neuen Projekts bis hin zum Anzeigen von Inhalten mit dem AEM Screens-Player.
translation-type: tm+mt
source-git-commit: 988872003c1d01c90ccdb38fa77c99019b9a6966
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 64%

---


# Schnellstartanleitung      {#kickstart-guide}

Dieser Abschnitt ist ein Kurzanleitung zu AEM Screens und zeigt, wie ein AEM Screens-Projekt eingerichtet und ausgeführt wird. Es führt Sie durch die Einrichtung einer grundlegenden digitalen Signatur, das Hinzufügen von Inhalten wie Assets und/oder Videos zu jedem Kanal und die weitere Veröffentlichung der Inhalte in einem AEM Screens-Player.

>[!NOTE]
>Bevor Sie mit der Arbeit an den Projektdetails beginnen, stellen Sie sicher, dass Sie das neueste Feature Pack installiert haben. Das neueste Feature Pack für AEM Screens 6.5.5 steht auf dem [Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) zum Download zur Verfügung (Adobe ID erforderlich). 

## Voraussetzungen {#prerequisites}

Gehen Sie wie folgt vor, um ein Beispielprojekt für AEM Screens zu erstellen und Inhalte im Screens Player zu veröffentlichen.

>[!NOTE]
>In der folgenden Übung wird die Wiedergabe des Inhalts Ihres Kanals im Chrome OS-Player gezeigt.

>[!IMPORTANT]
>**OSGi-Konfigurationseinstellungen**
>Sie müssen den leeren Referrer aktivieren, um dem Gerät das Bereitstellen von Daten auf dem Server zu erlauben. Wenn die Eigenschaft für den leeren Referrer deaktiviert ist, kann das Gerät keine Screenshots zurückgeben. Derzeit sind einige dieser Funktionen nur verfügbar, wenn der Apache Sling Werber-Filter Leer zulassen in der OSGi-Konfiguration aktiviert ist. Im Dashboard wird ggf. eine Warnung angezeigt, dass einige dieser Funktionen aufgrund der Sicherheitseinstellungen nicht funktionieren.
>Führen Sie die nachfolgenden Schritte aus, um den ***Apache Sling Referrer-Filter „Allow Empty“*** zu aktivieren:


## Zulassen von leeren Referrer-Anforderungen {#allow-empty-referrer-requests}

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole** über AEM-Instanz > Hammersymbol > **Vorgänge** > **Web-Konsole**.

   ![image](assets/config/empty-ref1.png)

1. Die **Konfiguration der Adobe Experience Manager-Web-Konsole** wird geöffnet. Suchen Sie nach „sling referrer“.

   Um nach der Eigenschaft „sling referrer“ zu suchen, drücken Sie **Befehl+F** für **Mac** und **Strg+F** für **Windows**.

1. Markieren Sie die Option **Leere erlauben**, wie in der folgenden Abbildung dargestellt.

   ![image](assets/config/empty-ref2.png)

1. Klicken Sie auf **Speichern**, um den Apache Sling Referrer-Filter „Leere erlauben“ zu aktivieren.


## Erstellen eines Erlebnisses für digitale Beschilderungen in fünf Minuten {#creating-a-digital-signage-experience-in-minutes}

### Erstellen eines AEM Screens-Projekts {#creating-project}

Der erste Schritt ist die Erstellung eines neuen AEM Screens-Projekts.

1. Navigieren Sie zu Ihrer Adobe Experience Manager-Instanz (AEM) und klicken Sie auf **Bildschirme**. Alternatively, you can navigate directly from `https://localhost:4502/screens.html/content/screens](https://localhost:4502/screens.html/content/screens`.

1. Click **Create Screens Project** to create a new Screens project. Enter the title as **DemoScreens** and click **Save**.

   ![image](assets/kickstart/demo-1.png)

   >[!NOTE]
   >Nachdem Sie das Projekt erstellt haben, gelangen Sie zurück zur Startseite &quot;Bildschirmprojekt&quot;. Sie können Ihr Projekt jetzt auswählen. In einem Projekt gibt es fünf verschiedene Ordner mit dem Titel **Anwendungen**, **Kanal**, **Geräte**, **Speicherorte** und **Zeitpläne**.


### Erstellen eines Kanals {#creating-channel}

Wenn Sie ein Projekt konfiguriert haben, müssen Sie einen neuen Kanal zum Verwalten der Inhalte erstellen.

Gehen Sie wie folgt vor, um einen neuen Kanal für Ihr Projekt zu erstellen:

1. Nachdem Sie ein Projekt erstellt haben, wählen Sie das **DemoScreens** -Projekt aus und wählen Sie den Ordner &quot; **Kanal&quot;**, wie in der folgenden Abbildung dargestellt. Click **+ Create** from the action bar.

   ![image](assets/kickstart/demo-2.png)

1. Choose the **Sequence Channel** from the wizard and click **Next**.
   ![image](assets/kickstart/demo-3.png)

1. Geben Sie **TestChannel** als *Titel* ein und klicken Sie auf **Erstellen**.

   ![image](assets/kickstart/demo-4.png)

Der *TestChannel* wird erstellt und zum Ordner „Kanäle“ hinzugefügt, wie in der nachfolgenden Abbildung gezeigt.

![image](assets/kickstart/demo-5.png)

### Hinzufügen von Inhalten zu Kanälen {#adding-content}

Wenn Sie einen Kanal erstellt haben, müssen Sie diesem Inhalte hinzufügen, die vom Screens-Player angezeigt werden.

Gehen Sie wie folgt vor, um dem Kanal (*TestChannel*) Ihres Projekts Inhalte hinzuzufügen:

1. Navigieren Sie zum erstellten **DemoProject** und wählen Sie den Ordner **Kanal** aus.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten** (siehe Abbildung unten). Der Editor für den **Testkanal** wird geöffnet.

   ![image](assets/kickstart/demo-6.png)

1. Klicken Sie auf der linken Seite der Aktionsleiste auf das Symbol zum Ein-/Ausblenden des seitlichen Bedienfelds, um die Assets und Komponenten zu öffnen.

1. Wählen Sie die Ihrem Kanal hinzuzufügenden Komponenten per Drag-and-Drop aus.

   ![image](assets/kickstart/demo-7.png)

### Erstellen eines Standorts {#creating-location}

Sobald Sie Ihren Kanal eingerichtet haben, müssen Sie einen Speicherort erstellen.

>[!NOTE]
>***Locations*** compartmentalize your various digital signage experiences and contains the configurations of the displays according to where the various screens are.

Gehen Sie wie folgt vor, um einen neuen Standort für Ihr Projekt zu erstellen:

1. Navigate to the **DemoProject** you created and select the **Locations** folder.

1. Click **+ Create** from the action bar.

1. Wählen Sie im Assistenten **Standort** aus und klicken Sie auf **Weiter**.

1. Enter the **Name** for your location (enter the title as *TestLocation*) and click **Create**.

Der Standort **TestLocation** wird erstellt und dem Ordner **Standorte** hinzugefügt.


### Erstellen einer Anzeige für einen Ort {#creating-display}

Nachdem Sie einen Standort konfiguriert haben, müssen Sie eine neue Anzeige für diesen erstellen.

>[!NOTE]
>***Anzeigen*** repräsentieren das digitale Erlebnis, das auf einem oder mehreren Bildschirmen dargestellt wird.

1. Navigate to the **TestLocation** and select it.

1. Klicken Sie in der Aktionsleiste auf **Erstellen**.

   ![image](assets/kickstart/demo-disp1.png)

1. Wählen Sie im Assistenten **Erstellen** die Option **Anzeige** aus und klicken Sie auf **Weiter**.

   ![image](assets/kickstart/demo-disp2.png)

1. Enter the **Title** as **LobbyDisplay** and click **Create**.

   ![image](assets/kickstart/demo-disp3.png)

A new display titled as **TestDisplay** is now added to your location **TestLocation**, as shown in the figure below.

![image](assets/kickstart/demo-disp4.png)

### Zuweisen von Kanälen {#assigning-channel}

Nachdem das Projekt fertig eingerichtet wurde, müssen Sie den Kanal einer Anzeige zuweisen, um den Inhalt anzuzeigen.

1. Navigate to the required display, for example, **DemoScreens** --> **Locations** --> **TestLocation** --> **LobbyDisplay**.

1. Tippen/klicken Sie in der Aktionsleiste auf **Kanal zuweisen**.

   Oder

   Tippen/klicken Sie in der Aktionsleiste auf **Dashboard** und klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **+Kanal zuweisen**.

1. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.

1. Unter **Einstellungen** können Sie den Kanal **nach Pfad** oder **nach Namen** auswählen, die **Kanalrolle**, **Priorität**, die **unterstützten Ereignisse** und die **Unterbrechungsmethoden** eingeben. Darüber hinaus können Sie die Attraktions-QuickInfos in diesem Dialogfeld aktivieren.


   >[!NOTE]
   >Weitere Informationen zu den Kanalzuweisungseigenschaften finden Sie im Abschnitt [Kanaleigenschaften](/help/user-guide/channel-assignment-latest-fp.md#channel-properties).

1. Wählen Sie unter **Zeitplan** die Optionen **Aktivierungsfenster** und **Intervallzeitplan** aus.

1. Klicken Sie auf **Speichern**, nachdem Sie Ihre Voreinstellungen konfiguriert haben.

### Registrieren von Geräten {#registering-device}

Sie müssen Ihr Gerät mithilfe des AEM-Dashboards registrieren.

### Anzeigen von Inhalten im Chrome-Player {#viewing-content-output}

In diesem Beispiel wird die Ausgabe auf einem Chrome-Player beschrieben. Nachdem Sie den Kanal Ihrer Anzeige zugewiesen haben, müssen Sie das Gerät bei einem Player registrieren.



