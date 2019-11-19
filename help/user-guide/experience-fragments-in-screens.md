---
title: Verwenden von Erlebnisfragmenten
seo-title: Verwenden von Erlebnisfragmenten
description: 'Auf dieser Seite erfahren Sie mehr über die Verwendung von Erlebnisfragmenten in AEM-Bildschirmen. '
seo-description: 'Auf dieser Seite erfahren Sie mehr über die Verwendung von Erlebnisfragmenten in AEM-Bildschirmen. '
uuid: 6ee16a94-3c53-43e0-99d5-c35cb9e01120
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 0e88e9e0-a95b-4acd-98ea-499d4d4e3c99
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Verwenden von Erlebnisfragmenten {#using-experience-fragments}

Diese Seite behandelt die folgenden Themen:

* **Überblick**
* **Verwenden von Erlebnisfragmenten in AEM Screens**
* **Änderungen von der Masterseite propagieren**

## Überblick {#overview}

Ein ***Erlebnisfragment**ist eine Gruppe aus einer oder mehreren Komponenten (einschließlich Inhalt und Layout), die innerhalb von Seiten referenziert werden können.* Erlebnisfragmente können beliebige Komponenten enthalten, beispielsweise eine oder mehrere Komponenten mit beliebigen Elementen innerhalb eines Absatzsystems, das für das Gesamterlebnis referenziert oder von einem dritten Endpunkt angefordert wird.


## Verwenden von Erlebnisfragmenten in AEM Screens {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>
>Im folgenden Beispiel wird **We.Retail** als Demoprojekt verwendet, bei dem das Erlebnisfragment von einer Seite mit **Sites** zu einem AEM Screens-Projekt genutzt wird.

Der folgende Arbeitsablauf veranschaulicht beispielsweise die Verwendung von Erlebnisfragmenten aus Web.Retail in Sites. Sie können eine Webseite auswählen und diese Inhalte in Ihrem AEM Screens-Kanal in einem Ihrer Projekte nutzen.

### Voraussetzungen {#pre-requisites}

**Erstellen eines Demoprojekts mit einem Kanal**

***Erstellen eines Projekts***

1. Click Screens and select **Create** --&gt; **Create Project **to create a new project.

1. Wählen Sie **Bildschirme **aus dem Assistenten zum Erstellen von Bildschirmen **s.

1. Geben Sie **DemoProject** als Titel ein.
1. Klicken Sie auf **Erstellen**.

Ein **DemoProject** wird Ihren AEM-Bildschirmen hinzugefügt.  ***Erstellen eines Kanals***

1. Navigate to the **DemoProject** you created and select the **Channels** folder.

1. Click **Create** from the action bar (see the figure below). Ein Assistent wird geöffnet.
1. Wählen Sie im Assistenten die Vorlage **Sequenzkanal** aus und klicken Sie auf **Weiter**.

1. Enter the **Title** as **TestChannel** and click **Create**.

Ein **TestChannel** wird Ihrem **DemoProject** hinzugefügt.\
![screen_shot_2019-07-29at105101am](assets/screen_shot_2019-07-29at105101am.png)



### Erstellen eines Experience Fragment {#creating-an-experience-fragment}

Gehen Sie wie folgt vor, um den Inhalt von **We.Retail** zu Ihrem **TestChannel** in **DemoProject** zu nutzen.

1. **Navigieren Sie zu einer Siteseite in We.Retail**

   1. Navigieren Sie zu Sites und wählen Sie **We.Retail **-&gt;** United States **-&gt;**English **und wählen Sie **Equipment** page, um dieses als Erlebnisfragment für Ihren Bildschirmkanal zu verwenden.

   1. Klicken Sie in der Aktionsleiste auf **Bearbeiten** , um die Seite zu öffnen, die Sie als Erlebnisfragment für Ihren Bildschirmkanal verwenden möchten.
   ![screen_shot_2018-06-06at105309am](assets/screen_shot_2018-06-06at105309am.png)

1. **Wiederverwenden des Inhalts**

   1. Wählen Sie das Fragment aus, das Sie in den Kanal aufnehmen möchten.
   1. Klicken Sie auf das letzte Symbol rechts, um das Dialogfeld "In Erlebnisfragment **konvertieren"** zu öffnen.
   ![screen_shot_2019-07-29at105314am](assets/screen_shot_2019-07-29at105314am.png)

1. **Erlebnisfragment erstellen**

   1. Wählen Sie die **Aktion** als neues Erlebnisfragment **erstellen**.

   1. Wählen Sie den **übergeordneten Pfad** aus.
   1. Select the **Template**. Wählen Sie hier die Vorlage **Erlebnisfragment - Bildschirmvarianz **aus.

   1. Enter the **Fragment Title **as **ScreensFragment**.

   1. Klicken Sie auf das Häkchen, um die Erstellung eines neuen Erlebnisfragments abzuschließen.
   ![screen_shot_2019-07-29at105918am](assets/screen_shot_2019-07-29at105918am.png)

1. **Erstellen einer Live-Kopie des Erlebnisfragments**

   1. Navigieren Sie zur AEM-Homepage.
   1. Wählen Sie " **Erlebnisfragmente** "aus, markieren Sie das **Bildschirmfragment** und klicken Sie auf " **Variation"als Live-Kopie**, wie in der folgenden Abbildung dargestellt:
   ![screen_shot_2019-07-29at110443am](assets/screen_shot_2019-07-29at110443am.png)

   c. Wählen Sie den Assistenten zum Erstellen **von** Live Copy*** ScreensFragment und klicken Sie auf **Weiter**.

   d. Geben Sie den **Titel** und den **Namen** als **Bildschirme** ein.

   e. Klicken Sie auf **Erstellen** , um die Live Copy zu erstellen.

   f. Klicken Sie auf **Fertig** , um zur Seite " **Bildschirmfragment** "zurückzukehren.

   ![screen_shot_2019-07-29at110616am](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >Nachdem Sie das Bildschirmfragment erstellt haben, können Sie die Eigenschaften des Fragments bearbeiten. Wählen Sie das Fragment aus und klicken Sie in der Aktionsleiste auf **Eigenschaften** .

   **Bearbeiten von Eigenschaften eines Bildschirmfragments**

   1. Navigieren Sie zum **Bildschirmfragment** (das Sie in den vorherigen Schritten erstellt haben) und klicken Sie in der Aktionsleiste auf **Eigenschaften** .

   1. Wählen Sie die Registerkarte " **Offline-Konfiguration** ", wie in der Abbildung unten dargestellt.
   Sie können Ihrem Erlebnisfragment die **clientseitigen Bibliotheken** (Java und CSS) und **statischen Dateien** hinzufügen.

   Das folgende Beispiel zeigt das Hinzufügen clientseitiger Bibliotheken und Schriften als Teil statischer Dateien zu Ihrem Erlebnisfragment.  ![Fragment](assets/fragment.gif)

1. **Erlebnisfragment als Komponente im Bildschirmkanal verwenden**

   1. Navigieren Sie zum Bildschirmkanal, in dem Sie das **Bildschirmfragment** verwenden möchten.
   1. Wählen Sie den **TestChannel** aus und klicken Sie in der Aktionsleiste auf **Bearbeiten** .

   1. Klicken Sie auf das Symbol Komponenten in der Registerkarte Seite.
   1. Ziehen Sie das **Erlebnisfragment** auf Ihren Kanal.
   ![screen_shot_2019-07-29at123115pm](assets/screen_shot_2019-07-29at123115pm.png)

   e. Wählen Sie die Komponente " **Erlebnisfragment** "und klicken Sie auf das Symbol oben links (Schraubenschlüssel), um das Dialogfeld " **Erlebnisfragment** "zu öffnen.

   f. Wählen Sie im Feld **Pfad **die Live-Kopie des Fragments aus, das Sie in **Schritt 3** ** erstellt haben.

   ![screen_shot_2019-07-26at82650pm](assets/screen_shot_2019-07-26at82650pm.png)

   f. Wählen Sie im Feld **Erlebnisfragment **die Live-Kopie des Fragments aus, das Sie in **Schritt 3** ** erstellt haben.

   ![screen_shot_2019-07-26at82509pm](assets/screen_shot_2019-07-26at82509pm.png)

   h. Geben Sie die Sekunden in das Feld** Dauer* ein.

   i. Wählen Sie im Dialogfeld " **Erlebnisfragmente** "die **Offline-Konfiguration** aus, um die clientseitigen Bibliotheken und die statischen Dateien zu definieren.

   >[!NOTE]
   >
   >Wenn Sie zusätzlich zu dem, was Sie in Schritt 4 konfiguriert haben, clientseitige Bibliotheken oder statische Dateien hinzufügen möchten, können Sie im Dialogfeld " **Erlebnisfragment** "auf der Registerkarte " **Offline-Konfiguration** "hinzufügen.

   ![screen_shot_2019-07-26at82844pm](assets/screen_shot_2019-07-26at82844pm.png)

   j. Klicken Sie auf das Häkchen, um den Vorgang abzuschließen.

### Validieren des Ergebnisses {#validating-the-result}

Nach Abschluss der vorherigen Schritte können Sie Ihr Erlebnisfragment in **ChannelOne** wie folgt validieren:

1. Navigieren zum **TestChannel**.
1. Wählen Sie die **Vorschau** in der Aktionsleiste aus.

Sie sehen den Inhalt auf der Seite **Sites** (Live-Kopie des Erlebnisfragments) in Ihrem Kanal, wie in der folgenden Abbildung dargestellt:\
![screen_shot_2018-06-08at120739pm](assets/screen_shot_2018-06-08at120739pm.png)

## Änderungen von der Masterseite propagieren {#propagating-changes-from-the-master-page}

***"Live Copy*** "bezieht sich auf die Kopie (der Quelle), die durch Synchronisierungsaktionen gemäß den Rollout-Konfigurationen verwaltet wird.

Da das Erlebnisfragment eine Live-Kopie von den Seiten **Sites** ist, sehen Sie die Änderungen an diesem bestimmten Fragment auf der Masterseite in Ihrem Kanal oder am Ziel, in dem Sie das Erlebnisfragment verwendet haben.

>[!NOTE]
>
>Weitere Informationen zu Live Copy finden Sie unter Wiederverwenden von Inhalt: Multi Site Manager und Live Copy.

Gehen Sie wie folgt vor, um Änderungen vom Masterkanal zum Zielkanal zu übertragen:

1. Wählen Sie auf der Seite " **Sites** (Master)"das Erlebnisfragment aus und klicken Sie auf das Stiftsymbol, um die Elemente im Erlebnisfragment zu bearbeiten.

   ![screen_shot_2018-06-08at122655pm](assets/screen_shot_2018-06-08at122655pm.png)

1. Wählen Sie das Erlebnisfragment aus und klicken Sie auf das Schraubenschlüsselsymbol, um das Dialogfeld zum Bearbeiten der Bilder zu öffnen.

   ![screen_shot_2018-06-08at25031pm](assets/screen_shot_2018-06-08at25031pm.png)

1. Das Dialogfeld " **Produktraster** "wird angezeigt.

   ![screen_shot_2018-06-08at25306pm](assets/screen_shot_2018-06-08at25306pm.png)

1. Sie können alle Bilder bearbeiten. Hier wird beispielsweise das erste Bild in diesem Fragment ersetzt.

   ![screen_shot_2018-06-08at25608pm](assets/screen_shot_2018-06-08at25608pm.png)

1. Wählen Sie das Erlebnisfragment aus und klicken Sie auf das Rollout-Symbol, um Änderungen an dem Fragment zu übertragen, das in Ihrem Kanal verwendet wird.

   ![screen_shot_2018-06-08at31352pm](assets/screen_shot_2018-06-08at31352pm.png)

1. Klicken Sie auf Rollout, um die Änderungen zu bestätigen.

   Sie sehen, dass die Änderungen ausgeführt werden.

   ![screen_shot_2018-06-08at32148pm](assets/screen_shot_2018-06-08at32148pm.png)

### Validieren der Änderungen {#validating-the-changes}

Gehen Sie wie folgt vor, um die Änderungen in Ihrem Kanal zu bestätigen:

1. Navigieren Sie zu den **Bildschirmen** -&gt; **Kanäle** -&gt; **TestChannel**.

1. Klicken Sie in der Aktionsleiste auf **Vorschau** , um die Änderungen zu bestätigen.

Die folgende Abbildung zeigt die Änderungen in Ihrem **TestChannel**:\
![screen_shot_2018-06-08at3351pm](assets/screen_shot_2018-06-08at33351pm.png)

