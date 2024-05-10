---
title: Konfigurieren von Autoren- und Veröffentlichungsinstanzen in AEM Screens
description: Erfahren Sie, wie Sie eine Autoreninstanz und eine Veröffentlichungsinstanz für AEM Screens konfigurieren.
exl-id: 5aef5f35-d946-4bf8-a2a8-c3ed532b7eef
source-git-commit: 6b4fc934c31640168528fa3e72cf634773f4f8e6
workflow-type: tm+mt
source-wordcount: '1940'
ht-degree: 33%

---


# Konfigurieren von Autoren- und Veröffentlichungsinstanzen in AEM Screens {#configuring-author-and-publish-in-aem-screens}

Auf dieser Seite werden folgende Themen vorgestellt:

* **Konfigurieren von Autoren- und Veröffentlichungsinstanzen**
* **Einrichten der Veröffentlichungstopologie**
* **Verwalten von Veröffentlichungen: Bereitstellen von Inhaltsaktualisierungen vom Autor zur Veröffentlichung auf dem Gerät**

## Voraussetzungen {#prerequisites}

Bevor Sie mit Autoren- und Veröffentlichungsservern beginnen, sollten Sie über Folgendes verfügen:

* **AEM-Topologie**
* **Erstellen und Verwalten von AEM Screens-Projekten**
* **Verfahren zur Geräteregistrierung**

>[!NOTE]
>
>Diese AEM Screens-Funktion ist nur verfügbar, wenn Sie AEM 6.4 Screens Feature Pack 2 installiert haben. Um Zugriff auf dieses Feature Pack zu erhalten, wenden Sie sich an den Adobe-Support und fordern Sie Zugriff an. Nachdem Sie die Berechtigung erhalten haben, können Sie sie von Package Share herunterladen.

