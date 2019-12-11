---
title: Notfallkanal
seo-title: Notfallkanal
description: In diesem Verwendungsfallbeispiel erfahren Sie, wie Sie einen Notfallkanal erstellen und verwalten, über den der Inhaltsautor im Falle einer Bedingung von einem Sequenzkanal wechseln kann.
seo-description: In diesem Verwendungsfallbeispiel erfahren Sie, wie Sie einen Notfallkanal erstellen und verwalten, über den der Inhaltsautor im Falle einer Bedingung von einem Sequenzkanal wechseln kann.
uuid: 612917c9-a832-453b-970c-f4365f7b105d
content-type: example
topic-tags: use-case-examples
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
discoiquuid: dbb4fae6-f3fb-496a-9bd6-1151e2862b5b
docset: aem65
translation-type: tm+mt
source-git-commit: 2708464222321fd138c986f19d8572c71f1dae75

---


# Notfallkanal {#emergency-channel}

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Abschnitt wird ein Verwendungsfallbeispiel beschrieben, in dem hervorgehoben wird, wie ein Notkanal erstellt und verwaltet wird, über den der Inhaltsautor im Falle einer Bedingung von einem Sequenzkanal wechseln kann.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Anwendungsfall beginnen, sollten Sie wissen, wie:

* **[Kanäle erstellen und verwalten](managing-channels.md)**
* **[Orte erstellen und verwalten](managing-locations.md)**
* **[Zeitpläne erstellen und verwalten](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Inhaltsersteller

## Grundlegender Fluss:Einrichten des Projekts {#basic-flow-setting-up-the-project}

Gehen Sie wie folgt vor, um einen Notfallkanal einzurichten:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Namen **EmergencyChannel**, wie unten dargestellt.

   >[!NOTE]
   >
   >Weitere Informationen zum Erstellen und Verwalten von Projekten in AEM Screens finden Sie unter Erstellen eines Projekts.

   ![screen_shot_2019-02-21at35809pm](assets/screen_shot_2019-02-21at35809pm.png)

1. **Erstellen eines Sequenzkanals**

   1. Wählen Sie den Ordner " **Kanäle** "und klicken Sie auf " **Erstellen** ", um den Assistenten zum Erstellen eines Kanals zu öffnen.

   1. Wählen Sie **Sequenzkanal** aus dem Assistenten und erstellen Sie den Kanal mit dem Titel **MainAdChannel**.
   ![screen_shot_2019-02-21at35932pm](assets/screen_shot_2019-02-21at35932pm.png)

1. **Hinzufügen von Inhalten zum Sequenzkanal**

   1. Wählen Sie den Kanal aus (**MainAdChannel**).
   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen. Ziehen Sie einige Assets per Drag &amp; Drop in Ihren Kanal.
   ![screen_shot_2019-02-21at40053pm](assets/screen_shot_2019-02-21at40053pm.png)

1. **Erstellen eines Notfallkanals**

   1. Wählen Sie den Ordner **Kanäle** aus.
   1. Klicken Sie auf **Erstellen** , um den Assistenten zu öffnen, um einen Kanal zu erstellen.
   1. Wählen Sie **Sequenzkanal** aus dem Assistenten und erstellen Sie den Kanal mit dem Namen **EmergencyChannel**.
   >[!NOTE]
   >
   >Normalerweise wird Ihr Notfallkanal zu Ihrem bereits bestehenden Produktionsprojekt hinzugefügt.

   ![screen_shot_2019-02-21at40151pm](assets/screen_shot_2019-02-21at40151pm.png)

1. **Hinzufügen von Inhalten zum Notfall-Kanal**

   1. Wählen Sie den Kanal aus (**Notkanal)**.
   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um den Editor zu öffnen. Ziehen Sie das Asset, das Sie im Notfall ausführen möchten, auf Ihren Kanal.
   ![screen_shot_2019-02-21at40516pm](assets/screen_shot_2019-02-21at40516pm.png)

1. **Erstellen eines Ortes**

   1. Navigieren Sie zum Ordner **Speicherorte** .
   1. Klicken Sie in der Aktionsleiste auf " **Erstellen** "und erstellen Sie im Assistenten einen Speicherort mit der Bezeichnung " **Store** ".
   ![screen_shot_2019-02-22at121638pm](assets/screen_shot_2019-02-22at121638pm.png)

1. **Erstellen von Displays am Standort**

   Navigieren Sie zu Ihrem Speicherort (**Store**) und klicken Sie in der Aktionsleiste auf **Erstellen** . Führen Sie den Assistenten aus, um zwei **Displays** mit dem Titel " **StoreFront** "und " **StoreRear"zu erstellen**.

   ![screen_shot_2019-02-22at122556pm](assets/screen_shot_2019-02-22at122556pm.png)

1. **Erstellen eines Zeitplans**

   1. Navigieren Sie zum Ordner " **Zeitpläne** ".
   1. Klicken Sie in der Aktionsleiste auf **Erstellen.** Folgen Sie dem Assistenten, um einen Zeitplan mit dem Titel **StoreScheduling** zu erstellen.
   ![screen_shot_2019-02-22at122845pm](assets/screen_shot_2019-02-22at122845pm.png)

1. Weisen Sie dem Zeitplan die Anzeige zu und legen Sie Prioritäten fest

   1. Wählen Sie den Zeitplan **(StoreSchedule)** aus und klicken Sie in der Aktionsleiste auf **Dashboard** .

   1. Klicken Sie auf **+ Kanal** zuweisen aus dem Bedienfeld **ZUGEWIESENE KANÄLE** .

   1. Wählen Sie im Dialogfeld **Kanalzuweisung** Folgendes aus:

      1. Wählen Sie den Pfad zum **MainAdChannel**
      1. Legen Sie die **Priorität** auf 2 fest.
      1. Set the Supported Events as **Initial Load** and **Idle Screen**.
      1. Klicken Sie auf **Speichern**
      Ebenso müssen Sie die gleichen Schritte wiederholen, um den **EmergencyChannel** zuzuweisen und seine **Priorität** festzulegen.
   >[!NOTE]
   >
   >Mit „Priorität“ können Zuweisungen gereiht werden, falls mehrere die Präsentationskriterien erfüllen. Höhere Werte haben stets Vorrang vor niedrigeren Werten.

   ![screen_shot_2019-03-04at104636am](assets/screen_shot_2019-03-04at104636am.png)

1. Klicken Sie auf **+ Kanal** zuweisen aus dem Bedienfeld **ZUGEWIESENE KANÄLE** .

1. Wählen Sie im Dialogfeld **Kanalzuweisung** Folgendes aus:

   1. Wählen Sie den Pfad zum **EmergencyChannel aus.**
   1. Legen Sie die **Priorität** auf 1 fest.

   1. Unterstützte Ereignisse als **anfängliche Ladevorgänge**, **Leerlauf** und **Benutzerinteraktion festlegen**

   1. Klicken Sie auf **Speichern**
   ![screen_shot_2019-03-04at104741am](assets/screen_shot_2019-03-04at104741am.png)

   Sie können die zugewiesenen Kanäle im Dashboard **StoreScheduling** anzeigen.

   ![screen_shot_2019-02-25at93658pm](assets/screen_shot_2019-02-25at93658pm.png)

1. **Jeder Anzeige Zeitplan zuweisen**

   1. Navigieren Sie zu den einzelnen Displays, z. B. **EmergencyChannel** —&gt; **Speicherorte** —&gt; **Store** —&gt;**StoreFront**.

   1. Click **Dashboard** from the action to open the display dashboard.
   1. **Klicken Sie auf**... Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE &amp; ZEITPLÄNE** auf **+Zeitplan** zuweisen.

   1. Wählen Sie den Pfad zum Zeitplan aus (hier z. B. **EmergencyChannel** —&gt; **Zeitpläne** —&gt;**StorePlan**).

   1. Klicken Sie auf **Speichern**.
   Sie können den der Anzeige zugewiesenen Zeitplan über das Dashboard **StorePlan** anzeigen.
   ![screen_shot_2019-03-04at122003pm](assets/screen_shot_2019-03-04at122003pm.png)

1. **Geräteregistrierung**

   Schließen Sie den Vorgang zur Geräteregistrierung ab und sehen Sie nach der Registrierung die folgende Ausgabe auf Ihrem AEM Screens-Player an.

   ![new30](assets/new30.gif)

## Wechsel zum Notkanal {#switching-to-emergency-channel}

Im Notfall führen Sie die folgenden Schritte aus:

1. Navigieren Sie zu **EmergencyChannel** —&gt; **Zeitpläne** —&gt; **StorePlan** und wählen Sie in der Aktionsleiste **Dashboard** .

   ![screen_shot_2019-02-25at10112pm](assets/screen_shot_2019-02-25at101112pm.png)

1. Wählen Sie den **EmergencyChannel** aus dem Dashboard **StorePlan** und klicken Sie auf Zuweisung **bearbeiten**.

   ![screen_shot_2019-02-25at101239pm](assets/screen_shot_2019-02-25at101239pm.png)

1. Aktualisieren Sie die **Priorität** des **EmergencyChannel** auf **3** im Dialogfeld **Kanalzuweisung** und klicken Sie auf **Speichern**.

   ![screen_shot_2019-02-25at101622pm](assets/screen_shot_2019-02-25at101622pm.png)

1. Sobald die Priorität des Kanals aktualisiert wurde, zeigt der gesamte AEM Screens-Player den **EmergencyChannel** -Inhalt an, wie unten dargestellt.

   ![screen_shot_2019-02-25at101742pm](assets/screen_shot_2019-02-25at101742pm.png)

### Zusammenfassung {#conclusion}

Der **EmergencyChannel** zeigt seinen Inhalt weiterhin an, bis der Inhaltsautor den Prioritätswert auf 1 zurücksetzt.

Sobald der Autor des Inhalts die Anweisungen erhalten hat, dass der Notfall gelöscht wurde, sollte er die Priorität des **MainAdChannel** aktualisieren, wodurch die normale Wiedergabe wieder aufgenommen wird.
