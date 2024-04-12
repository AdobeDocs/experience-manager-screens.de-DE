---
title: Notfallkanal
description: Erfahren Sie mehr über das Erstellen und Verwalten eines Notfallkanals, den der Inhaltsautor von einem Sequenzkanal aus wechseln kann, wenn eine Bedingung vorliegt.
content-type: example
topic-tags: use-case-examples
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d409ba46-b48a-44db-b305-27c392cd55de
source-git-commit: ba5327077e4a2d30cc7b77f02123da5a240c67ae
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 60%

---

# Notfallkanal {#emergency-channel}

## Nutzungsszenario – Beschreibung {#use-case-description}

In diesem Abschnitt wird ein Nutzungsszenario beschrieben, das sich auf die Erstellung und Verwaltung eines Notfallkanals konzentriert, zu dem der Inhaltsautor von einem Sequenzkanal wechseln kann, wenn eine Bedingung vorliegt.

### Voraussetzungen {#preconditions}

Bevor Sie mit diesem Nutzungsszenario beginnen, sollten Sie sich mit den folgenden Themen vertraut machen:

* **[Erstellen und Verwalten von Kanälen](managing-channels.md)**
* **[Erstellen und Verwalten von Standorten](managing-locations.md)**
* **[Erstellen und Verwalten von Zeitplänen](managing-schedules.md)**
* **[Geräteregistrierung](device-registration.md)**

### Hauptakteure {#primary-actors}

Autoren von Inhalten

## Grundlegender Ablauf: Einrichten des Projekts {#basic-flow-setting-up-the-project}

Gehen Sie wie folgt vor, um einen Notfallkanal einzurichten:

1. Erstellen Sie ein AEM Screens-Projekt mit dem Namen **EmergencyChannel**, wie unten dargestellt.

   >[!NOTE]
   >Weitere Informationen zum Erstellen und Verwalten von Projekten in AEM Screens finden Sie unter Erstellen eines Projekts.

   ![screen_shot_2019-02-21at35809pm](assets/screen_shot_2019-02-21at35809pm.png)

1. **Erstellen eines Sequenzkanals**

   1. Wählen Sie die **Kanäle** Ordner und klicken Sie auf **Erstellen**.

   1. Wählen Sie im Assistenten die Option **Sequenzkanal** aus und erstellen Sie den Kanal mit dem Titel **MainAdChannel**.

   ![screen_shot_2019-02-21at35932pm](assets/screen_shot_2019-02-21at35932pm.png)

1. **Hinzufügen von Inhalten zu Sequenzkanälen**

   1. Wählen Sie den Kanal (**MainAdChannel**) aus.
   1. Klicks **Bearbeiten** in der Aktionsleiste aus.
   1. Ziehen Sie einige Assets per Drag-and-Drop in Ihren Kanal.

   ![screen_shot_2019-02-21at40053pm](assets/screen_shot_2019-02-21at40053pm.png)

1. **Erstellen eines Notfallkanals**

   1. Wählen Sie den Ordner **Kanäle** aus.
   1. Klicken Sie auf **Erstellen**.
   1. Wählen Sie im Assistenten die Option **Sequenzkanal** aus und erstellen Sie den Kanal mit dem Titel **EmergencyChannel**.

   >[!NOTE]
   >
   >Normalerweise wird Ihr Notfallkanal Ihrem bereits bestehenden Produktionsprojekt hinzugefügt.

   ![screen_shot_2019-02-21at40151pm](assets/screen_shot_2019-02-21at40151pm.png)

1. **Hinzufügen von Inhalten zu Notfallkanälen**

   1. Wählen Sie den Kanal (**Notfallkanal**) aus.
   1. Klicks **Bearbeiten** in der Aktionsleiste aus.
   1. Ziehen Sie das Asset, das Sie im Notfall ausführen möchten, in Ihren Kanal.

   ![screen_shot_2019-02-21at40516pm](assets/screen_shot_2019-02-21at40516pm.png)

1. **Erstellen eines Standorts**

   1. Navigieren Sie zum Ordner **Standorte**.
   1. Klicken Sie in der Aktionsleiste auf **Erstellen** und erstellen Sie im Assistenten einen Standort mit dem Titel **Store**.

   ![screen_shot_2019-02-22at121638pm](assets/screen_shot_2019-02-22at121638pm.png)

1. **Erstellen von Anzeigen für Ihren Standort**

   Navigieren Sie zu Ihrem Standort (**Store**) und klicken Sie in der Aktionsleiste auf **Erstellen**. Erstellen Sie im Anschluss an den Assistenten zwei **Anzeigen** benannt als **StoreFront** und **StoreRear**.

   ![screen_shot_2019-02-22at122556pm](assets/screen_shot_2019-02-22at122556pm.png)

1. **Erstellen eines Zeitplans**

   1. Navigieren Sie zum Ordner **Zeitpläne**.
   1. Klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Erstellen Sie im Anschluss an den Assistenten einen Zeitplan mit dem Titel **StoreSchedule**.

   ![screen_shot_2019-02-22at122845pm](assets/screen_shot_2019-02-22at122845pm.png)

