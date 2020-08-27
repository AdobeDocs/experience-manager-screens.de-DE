---
title: Schnellstartanleitung
seo-title: Schnellstartanleitung
description: Befolgen Sie die Anweisungen auf dieser Seite, um ein Demoprojekt für AEM Screens zu erstellen. Ein Demoprojekt unterstützt Sie beim Erstellen eines digitalen Beschilderungserlebnisses – von der Installation und Konfiguration eines neuen Projekts bis hin zum Anzeigen von Inhalten mit dem AEM Screens-Player.
translation-type: tm+mt
source-git-commit: 8ffa53c6ffb24ff80adfdce33a69a9d80e03bb75
workflow-type: tm+mt
source-wordcount: '1630'
ht-degree: 98%

---


# Schnellstartanleitung     {#kickstart-guide}

Dieser Abschnitt ist eine Schnellstartanleitung für AEM Screens, in dem eine Reihe grundlegender Aktionen vorgestellt werden. Er erläutert, wie Sie ein einfaches Erlebnis für digitale Beschilderung mit Inhalten/Assets erstellen und in einem Screens-Player veröffentlichen.

## Erstellen eines Erlebnisses für digitale Beschilderungen in fünf Minuten {#creating-a-digital-signage-experience-in-minutes}

Mit den nachfolgenden Schritten können Sie ein Beispielprojekt für Screens erstellen und Inhalte im Screens-Player veröffentlichen.

