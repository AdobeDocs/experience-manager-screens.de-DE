---
title: Einbetten einer REACT-Anwendung mit dem AEM-SPA-Editor und Integrieren in AEM Screens Analytics
description: Erfahren Sie, wie Sie eine interaktive Single Page Application, die auf REACT (oder Angular) basiert, mit dem AEM-SPA-Editor einbetten.
content-type: reference
topic-tags: developing
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
discoiquuid: e4ecc179-e421-4687-854c-14d31bed031d
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 7dc7d07e-cd94-4ce1-a106-98669be62046
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: ht
source-wordcount: '674'
ht-degree: 100%

---

# Einbetten einer REACT-Anwendung mit dem AEM-SPA-Editor und Integrieren in AEM Screens Analytics {#embedding-a-react-application-using-the-aem-spa-editor-and-integrating-with-aem-screens-analytics}

Sie können eine interaktive Single Page Application einbetten, die auf REACT (oder Angular) basiert. Verwenden Sie dazu den AEM-SPA-Editor, der von Unternehmens-Fachleuten in AEM konfiguriert wird. Sie können auch lernen, wie Sie Ihre interaktive Anwendung in Adobe Analytics im Offline-Modus integrieren.

## Verwenden des AEM SPA Editors {#using-the-aem-spa-editor}

Gehen Sie wie folgt vor, um den AEM SPA Editor zu verwenden:

1. Klonen Sie die AEM SPA Editor-Repo unter [https://github.com/adobe/aem-spa-project-archetype.](https://github.com/adobe/aem-spa-project-archetype)

   >[!NOTE]
   >
   >Dieser Archetyp erstellt ein Adobe Experience Manager-Projekt mit minimalen Umfang als Ausgangspunkt für Ihre eigenen SPA-Projekte. Die Eigenschaften, die bei Verwendung dieses Archetyps angegeben werden müssen, ermöglichen es, alle Teile dieses Projekts beliebig zu benennen.

1. Folgen Sie den Readme-Anweisungen, um ein AEM-SPA-Editor-Archetypprojekt zu erstellen:

   ```
   mvn clean install archetype:update-local-catalog
   mvn archetype:crawl
   
   mvn archetype:generate \
   -DarchetypeCatalog=internal \
   -DarchetypeGroupId=com.adobe.cq.spa.archetypes \
   -DarchetypeArtifactId=aem-spa-project-archetype \
   -DarchetypeVersion=1.0.3-SNAPSHOT \
   ```

   >[!NOTE]
   >
   >In dieser Dokumentation wird als **GroupId** der Wert ***com.adobe.aem.screens*** und als **ArtifactId** der Wert ***Meine Beispiel-SPA*** (die Standardeinstellungen) verwendet. Sie können nach Bedarf Ihre eigenen Parameter auswählen.

1. Nachdem das Projekt erstellt wurde, verwenden Sie entweder eine IDE oder einen Editor Ihrer Wahl und importieren Sie das erstellte Maven-Projekt.
1. Stellen Sie es in Ihrer lokalen AEM-Instanz mit dem Befehl ***mvn clean install -PautoInstallPackage*** bereit.

### Bearbeiten von Inhalten in der REACT-App {#editing-content-in-the-react-app}

So bearbeiten Sie Inhalte in der REACT-App:

1. Navigieren Sie zu `https://localhost:4502/editor.html/content/mysamplespa/en/home.html` (ersetzen Sie ggf. den Host-Namen, Port und Projektnamen).
1. Seien Sie in der Lage, den Text zu bearbeiten, der in der Anwendung „Hello World“ angezeigt wird.

### Hinzufügen der interaktiven REACT-App zu AEM Screens {#adding-the-interactive-react-app-to-aem-screens}

Gehen Sie wie folgt vor, um die interaktive REACT-App zu AEM Screens hinzuzufügen:

1. Erstellen Sie ein AEM Screens-Projekt. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Projekten](creating-a-screens-project.md).
1. Erstellen Sie einen neuen **Anwendungskanal** (vorzugsweise, oder alternativ eine 1x1-Vorlage oder einen Mehrzonen-Kanal) im Ordner **Kanäle** Ihres AEM Screens-Projekts.

   >[!NOTE]
   >**Sequenzkanäle** werden für diesen Anwendungsfall nicht empfohlen, da sie von Natur aus mit einer Diashow-Logik ausgestattet sind, die mit der interaktiven Natur des Erlebnisses in Konflikt steht.
   >Weitere Informationen finden Sie unter [Erstellen und Verwalten von Kanälen](managing-channels.md).

1. Bearbeiten Sie einen beliebigen Sequenzkanal und ziehen Sie eine eingebettete Seitenkomponente per Drag-and-Drop.

   Weitere Informationen finden Sie unter [Hinzufügen von Komponenten zu Kanälen](adding-components-to-a-channel.md).

   >[!NOTE]
   >
   >Stellen Sie sicher, dass Sie beim Zuweisen des Kanals zur Anzeige das Benutzerinteraktionsereignis hinzufügen.

