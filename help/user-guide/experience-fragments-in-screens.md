---
title: Verwenden von Experience Fragments
description: Erfahren Sie mehr über die Verwendung von Experience Fragments in AEM Screens.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Experience Fragments
role: Admin, Developer
level: Intermediate
exl-id: 13c0d75e-435f-433e-8886-f451df863517
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 32%

---

# Verwenden von Experience Fragments {#using-experience-fragments}

Auf dieser Seite werden die folgenden Themen behandelt:

* **Überblick**
* **Verwenden von Experience Fragments in AEM Screens**
* **Übertragen von Änderungen auf die Seite**

## Überblick {#overview}

Ein ***Experience Fragment*** ist eine Gruppe aus einer oder mehreren Komponenten (einschließlich Inhalt und Layout), die innerhalb von Seiten referenziert werden können. Experience Fragments können beliebige Komponenten enthalten, z. B. eine oder mehrere Komponenten, die beliebige Elemente innerhalb eines Absatzsystems enthalten können, die in das gesamte Erlebnis referenziert oder von einem dritten Endpunkt angefordert werden.


## Verwenden von Experience Fragments in AEM Screens {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>Das folgende Beispiel verwendet **`We.Retail`** als Demoprojekt, von dem aus das Experience Fragment von einem **Sites** zu einem AEM Screens-Projekt hinzugefügt.

Der folgende Workflow veranschaulicht beispielsweise die Verwendung von Experience Fragments aus `We.Retail` in Sites. Sie können eine Webseite auswählen und diesen Inhalt in Ihrem AEM Screens-Kanal in einem Ihrer Projekte verwenden.

### Voraussetzungen {#pre-requisites}

**Erstellen eines Demoprojekts mit einem Kanal**

***Erstellen eines Projekts***

1. Klicken Sie zum Erstellen eines Projekts auf **Screens-Projekt erstellen**.
1. Geben Sie **DemoProject** als Titel ein.
1. Klicken Sie auf **Speichern**.

A **DemoProject** zu Ihrer AEM Screens hinzugefügt.

***Erstellen eines Kanals***

1. Navigieren Sie zum **DemoProject** Sie haben erstellt und klicken Sie auf **Kanäle** Ordner.

1. Klicks **Erstellen** in der Symbolleiste, damit Sie den Assistenten öffnen können.
1. Wählen Sie im Assistenten die Vorlage **Sequenzkanal** aus und klicken Sie auf **Weiter**.

1. Geben Sie **TestChannel** als **Titel** ein und klicken Sie auf **Erstellen**.

A **TestChannel** wird zu Ihrem **DemoProject**.\
![screen_shot_2019-07-29at105101am](assets/screen_shot_2019-07-29at105101am.png)


### Erstellen eines Experience Fragment {#creating-an-experience-fragment}

Gehen Sie wie folgt vor, um den Inhalt aus **`We.Retail`** auf **TestChannel** in **DemoProject**.

1. **Navigieren zu einer Sites-Seite in We.Retail**

   1. Navigieren Sie zu Sites und klicken Sie auf **`We.Retail`** > **Vereinigte Staaten** > **englisch** > **Ausrüstung** und klicken Sie auf diese Seite, damit Sie dies als Experience Fragment für Ihren Screens-Kanal verwenden können.

   1. Klicks **Bearbeiten** in der Aktionsleiste, damit Sie die Seite öffnen können, die Sie als Experience Fragment für Ihren Screens-Kanal verwenden möchten.

1. **Wiederverwenden des Inhalts**

   1. Klicken Sie auf das Fragment, das Sie in Ihren Kanal aufnehmen möchten.
   1. Klicken Sie auf das letzte Symbol rechts, damit Sie die **In Experience Fragment konvertieren** Dialogfeld.

   ![screen_shot_2019-07-29at105314am](assets/screen_shot_2019-07-29at105314am.png)