Um einen **AEM Screens-Player** herunterzuladen, klicken Sie [hier](https://download.macromedia.com/screens/).


Informationen zur Implementierung des Players für Chrome OS finden Sie unter [Chrome Management Console](implementing-chrome-os-player.md).

Weitere Informationen zum Installieren und Konfigurieren der Bildschirmplayer auf Ihren Geräten finden Sie unter Bildschirme [installieren und konfigurieren](configuring-screens-introduction.md) .

>[!NOTE]
>**OSGi-Einstellungen**
>Sie müssen den leeren Referrer aktivieren, um dem Gerät das Bereitstellen von Daten auf dem Server zu erlauben. Wenn die Eigenschaft für den leeren Referrer deaktiviert ist, kann das Gerät keine Screenshots zurückgeben. Derzeit sind einige dieser Funktionen nur verfügbar, wenn der Apache Sling Referrer-Filter „Allow Empty“ in der OSGi-Konfiguration aktiviert ist. Im Dashboard wird ggf. eine Warnung angezeigt, dass einige dieser Funktionen aufgrund der Sicherheitseinstellungen nicht funktionieren.
>
>
>Führen Sie die nachfolgenden Schritte aus, um den ***Apache Sling Referrer-Filter „Allow Empty“*** zu aktivieren:


## Zulassen von leeren Referrer-Anforderungen {#allow-empty-referrer-requests}

1. Navigieren Sie zur **Konfiguration der Adobe Experience Manager-Web-Konsole** über AEM-Instanz > Hammersymbol > **Vorgänge** > **Web-Konsole**.

   ![image](assets/config/empty-ref1.png)

1. Die **Konfiguration der Adobe Experience Manager-Web-Konsole** wird geöffnet. Suchen Sie nach „sling referrer“.

   Um nach der Eigenschaft „sling referrer“ zu suchen, drücken Sie **Befehl+F** für **Mac** und **Strg+F** für **Windows**.

1. Markieren Sie die Option **Leere erlauben**, wie in der folgenden Abbildung dargestellt.

   ![image](assets/config/empty-ref2.png)

1. Klicken Sie auf **Speichern**, um den Apache Sling Referrer-Filter „Leere erlauben“ zu aktivieren.


## Tutorial {#tutorial}

1. **Erstellen eines neuen Projekts**

   1. Wählen Sie den Adobe Experience Manager-Link (oben links) und dann **Screens** aus. Sie haben auch die Möglichkeit, direkt zur folgenden URL zu wechseln: `https://localhost:4502/screens.html/content/screens](https://localhost:4502/screens.html/content/screens`.

   1. Klicken Sie auf **Erstellen**, um ein neues Screens-Projekt zu erstellen (siehe Abbildung unten).
   1. Wählen Sie im Assistenten **Screens-Projekt erstellen** die Option **Screens** aus und klicken Sie auf **Weiter**.

   1. Geben Sie als Titel *Test_Project* ein und klicken Sie auf **Erstellen**.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Wenn das Projekt erstellt wurde, kehren Sie zur Screens-Projektkonsole zurück. Sie können Ihr Projekt jetzt auswählen. Ein Projekt umfasst fünf Ordnertypen: **Anwendungen**, **Kanäle**, **Geräte**, **Standorte** und **Zeitpläne**, wie in der nachfolgenden Abbildung gezeigt.

   >[!NOTE]
   >
   >Zeitpläne sind nur verfügbar, wenn Sie das Feature Pack 1 für AEM 6.3 Sites installiert haben. Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   Weitere Informationen finden Sie unter [Erstellen und Verwalten von Screens-Projekten](creating-a-screens-project.md).

1. **Erstellen von neuen Kanälen**

   Wenn Sie ein Projekt konfiguriert haben, müssen Sie einen neuen Kanal zum Verwalten der Inhalte erstellen.

   Gehen Sie wie folgt vor, um einen neuen Kanal für Ihr Projekt zu erstellen:

   1. Navigieren Sie zum erstellten *Test_Project* und wählen Sie den Ordner **Kanäle** aus.

   1. Klicken Sie in der Aktionsleiste auf **Erstellen** (siehe Abbildung unten). Ein Assistent wird geöffnet.
   1. Wählen Sie den **Sequenzkanal** aus und klicken Sie auf **Weiter**.

   1. Geben Sie als **Name** und **Titel** *TestChannel* ein und klicken Sie auf **Erstellen**.

   ![chlimage_1-6](assets/chlimage_1-6.png)

   Der *TestChannel* wird erstellt und zum Ordner „Kanäle“ hinzugefügt, wie in der nachfolgenden Abbildung gezeigt.

   ![chlimage_1-7](assets/chlimage_1-7.png)

   Weitere Einzelheiten zum Erstellen und Verwalten von Kanälen finden Sie unter [Kanalverwaltung](managing-channels.md).

1. **Hinzufügen von Inhalten zu Kanälen**

   Wenn Sie einen Kanal erstellt haben, müssen Sie diesem Inhalte hinzufügen, die vom Screens-Player angezeigt werden.

   Gehen Sie wie folgt vor, um dem Kanal (*TestChannel*) Ihres Projekts Inhalte hinzuzufügen:

   1. Navigieren Sie zum erstellten *Test_Project* und wählen Sie den Ordner **Kanäle** aus.

   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten** (siehe Abbildung unten). Der Editor für den *Testkanal* wird geöffnet.

   1. Klicken Sie auf der linken Seite der Aktionsleiste auf das Symbol zum Ein-/Ausblenden des seitlichen Bedienfelds, um die Assets und Komponenten zu öffnen.
   1. Wählen Sie die Ihrem Kanal hinzuzufügenden Komponenten per Drag-and-Drop aus.

   ![chlimage_1-8](assets/chlimage_1-8.png)

   In diesem Beispiel zeigt der Editor ein Bild, das dem Kanal hinzugefügt wurde.

   ![chlimage_1-9](assets/chlimage_1-9.png)

1. **Erstellen eines neuen Standorts**

   Wenn der Kanal konfiguriert wurde, müssen Sie den Standort erstellen.

   ***Standorte*** gliedern die verschiedenen Digital Signage-Erlebnisse und enthalten die Konfigurationen der einzelnen Anzeigen, abhängig vom jeweiligen Standort.

   Gehen Sie wie folgt vor, um einen neuen Standort für Ihr Projekt zu erstellen:

   1. Navigieren Sie zum erstellten *Test_Project* und wählen Sie den Ordner **Standorte** aus.

   1. Klicken Sie neben dem Plussymbol in der Aktionsleiste auf **Erstellen** (siehe Abbildung unten). Ein Assistent wird geöffnet.
   1. Wählen Sie im Assistenten **Standort** aus und klicken Sie auf **Weiter**.

   1. Geben Sie den **Namen** und **Titel** für Ihren Standort ein (geben Sie als Titel *TestLocation* ein) und klicken Sie auf **Erstellen**.

   ![chlimage_1-10](assets/chlimage_1-10.png)

   Der Standort *TestLocation* wird erstellt und dem Ordner **Standorte** hinzugefügt.

   ![chlimage_1-11](assets/chlimage_1-11.png)

1. **Erstellen einer neuen Anzeige für *TestLocation***

   Nachdem Sie einen Standort konfiguriert haben, müssen Sie eine neue Anzeige für diesen erstellen.

   ***Anzeigen*** repräsentieren das digitale Erlebnis, das auf einem oder mehreren Bildschirmen dargestellt wird.

   1. Navigieren Sie zum Standort, an dem Ihre Anzeige erstellt werden soll (*Test_Project* > **Standorte** > *TestLocation)*, wie in der Abbildung oben gezeigt, und wählen Sie *TestLocation* aus.

   1. Klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Wählen Sie im Assistenten **Erstellen** die Option **Anzeige** aus und klicken Sie auf **Weiter**.

   1. Geben Sie einen **Namen** und **Titel** für den Standort der Anzeige ein (geben Sie als Titel *TestDisplay* ein).

   1. Wählen Sie auf der Registerkarte **Anzeige** die Details für das Layout aus.

      1. Wählen Sie unter **Auflösung** die Option **Full HD** aus.

      1. Wählen Sie für **Anzahl der Geräte horizontal** die Option „1“ aus.
      1. Wählen Sie für **Anzahl der Geräte vertikal** die Option „1“ aus.
   1. Klicken Sie auf **Erstellen**.

   Eine neue Anzeige (*TestDisplay*) wird Ihrem Standort (*TestLocation*) hinzugefügt, wie in der nachfolgenden Abbildung gezeigt.

   ![chlimage_1-12](assets/chlimage_1-12.png)

1. **Hinzufügen von Zeitplänen**

   Mit der Funktion *Zeitpläne* in AEM Screens können Sie Kanäle zu wiederverwendbaren Gruppen zusammenfassen, sodass Sie nicht für jede einzelne Anzeige, in der Sie einen bestimmten Inhalt zeigen möchten, eine neue Zuweisung vornehmen müssen.

   >[!NOTE]
   >
   >Diese Screens-Funktion ist nur verfügbar, wenn Sie das Feature Pack 1 für AEM 6.3 Sites installiert haben. Wenden Sie sich an den Adobe-Support, um Zugriff auf dieses Feature Pack zu erhalten. Wenn Sie die entsprechenden Berechtigungen erhalten haben, können Sie es von Package Share herunterladen.

   1. Navigieren Sie über „Test_Project“ > **Zeitpläne** zum Ordner **Zeitpläne**.

   1. Klicken Sie in der Aktionsleiste auf **Erstellen**. Ein Assistent wird geöffnet.
   1. Wählen Sie auf der Seite des Assistenten **Erstellen** die Option **Zeitplan** aus.

   1. Geben Sie auf der Eigenschaftenseite *ZeitplanVormittag* als **Name** und **Titel** ein.

   1. Wenn Sie auf **Erstellen** klicken, wird der Zeitplan zum Ordner **Zeitpläne** hinzugefügt, wie in der nachfolgend Abbildung gezeigt.

   ![chlimage_1-13](assets/chlimage_1-13.png)

   Wählen Sie darüber hinaus den Zeitplan (*ZeitplanVormittag*) aus und klicken Sie in der Aktionsleiste auf **Dashboard**, um das Dashboard für Zeitpläne anzuzeigen. Mit dem Dashboard können Sie die Eigenschaften des Zeitplans anzeigen/ändern, Kanäle zuweisen und zugewiesene Anzeigen anzeigen.

   ![chlimage_1-14](assets/chlimage_1-14.png)

   Unter [Erstellen und Verwalten von Zeitplänen](managing-schedules.md) finden Sie detaillierte Informationen zu Zeitplänen.

1. **Zuweisen von Kanälen**

   1. Navigieren Sie über *Test_Project* > **Standorte** > *TestLocation* > *TestDisplay* zur Anzeige.

   1. Wählen Sie *TestDisplay* aus und tippen/klicken Sie in der Aktionsleiste auf „Kanal zuweisen“.**

   1. Alternativ dazu können Sie auf **Dashboard** klicken und oben rechts im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** die Option **+Kanal zuweisen** auswählen, wie in der nachfolgenden Abbildung gezeigt. Daraufhin wird das Dialogfeld **Kanalzuweisung** geöffnet.

   1. Wählen Sie als Vorgehensweise für **Kanal referenzieren** die Option **Pfad** aus

   1. Geben Sie als **Kanalrolle** den Wert *LiveStream* ein.

   1. Wählen Sie den **Kanalpfad** (*Test_Project* > *Kanäle* > *TestChannel*) unter **Kanal** aus.

   1. Wählen Sie als **Priorität** für den Kanal *1* aus.

   1. Wählen Sie unter **Unterstützte Ereignisse** die Optionen **Erster Ladevorgang** und **Bildschirm bei Untätigkeit** aus.

   1. Geben Sie den **Zeitplan** ein und wählen Sie unter **aktiv ab** und **aktiv bis** jeweils ein Datum aus.

   1. Klicken Sie auf **Speichern**.

   Der Kanal wird erstellt und dem Bedienfeld hinzugefügt.

   ![chlimage_1-15](assets/chlimage_1-15.png)

   Weitere Informationen zum Dialogfeld **Kanalzuweisung** und den damit verbundenen Eigenschaften finden Sie unter [Kanäle zuweisen](channel-assignment.md).

1. **Hinzufügen von Zeitplänen zu Kanälen**

   1. Navigieren Sie über *Test_Project* > **Standorte** > *TestLocation* > *TestDisplay* zur Anzeige.

   1. Klicken Sie auf **Dashboard** und wählen Sie oben rechts im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** die Option **+Zeitplan zuweisen** aus, wie in der obigen Abbildung gezeigt. Das Dialogfeld **Zeitplanzuweisung** wird geöffnet.

   1. Wählen Sie den Pfad aus, unter dem Sie den Zeitplan erstellt haben (hier *Test_Project* > **Zeitpläne** > *ZeitplanVormittag*).

   1. Klicken Sie auf **Speichern**, um den Zeitplan Ihrem Kanal hinzuzufügen.

   ![chlimage_1-16](assets/chlimage_1-16.png)

1. **Registrieren von Geräten**

   Sie müssen Ihr Gerät mithilfe des AEM-Dashboards registrieren.

   >[!NOTE]
   >
   >Sie können den Screens-Player über die heruntergeladene AEM Screens-App oder mithilfe des Webbrowsers öffnen.

   Anzeigen von ausstehenden Geräten:

   1. Öffnen Sie ein separates Browser-Fenster.
   1. Wechseln Sie mithilfe des *Webbrowsers* zum Screens-Player `https://localhost:4502/content/mobileapps/cq-screens-player/firmware.html` oder starten Sie die AEM Screens-App. Wenn Sie das Gerät öffnen, können Sie sehen, dass das Gerät nicht registriert ist.
   1. Navigieren Sie im AEM-Dashboard zu *Test_Project* > **Geräte**

   1. Klicken Sie in der Aktionsleiste auf **Geräte-Manager**.
   1. Klicken Sie auf **Geräteregistrierung**. Daraufhin werden die ausstehenden Geräte angezeigt, wie in der nachfolgenden Abbildung dargestellt.

   ![chlimage_1-17](assets/chlimage_1-17.png)

   Wählen Sie das zu registrierende Gerät aus und klicken Sie auf **Gerät registrieren**.

   ![chlimage_1-18](assets/chlimage_1-18.png)

   Sie müssen den Code validieren, indem Sie ihn über den Webbrowser oder den AEM Screens-Player überprüfen.

   Klicken Sie auf **Validieren**, um zum Bildschirm **Geräteregistrierung** zu wechseln.

   ![chlimage_1-19](assets/chlimage_1-19.png)

   Geben Sie den **Titel** ein und klicken Sie auf **Registrieren**. Daraufhin wird das Gerät registriert.

   Klicken Sie auf **Beenden**, um die Geräteregistrierung abzuschließen.

   ![chlimage_1-20](assets/chlimage_1-20.png)

   Durch Klicken auf **Beenden** kehren Sie zur Geräteseite zurück, auf der die zugewiesenen und nicht zugewiesenen Geräte angezeigt werden.

   ![chlimage_1-21](assets/chlimage_1-21.png)

   >[!NOTE]
   >
   >Das hinzugefügte Gerät wird unter **Zugeordnet** mit dem Status **Nicht zugewiesen** angezeigt.

1. **Zuweisen von Geräten zu Anzeigen**

   Wenn Sie das Gerät registriert haben, müssen Sie es einer Anzeige zuweisen.

   Gehen Sie wie folgt vor, um ein Gerät zuzuweisen:

   1. Wählen Sie das zuzuweisende Gerät aus.
   1. Klicken Sie in der Aktionsleiste auf **Gerät zuweisen**.
   1. Wählen als Anzeigepfad für Ihren Kanal `/content/screens/Test_Project/***Locations***/TestLocation/TestDisplay.`

   1. Klicken Sie auf **Zuweisen**.
   1. Klicken Sie auf **Beenden**, um den Vorgang abzuschließen. Das Gerät ist jetzt zugewiesen.

   ![chlimage_1-22](assets/chlimage_1-22.png)

   Das Dashboard der Anzeige wird geöffnet und zeigt alle Informationen zu den zugewiesenen Kanälen und Zeitplänen sowie die Details der Gerätekonfiguration an.

   ![screen_shot_2017-12-18at122041pm](assets/screen_shot_2017-12-18at122041pm.png)

### Anzeigen von Inhalten im Screens-Player {#viewing-the-content-in-screens-player}

Wenn die obigen Konfigurationen hinzugefügt wurden, sollte der Player automatisch den Standardkanal für die Anzeige auf Ihrem Gerät zeigen, z. B. ein Bild (in diesem Szenario sind ein Sequenzkanal und dessen Inhalt im Screens-Player für den Webbrowser dargestellt).

![chlimage_1-23](assets/chlimage_1-23.png)

Weitere Informationen zum AEM Screens-Player finden Sie unter [AEM Screens-Player](working-with-screens-player.md).
