---
title: Entwickeln einer benutzerdefinierten Komponente für AEM Screens
seo-title: Entwickeln einer benutzerdefinierten Komponente für AEM Screens
description: Das folgende Tutorial führt Sie durch die Schritte zum Erstellen einer benutzerdefinierten Komponente für AEM Screens. AEM Screens verwendet viele vorhandene Design-Muster und Technologien anderer AEM-Produkte. Das Tutorial hebt Unterschiede und besondere Überlegungen bei der Entwicklung für AEM Screens hervor.
seo-description: Ein einführendes Tutorial zum Erstellen einer einfachen Komponente „Hello World“ für AEM Screens. AEM Screens verwendet viele vorhandene Design-Muster und Technologien anderer AEM-Produkte. Im folgenden Tutorial werden die spezifischen Unterschiede und Überlegungen bei der Entwicklung für AEM Screens hervorgehoben.
uuid: 8ec8be5a-6348-48f2-9cb7-75b2bad555a6
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
discoiquuid: 24eb937f-ab51-4883-8236-8ebe6243f6e3
targetaudience: target-audience new
feature: Entwicklung in Screens
role: Developer
level: Intermediate
exl-id: d14f8c55-dc09-4ac9-8d75-bafffa82ccc0
source-git-commit: 60a6583dd3bf79ef09099506107705bf0bce1e07
workflow-type: tm+mt
source-wordcount: '2188'
ht-degree: 100%

---

# Entwickeln einer benutzerdefinierten Komponente für AEM Screens {#developing-a-custom-component-for-aem-screens}

Das folgende Tutorial führt Sie durch die Schritte zum Erstellen einer benutzerdefinierten Komponente für AEM Screens. AEM Screens verwendet viele vorhandene Design-Muster und Technologien anderer AEM-Produkte. Das Tutorial hebt Unterschiede und besondere Überlegungen bei der Entwicklung für AEM Screens hervor.

## Überblick {#overview}

Dieses Tutorial richtet sich an Entwickler, die neu bei AEM Screens sind. In diesem Tutorial wird eine einfache Komponente „Hello World“ für einen Sequenzkanal in AEM Screens erstellt. Über ein Dialogfeld können Autoren den angezeigten Text aktualisieren.

![overviewhellow](assets/overviewhellow.png)

## Voraussetzungen {#prerequisites}

Um dieses Tutorial abzuschließen, benötigen Sie Folgendes:

