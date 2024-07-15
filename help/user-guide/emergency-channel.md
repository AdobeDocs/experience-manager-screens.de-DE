---
title: Notfallkanal
description: Lernen Sie, wie man einen Notfallkanal erstellt und verwaltet, den die Inhaltsautorin oder der Inhaltsautor aus einem Sequenzkanal umschalten kann, wenn es eine Vorbedingung gibt.
content-type: example
topic-tags: use-case-examples
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d409ba46-b48a-44db-b305-27c392cd55de
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 100%

---

# Notfallkanal {#emergency-channel}

## Anwendungsfall – Beschreibung {#use-case-description}

In diesem Abschnitt wird ein Beispiel für einen Anwendungsfall beschrieben. Der Hauptaspekt liegt auf der Erstellung und Verwaltung eines Notfallkanals, den die Inhaltsautorin oder der Inhaltsautor aus einem Sequenzkanal umschalten kann, wenn es eine Vorbedingung gibt.

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
   >Weitere Informationen zum Erstellen und Verwalten von Projekten in AEM Screens finden Sie unter „Erstellen eines Projekts“.

   ![screen_shot_2019-02-21at35809pm](assets/screen_shot_2019-02-21at35809pm.png)

1. **Erstellen eines Sequenzkanals**

   1. Klicken Sie auf den Ordner **Kanäle** und dann auf **Erstellen**.

   1. Klicken Sie im Assistenten auf **Sequenzkanal** und erstellen Sie einen Kanal mit dem Namen **MainAdChannel**.

   ![screen_shot_2019-02-21at35932pm](assets/screen_shot_2019-02-21at35932pm.png)

1. **Hinzufügen von Inhalten zu Sequenzkanälen**

   1. Klicken Sie auf den Kanal (**MainAdChannel**).
   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**. 
   1. Ziehen Sie einige Assets per Drag-and-Drop in Ihren Kanal.

   ![screen_shot_2019-02-21at40053pm](assets/screen_shot_2019-02-21at40053pm.png)

1. **Erstellen eines Notfallkanals**

   1. Klicken Sie auf den Ordner **Kanäle**.
   1. Klicken Sie auf **Erstellen**.
   1. Klicken Sie im Assistenten auf **Sequenzkanal** und erstellen Sie einen Kanal mit dem Namen **EmergencyChannel**.

   >[!NOTE]
   >
   >Normalerweise wird Ihr Notfallkanal Ihrem bereits bestehenden Produktionsprojekt hinzugefügt.

   ![screen_shot_2019-02-21at40151pm](assets/screen_shot_2019-02-21at40151pm.png)

1. **Hinzufügen von Inhalten zu Notfallkanälen**

   1. Klicken Sie auf den Kanal (**Notrufkanal)**.
   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**. 
   1. Ziehen Sie das Asset, das Sie im Notfall ausführen möchten, per Drag-and-Drop in Ihren Kanal.

   ![screen_shot_2019-02-21at40516pm](assets/screen_shot_2019-02-21at40516pm.png)

1. **Erstellen eines Standorts**

   1. Navigieren Sie zum Ordner **Standorte**.
   1. Klicken Sie in der Aktionsleiste auf **Erstellen** und erstellen Sie im Assistenten einen Standort mit dem Titel **Store**.

   ![screen_shot_2019-02-22at121638pm](assets/screen_shot_2019-02-22at121638pm.png)

1. **Erstellen von Anzeigen für Ihren Standort**

   Navigieren Sie zu Ihrem Standort (**Store**) und klicken Sie in der Aktionsleiste auf **Erstellen**. Folgen Sie dem Assistenten und erstellen Sie zwei **Anzeigen** mit den Namen **StoreFront** und **StoreRear**.

   ![screen_shot_2019-02-22at122556pm](assets/screen_shot_2019-02-22at122556pm.png)

1. **Erstellen eines Zeitplans**

   1. Navigieren Sie zum Ordner **Zeitpläne**.
   1. Klicken Sie in der Aktionsleiste auf **Erstellen**.
   1. Folgen Sie den Anweisungen des Assistenten und erstellen Sie einen Zeitplan mit dem Namen **StoreSchedule**.

   ![screen_shot_2019-02-22at122845pm](assets/screen_shot_2019-02-22at122845pm.png)

