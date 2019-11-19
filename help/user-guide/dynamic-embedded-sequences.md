---
title: Verwenden dynamischer eingebetteter Sequenzen
seo-title: Verwenden dynamischer eingebetteter Sequenzen
description: Auf dieser Seite erfahren Sie, wie Sie dynamische eingebettete Sequenzen in Ihrem AEM Screens-Projekt implementieren.
seo-description: Auf dieser Seite erfahren Sie, wie Sie dynamische eingebettete Sequenzen in Ihrem AEM Screens-Projekt implementieren.
uuid: 1f442489-2eeb-4dd8-b892-911fcccb3377
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: a40eb5bb-fbf7-4c0d-a34a-db79b884de8f
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Verwenden dynamischer eingebetteter Sequenzen {#using-dynamic-embedded-sequence}

Die Verwendung dynamischer eingebetteter Sequenzen umfasst die folgenden Themen:

* **Überblick**
* **Dynamisches eingebettetes Erlebnis in AEM-Bildschirmen**
* **Ansicht der Ergebnisse**
* **Eingrenzen von Benutzern und Ändern der ACLs**

## Überblick {#overview}

***Dynamische eingebettete Sequenzen*** werden für große Projekte erstellt, die der übergeordneten untergeordneten Hierarchie folgen. Dabei wird auf das untergeordnete Element in einem Ordner "location"und nicht in einem Kanalordner verwiesen. It allows the user to embed a sequence inside a channel by ***Channel Role***. Damit kann der Benutzer standortspezifische Platzhalter für verschiedene Standorte mithilfe einer eingebetteten Sequenz innerhalb eines Hauptkanals definieren.

Beim Zuweisen eines Kanals zu einer Anzeige haben Sie die Möglichkeit, entweder den Pfad der Anzeige oder die Rolle des Kanals anzugeben, der nach Kontext zu einem tatsächlichen Kanal aufgelöst wird.

Um die dynamische eingebettete Sequenz zu verwenden, weisen Sie einen Kanal nach ***Kanalrolle*** zu. Die Kanalrolle definiert den Kontext der Anzeige. Die Rolle wird durch verschiedene Aktionen bestimmt und ist unabhängig vom tatsächlichen Kanal, der die Rolle erfüllt. In diesem Abschnitt wird ein Nutzungsszenario beschrieben, um Kanäle rollenbasiert zu definieren. Außerdem erfahren Sie, wie Sie diesen Inhalt für einen globalen Kanal nutzen können. Sie können sich die Rolle auch als ID für die Zuweisung oder als Alias für den Kanal im Kontext von vorstellen.

### Vorteile der Verwendung dynamischer eingebetteter Sequenzen {#benefits-of-using-dynamic-embedded-sequences}

Der Hauptvorteil des Platzierens eines Sequenzkanals innerhalb eines Speicherorts anstelle des Kanalordners besteht darin, lokalen oder regionalen Autoren zu ermöglichen, für sie relevante Inhalte zu bearbeiten, während sie von den Bearbeitungskanälen in der Hierarchie weiter oben eingeschränkt werden.

Referencing a *Channel By Role*, allows you to create local version of a channel, in order to dynamically resolve location-specific content and also allows you to create a global channel that leverages the content for the location-specific channels.

>[!NOTE]
>
>**Eingebettete und dynamische eingebettete Sequenzen**
>
>Eine dynamische eingebettete Sequenz ähnelt einer eingebetteten Sequenz, ermöglicht es dem Benutzer jedoch, einer Hierarchie zu folgen, in der die an einem Kanal vorgenommenen Änderungen/Aktualisierungen in Bezug auf einen anderen übertragen werden. Es folgt der Hierarchie von übergeordneter und untergeordneter Ebene und umfasst auch Elemente wie Bilder oder Videos.
>
>***Mit dynamischen eingebetteten Sequenzen*** können Sie standortspezifischen Inhalt anzeigen, während ***eingebettete Sequenzen*** nur eine allgemeine Diashow des Inhalts anzeigen. Außerdem müssen Sie beim Einrichten der dynamischen eingebetteten Sequenzen den Kanal mit Kanalrolle und Kanalname konfigurieren. Für die praktische Umsetzung gehen Sie bitte wie folgt vor:
>
>Weitere Informationen zur Implementierung von eingebetteten Sequenzen finden Sie unter [Eingebettete Sequenzen](embedded-sequences.md) in AEM Screens.

Das folgende Beispiel bietet eine Lösung, indem der Schwerpunkt auf die folgenden Schlüsselbegriffe gelegt wird:

* einen ***Hauptsequenzkanal*** für die globale Sequenz
* ***dynamische integrierte Sequenzkomponenten*** für jeden lokal anpassbaren Teil der Sequenz
* ***einzelne Sequenzkanäle*** an den jeweiligen Positionen mit einer *Rolle* in der Anzeige, die der **Rolle *der*dynamischen eingebetteten Sequenzkomponente entspricht.**

>[!NOTE]
>
>To learn more about channel assignment, see **[Channel Assignment](channel-assignment.md)** under Authoring section in AEM Screens documentation.

## Verwenden dynamischer eingebetteter Sequenzen {#using-dynamic-embedded-sequence-2}

Im folgenden Abschnitt wird die Erstellung einer dynamischen eingebetteten Sequenz in einem AEM-Bildschirmkanal erläutert.

### Voraussetzungen {#prerequisites}

Bevor Sie mit der Implementierung dieser Funktion beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen müssen, um mit der Implementierung dynamischer eingebetteter Sequenzen beginnen zu können:

* Erstellen eines AEM Screens-Projekts (in diesem Beispiel **Demo**)

* Kanal als **Global** im Ordner " **Kanäle** "erstellen

* Hinzufügen von Inhalten zu Ihrem **globalen** Kanal (*Überprüfen Sie **Resources.zip**für relevante Assets*)

Die folgende Abbildung zeigt das **Demo** -Projekt mit dem **globalen** Kanal im Ordner **Channels** .
![screen_shot_2018-09-07at21032pm](assets/screen_shot_2018-09-07at21032pm.png)

### Ressourcen {#resources}

Sie können die folgenden Ressourcen (Bilder und Assets hinzufügen) herunterladen und sie als Kanalinhalt für Demonstrationszwecke verwenden.

[Datei abrufen](assets/resources.zip)

>[!NOTE]
>
>Weitere Informationen zum Erstellen eines Projekts und zum Erstellen eines Sequenzkanals finden Sie in den nachfolgend aufgeführten Ressourcen:
>
>* **[Erstellen und Verwalten von Projekten](creating-a-screens-project.md)**
>* **[Verwalten eines Kanals](managing-channels.md)**
>



Die Implementierung der dynamischen eingebetteten Sequenz in einem AEM Screens-Projekt umfasst drei Hauptaufgaben:

1. **Einrichten der Projekttaxonomie einschließlich Kanälen, Orten und Anzeigen**
1. **Erstellen eines Zeitplans**
1. **Jeder Anzeige Zeitplan zuweisen**

Gehen Sie wie folgt vor, um die Funktion zu implementieren:

>[!CAUTION]
>
>Achten Sie bei der Implementierung dynamischer eingebetteter Sequenzen darauf, beim Erstellen von Kanälen unter den einzelnen Orten die **Felder "Name** "und " **Titel** "zu verwenden. Bitte befolgen Sie die Hinweise zur Nomenklatur sorgfältig.

1. **Erstellen Sie zwei Speicherorte.**

   Navigieren Sie im AEM Screens-Projekt zu Ihrem Ordner **Locations** und erstellen Sie zwei Ortsordner: **Region A** und **Region B**.

   >[!NOTE]
   >
   >Achten Sie beim Erstellen des Ordners **Region A** darauf, den **Titel** als **Region A** einzugeben und das Feld **Name** leer zu lassen. Daher wird automatisch ein **Region-ein** Name aufgenommen.
   >
   >Ähnlich ist es bei der Erstellung des Ordners **Region B**:

   ![screen_shot_2018-09-13at23212pm](assets/screen_shot_2018-09-13at23212pm.png)

   >[!NOTE]
   >
   >Informationen zum Erstellen eines Speicherorts finden Sie unter **[Erstellen und Verwalten von Speicherorten](managing-locations.md)**.

1. **Erstellen Sie unter jedem Ordner zwei Speicherorte und einen Kanal.**

   1. Navigieren Sie zu **Demo** —&gt; **Speicherorte** —&gt; **Region A**.
   1. Select **Region A** and click **+ Create** from the action bar.
   1. Wählen Sie **Ort** im Assistenten mit **Titel** als **Store 1**. Erstellen Sie auf ähnliche Weise einen anderen Speicherort aus dem Assistenten mit dem Titel " **Store 2** "mit **Titel** als **Store 2**. Sie können das Feld **Name** leer lassen, während Sie **Store 1** und **Store 2** erstellen.
   1. Wiederholen Sie Schritt b und wählen Sie jetzt **Sequenzkanal** aus dem Assistenten. Geben Sie den **Titel** als **Region A** und **Name** als **Region **für diesen Kanal ein.
   >[!CAUTION]
   >
   >Bitte geben Sie bei der Erstellung des Kanals **Region A** den **Titel** als **Region A **und den **Namen** als **Region** ein.

   ![screen_shot_2018-09-13at22857pm](assets/screen_shot_2018-09-13at22857pm.png)

   Erstellen Sie auf ähnliche Weise zwei Speicherorte unter **Region B** mit dem Titel **Store 3** und **Store 4**. Erstellen Sie außerdem einen **Sequenzkanal** mit **Titel** als **Region B** und **Name** als **Region**.

   >[!CAUTION]
   >
   >Achten Sie darauf, dass Sie denselben Namen für die Kanäle verwenden können, die in **Region A** und **Region B** wie in der **Region** erstellt wurden.

   ![screen_shot_2018-09-13at24408pm](assets/screen_shot_2018-09-13at24408pm.png)

1. **Erstellen Sie Anzeige und Kanal unter jedem Standort.**

   1. Navigieren Sie zu **Demo** —&gt; **Speicherorte** —&gt; **Region A** —&gt; **Store 1**.
   1. Select **Store 1** and click **+ Create** from the action bar.
   1. Wählen Sie im Assistenten die Option **Anzeigen** und erstellen Sie **Store1 Display.**
   1. Wiederholen Sie Schritt b und wählen Sie diesmal **Sequenzkanal** aus dem Assistenten. Geben Sie den **Titel** als **Store1Channel** und den **Namen** als **Store** ein.
   >[!CAUTION]
   >
   >Bei der Erstellung eines Sequenzkanals ist es wichtig, dass der **Titel** des Kanals Ihren Anforderungen entspricht. Der **Name** sollte jedoch in allen lokalen Kanälen gleich sein.
   >
   >In diesem Beispiel verwenden die Kanäle unter **Region A** und **Region B** denselben **Namen** wie **Region** und **Store 1**-Kanäle,Store 2,Store 3,Store 4 und ************ **** **** Store 4denselben Namen wie NameStore.

   ![screen_shot_2018-09-19at120206pm](assets/screen_shot_2018-09-19at120206pm.png)

   Ebenso erstellen Sie eine Anzeige als **Store2Display** und einen Channel **Store2Channel** unter** Store 2** (mit dem Namen als **Store**).

   >[!NOTE]
   >
   >Bitte stellen Sie sicher, dass Sie denselben Namen für die Kanäle verwenden können, die in **Store 1** und **Store 2** als **Store** erstellt wurden.

   ![screen_shot_2018-09-19at120329pm](assets/screen_shot_2018-09-19at120329pm.png)

   Gehen Sie wie folgt vor, um einen Kanal zu erstellen und in **Store 3** und **Store 4** unter **Region B** anzuzeigen. Stellen Sie erneut sicher, dass Sie denselben **Namen** wie **Store** verwenden, während Sie channel **Store3Channel** bzw. **Store4Channel** erstellen.

   Die folgende Abbildung zeigt die Anzeige und den Kanal im **Store 3**.

   ![screen_shot_2018-09-19at120448pm](assets/screen_shot_2018-09-19at120448pm.png)

   Die folgende Abbildung zeigt die Anzeige und den Kanal im **Store 4**.

   ![screen_shot_2018-09-19at120552pm](assets/screen_shot_2018-09-19at120552pm.png)

1. **Fügen Sie den Kanälen an ihren jeweiligen Speicherorten Inhalt hinzu.**

   Navigieren Sie zur **Demo** -&gt; **Speicherorte** -&gt; **Region A** -&gt; **Region A** und klicken Sie in der Aktionsleiste auf **Bearbeiten** . Ziehen Sie die Assets, die Sie zu Ihrem Kanal hinzufügen möchten, per Drag &amp; Drop.

   >[!NOTE]
   >
   >Sie können die Datei " ***Resources.zip*** "im Abschnitt " **Resources** "verwenden, um die Bilder als Elemente für Ihren Kanalinhalt zu verwenden.

   ![screen_shot_2018-09-12at12438pm](assets/screen_shot_2018-09-12at12438pm.png)

   Ebenso navigieren Sie zur **Demo** -&gt; **Speicherorte** -&gt; **Region B** -&gt; **Region B** und klicken Sie in der Aktionsleiste auf **Bearbeiten** , um die Assets per Drag &amp; Drop in Ihren Kanal zu ziehen, wie nachfolgend gezeigt:

   ![screen_shot_2018-09-12at13133pm](assets/screen_shot_2018-09-12at13133pm.png)

   Führen Sie die folgenden Schritte und die Ressourcen aus, um den folgenden Kanälen Inhalte hinzuzufügen:

   * **Store1Channel**
   * **Store2Channel**
   * **Store3Channel**
   * **Store4Channel**

1. **Zeitplan erstellen**

   Navigieren Sie zum Ordner " **Zeitpläne** "in Ihrem AEM Screens-Projekt und klicken Sie in der Aktionsleiste auf " **Erstellen** ", um einen neuen Zeitplan zu erstellen.

   Die folgende Abbildung zeigt den **AdScheduler** , der im **Demo** -Projekt erstellt wurde.

   ![screen_shot_2018-09-13at3307pm](assets/screen_shot_2018-09-13at33307pm.png)

1. **Zuweisen von Kanälen zu einem Zeitplan**

   1. Navigieren Sie zu **Demo** —&gt; **Zeitpläne** —&gt; **AdPlan** und klicken Sie in der Aktionsleiste auf **Dashboard** .
   1. Klicken Sie auf **+ Kanal** zuweisen aus **ZUGEWIESENEN KANÄLEN** , um das Dialogfeld " **Kanalzuweisung** "zu öffnen.
   1. Select **Reference Channel**.. by path.
   1. Wählen Sie den **Kanalpfad** als **Demo*** —&gt; ***Kanäle*** —&gt; ***Global***.
   1. Enter the **Channel Role** as **GlobalAdSegment**.
   1. Wählen Sie die **unterstützten Ereignisse** als **Erstladevorgang**, **Leerlauf** und **Benutzerinteraktion** aus.
   1. Klicken Sie auf **Speichern**.
   **Kanal nach Rolle für Region zuweisen:**

   1. Klicken Sie auf **+ Kanal** zuweisen aus **ZUGEWIESENEN KANÄLEN** , um das Dialogfeld " **Kanalzuweisung** "zu öffnen.
   1. Wählen Sie **Referenzkanal**. nach Name.
   1. Geben Sie den **Kanalnamen** als **region*** ein.*
   1. Enter the **Channel Role** as **RegionAdSegment**.
   1. Klicken Sie auf **Speichern**.
   **Kanal nach Rolle für den Store zuweisen:**

   1. Klicken Sie auf **+ Kanal** zuweisen aus **ZUGEWIESENEN KANÄLEN** , um das Dialogfeld " **Kanalzuweisung** "zu öffnen.
   1. Wählen Sie **Referenzkanal**. nach Name.
   1. Geben Sie den **Kanalnamen** als **Store** ein.
   1. Enter the **Channel Role** as **StoreAdSegment**.
   1. Klicken Sie auf **Speichern**.
   Die folgende Abbildung zeigt die zugewiesenen Kanäle nach Pfad und Rolle.

   ![screen_shot_2018-09-12at21429pm](assets/screen_shot_2018-09-12at21429pm.png)

1. **Konfigurieren der dynamischen eingebetteten Sequenz für den globalen Kanal.**

   Navigieren Sie zum **globalen** Kanal, den Sie ursprünglich im **Demo** -Projekt erstellt haben.

   Click **Edit** from the action to open the editor.

   ![screen_shot_2018-09-13at52754pm](assets/screen_shot_2018-09-13at52754pm.png)

   Ziehen Sie zwei **Komponenten der dynamischen eingebetteten Sequenz** per Drag &amp; Drop in den Kanaleditor.

   Öffnen Sie die Eigenschaften einer der Komponenten und geben Sie die **Kanalzuweisungsrolle** als **RegionAdSegment** ein.

   Ebenso wählen Sie die andere Komponente und öffnen Sie die Eigenschaften, um die **Kanalzuweisungsrolle** als **StoreAdSegment** einzugeben.

   ![channeldisplay4](assets/channeldisplay4.gif)

1. **Jeder Anzeige Zeitplan zuweisen**

   1. Navigieren Sie zum jeweiligen Display, z. B. **Demo** —&gt; **Speicherorte** —&gt; **Region A** —&gt;**Store 1** —&gt;**Store1Display**.
   1. Click **Dashboard** from the action to open the display dashboard.
   1. **Klicken Sie auf**... Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE &amp; ZEITPLÄNE** auf **+Zeitplan** zuweisen.
   1. Wählen Sie den Pfad zum Zeitplan aus (z. B. hier **Demo** —&gt; **Zeitpläne** —&gt;**AdPlan**).
   1. Klicken Sie auf **Speichern**.

## Ansicht der Ergebnisse {#viewing-the-results}

Sobald Sie die Einrichtung für Kanäle und die Anzeige abgeschlossen haben, starten Sie den AEM Screens Player, um den Inhalt anzuzeigen.

>[!NOTE]
>
>Weitere Informationen zu AEM Screen Player finden Sie in den folgenden Ressourcen:
>
>* [AEM Screenplayer-Downloads](https://download.macromedia.com/screens/)
>* [Arbeiten mit AEM Screens Player](working-with-screens-player.md)



Die folgende Ausgabe bestätigt Ihren Kanalinhalt im AEM Screens Player, je nach Anzeigepfad.

**Szenario 1**:

Wenn Sie den Anzeigepfad als **Demo** —&gt; **Speicherorte** —&gt; **Region A** —&gt;** Store 1** —&gt; **Store1Display** zuweisen, wird der folgende Inhalt im AEM Screens Player angezeigt.

![channeldisplay1](assets/channeldisplay1.gif)

**Szenario 1**:

Wenn Sie den Anzeigepfad als **Demo** —&gt; **Speicherorte** —&gt; **Region B** —&gt;* Store 3** —&gt; **Store3Display** zuweisen, wird der folgende Inhalt im AEM Screens Player angezeigt.

![channeldisplay2](assets/channeldisplay2.gif)

## Eingrenzen von Benutzern und Ändern der ACLs {#restricting-users-and-modifying-the-acls}

Sie können globale, regionale oder lokale Autoren erstellen, um für sie relevante Inhalte zu bearbeiten, während Sie von den Bearbeitungskanälen weiter oben in der Hierarchie eingeschränkt werden.

Sie müssen die ACLs ändern, um den Zugriff der Benutzer auf die Inhalte je nach Standort einzuschränken.

### Verwendungsfall {#example-use-case}

Im folgenden Beispiel können Sie drei Benutzer für das obige Demo-Projekt erstellen.

Die Berechtigungen werden jeder Gruppe wie folgt zugewiesen:

**Gruppen**:

* **Global-Author**: Besteht aus Benutzern, die Zugriff auf alle Speicherorte und Kanäle im **Demo** -Projekt haben und über alle Lese-, Schreib- und Bearbeitungsberechtigungen verfügen.

* **Region-Autor**: Besteht aus Benutzern, die Lese-, Schreib- und Bearbeitungsberechtigungen für **Region A** und **Region B** besitzen.

* **Store-Autor**: Besteht aus Benutzern, die nur über Lese-, Schreib- und Bearbeitungsberechtigungen für **Store 1**, **Store 2**, **Store 3** und **Store 4** verfügen.

#### Schritte zum Erstellen von Benutzergruppen, Benutzern und Einrichten von ACLs {#steps-for-creating-user-groups-users-and-setting-up-acls}

>[!NOTE]
>
>Detaillierte Informationen dazu, wie Sie Projekte mithilfe von ACLs trennen, damit jede Einzelperson oder jedes Team ihr eigenes Projekt handhabt, finden Sie unter **Einrichten von ACLs**.

Gehen Sie wie folgt vor, um Gruppen zu erstellen, Benutzer zu verwenden und die Zugriffsberechtigungen für Zugriffsrechte zu ändern:

1. **Gruppen erstellen**

   1. Navigate to **Adobe Experience Manager**.
   1. Click **Tools** --&gt; **Security** --&gt; **Groups**.
   1. Klicken Sie auf Gruppe **erstellen** und geben Sie **Global-Author** in die **ID** ein.
   1. Klicken Sie auf **Speichern und schließen**.
   Erstellen Sie auf ähnliche Weise zwei weitere Gruppen wie **Region-Autor** und **Store-Autor**.

   ![screen_shot_2018-09-17at34008pm](assets/screen_shot_2018-09-17at34008pm.png)

1. **Benutzer erstellen und Gruppen Benutzer hinzufügen**

   1. Navigate to **Adobe Experience Manager**.
   1. Click **Tools** --&gt; **Security** --&gt; **Users**.
   1. Klicken Sie auf Benutzer **erstellen** und geben Sie **Global-User** in die **ID** ein.
   1. Geben Sie **Kennwort** ein und bestätigen Sie das Kennwort für diesen Benutzer.
   1. Klicken Sie auf die Registerkarte " **Gruppen** "und geben Sie den Gruppennamen in Gruppe **auswählen** ein. Geben Sie beispielsweise **Global-Author** ein, um dieser Gruppe **Global-User** hinzuzufügen.
   1. Klicken Sie auf **Speichern und schließen**.
   Erstellen Sie auf ähnliche Weise zwei weitere Benutzer wie **Region-Benutzer** und **Store-Benutzer** und fügen Sie sie **Region-Autor** bzw. **Store-Autor** hinzu.

   >[!NOTE]
   >
   >Es empfiehlt sich, Benutzer einer Gruppe hinzuzufügen und dann jeder bestimmten Benutzergruppe Berechtigungen zuzuweisen.

   ![screen_shot_2018-09-17at34412pm](assets/screen_shot_2018-09-17at34412pm.png)

1. **Hinzufügen aller Gruppen zu den beitragenden Personen**

   1. Navigate to **Adobe Experience Manager**.
   1. Click **Tools** --&gt; **Security** --&gt; **Groups**.
   1. Wählen Sie in der Liste die Option " **Mitarbeiter** "und wählen Sie die Registerkarte " **Mitglieder** "aus.
   1. Wählen Sie die **Gruppe** aus, z. B. **Global-Author**, **Region-Autor und** Store-Autor **** für Mitarbeiter.
   1. Klicken Sie auf **Speichern und schließen**.

1. **Zugriff auf Berechtigungen für jede Gruppe**

   1. Navigieren Sie zum *Benutzeradmin* und ändern Sie mithilfe dieser Benutzeroberfläche die Berechtigungen für verschiedene Gruppen.
   1. Suchen Sie nach **Global-Author** und klicken Sie auf die Registerkarte **Berechtigungen** , wie in der Abbildung unten dargestellt.
   1. Ebenso können Sie auf die Berechtigungen für **Region-Autor** und **Store-Autor** zugreifen.
   ![screen_shot_2018-09-18at73523am](assets/screen_shot_2018-09-18at73523am.png)

1. **Berechtigungen für jede Gruppe ändern**

   **Für Global-Author:**

   1. Navigate to the **Permissions** tab
   1. Navigieren Sie zu ***/content/screens/demo*** und überprüfen Sie alle Berechtigungen
   1. Navigieren Sie zu ***/content/screens/demo/locations*** und überprüfen Sie alle Berechtigungen
   1. Navigieren Sie zu ***/content/screens/demo/locations***/***region-a*** und überprüfen Sie alle Berechtigungen. Überprüfen Sie auf ähnliche Weise die Berechtigungen für **region-b**.
   Die Schritte sind in der folgenden Abbildung nachzulesen:
   ![screen_shot_2018-09-18at115752am](assets/screen_shot_2018-09-18at115752am.png)

   Die folgende Abbildung zeigt, dass der **Global-User** nun Zugriff auf den **Globalen Kanal** und sowohl auf **Region A** als auch auf **Region B** hat, mit allen vier Stores, nämlich **Store 1**************,Store 2,Store 3undStore 4.

   Den Ordner ![global](assets/global.gif)

   **Für Region-Autor:**

   1. Navigate to the **Permissions** tab.
   1. Navigieren Sie zu ***/content/screens/demo*** und prüfen Sie nur die** Read***-Berechtigungen.
   1. Navigieren Sie zu ***/content/screens/demo/locations*** und prüfen Sie nur die **Leseberechtigung** .
   1. Navigieren Sie zu ***/content/screens/demo/kanäle ***und deaktivieren Sie die Berechtigungen für**globale **Kanäle.***
   1. Navigieren Sie zu ***/content/screens/demo/locations***/***region-a*** und überprüfen Sie alle Berechtigungen. Überprüfen Sie auf ähnliche Weise die Berechtigungen für **region-b**.
   Die Schritte sind in der folgenden Abbildung nachzulesen:

   ![screen_shot_2018-09-18at125158pm](assets/screen_shot_2018-09-18at125158pm.png)

   Die folgende Abbildung zeigt, dass der Region-Benutzer nun Zugriff auf **Region A** und **Region B** hat, mit allen vier Stores, nämlich **Store 1**, **Store 2**, **Store 3****** **** undStore 4, aber keinen Zugriff auf den ChannelGlobal hat.

   ![region](assets/region.gif)

   **Für Store-Autor:**

   1. Navigate to the **Permissions** tab.
   1. Navigieren Sie zu ***/content/screens/demo*** und prüfen Sie nur die **Leseberechtigung** .
   1. Navigieren Sie zu ***/content/screens/demo/locations*** und prüfen Sie nur die **Leseberechtigung** .
   1. Navigieren Sie zu ***/content/screens/demo/kanäle*** und deaktivieren Sie die Berechtigungen für den **globalen** Kanal.
   1. Navigieren Sie zu ***/content/screens/demo/locations/region-a*** und prüfen Sie nur die **Leseberechtigung** . Ebenso sollten Sie nur die **Read** -Berechtigungen für **region-b**&#x200B;überprüfen.
   1. Navigieren Sie zu ***/content/screens/demo/locations***/***region-a /store-1*** und überprüfen Sie alle Berechtigungen. Überprüfen Sie auf ähnliche Weise die Berechtigungen für **store-2,** store-3 und **store-4**.
   Die Schritte sind in der folgenden Abbildung nachzulesen:

   ![screen_shot_2018-09-18at12415pm](assets/screen_shot_2018-09-18at12415pm.png)

   Die folgende Abbildung zeigt, dass der **Store-Benutzer** jetzt nur noch Zugriff auf die vier Stores **Store 1**, **Store 2**, **Store 3** und **Store 4** **** **** hat, jedoch keine Zugriffsberechtigungen auf die KanäleGlobaloder die Region (**Region A **und Region B) hat.

   ![store](assets/store.gif)

>[!NOTE]
>
>Ausführliche Informationen zum Einrichten von Berechtigungen finden Sie unter [Einrichten von ACLs](setting-up-acls.md).

