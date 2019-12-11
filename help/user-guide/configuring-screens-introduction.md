---
title: Konfigurieren und Bereitstellen von AEM-Bildschirmen
seo-title: Konfigurieren und Bereitstellen von Screens
description: Der AEM Screens Player ist für Android, Chrome OS, iOS und Windows verfügbar. Diese Seite beschreibt die Konfiguration und Bereitstellung von AEM Screens und fasst die h/w-Auswahlrichtlinien für Player-Geräte zusammen.
seo-description: Der AEM Screens Player ist für Android, Chrome OS, iOS und Windows verfügbar. Diese Seite beschreibt die Konfiguration und Bereitstellung von AEM Screens und fasst die h/w-Auswahlrichtlinien für Player-Geräte zusammen.
uuid: bf730d0f-e590-4c0d-a554-e1ff914eb420
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 0c7d6248-8ac0-4387-8725-57ed941f28f7
docset: aem65
translation-type: tm+mt
source-git-commit: 323e2df2419cc65de7bfe88648ffd1dbd3a91aec

---


# Configuring and Deploying AEM Screens {#configuring-and-deploying-aem-screens}

Auf dieser Seite erfahren Sie, wie Sie AEM Screens Player auf Ihren Geräten installieren und konfigurieren.

## Serverkonfiguration {#server-configuration}

>[!NOTE]
>
>**Wichtig**:
>
>Der AEM Screens-Player verwendet kein Site-übergreifendes Anforderungsfälschungs-Token (CSRF-Token). Um einen AEM-Server für den Einsatz von AEM Screens zu konfigurieren, müssen Sie daher den Referrer-Filter überspringen, indem Sie leere Referrer zulassen.

### Voraussetzungen {#prerequisites}

Die folgenden wichtigen Punkte bieten Hilfestellung beim Konfigurieren von AEM-Servern für die Nutzung von AEM Screens:

#### Zulassen von leeren Referrer-Anforderungen {#allow-empty-referrer-requests}

1. Navigieren Sie zur **Adobe Experience Manager Web Console-Konfiguration** über AEM-Instanz —&gt; Hammer-Symbol —&gt; **Vorgänge** —&gt; **Web-Konsole**.

   ![screen_shot_2019-07-31at91253am](assets/screen_shot_2019-07-31at91253am.png)

1. **Adobe Experience Manager Web Console Configuration** wird geöffnet. Suchen Sie nach einer verweisenden Stelle.

   Zum Durchsuchen der Eigenschaft "sling referrer"drücken Sie **Befehl+F** für **Mac** und **Strg+F** für **Windows**.

   ![screen_shot_2019-07-31at91728am](assets/screen_shot_2019-07-31at91728am.png)

1. Markieren Sie die Option **Leeres Feld zulassen **wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2019-07-31at91807am](assets/screen_shot_2019-07-31at91807am.png)

1. Klicken Sie auf **Speichern** , um den Apache Sling Referrer-Filter Leer zulassen zu aktivieren.

#### Touch-Benutzeroberfläche für AEM-Bildschirme aktivieren {#enable-touch-ui-for-aem-screens}

AEM Screens erfordert die TOUCH-Benutzeroberfläche und funktioniert nicht mit der CLASSIC-Benutzeroberfläche von Adobe Experience Manager (AEM).

1. Navigieren Sie zu *&lt;yourAuthorInstance&gt;/system/console/configMgr/com.day.cq.wcm.core.impl.AuthoringUIModeServiceImpl*
1. Stellen Sie sicher, dass der **Standard-Authoring-UI-Modus** auf **TOUCH** eingestellt ist (siehe folgende Abbildung)

Alternativ können Sie die gleiche Einstellung auch mit *&lt;IhrAuthorInstance&gt;*-&gt;*Tools (Hammersymbol)* -&gt; **Vorgänge** -&gt; **Web-Konsole** durchführen und nach **WCM Authoring UI Mode Service** suchen.

![screen_shot_2018-12-04at22425pm](assets/screen_shot_2018-12-04at22425pm.png)

>[!NOTE]
>
>Sie können die klassische Benutzeroberfläche jederzeit mithilfe der Benutzereinstellungen für bestimmte Benutzer aktivieren.

#### AEM im NOSAMPLECONTENT-Ausführungsmodus {#aem-in-nosamplecontent-runmode}

Running AEM in production uses the **NOSAMPLECONTENT** runmode. *Entfernen Sie die Kopfzeile "X-Frame-Options=SAMEORIGIN* "(im Abschnitt "Zusätzliche Antwort-Kopfzeile") aus

`https://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet`.

Dies ist erforderlich, damit AEM Screens Player Online-Kanäle wiedergeben kann.

#### Kennworteinschränkungen {#password-restrictions}

Mit den neuesten Änderungen an ***DeviceServiceImpl*** müssen Sie die Kennwortbeschränkungen nicht entfernen.

Sie können ***DeviceServiceImpl*** über den unten stehenden Link konfigurieren, um beim Erstellen des Kennworts für die Bildschirmbenutzer die Kennwortbeschränkung zu aktivieren:

`https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService`

Gehen Sie wie folgt vor, um ***DeviceServiceImpl*** zu konfigurieren:

1. Navigieren Sie zur **Adobe Experience Manager Web Console-Konfiguration** über AEM-Instanz —&gt; Hammer-Symbol —&gt; **Vorgänge** —&gt; **Web-Konsole**.

1. **Adobe Experience Manager Web Console Configuration **wird geöffnet. Suchen Sie nach DeviceService. Drücken Sie zum Durchsuchen der Eigenschaft **Befehl+F** für **Mac** und **Strg+F** für **Windows**.

![screen_shot_2019-07-31at92058am](assets/screen_shot_2019-07-31at92058am.png)

#### Dispatcherkonfiguration {#dispatcher-configuration}

Weitere Informationen zum Konfigurieren des Dispatchers für ein AEM Screens-Projekt finden Sie unter [Konfigurieren von Dispatcher für ein AEM Screens-Projekt](dispatcher-configurations-aem-screens.md).

#### Java-Kodierung {#java-encoding}

Set the ***Java encoding*** to Unicode. *Dfile.encoding=Cp1252* funktioniert beispielsweise nicht.

>[!NOTE]
>
>**Empfehlung:**
>
>Für AEM Screens Server in Produktionsumgebungen wird HTTPS empfohlen.