1. **Erstellen eines Experience Fragments**

   1. Wählen Sie unter **Aktion** die Option **Neues Experience Fragment erstellen** aus.

   1. Klicken Sie auf **Übergeordneter Pfad**.
   1. Klicken Sie auf **Vorlage**. Wählen Sie hier die Vorlage **Experience Fragment - Screens-Variante** aus (Wert im Feld `/libs/settings/screens/experience-fragments/templates/experience-fragment-template-screens`).

   1. Geben Sie unter **Fragmenttitel** den Wert **ScreensFragment** ein.

   1. Um die Erstellung eines neuen Experience Fragment abzuschließen, klicken Sie auf das Häkchen.

   ![screen_shot_2019-07-29at105918am](assets/screen_shot_2019-07-29at105918am.png)

   Hinweis: Um auf eine einfachere Option zu klicken, klicken Sie auf das Kontrollkästchen rechts neben dem Feld, damit Sie das Auswahldialogfeld öffnen können.

1. **Erstellen einer Live Copy des Experience Fragments**

   1. Navigieren Sie zur AEM-Homepage.
   1. Klicks **Experience Fragments** und markieren Sie **ScreensFragment** und klicken **Variante als Live Copy**, wie in der folgenden Abbildung dargestellt:

   ![screen_shot_2019-07-29at110443am](assets/screen_shot_2019-07-29at110443am.png)

   c. Klicken Sie auf die **ScreensFragment** von **Erstellen einer Live Copy** Assistent und klicken Sie auf **Nächste**.

   d. Geben Sie unter **Titel** und unter **Namen** den Wert **Screens** ein.

   e. Klicken Sie auf **Erstellen** , damit Sie die Live Copy erstellen können.

   f. Klicken Sie auf **Fertig** , damit Sie zurück zu **ScreensFragment** Seite.

   ![screen_shot_2019-07-29at110616am](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >Nachdem Sie ein AEM Screens-Fragment erstellt haben, können Sie die Eigenschaften des Fragments bearbeiten. Klicken Sie auf das Fragment und klicken Sie auf **Eigenschaften** in der Aktionsleiste aus.

   **Bearbeiten von Eigenschaften eines Screens-Fragments**

   1. Navigieren Sie zum **ScreensFragment** (das Sie in den vorherigen Schritten erstellt haben) und klicken Sie in der Aktionsleiste auf **Eigenschaften**.

   1. Klicken Sie auf **Offline-Konfiguration** wie in der folgenden Abbildung dargestellt.

   Sie können die **Client-seitige Bibliotheken** (Java™ und CSS) und **Statische Dateien** zu Ihrem Experience Fragment hinzu.

   Das folgende Beispiel zeigt das Hinzufügen von Client-seitigen Bibliotheken und Schriftarten als Teil statischer Dateien zu Ihrem Experience Fragment.  ![fragment](assets/fragment.gif)

1. **Verwenden des Experience Fragments als Komponente im Screens-Kanal**

   1. Navigieren Sie zum Screens-Kanal, in dem Sie das **Screens**-Fragment verwenden möchten.
   1. Klicken Sie auf **TestChannel** und klicken **Bearbeiten** in der Aktionsleiste aus.

   1. Klicken Sie in der Seitenleiste auf das Komponentensymbol.
   1. Ziehen Sie das **Experience Fragment** in Ihren Kanal.

   ![screen_shot_2019-07-29at123115pm](assets/screen_shot_2019-07-29at123115pm.png)

   e. Klicken Sie auf die **Experience Fragment** und klicken Sie auf das Symbol oben links (Schraubenschlüssel), damit Sie die **Experience Fragment** Dialogfeld.

   f. Klicken Sie auf die **Screens** Live Copy des Fragments, das Sie in erstellt haben *Schritt 3* in **Pfad**.

   ![screen_shot_2019-07-26at82650pm](assets/screen_shot_2019-07-26at82650pm.png)

   f. Klicken Sie auf die **Screens** Live Copy des Fragments, das Sie in erstellt haben *Schritt 3* im **Experience Fragment**.

   ![screen_shot_2019-07-26at82509pm](assets/screen_shot_2019-07-26at82509pm.png)

   h. Geben Sie die Millisekunden in **Dauer** ein.

   i. Klicken Sie auf die **Offline-Konfiguration** aus dem **Experience Fragments** -Dialogfeld, damit Sie die clientseitigen Bibliotheken und die statischen Dateien definieren können.

   >[!NOTE]
   >
   >Um Client-seitige Bibliotheken oder statische Dateien zusätzlich zu dem hinzuzufügen, was Sie in Schritt 4 konfiguriert haben, können Sie über die **Offline-Konfiguration** im **Experience Fragment** Dialogfeld.

   ![screen_shot_2019-07-26at82844pm](assets/screen_shot_2019-07-26at82844pm.png)

   j. Klicken Sie auf das Häkchen, damit Sie den Vorgang abschließen können.

### Validieren des Ergebnisses {#validating-the-result}

Nach Abschluss der vorherigen Schritte können Sie Ihr Experience Fragment in **ChannelOne** durch:

1. Navigieren Sie zum **TestChannel**.
1. Wählen Sie in der Aktionsleiste die **Vorschau** aus.

Anzeigen des Inhalts aus der **Sites** Seite (Live Copy des Experience Fragment) in Ihrem Kanal verwenden, wie in der folgenden Abbildung dargestellt:\
![screen_shot_2018-06-08at120739pm](assets/screen_shot_2018-06-08at120739pm.png)

## Übertragen von Änderungen auf die Seite {#propagating-changes-from-the-master-page}

***Live Copy*** bezieht sich auf die Kopie (der Quelle), die durch Synchronisierungsaktionen aufrechterhalten wird, wie in den Rollout-Konfigurationen definiert.

Da das von Ihnen erstellte Experience Fragment eine Live Copy aus dem **Sites** und wenn Sie dieses Fragment von der primären Seite aus ändern, sehen Sie die Änderungen in Ihrem Kanal. Sie können auch das Ziel anzeigen, in dem Sie das Experience Fragment verwendet haben.

>[!NOTE]
>
>Weitere Informationen zur Live Copy finden Sie unter Wiederverwenden von Inhalten: Multisite-Manager und Live Copy .

Gehen Sie wie folgt vor, um Änderungen vom primären Kanal auf den Zielkanal zu übertragen:

1. Klicken Sie auf das Experience Fragment aus der **Sites** (primäre Seite) und klicken Sie auf das Stiftsymbol, damit Sie die Elemente im Experience Fragment bearbeiten können.

   ![screen_shot_2018-06-08at122655pm](assets/screen_shot_2018-06-08at122655pm.png)

1. Klicken Sie auf das Experience Fragment und dann auf das Schraubenschlüsselsymbol, um das Dialogfeld zum Bearbeiten der Bilder zu öffnen.

   ![screen_shot_2018-06-08at25031pm](assets/screen_shot_2018-06-08at25031pm.png)

1. Das Dialogfeld **Produktraster** wird geöffnet.

   ![screen_shot_2018-06-08at25306pm](assets/screen_shot_2018-06-08at25306pm.png)

1. Sie können alle Bilder bearbeiten. Hier wird beispielsweise das erste Bild in diesem Fragment ersetzt.

   ![screen_shot_2018-06-08at25608pm](assets/screen_shot_2018-06-08at25608pm.png)

1. Klicken Sie auf das Experience Fragment und dann auf das Rollout -Symbol, damit Sie Änderungen an dem Fragment übertragen können, das in Ihrem Kanal verwendet wird.

   ![screen_shot_2018-06-08at31352pm](assets/screen_shot_2018-06-08at31352pm.png)

1. Klicken Sie auf Rollout.

   Beachten Sie, dass die Änderungen eingeführt werden.

   ![screen_shot_2018-06-08at32148pm](assets/screen_shot_2018-06-08at32148pm.png)

### Validieren der Änderungen {#validating-the-changes}

Gehen Sie wie folgt vor, um die Änderungen in Ihrem Kanal zu bestätigen:

1. Navigieren Sie zum **Screens** > **Kanäle** > **TestChannel**.

1. Klicks **Vorschau** in der Aktionsleiste aus.

Die folgende Abbildung zeigt die Änderungen in Ihrem **TestChannel**:\
![screen_shot_2018-06-08at33351pm](assets/screen_shot_2018-06-08at33351pm.png)