1. Weisen Sie dem Zeitplan beide Anzeigen zu und legen Sie Prioritäten fest

   1. Wählen Sie den Zeitplan **(StoreSchedule)** aus und klicken Sie in der Aktionsleiste auf **Dashboard**.

   1. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE** auf **+ Kanal zuweisen**.

   1. Wählen Sie im Dialogfeld **Kanalzuweisung** Folgendes aus:

      1. Wählen Sie den Pfad zum **MainAdChannel** aus
      1. Legen Sie die **Priorität** auf „2“ fest
      1. Wählen Sie unter „Unterstützte Ereignisse“ die Optionen **Erster Ladevorgang** und **Bildschirm bei Untätigkeit**.
      1. Klicken Sie auf **Speichern**.

      Führen Sie dieselben Schritte erneut aus, um die **EmergencyChannel** und legen **Priorität**.

   >[!NOTE]
   >
   >Die Priorität wird verwendet, um die Zuweisungen in eine Reihenfolge zu bringen, wenn mehrere Zuweisungen den Wiedergabekriterien entsprechen. Der Wert mit dem höchsten Wert hat immer Vorrang vor niedrigeren Werten.

   ![screen_shot_2019-03-04at104636am](assets/screen_shot_2019-03-04at104636am.png)

1. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE** auf **+ Kanal zuweisen**.

1. Wählen Sie im Dialogfeld **Kanalzuweisung** Folgendes aus:

   1. Wählen Sie den Pfad zum **EmergencyChannel** aus
   1. Legen Sie die **Priorität** auf „1“ fest

   1. Wählen Sie unter „Unterstützte Ereignisse“ die Optionen **Erster Ladevorgang**, **Bildschirm bei Untätigkeit** und **Benutzerinteraktion**.

   1. Klicken Sie auf **Speichern**.

   ![screen_shot_2019-03-04at104741am](assets/screen_shot_2019-03-04at104741am.png)

   Sie können die zugewiesenen Kanäle im Dashboard **StoreSchedule** anzeigen.

   ![screen_shot_2019-02-25at93658pm](assets/screen_shot_2019-02-25at93658pm.png)

1. **Zuweisen eines Zeitplans zu jeder Anzeige**

   1. Navigieren Sie zu jeder Anzeige, z. B. **EmergencyChannel** > **Standorte** > **Store** >**StoreFront**.

   1. Klicks **Dashboard** in der Aktionsleiste aus.
   1. Klicken Sie auf **...** im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** und klicken Sie auf **+ Zeitplan zuweisen**.

   1. Wählen Sie den Pfad zum Zeitplan aus (hier beispielsweise **EmergencyChannel** > **Zeitpläne** >**StoreSchedule**).

   1. Klicken Sie auf **Speichern**.

   Sie können den der Anzeige zugewiesenen Zeitplan im Dashboard **StoreSchedule** anzeigen.
   ![screen_shot_2019-03-04at122003pm](assets/screen_shot_2019-03-04at122003pm.png)

1. **Geräteregistrierung**

   Schließen Sie den Prozess zur Geräteregistrierung ab. Wenn Sie sich registriert haben, können Sie die folgende Ausgabe auf Ihrem AEM Screens-Player anzeigen.

   ![new30](assets/new30.gif)

## Wechseln zum Notfallkanal {#switching-to-emergency-channel}

Führen Sie im Notfall die folgenden Schritte aus:

1. Navigieren Sie zu **EmergencyChannel** > **Zeitpläne** > **StoreSchedule** und wählen **Dashboard** in der Aktionsleiste aus.

   ![screen_shot_2019-02-25at101112pm](assets/screen_shot_2019-02-25at101112pm.png)

1. Wählen Sie **EmergencyChannel** aus dem Dashboard **StoreSchedule** und klicken Sie auf **Zuweisung bearbeiten**.

   ![screen_shot_2019-02-25at101239pm](assets/screen_shot_2019-02-25at101239pm.png)

1. Aktualisieren Sie im Dialogfeld **Kanalzuweisung** die **Priorität** des **EmergencyChannel** auf **3** und klicken Sie auf **Speichern**.

   ![screen_shot_2019-02-25at101622pm](assets/screen_shot_2019-02-25at101622pm.png)

1. Wenn die Priorität des Kanals aktualisiert wird, zeigt der gesamte AEM Screens-Player die **EmergencyChannel** Inhalt.

   ![screen_shot_2019-02-25at101742pm](assets/screen_shot_2019-02-25at101742pm.png)

### Zusammenfassung {#conclusion}

Die **EmergencyChannel** zeigt seinen Inhalt weiterhin an, bis der Inhaltsautor den Prioritätswert auf 1 zurücksetzt.

Wenn der Inhaltsautor die Anweisungen erhält, dass der Notfall behoben wurde, sollte er die Priorität der **MainAdChannel** wodurch die normale Wiedergabe fortgesetzt wird.