1. Weisen Sie dem Zeitplan beide Anzeigen zu und legen Sie Prioritäten fest

   1. Klicken Sie auf den Zeitplan **(StoreSchedule)** und klicken Sie in der Aktionsleiste auf **Dashboard**.

   1. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE** auf **+ Kanal zuweisen**.

   1. Tun Sie im Dialogfeld **Kanalzuweisung** Folgendes:

      1. Klicken Sie auf den Pfad zum **MainAdChannel**
      1. Legen Sie die **Priorität** auf „2“ fest
      1. Wählen Sie unter „Unterstützte Ereignisse“ die Optionen **Erster Ladevorgang** und **Bildschirm bei Untätigkeit**.
      1. Klicken Sie auf **Speichern**.

      Führen Sie die gleichen Schritte erneut aus, um den **EmergencyChannel** zuzuweisen und seine **Priorität** festzulegen.

   >[!NOTE]
   >
   >Die Priorität wird verwendet, um die Zuweisungen in eine Reihenfolge zu bringen, wenn es mehrere Zuweisungen gibt, die den Wiedergabekriterien entsprechen. Höhere Werte haben immer Vorrang vor niedrigeren Werten.

   ![screen_shot_2019-03-04at104636am](assets/screen_shot_2019-03-04at104636am.png)

1. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE** auf **+ Kanal zuweisen**.

1. Tun Sie im Dialogfeld **Kanalzuweisung** Folgendes:

   1. Klicken Sie auf den Pfad zum **EmergencyChannel**
   1. Legen Sie die **Priorität** auf „1“ fest

   1. Wählen Sie unter „Unterstützte Ereignisse“ die Optionen **Erster Ladevorgang**, **Bildschirm bei Untätigkeit** und **Benutzerinteraktion**.

   1. Klicken Sie auf **Speichern**.

   ![screen_shot_2019-03-04at104741am](assets/screen_shot_2019-03-04at104741am.png)

   Sie können die zugewiesenen Kanäle im Dashboard **StoreSchedule** anzeigen.

   ![screen_shot_2019-02-25at93658pm](assets/screen_shot_2019-02-25at93658pm.png)

1. **Zuweisen eines Zeitplans zu jeder Anzeige**

   1. Navigieren Sie zu jeder Anzeige, z. B. **EmergencyChannel** > **Standorte** > **Store** >**StoreFront**.

   1. Klicken Sie in der Aktionsleiste auf **Dashboard**.
   1. Klicken Sie im Bedienfeld **ZUGEWIESENE KANÄLE UND ZEITPLÄNE** auf **…** und dann auf **+ Zeitplan zuweisen**.

   1. Klicken Sie auf den Pfad zum Zeitplan (hier zum Beispiel **EmergencyChannel** > **Zeitpläne** >**StoreSchedule**).

   1. Klicken Sie auf **Speichern**.

   Sie können den der Anzeige zugewiesenen Zeitplan im Dashboard **StoreSchedule** anzeigen.
   ![screen_shot_2019-03-04at122003pm](assets/screen_shot_2019-03-04at122003pm.png)

1. **Geräteregistrierung**

   Schließen Sie den Prozess zur Geräteregistrierung ab. Wenn Sie registriert sind, können Sie die folgende Ausgabe auf Ihrem AEM Screens-Player sehen.

   ![new30](assets/new30.gif)

## Wechseln zum Notfallkanal {#switching-to-emergency-channel}

Führen Sie im Notfall die folgenden Schritte aus:

1. Navigieren Sie zu **EmergencyChannel** > **Zeitpläne** > **StoreSchedule** und klicken Sie in der Aktionsleiste auf **Dashboard**.

   ![screen_shot_2019-02-25at101112pm](assets/screen_shot_2019-02-25at101112pm.png)

1. Klicken Sie im Dashboard **StoreSchedule** auf **EmergencyChannel** und dann auf **Zuweisung bearbeiten**.

   ![screen_shot_2019-02-25at101239pm](assets/screen_shot_2019-02-25at101239pm.png)

1. Aktualisieren Sie im Dialogfeld **Kanalzuweisung** die **Priorität** des **EmergencyChannel** auf **3** und klicken Sie auf **Speichern**.

   ![screen_shot_2019-02-25at101622pm](assets/screen_shot_2019-02-25at101622pm.png)

1. Wenn die Priorität des Kanals aktualisiert wird, zeigen alle AEM Screens-Player den Inhalt des **EmergencyChannel** an.

   ![screen_shot_2019-02-25at101742pm](assets/screen_shot_2019-02-25at101742pm.png)

### Zusammenfassung {#conclusion}

Der **EmergencyChannel** zeigt seinen Inhalt so lange an, bis die Autorin bzw. der Autor des Inhalts den Prioritätswert auf 1 zurücksetzt.

Wenn die Inhaltsautorin bzw. der Inhaltsautor die Anweisung erhält, dass der Notfall behoben wurde, sollte sie bzw. er die Priorität des **MainAdChannel** aktualisieren.  Hierdurch wird die normale Wiedergabe fortgesetzt.