1. [AEM 6.5](https://helpx.adobe.com/de/experience-manager/6-4/release-notes.html) oder [AEM 6.3](https://helpx.adobe.com/de/experience-manager/6-3/release-notes.html) + neuestes Screen Feature Pack

1. [AEM Screens-Player](https://helpx.adobe.com/de/experience-manager/6-4/sites/deploying/using/configuring-screens-introduction.html)
1. Lokale Entwicklungsumgebung

Für die Tutorial-Schritte und Screenshots wird **CRXDE-Lite** genutzt. IDEs können auch zum Abschluss des Tutorials verwendet werden. Weitere Informationen zur Verwendung einer IDE zur Entwicklung mit AEM [finden Sie hier](https://helpx.adobe.com/de/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part1.html#eclipse-ide).


## Projekt-Setup {#project-setup}

Der Quell-Code eines Screens-Projekts wird normalerweise als Maven-Projekt mit mehreren Modulen verwaltet. Um das Tutorial zu beschleunigen, wurde ein Projekt mithilfe des [AEM-Projektarchetyps 13](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype) vorgeneriert. Weitere Informationen zum [Erstellen eines Projekts mit einem Maven-Archetyp für AEM-Projekte finden Sie hier](https://helpx.adobe.com/de/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part1.html#maven-multimodule).

1. Laden Sie die folgenden Pakete mit [CRX Package Manager](http://localhost:4502/crx/packmgr/index.jsp) herunter und installieren Sie sie:

[Datei laden](assets/base-screens-weretail-runuiapps-001-snapshot.zip)

   [Datei laden](assets/base-screens-weretail-runuicontent-001-snapshot.zip)
   Wenn Sie mit Eclipse oder einer anderen IDE arbeiten, laden Sie **optional** das folgende Quellpaket herunter. Stellen Sie das Projekt mithilfe des folgenden Maven-Befehls in einer lokalen AEM-Instanz bereit:

   **`mvn -PautoInstallPackage clean install`**

   Starten von HelloWorld SRC Screens im Projekt „We.Retail Run“

[Datei laden](assets/src-screens-weretail-run.zip)

1. Überprüfen Sie in [CRX Package Manager](http://localhost:4502/crx/packmgr/index.jsp), ob die folgenden beiden Pakete installiert sind:

   1. **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip**
   1. **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip**

   ![Pakete Ui.Apps und Ui.Content für das Screens-Projekt „We.Retail Run“ über CRX Package Manager installiert](assets/crx-packages.png)

   Pakete Ui.Apps und Ui.Content für das Screens-Projekt „We.Retail Run“ über CRX Package Manager installiert

1. Das Paket **screens-weretail-run.ui.apps** installiert Code unter `/apps/weretail-run`.

   Dieses Paket enthält den Code, der für das Rendern von benutzerdefinierten Komponenten für das Projekt verantwortlich ist. Dieses Paket enthält Komponenten-Code und alle erforderlichen JavaScript- oder CSS-Funktionen. Dieses Paket beinhaltet auch **screens-weretail-run.core-0.0.1-SNAPSHOT.jar**, die den Java-Code enthält, der für das Projekt benötigt wird.

   >[!NOTE]
   >
   >In diesem Tutorial wird kein Java-Code geschrieben. Wenn eine komplexere Geschäftslogik erforderlich ist, kann Backend-Java mit dem Core Java-Bundle erstellt und bereitgestellt werden.

   ![Darstellung des ui.apps-Codes in CRXDE Lite](assets/uipps-contents.png)

   Darstellung des ui.apps-Codes in CRXDE Lite

   Die Komponente **helloworld** ist derzeit nur ein Platzhalter. Im Laufe des Tutorials werden Funktionen hinzugefügt, die es einem Autor ermöglichen, die von der Komponente angezeigte Nachricht zu aktualisieren.

1. Das Paket **screens-weretail-run.ui.content** installiert den folgenden Code:

   * `/conf/we-retail-run`
   * `/content/dam/we-retail-run`
   * `/content/screens/we-retail-run`

   Dieses Paket enthält den für das Projekt benötigten Startinhalt und die für das Projekt erforderliche Konfigurationsstruktur. **`/conf/we-retail-run`** enthält alle Konfigurationen für das Projekt „We.Retail Run“. **`/content/dam/we-retail-run`** umfasst das Starten digitaler Assets für das Projekt. **`/content/screens/we-retail-run`** enthält die Screens-Inhaltsstruktur. Der Inhalt unter allen diesen Pfaden wird hauptsächlich in AEM aktualisiert. Um die Konsistenz zwischen Umgebungen (Lokal, Entwicklung, Test und Produktion) zu fördern, wird häufig eine grundlegende Inhaltsstruktur in der Quell-Code-Verwaltung gespeichert.

1. **Navigieren Sie zum Projekt „AEM Screens“ > „We.Retail Run“:**

   Klicken Sie im AEM-Startmenü auf das Screens-Symbol. Überprüfen Sie, ob das Projekt „We.Retail Run“ zu sehen ist.

   ![we-retaiul-run-starter](assets/we-retaiul-run-starter.png)

## Erstellen der Komponente „Hello World“ {#hello-world-cmp}

Die Komponente „Hello World“ ist eine einfache Komponente, mit der ein Benutzer eine Nachricht eingeben kann, die auf dem Bildschirm angezeigt werden soll. Die Komponente basiert auf der [Komponentenvorlage für AEM Screens: https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template).

AEM Screens weist einige interessante Einschränkungen auf, die nicht unbedingt für herkömmliche Komponenten von WCM-Sites gelten.

* Die meisten Screens-Komponenten müssen im Vollbildmodus auf den Digital-Signage-Zielgeräten ausgeführt werden
* Die meisten Bildschirmkomponenten müssen in die Sequenzkanäle eingebettet werden, um Diashows zu erstellen
* Bei der Inhaltserstellung sollte es möglich sein, einzelne Komponenten in einem Sequenzkanal zu bearbeiten, sodass das Rendern im Vollbildmodus nicht in Frage kommt

1. Navigieren Sie in **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp` (oder der IDE Ihrer Wahl) zu `/apps/weretail-run/components/content/helloworld.`

   Fügen Sie der Komponente `helloworld` die folgenden Eigenschaften hinzu:

   ```
       jcr:title="Hello World"
       sling:resourceSuperType="foundation/components/parbase"
       componentGroup="We.Retail Run - Content"
   ```

   ![Eigenschaften für /apps/weretail-run/components/content/helloworld](assets/2018-04-28_at_4_23pm.png)

   Eigenschaften für /apps/weretail-run/components/content/helloworld

   Die Komponente **helloworld** erweitert die Komponente **foundation/components/parbase**, sodass sie innerhalb eines Sequenzkanals richtig verwendet werden kann.

1. Erstellen Sie unter `/apps/weretail-run/components/content/helloworld` eine Datei mit dem Namen `helloworld.html.`

   Füllen Sie die Datei mit folgendem Inhalt:

   ```xml
   <!--/*
   
    /apps/weretail-run/components/content/helloworld/helloworld.html
   
   */-->
   
   <!--/* production: preview authoring mode + unspecified mode (i.e. on publish) */-->
   <sly data-sly-test.production="${wcmmode.preview || wcmmode.disabled}" data-sly-include="production.html" />
   
   <!--/* edit: any other authoring mode, i.e. edit, design, scaffolding, etc. */-->
   <sly data-sly-test="${!production}" data-sly-include="edit.html" />
   ```

   Screens-Komponenten erfordern je nach verwendetem [Inhaltserstellungsmodus](https://helpx.adobe.com/de/experience-manager/6-4/sites/authoring/using/author-environment-tools.html#PageModes) zwei unterschiedliche Wiedergaben:

   1. **Produktion**: Vorschau- oder Veröffentlichungsmodus (wcmmode=disabled)
   1. **Bearbeiten**: für alle anderen Inhaltserstellungsmodi, d.h. Bearbeiten, Design, Strukturvorlage, Entwickler ...

   `helloworld.html` fungiert als Schalter, der überprüft, welcher Inhaltserstellungsmodus gerade aktiv ist, und zu einem anderen HTL-Skript umleitet. Eine gängige Konvention, die von Screens-Komponenten verwendet wird, besteht darin, ein `edit.html`-Skript für den Bearbeitungsmodus und ein `production.html`-Skript für den Produktionsmodus zu verwenden.

1. Erstellen Sie unter `/apps/weretail-run/components/content/helloworld` eine Datei mit dem Namen `production.html.`

   Füllen Sie die Datei mit folgendem Inhalt:

   ```xml
   <!--/*
    /apps/weretail-run/components/content/helloworld/production.html
   
   */-->
   
   <div data-duration="${properties.duration}" class="cmp-hello-world">
    <h1 class="cmp-hello-world__message">${properties.message}</h1>
   </div>
   ```

   Oben ist das Produktions-Markup für die Komponente „Hello World“. Ein Attribut `data-duration` ist enthalten, da die Komponente auf einem Sequenzkanal verwendet wird. Das Attribut `data-duration` wird vom Sequenzkanal verwendet, um zu erfahren, wie lange ein Sequenz-Element angezeigt werden soll.

   Die Komponente rendert ein `div`- und ein `h1`-Tag mit Text. `${properties.message}` ist ein Teil des HTL-Skripts, der den Inhalt einer JCR-Eigenschaft mit dem Namen `message` ausgibt. Später wird ein Dialogfeld erstellt, in dem der Benutzer einen Wert für den Eigenschaftstext `message` eingeben kann.

   Beachten Sie außerdem, dass die BEM-Notation (Block Element Modifier) mit der Komponente verwendet wird. BEM ist eine CSS-Kodierungskonvention, die die Erstellung wiederverwendbarer Komponenten erleichtert. BEM ist die von [AEM-Kernkomponenten](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/wiki/CSS-coding-conventions) verwendete Notation. Weitere Informationen finden Sie unter [https://getbem.com/](https://getbem.com/)

1. Erstellen Sie unter `/apps/weretail-run/components/content/helloworld` eine Datei mit dem Namen `edit.html.`

   Füllen Sie die Datei mit folgendem Inhalt:

   ```xml
   <!--/*
   
    /apps/weretail-run/components/content/helloworld/edit.html
   
   */-->
   
   <!--/* if message populated */-->
   <div
    data-sly-test.message="${properties.message}"
    class="aem-Screens-editWrapper cmp-hello-world">
    <p class="cmp-hello-world__message">${message}</p>
   </div>
   
   <!--/* empty place holder */-->
   <div data-sly-test="${!message}"
        class="aem-Screens-editWrapper cq-placeholder cmp-hello-world"
        data-emptytext="${'Hello World' @ i18n, locale=request.locale}">
   </div>
   ```

   Oben befindet sich das Bearbeitungs-Markup für die Komponente „Hello World“. Im ersten Block wird eine Bearbeitungsversion der Komponente angezeigt, wenn die Dialogfeldmeldung eingegeben wurde.

   Der zweite Block wird gerendert, wenn keine Dialogfeldmeldung eingegeben wurde. `cq-placeholder` und `data-emptytext` rendern die Beschriftung ***Hello World*** in diesem Fall als Platzhalter. Die Zeichenfolge für die Beschriftung kann mithilfe von i18n internationalisiert werden, um die Inhaltserstellung in mehreren Gebietsschemas zu unterstützen.

1. **Kopieren Sie das Screens-Bilddialogfeld, das für die Komponente „Hello World“ verwendet werden soll.**

   Es ist am einfachsten, von einem vorhandenen Dialogfeld aus zu starten und dann Änderungen vorzunehmen.

   1. Kopieren Sie das Dialgofeld aus `/libs/screens/core/components/content/image/cq:dialog`
   1. Fügen Sie das Dialogfeld hier ein: `/apps/weretail-run/components/content/helloworld`

   ![copy-image-dialog](assets/copy-image-dialog.gif)

1. **Aktualisieren Sie das Dialogfeld „Hello World“, um eine Registerkarte für die Meldung einzuschließen.**

   Aktualisieren Sie das Dialogfeld, sodass er mit Folgendem übereinstimmt: Die JCR-Knotenstruktur des finalen Dialogfelds wird nachfolgend in XML dargestellt:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0" xmlns:cq="https://www.day.com/jcr/cq/1.0" xmlns:jcr="https://www.jcp.org/jcr/1.0" xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
       jcr:primaryType="nt:unstructured"
       jcr:title="Hello World"
       sling:resourceType="cq/gui/components/authoring/dialog">
       <content
           jcr:primaryType="nt:unstructured"
           sling:resourceType="granite/ui/components/coral/foundation/tabs"
           size="L">
           <items jcr:primaryType="nt:unstructured">
               <message
                   jcr:primaryType="nt:unstructured"
                   jcr:title="Message"
                   sling:resourceType="granite/ui/components/coral/foundation/fixedcolumns">
                   <items jcr:primaryType="nt:unstructured">
                       <column
                           jcr:primaryType="nt:unstructured"
                           sling:resourceType="granite/ui/components/coral/foundation/container">
                           <items jcr:primaryType="nt:unstructured">
                               <message
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/textfield"
                                   fieldDescription="Message for component to display"
                                   fieldLabel="Message"
                                   name="./message"/>
                           </items>
                       </column>
                   </items>
               </message>
               <sequence
                   jcr:primaryType="nt:unstructured"
                   jcr:title="Sequence"
                   sling:resourceType="granite/ui/components/coral/foundation/fixedcolumns">
                   <items jcr:primaryType="nt:unstructured">
                       <column
                           jcr:primaryType="nt:unstructured"
                           sling:resourceType="granite/ui/components/coral/foundation/container">
                           <items jcr:primaryType="nt:unstructured">
                               <duration
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/numberfield"
                                   defaultValue=""
                                   fieldDescription="Amount of time the image will be shown in the sequence, in milliseconds"
                                   fieldLabel="Duration (ms)"
                                   min="0"
                                   name="./duration"/>
                           </items>
                       </column>
                   </items>
               </sequence>
           </items>
       </content>
   </jcr:root>
   ```

   Das Textfeld für die Meldung wird in einer Eigenschaft mit dem Namen `message` gespeichert und das numerische Feld für die Dauer wird in einer Eigenschaft mit dem Namen `duration` gespeichert. Diese beiden Eigenschaften werden in `/apps/weretail-run/components/content/helloworld/production.html` von HTL als `${properties.message}` und `${properties.duration}` referenziert.

   ![Hello World – fertiges Dialogfeld](assets/2018-04-29_at_5_21pm.png)

   Hello World – fertiges Dialogfeld

## Erstellen Client-seitiger Bibliotheken {#clientlibs}

Client-seitige Bibliotheken bieten einen Mechanismus zum Organisieren und Verwalten von CSS- und JavaScript-Dateien, die für eine AEM-Implementierung erforderlich sind.

AEM Screens-Komponenten werden im Bearbeitungsmodus anders als im Vorschaumodus/Produktionsmodus dargestellt. Es werden zwei Client-Bibliotheken erstellt, eine für den Bearbeitungsmodus und eine für die Vorschau/Produktion.

1. Erstellen Sie einen Ordner für Client-seitige Bibliotheken für die Komponente „Hello World“.

   Erstellen Sie unter `/apps/weretail-run/components/content/helloworld` einen neuen Ordner mit dem Namen `clientlibs`.

   ![2018-04-30_at_1046am](assets/2018-04-30_at_1046am.png)

1. Erstellen Sie unter dem Ordner `clientlibs` einen neuen Knoten `shared` des Typs `cq:ClientLibraryFolder.`

   ![2018-04-30_at_1115am](assets/2018-04-30_at_1115am.png)

1. Fügen Sie der freigegebenen Client-Bibliothek die folgenden Eigenschaften hinzu:

   * `allowProxy` | Boolesch | `true`

   * `categories`| Zeichenfolge[] | `cq.screens.components`

   ![Eigenschaften für /apps/weretail-run/components/content/helloworld/clientlibs/shared](assets/2018-05-03_at_1026pm.png)

   Eigenschaften für /apps/weretail-run/components/content/helloworld/clientlibs/shared

   Die Eigenschaft „categories“ ist eine Zeichenfolge, die die Client-Bibliothek identifiziert. Die Kategorie „cq.screens.components“ wird sowohl im Bearbeitungs- als auch im Vorschau-/Produktionsmodus verwendet. Daher wird jedes in sharedclientlib definierte CSS/JS in allen Modi geladen.

   Es empfiehlt sich, in einer Produktionsumgebung niemals Pfade direkt zu /apps bereitzustellen. Die allowProxy-Eigenschaft stellt sicher, dass auf die Pfade zu Client-Bibliotheks-CSS und -JS über ein Präfix „of/etc.clientlibs“ verwiesen wird.

1. Erstellen Sie eine Datei mit dem Namen `css.txt` unter dem freigegebenen Ordner.

   Füllen Sie die Datei mit folgendem Inhalt:

   ```
   #base=css
   
   styles.less
   ```

1. Erstellen Sie einen Ordner mit dem Namen `css` unter dem Ordner `shared`. Fügen Sie eine Datei mit dem Namen `style.less` unter dem Ordner `css` hinzu. Die Struktur der Client-Bibliotheken sollte jetzt wie folgt aussehen:

   ![2018-04-30_at_3_11pm](assets/2018-04-30_at_3_11pm.png)

   Anstatt CSS direkt zu schreiben, verwendet dieses Tutorial LESS. [LESS](https://lesscss.org/) ist ein beliebter CSS-Precompiler, der CSS-Variablen, Mixins und Funktionen unterstützt. AEM-Client-Bibliotheken unterstützen nativ die LESS-Kompilierung. Sass oder andere Precompiler können verwendet werden, müssen aber außerhalb von AEM kompiliert werden.

1. Füllen Sie `/apps/weretail-run/components/content/helloworld/clientlibs/shared/css/styles.less` wie folgt:

   ```css
   /**
       Shared Styles
      /apps/weretail-run/components/content/helloworld/clientlibs/shared/css/styles.less
   
   **/
   
   .cmp-hello-world {
       background-color: #fff;
   
    &__message {
     color: #000;
     font-family: Helvetica;
     text-align:center;
    }
   }
   ```

1. Kopieren Sie den Client-Bibliotheksordner `shared` und fügen Sie ihn ein, um eine neue Client-Bibliothek mit dem Namen `production` zu erstellen.

   ![Kopieren Sie die freigegebene Client-Bibliothek, um eine neue Produktions-Client-Bibliothek zu erstellen](assets/copy-clientlib.gif)

   Kopieren Sie die freigegebene Client-Bibliothek, um eine neue Produktions-Client-Bibliothek zu erstellen

1. Aktualisieren Sie die Eigenschaft `categories` der Produktions-Client-Bibliothek auf `cq.screens.components.production.`

   Dadurch wird sichergestellt, dass die Stile nur im Vorschau-/Produktionsmodus geladen werden.

   ![Eigenschaften für /apps/weretail-run/components/content/helloworld/clientlibs/production](assets/2018-04-30_at_5_04pm.png)

   Eigenschaften für /apps/weretail-run/components/content/helloworld/clientlibs/production

1. Füllen Sie `/apps/weretail-run/components/content/helloworld/clientlibs/production/css/styles.less` wie folgt:

   ```css
   /**
       Production Styles
      /apps/weretail-run/components/content/helloworld/clientlibs/production/css/styles.less
   
   **/
   .cmp-hello-world {
   
       height: 100%;
       width: 100%;
       position: fixed;
   
    &__message {
   
     position: relative;
     font-size: 5rem;
     top:25%;
    }
   }
   ```

   Die oben genannten Stile zeigen die Meldung zentriert in der Mitte des Bildschirms an, jedoch nur im Produktionsmodus.

Eine dritte clientlib-Kategorie: `cq.screens.components.edit` könnte zum Hinzufügen von nur bearbeitbaren spezifischen Stilen zur Komponente verwendet werden.

| Clientlib-Kategorie | Nutzung |
|---|---|
| `cq.screens.components` | Stile und Skripte, die sowohl im Bearbeitungs- als auch im Produktionsmodus verwendet werden |
| `cq.screens.components.edit` | Stile und Skripte, die nur im Bearbeitungsmodus verwendet werden |
| `cq.screens.components.production` | Stile und Skripte, die nur im Produktionsmodus verwendet werden |

## Erstellen einer Design-Seite {#design-page}

AEM Screens verwendet [statische Seitenvorlagen](https://helpx.adobe.com/de/experience-manager/6-5/sites/developing/using/page-templates-static.html) und [Design-Konfigurationen](https://helpx.adobe.com/de/experience-manager/6-4/sites/authoring/using/default-components-designmode.html) für globale Änderungen. Design-Konfigurationen werden häufig verwendet, um zulässige Komponenten für die Parsys auf einem Kanal zu konfigurieren. Eine bewährte Methode besteht darin, diese Konfigurationen anwendungsspezifisch zu speichern.

Unter „We.Retail Run“ wird eine Design-Seite erstellt, die alle für das Projekt „We.Retail Run“ spezifischen Konfigurationen speichert.

1. Navigieren Sie in **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs` zu `/apps/settings/wcm/designs`
1. Erstellen Sie unter dem Ordner „designs“ einen neuen Knoten mit dem Namen `we-retail-run` und dem Typ `cq:Page`.
1. Fügen Sie unter der Seite `we-retail-run` einen weiteren Knoten mit dem Namen `jcr:content` und dem Typ `nt:unstructured` hinzu. Fügen Sie dem Knoten `jcr:content` folgende Eigenschaften hinzu:

   | Name | Typ | Wert |
   |---|---|---|
   | jcr:title | Zeichenfolge | We.Retail Run |
   | sling:resourceType | Zeichenfolge | wcm/core/components/designer |
   | cq:doctype | Zeichenfolge | html_5 |

   ![Design-Seite unter /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1219pm.png)

   Design-Seite unter /apps/settings/wcm/designs/we-retail-run

## Erstellen eines Sequenzkanals {#create-sequence-channel}

Die Komponente „Hello World“ ist für die Verwendung in einem Sequenzkanal vorgesehen. Zum Testen der Komponente wird ein neuer Sequenzkanal erstellt.

1. Navigieren Sie im AEM-Startmenü zu **Screens** > **We.Retail Run** > und wählen Sie **Kanäle** aus.

1. Klicken Sie auf die Schaltfläche **Erstellen**

   1. Wahlen Sie **Entität erstellen** aus

   ![2018-04-30_at_5_18pm](assets/2018-04-30_at_5_18pm.png)

1. Im Assistenten „Erstellen“:

1. Vorlagenschritt – Wählen Sie **Sequenzkanal** aus

   1. Eigenschaftenschritt
   * Registerkarte „Einfach“ > „Titel“ = **Idle Channel**
   * Registerkarte „Kanal“ > aktivieren Sie **Online-Kanal erstellen**

   ![idle-channel](assets/idle-channel.gif)

1. Öffnen Sie die Seiteneigenschaften für den inaktiven Kanal (Idle Channel). Aktualisieren Sie das Feld „Design“, um auf `/apps/settings/wcm/designs/we-retail-run,` die im vorherigen Abschnitt erstellte Design-Seite zu verweisen.

   ![Design config /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1240pm.png)

   Design-Konfiguration mit Verweis auf /apps/settings/wcm/designs/we-retail-run

1. Bearbeiten Sie den neu inaktiven Kanal (Idle Channel), um ihn zu öffnen.

1. Schalten Sie den Seitenmodus in den Modus **Design** um

   1. Klicken Sie auf das **Schraubenschlüsselsymbol** in der Parsys, um die zulässigen Komponenten zu konfigurieren

   1. Wählen Sie die Gruppe **Screens** und die Gruppe **We.Retail Run - Inhalt** aus.

   ![2018-04-30_at_5_43pm](assets/2018-04-30_at_5_43pm.png)

1. Schalten Sie den Seitenmodus in **Bearbeiten** um. Die Komponente „Hello World“ kann jetzt der Seite hinzugefügt und mit anderen Komponenten des Sequenzkanals kombiniert werden.

   ![2018-04-30_at_5_53pm](assets/2018-04-30_at_5_53pm.png)

1. Navigieren Sie in **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs/we-retail-run/jcr%3Acontent/sequencechannel/par` zu `/apps/settings/wcm/designs/we-retail-run/jcr:content/sequencechannel/par`. Beachten Sie, dass die Eigenschaft `components` jetzt `group:Screens`, `group:We.Retail Run - Content` beinhaltet.

   ![Design-Konfiguration unter /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1_14pm.png)

   Design-Konfiguration unter /apps/settings/wcm/designs/we-retail-run

## Vorlage für benutzerdefinierte Handler {#custom-handlers}

Wenn Ihre benutzerdefinierte Komponente externe Ressourcen wie Assets (Bilder, Videos, Schriftarten, Symbole usw.), bestimmte Asset-Darstellungen oder Client-seitige Bibliotheken (css, js usw.) verwendet, werden diese nicht automatisch der Offline-Konfiguration hinzugefügt, da nur das HTML-Markup standardmäßig gebündelt wird.

Damit Sie genau die Assets, die auf den Player heruntergeladen werden, anpassen und optimieren können, wird ein Erweiterungsmechanismus für benutzerdefinierte Komponenten angeboten, um deren Abhängigkeiten von der Offline-Cache-Logik in Screens darzustellen.

Im folgenden Abschnitt werden die Vorlage für die benutzerdefinierten Offline-Ressourcen-Handler und die Mindestanforderungen in der Datei `pom.xml` für dieses spezifische Projekt vorgestellt.

```java
package …;

import javax.annotation.Nonnull;

import org.apache.felix.scr.annotations.Component;
import org.apache.felix.scr.annotations.Reference;
import org.apache.felix.scr.annotations.Service;
import org.apache.sling.api.resource.Resource;
import org.apache.sling.api.resource.ResourceUtil;
import org.apache.sling.api.resource.ValueMap;

import com.adobe.cq.screens.visitor.OfflineResourceHandler;

@Service(value = OfflineResourceHandler.class)
@Component(immediate = true)
public class MyCustomHandler extends AbstractResourceHandler {

 @Reference
 private …; // OSGi services injection

 /**
  * The resource types that are handled by the handler.
  * @return the handled resource types
  */
 @Nonnull
 @Override
 public String[] getSupportedResourceTypes() {
     return new String[] { … };
 }

 /**
  * Accept the provided resource, visit and traverse it as needed.
  * @param resource The resource to accept
  */
 @Override
 public void accept(@Nonnull Resource resource) {
     ValueMap properties = ResourceUtil.getValueMap(resource);
     
     /* You can directly add explicit paths for offline caching using the `visit`
        method of the visitor. */
     
     // retrieve a custom property from the component
     String myCustomRenditionUrl = properties.get("myCustomRenditionUrl", String.class);
     // adding that exact asset/rendition/path to the offline manifest
     this.visitor.visit(myCustomRenditionUrl);
     
     
     /* You can delegate handling for dependent resources so they are also added to
        the offline cache using the `accept` method of the visitor. */
     
     // retrieve a referenced dependent resource
     String referencedResourcePath = properties.get("myOtherResource", String.class);
     ResourceResolver resolver = resource.getResourceResolver();
     Resource referencedResource = resolver.getResource(referencedResourcePath);
     // let the handler for that resource handle it
     if (referencedResource != null) {
         this.visitor.accept(referencedResource);
     }
   }
}
```

Der folgende Code stellt die Mindestanforderungen in der Datei `pom.xml` für dieses spezifische Projekt bereit:

```css
   <dependencies>
        …
        <!-- Felix annotations -->
        <dependency>
            <groupId>org.apache.felix</groupId>
            <artifactId>org.apache.felix.scr.annotations</artifactId>
            <version>1.9.0</version>
            <scope>provided</scope>
        </dependency>

        <!-- Screens core bundle with OfflineResourceHandler/AbstractResourceHandler -->
        <dependency>
            <groupId>com.adobe.cq.screens</groupId>
            <artifactId>com.adobe.cq.screens</artifactId>
            <version>1.5.90</version>
            <scope>provided</scope>
        </dependency>
        …
      </dependencies>
```

## Alles zusammenbringen {#putting-it-all-together}

Das folgende Video zeigt die fertige Komponente und wie sie einem Sequenzkanal hinzugefügt werden kann. Der Kanal wird dann einer Standortsanzeige hinzugefügt und letztendlich einem Screens-Player zugewiesen.

>[!VIDEO](https://video.tv.adobe.com/v/22385?quaity=9)

## Fertiger Code {#finished-code}

Unten finden Sie den fertigen Code aus dem Tutorial. **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip** und **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip** sind kompilierte AEM-Pakete. SRC-screens-weretail-run-0.0.1.zip ist der nicht kompilierte Quell-Code, der mithilfe von Maven bereitgestellt werden kann.

[Datei laden](assets/screens-weretail-runuiapps-001-snapshot.zip)

[Datei laden](assets/screens-weretail-runuicontent-001-snapshot.zip)

[Datei laden](assets/screens-weretail-run.zip)