1. Klicken Sie in der Aktionsleiste auf **Bearbeiten**, um die Eigenschaften des Kanals zu bearbeiten.

   ![screen_shot_2019-02-15at100555am](assets/screen_shot_2019-02-15at100555am.png)

1. Ziehen Sie die Komponente **Eingebettete Seite** per Drag-and-Drop oder verwenden Sie die vorhandene Komponente erneut in einem Anwendungskanal. Klicken Sie dann auf die Startseite unter der Anwendung „mysamplespa“, z. B. ***/content/mysamplespa/en/home***.

   ![screen_shot_2019-02-15at101104am](assets/screen_shot_2019-02-15at101104am.png)

1. Weisen Sie den Kanal einer Anzeige zu.

   >[!NOTE]
   >Stellen Sie sicher, dass Sie beim Zuweisen des Kanals zur Anzeige das Benutzerinteraktionsereignis hinzufügen.

1. Registrieren Sie einen Player für dieses Projekt, und weisen Sie ihn der Anzeige zu. Sie können nun sehen, wie Ihre interaktive Anwendung in AEM Screens ausgeführt wird.

   Weitere Informationen zur Registrierung eines Geräts finden Sie unter [Geräteregistrierung](device-registration.md).

## Integrieren der SPA mit Adobe Analytics mit Offline-Funktionen über AEM Screens {#integrating-the-spa-with-adobe-analytics-with-offline-capability-through-aem-screens}

Gehen Sie wie folgt vor, um die SPA mit Adobe Analytics mit Offline-Funktionen über AEM Screens zu integrieren:

1. Konfigurieren Sie Adobe Analytics in AEM Screens.

   Weitere Informationen zum Ausführen der Sequenzierung in Adobe Analytics mit AEM Screens und zum Senden benutzerdefinierter Ereignisse mit Adobe Analytics im Offline-Modus finden Sie unter [Konfigurieren von Adobe Analytics mit AEM Screens](configuring-adobe-analytics-aem-screens.md).

1. Bearbeiten Sie Ihre React-App in der IDE oder dem Editor Ihrer Wahl (insbesondere die Textkomponente oder eine andere Komponente, die Sie zum Ausgeben von Ereignissen verwenden möchten).
1. Fügen Sie dem Klick-Ereignis oder einem anderen Ereignis, das Sie für Ihre Komponente erfassen möchten, die Analyseinformationen mithilfe des Standarddatenmodells hinzu.

   Weitere Informationen finden Sie unter [Konfigurieren von Adobe Analytics mit AEM Screens](configuring-adobe-analytics-aem-screens.md).

1. Rufen Sie die AEM Screens Analytics-API auf, um das Ereignis offline zu speichern und es in Bursts an Adobe Analytics zu senden.

   Zum Beispiel:

   ```
   handleClick() {
       if ((window.parent) && (window.parent.CQ) && (window.parent.CQ.screens) && (window.parent.CQ.screens.analytics))
       {
           var analyticsEvent = {};
           analyticsEvent['event.type'] = 'play'; // Type of event
    analyticsEvent['event.coll_dts'] = new Date().toISOString(); // Start of collecting the event
    analyticsEvent['event.dts_start'] = new Date().toISOString(); // Event start
    analyticsEvent['content.type'] = 'Washing machine'; // Mime Type or product category
    analyticsEvent['content.action'] = 'Path to the washing machine asset in AEM'; // Path in AEM to relevant asset
    analyticsEvent['trn.product'] = 'Washing machine Model number'; // Product being explored
    analyticsEvent['trn.amount'] = 1000; // Product pricing or other numeric value or weight
    analyticsEvent['event.dts_end'] = new Date().toISOString(); // Event end
    analyticsEvent['event.count'] = 100; // Numeric value that may count a number of clicks or keystrokes or wait time in seconds for example
    analyticsEvent['event.value'] = 'My favorite analytics event';
           analyticsEvent['trn.quantity'] = 10; // Quantity of product selection
    analyticsEvent['event.subtype'] = 'end'; // Event subtype if applicable
    window.parent.CQ.screens.analytics.sendTrackingEvent(analyticsEvent);
       }
   }
   ```

   >[!NOTE]
   >
   >Die Player-Firmware fügt den gesendeten benutzerspezifischen Analysedaten automatisch weitere Details zum Player und seiner Laufzeitumgebung hinzu. Daher müssen Sie ggf. Details zu Betriebssystemen und Geräten auf niedriger Ebene erfassen, sofern dies nicht erforderlich ist. Konzentrieren Sie sich auf die Geschäftsanalysedaten.