>[!IMPORTANT]
>
>Wenn Sie mehr als eine Veröffentlichungsinstanz mit dem Dispatcher verwenden möchten, aktualisieren Sie den Dispatcher. Siehe [Aktivieren von fixierbaren Sitzungen](dispatcher-configurations-aem-screens.md#enable-sticky-session).

## Konfigurieren von Autoren- und Veröffentlichungsinstanz {#configuring-author-and-publish-instances}

>[!NOTE]
>
>Weitere Informationen zur Architektur der Autoren- und Veröffentlichungsinstanz und dazu, wie der Inhalt in einer AEM-Autoreninstanz erstellt und dann in mehrere Veröffentlichungsinstanzen vorwärts repliziert wird, finden Sie unter [Architektonischer Überblick zur Autoren- und Veröffentlichungsinstanz](author-publish-architecture-overview.md).

Im folgenden Abschnitt wird beschrieben, wie Sie Replikationsagenten in der Autoren- und Veröffentlichungstopologie einrichten.

Sie können ein einfaches Beispiel einrichten, in dem Sie eine Autoren- und zwei Veröffentlichungsinstanzen hosten:

* Autor > localhost:4502
* Veröffentlichung 1 (pub1) > localhost:4503
* Veröffentlichung 2 (pub2) > localhost:4504

## Einrichten von Replikationsagenten in der Autoreninstanz {#setting-replication-agents}

Um Replikationsagenten zu erstellen, erfahren Sie, wie Sie einen standardmäßigen Replikationsagenten erstellen.

Für Screens sind drei Replikationsagenten erforderlich:

1. **Standardmäßiger Replikationsagent ***(angegeben als*** Standard Replication Agent**)
1. **Screens-Replikationsagent**
1. **Agent für Rückwärtsreplikation**

### Schritt 1: Erstellen eines standardmäßigen Replikationsagenten {#step-creating-a-default-replication-agent}

Gehen Sie wie folgt vor, um einen standardmäßigen Replikationsagenten einzurichten:

1. Navigieren Sie zu Ihrer AEM-Instanz > Hammersymbol > **Aktivitäten** > **Konfiguration**.

   ![screen_shot_2019-02-25at24621pm](assets/screen_shot_2019-02-25at24621pm.png)

1. Klicken Sie auf **Replikation** aus der linken Navigationsstruktur.

   ![screen_shot_2019-02-25at24715pm](assets/screen_shot_2019-02-25at24715pm.png)

1. Klicken Sie auf **Agenten für Autor** aus dem **Replikation** Ordner und klicken Sie auf **Neu** , um einen neuen standardmäßigen Replikationsagenten zu erstellen.

   ![screen_shot_2019-02-25at25400pm](assets/screen_shot_2019-02-25at25400pm.png)

1. Geben Sie die **Titel** und **Name** , damit Sie den Replikationsagenten erstellen können, klicken Sie auf **Erstellen**.

   ![screen_shot_2019-02-25at25737pm](assets/screen_shot_2019-02-25at25737pm.png)

1. Klicken Sie mit der rechten Maustaste auf den Replikationsagenten und klicken Sie auf **Öffnen** um die Einstellungen zu bearbeiten.

   ![screen_shot_2019-02-25at30018pm](assets/screen_shot_2019-02-25at30018pm.png)

1. Klicken Sie auf **Bearbeiten**.

1. Im **Agenteneinstellungen** Geben Sie die Details ein.

   >[!NOTE]
   >
   >Der Benutzer muss **Aktiviert** , um den Replikationsagenten zu aktivieren. Aktivieren Sie diese Option bei den Replikationsagenten &quot;Standard&quot;, &quot;Screens&quot;und &quot;Rückwärtsreplikation&quot;.

   ![screen_shot_2019-02-25at30134pm](assets/screen_shot_2019-02-25at30134pm.png)

1. Navigieren Sie zum **Verkehr** und geben Sie die **URI**, **Benutzer**, und **Passwort**.

   ![screen_shot_2019-03-04at34955pm](assets/screen_shot_2019-03-04at34955pm.png)

   >[!NOTE]
   >
   >Alternativ können Sie einen vorhandenen Replikationsagenten kopieren und umbenennen.


#### Erstellen von standardmäßigen Replikationsagenten {#creating-standard-replication-agents}

1. Erstellen Sie einen standardmäßigen Replikationsagenten für pub1 (ein vordefinierter Standardagent sollte bereits konfiguriert sein). Beispiel: *`https://<hostname>:4503/bin/receive?sling:authRequestLogin=1`*
1. Erstellen Sie einen standardmäßigen Replikationsagenten für pub2. Sie können den Replikationsagenten von pub1 kopieren und den für pub2 zu verwendenden Transport aktualisieren, indem Sie in der Transportkonfiguration den Port ändern. Zum Beispiel: *`https://<hostname>:4504/bin/receive?sling:authRequestLogin=1`*.

#### Erstellen von Screens-Replikationsagenten {#creating-screens-replication-agents}

1. Erstellen Sie einen AEM Screens-Replikationsagenten für pub1. Standardmäßig gibt es einen benannten Screens-Replikationsagenten, der auf Port 4503 verweist. Aktivieren Sie es.
1. Erstellen Sie einen AEM Screens-Replikationsagenten für pub2. Kopieren Sie den Screens-Replikationsagenten für pub1 und ändern Sie den Port für pub2 so, dass er auf 4504 verweist.

   >[!NOTE]
   >Informationen zum Konfigurieren von Screens-Replikationsagenten finden Sie unter [Konfigurieren des Screens-Replikationsagenten](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configure-screens-replication).

#### Erstellen von Screens-Agenten für die Rückwärtsreplikation {#creating-screens-reverse-replication-agents}

1. Erstellen Sie für pub1 einen Agenten für die Rückwärtsreplikation.
1. Erstellen Sie für pub2 einen Agenten für die Rückwärtsreplikation. Sie können den Agenten für die Rückwärtsreplikation für pub1 kopieren und den für pub2 zu verwendenden Transport aktualisieren, indem Sie den Port in der Transportkonfiguration ändern.

## Einrichten der Veröffentlichungstopologie {#setting-up-publish-topology}

### Schritt 1: Konfigurieren der Apache Sling Oak-basierten Erkennung {#step-configure-apache-sling-oak-based-discovery}

Einrichten der Apache Sling Oak-basierten Erkennung für alle Veröffentlichungsinstanzen in der Topologie

Für jede Veröffentlichungsinstanz:

1. Navigieren Sie zu `https://<host>:<port>/system/console/configMgr`
1. Klicks **Apache Sling Oak-basierter Erkennungsdienst** Konfiguration.
1. Aktualisieren Sie die Topologie-Connector-URLs: Fügen Sie URLs aller beteiligten Veröffentlichungsinstanzen hinzu, die:
   * `https://publish:4503/libs/sling/topology/connector`
   * `https://publish:4504/libs/sling/topology/connector`
1. **Topologie-Connector `Whitelist` Liste**: Passen Sie die Anpassung an IPs oder Subnetze an, die alle Veröffentlichungsinstanzen abdecken. Stellen Sie sicher `whitelist` IP/Hostname aller Veröffentlichungsinstanzen ohne Portnummer.

1. Aktivieren Sie **Auto-Stop Local-Loops**

Die Konfiguration sollte für jede Veröffentlichungsinstanz identisch sein und die automatische Stopp-Lokale Schleife verhindert eine Endlosschleife.

#### Schritt 2: Überprüfen der Veröffentlichungstopologie {#step-verify-publish-topology}

Navigieren Sie bei allen Veröffentlichungsinstanzen zu `https://:/system/console/topology`. Jede Veröffentlichungsinstanz sollte in der Topologie unter **Ausgehende Topologie-Connectoren**.

#### Schritt 3: Einrichten des ActiveMQ Artemis-Clusters {#step-setup-activemq-artemis-cluster}

In diesem Schritt können Sie ein verschlüsseltes Kennwort für den ActiveMQ Artemis-Cluster erstellen.
Der Cluster-Benutzer und das Kennwort aller Veröffentlichungsinstanzen in der Topologie müssen identisch sein. Das Kennwort der ActiveMQ Artemis-Konfiguration muss verschlüsselt sein. Da jede Instanz über einen eigenen Verschlüsselungsschlüssel verfügt, müssen Sie mithilfe von Crypto Support eine verschlüsselte Kennwortzeichenfolge erstellen. Anschließend kann das verschlüsselte Kennwort in der OSGi-Konfiguration für ActiveMQ verwendet werden.

Bei jeder Veröffentlichungsinstanz:

1. Navigieren Sie in der OSGi-Konsole zu **HAUPTANFANG** > **Crypto-Unterstützung** (`https://<host>:<port>/system/console/crypto`).
1. Geben Sie in **Nur Text** das gewünschte Passwort ein (nur Text; für alle Instanzen gleich).
1. Klicken Sie auf **Schützen**.
1. Wert kopieren **Geschützter Text** in einen Notizblock oder Texteditor. Dieser Wert kann in der OSGi-Konfiguration für ActiveMQ verwendet werden.

Da jede Veröffentlichungsinstanz standardmäßig über eindeutige Verschlüsselungsschlüssel verfügt, führen Sie diesen Schritt für jede Pub-Instanz aus und speichern Sie den eindeutigen Schlüssel für die nächste Konfiguration.

>[!NOTE]
>
>Das Passwort sollte mit geschweiften Klammern beginnen und enden. Beispiel:
>`{1ec346330f1c26b5c48255084c3b7272a5e85260322edd59119828d1fa0a610e}`

#### Schritt 4: Aktivieren des ActiveMQ Artemis-Clusters {#step-activate-activemq-artemis-cluster}

In jeder Veröffentlichungsinstanz:

1. Navigieren Sie zum OSGi-Konfigurations-Manager `https://<host>:<port>/system/console/configMgr`
1. Klicks **Apache ActiveMQ Artemis JMS Provider** Konfiguration
1. Aktualisieren Sie Folgendes:

   * ***Cluster-Kennwort***: Verwenden Sie den verschlüsselten Wert aus dem vorherigen Schritt pro Instanz.
   * ***Themen***: `{name: 'commands', address: 'com.adobe.cq.screens.commands', maxConsumers: 50}`

#### Überprüfen des ActiveMQ Artemis-Clusters {#verify-activemq-artemis-cluster}

Gehen Sie bei jeder Veröffentlichungsinstanz wie folgt vor:

1. Navigieren Sie zur OSGi-Konsole > Haupt > ActiveMQ Artemis . `https://localhost:4505/system/console/mq`.
1. Überprüfen Sie die Ports anderer Instanzen unter „Cluster-Informationen“ > „Topologie“ > „nodes=2, members=2“.
1. Senden Sie eine Testnachricht (oben im Bildschirm unter „Broker-Informationen“).
1. Geben Sie folgende Änderungen in die Felder ein:

   1. **Ziel**: /com.adobe.cq.screens/devTestTopic
   1. **Text**: Hallo Welt
   1. Anzeigen der `error.log` für jede Instanz, damit Sie sehen können, dass die Nachricht im gesamten Cluster gesendet und empfangen wurde.

>[!NOTE]
>
>Das Navigieren zur OSGi-Konsole kann einige Sekunden dauern, nachdem die Konfiguration im vorherigen Schritt gespeichert wurde. Sie können das Fehlerprotokoll (error.log) auch auf weitere Details prüfen.

Beispiel: Das folgende Bild zeigt eine erfolgreiche Konfiguration von ActiveMQ Artemis Server.

Wenn Sie die folgende Konfiguration über */system/console/mq* nicht sehen können, navigieren Sie zu */system/console/mq* und klicken Sie auf **Neu starten**, um den Broker neu zu starten.

![image-2018-06-18-18-14-55-449](assets/image-2018-06-18-18-14-55-449.png)

#### Anforderung für Referrer-Header entfernen {#remove-referrer-header-requirement}

Führen Sie die Schritte in den einzelnen Veröffentlichungsinstanzen aus:

1. Navigieren Sie zur **OSGi-Konsole** > **Configuration Manager**
1. Klicks **Apache Sling Referrer Filter**
1. Aktualisieren Sie die Konfiguration und aktivieren Sie **Allow Empty**

### Konfigurieren der Autoren- und Veröffentlichungsinstanz {#configuring-author-and-publish-instance}

Nachdem Sie die Veröffentlichungstopologie eingerichtet haben, konfigurieren Sie die Autoren- und Veröffentlichungsinstanzen so, dass die praktischen Ergebnisse der Implementierung angezeigt werden:

>[!NOTE]
>
>**Voraussetzungen**
>
>Erstellen Sie zunächst ein AEM Screens-Projekt und anschließend einen Standort, eine Anzeige und einen Kanal in Ihrem Projekt. Fügen Sie Ihrem Kanal Inhalte hinzu und weisen Sie den Kanal einer Anzeige zu.

#### Schritt 1: Starten eines AEM Screens-Players (Gerät)

1. Öffnen Sie ein separates Browser-Fenster.
1. Rufen Sie mithilfe des *Webbrowsers*, d. h. `https://localhost:4502/content/mobileapps/cq-screens-player/firmware.html`, den Screens-Player auf oder starten Sie die AEM Screens-App. Wenn Sie das Gerät öffnen, stellen Sie fest, dass der Status des Geräts abgemeldet ist.

>[!NOTE]
>
>Sie können einen AEM Screens-Player mit der heruntergeladenen AEM Screens-App oder über den Webbrowser öffnen.

#### Schritt 2: Registrieren eines Geräts in der Autoreninstanz {#step-registering-a-device-on-author}

1. Navigieren Sie zu `https://localhost:4502/screens.html/content/screens/we-retail` oder klicken Sie auf Ihr Projekt und navigieren Sie zu Geräte > Geräte-Manager.
1. Klicks **Gerät registrieren**.
1. Klicks **Geräteregistrierung**.
1. Klicken Sie auf das Gerät, das Sie registrieren möchten, und klicken Sie auf **Gerät registrieren**.
1. Überprüfen Sie den Registrierungs-Code und klicken Sie auf **Bestätigen**.
1. Geben Sie einen Titel für Ihr Gerät ein und klicken Sie auf **registrieren**.

#### Schritt 3: Zuweisen des Geräts zur Anzeige {#step-assigning-the-device-to-display}

1. Klicken Sie im Dialogfeld aus dem vorherigen Schritt auf **Anzeige zuweisen**.
1. Klicken Sie auf den Anzeigepfad für Ihren Kanal im **Standorte** Ordner.
1. Klicken Sie auf **Zuweisen**.
1. Klicken Sie auf **Beenden**, um den Vorgang abzuschließen. Das Gerät ist jetzt zugewiesen.

Überprüfen Sie Ihren Player und beachten Sie den Inhalt, den Sie in Ihrem Kanal hinzugefügt haben.

#### Schritt 4: Veröffentlichen der Gerätekonfiguration auf Veröffentlichungsinstanzen {#step-publishing-device-configuration-to-publish-instances}

**Überprüfen des Geräts**

Gehen Sie wie folgt vor, um den Gerätebenutzer zu replizieren:

1. Navigieren Sie zur Admin-Seite des Benutzers. Zum Beispiel: `https://localhost:4502/useradmin`.
1. Suchen Sie nach **`screens-devices-master`** hinzugefügt.
1. Klicken Sie mit der rechten Maustaste auf die Gruppe und klicken Sie **Aktivieren**.

>[!CAUTION]
>
>Aktivieren Sie den Dienst author-publish-screens-service nicht, da er ein vom Autorenauftrag verwendeter Systembenutzer ist.

Sie können das Gerät auch über die Geräteverwaltungskonsole aktivieren. Führen Sie dazu folgende Schritte durch:

1. Navigieren Sie zu Ihrem Screens-Projekt > **Geräte**.
1. Klicken Sie in der Aktionsleiste auf **Geräte-Manager**.
1. Klicken Sie auf das Gerät und klicken Sie auf **Aktivieren** in der Aktionsleiste, wie in der folgenden Abbildung dargestellt.

![screen_shot_2019-02-21at111036am](assets/screen_shot_2019-02-21at111036am.png)

>[!NOTE]
>
>Alternativ können Sie nach der Aktivierung des Geräts auch die Server-URL bearbeiten oder aktualisieren. Klicken Sie in der Aktionsleiste auf **Server-URL bearbeiten**, wie in der folgenden Abbildung dargestellt. Ihre Änderungen werden auf den AEM Screens-Player übertragen.

![screen_shot_2019-02-21at105527am](assets/screen_shot_2019-02-21at105527am.png)

### Checkliste für Veröffentlichungen {#publishing-check-list}

Die folgenden Punkte fassen die Checkliste für Veröffentlichungen zusammen:

* *Screens-Gerätebenutzer* - Diese Informationen werden als AEM Benutzer gespeichert und können über aktiviert werden. **Instrumente** > **Sicherheit** > **Benutzer**. Dem Benutzer wird &quot;screens&quot;mit einer langen serialisierten Zeichenfolge vorangestellt.

* *Projekt*: Das AEM Screens-Projekt.
* *Standort* - Standort, an den das Gerät angeschlossen ist.
* *Kanäle* - Ein oder mehrere Kanäle, die am Standort angezeigt werden.
* *Zeitplan* - Stellen Sie bei Verwendung eines Zeitplans sicher, dass dieser Zeitplan veröffentlicht wird.
* *Standort-, Zeitplan- und Kanalordner* - Wenn sich die entsprechenden Ressourcen in einem Ordner befinden.

Gehen Sie wie folgt vor, um das Authoring- und Publishing-Verhalten zu überprüfen:

1. Aktualisieren Sie einige Kanalinhalte in der -Autoreninstanz.
1. Ausführen **Veröffentlichung verwalten** , um neue Änderungen in allen Veröffentlichungsinstanzen zu veröffentlichen.
1. Presse **Aktivieren** , um das Gerät zu aktivieren von **Geräte-Manager**.
1. Auswählen **URL bearbeiten** von der Autoreninstanz-URL zu einer der Veröffentlichungsinstanzen-URL.
1. Überprüfen Sie, ob der aktualisierte Kanalinhalt auf dem AEM Screens-Player angezeigt wird.
1. Wiederholen Sie diese Schritte mit einer anderen Veröffentlichungsinstanz.


#### Schritt 5: Verweisen des Geräts auf eine Veröffentlichungsinstanz im Admininistrator-Bedienfeld {#step-pointing-the-device-to-publish-instance-in-the-admin-panel}

1. Zeigen Sie die Administrator-Benutzeroberfläche vom Screens-Player aus an, drücken Sie die linke obere Ecke, damit Sie das Menü &quot;Admin&quot;auf Ihrem Touch-optimierten AEM Screens-Player öffnen können, oder verwenden Sie eine Maus.
1. Klicken Sie im seitlichen Bereich auf die Option **Konfiguration**.
1. Ändern Sie die Autoreninstanz in die Veröffentlichungsinstanz in **Server**.

Zeigen Sie die Änderungen in Ihrem AEM Screens-Player an.

Alternativ können Sie über die Geräteverwaltungskonsole die Server-URL aktualisieren/bearbeiten:

1. Navigieren Sie zu Ihrem AEM Screens-Projekt und klicken Sie auf das **Geräte** Ordner.
1. Klicken Sie in der Aktionsleiste auf **Geräte-Manager**.
1. Klicken Sie auf das Gerät und dann in der Aktionsleiste auf **Server-URL bearbeiten**, wie in der folgenden Abbildung dargestellt. Ihre Änderungen werden auf den AEM Screens-Player übertragen.

![screen_shot_2019-02-07at31028pm](assets/screen_shot_2019-02-07at31028pm.png)

Die **Veröffentlichung verwalten** -Funktion können Sie Inhaltsaktualisierungen von der Autoren- zur Veröffentlichungsinstanz auf dem Gerät bereitstellen. Sie können Inhalte für Ihr gesamtes AEM Screens-Projekt oder nur für einen Ihrer Kanäle, Standorte, Geräte, Anwendungen oder Zeitpläne veröffentlichen bzw. dessen Veröffentlichung rückgängig machen. Weitere Informationen zu dieser Funktion finden Sie unter [On-Demand-Inhaltsaktualisierung](on-demand-content.md).

## Tipps zur Fehlerbehebung {#troubleshoot-tips}

Im folgenden Abschnitt finden Sie Antworten auf häufig gestellte Fragen zur Autoren-/Veröffentlichungseinrichtung.

### Wie kann nach der ersten Registrierung und Zuweisung eine Umleitung von https zu http hinzugefügt werden? {#add-redirect}

**Lösung**
Setzen Sie unter „Aktivieren“ die Option `Proxy/Load Balancer Connection in the Jetty configuration` auf `true`.

### Wie werden Offline-Inhalte und Player-Download-Probleme mit Assets außerhalb von `/content/dam/projects/<project>` aktualisiert? {#update-offline-content}

**Lösung**
Erteilen Sie Leseberechtigungen für den Benutzer Massen-Offline-Update-Screens-Service und `screens-devices-master` Gruppe für alle `/content/dam` oder die spezifischen Assets, die Sie verwenden möchten, wenn Sie restriktiver sein möchten.

### Wie können Screens-Replikationsagenten-Fehler behoben werden? {#replication-agent}

**Lösung**
Vergewissern Sie sich, dass Sie in der Agentenkonfiguration die Option „Für Rückwärtsreplikation verwenden“ nicht aktiviert haben. Der Screens-Replikationsagent kann nicht als Agenten für die Rückwärtsreplikation verwendet werden und der Umfang dieser Funktion besteht darin, Gerätebefehle von der Autoren- zur Veröffentlichungsinstanz weiterzuleiten.