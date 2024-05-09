---
title: Erstellen und Verwalten von Anzeigen
description: Erfahren Sie mehr über das Erstellen einer Anzeige- und Gerätekonfiguration in AEM Screens. Erfahren Sie auch mehr über das Anzeigen-Dashboard.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: c55dc128-208d-4379-95a8-60a39d495dc0
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 27%

---

# Erstellen und Verwalten von Anzeigen {#creating-and-managing-displays}

Eine Anzeige ist eine virtuelle Gruppierung von Bildschirmen, die nebeneinander angeordnet sind. Die Anzeige ist in Bezug auf eine Anlage dauerhaft. Es ist das Objekt, mit dem Inhaltsautoren arbeiten und immer als logische Darstellung und nicht als physische Gegenteile referenzieren.

Wenn Sie einen Standort erstellen, müssen Sie eine Anzeige für Ihren Standort erstellen.

Auf dieser Seite wird beschrieben, wie Anzeigen für Screens erstellt und verwaltet werden.

**Voraussetzungen**:

* [Konfigurieren und Bereitstellen von Screens](configuring-screens-introduction.md)
* [Erstellen und Verwalten von Screens-Projekten](creating-a-screens-project.md)
* [Erstellen und Verwalten von Kanälen](managing-channels.md)
* [Erstellen und Verwalten von Standorten](managing-locations.md)

## Erstellen einer neuen Anzeige {#creating-a-new-display}

>[!NOTE]
>
>Erstellen Sie einen Ort, bevor Sie eine Anzeige erstellen. Siehe [Erstellen und Verwalten von Standorten](managing-locations.md) für weitere Informationen.

1. Navigieren Sie zum entsprechenden Standort, z. B. `http://localhost:4502/screens.html/content/screens/TestProject`.
1. Klicken Sie auf Ihren Standortordner und klicken Sie auf **Erstellen** neben dem Pluszeichen in der Aktionsleiste.
1. Klicks **Anzeige** aus dem **Erstellen** Assistent, klicken Sie auf **Nächste**.
1. Geben Sie Ihre **Name** und **Titel** für Ihren Anzeigeort.
1. Wählen Sie auf der Registerkarte **Anzeige** die Details für das Layout aus. Wählen Sie die gewünschte **Auflösung**, beispielsweise **Full HD**. Wählen Sie die Anzahl der Geräte horizontal und vertikal aus.
1. Klicken Sie auf **Erstellen**.

Die Anzeige (*StoreDisplay*) wird erstellt und dem Standort (*SanJose*) hinzugefügt.

![display](assets/display.gif)

Wenn Sie eine Anzeige an einer Position haben, besteht der nächste Schritt darin, eine Gerätekonfiguration für diese bestimmte Anzeige zu erstellen.

>[!NOTE]
>
>**Der nächste Schritt**:
>
>Wenn Sie eine Anzeige für Ihren Standort erstellen, weisen Sie Ihrer Anzeige einen Kanal zu, um den Inhalt zu verwenden.
>
>Siehe [Zuweisen von Kanälen](channel-assignment.md) -Abschnitt, um zu erfahren, wie Sie der Anzeige einen Kanal zuweisen.

## Erstellen einer neuen Gerätekonfiguration {#creating-a-new-device-config}

Eine Gerätekonfiguration fungiert als Platzhalter für ein Digital-Signage-Gerät, das noch nicht installiert ist.

1. Navigieren Sie zur entsprechenden Anzeige, z. B. `http://localhost:4502/screens.html/content/screens/TestProject/locations/newlocation`.
1. Klicken Sie auf den Anzeigeordner und klicken Sie auf **Dashboard anzeigen** in der Aktionsleiste.
1. Klicks **+ Gerätekonfiguration hinzufügen** oben rechts im **Geräte** Bedienfeld.

1. Klicken Sie auf **Gerätekonfiguration** als erforderliche Vorlage verwenden und auf **Nächste**.

1. Geben Sie die Eigenschaften nach Bedarf ein und klicken Sie auf **Erstellen**.

Die Gerätekonfiguration wird erstellt und der aktuellen Anzeige hinzugefügt. (In der folgenden Demonstration ist *DeviceConfig* die neue Gerätekonfiguration.)

![deviceconfig](assets/deviceconfig.gif)

>[!NOTE]
>
>Wenn eine Gerätekonfiguration für Ihre Anzeige am Standort festgelegt ist, besteht der nächste Schritt darin, Ihrer Anzeige einen Kanal zuzuweisen.
>
>Wie in der folgenden Abbildung gezeigt, wenn die Gerätekonfiguration in der **Geräte** -Bedienfeld, wenn dieser Gerätekonfiguration kein Kanal zugewiesen ist.
>
>Sie sollten über Vorkenntnisse im Erstellen und Verwalten von Kanälen verfügen. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Kanälen](managing-channels.md).

![chlimage_1-9](assets/chlimage_1-9.png)

## Anzeigen-Dashboard {#display-dashboard}

Das Anzeigen-Dashboard bietet verschiedene Bedienfelder für die Verwaltung von Anzeigegeräten. Außerdem können Sie damit Ihr Gerät konfigurieren.

![screen_shot_2018-08-23at42810pm](assets/screen_shot_2018-08-23at42810pm.png)

>[!NOTE]
>
>Sie können auf die Dashboard-Listen und Trigger-Massenaktionen für Elemente klicken, anstatt jedes Element einzeln zu durchlaufen.
>
>Die folgende Abbildung zeigt beispielsweise, wie Sie im Anzeigen-Dashboard auf mehrere Kanäle klicken können.

![cqdoc9456](assets/cqdoc9456.gif)

### Bedienfeld „Anzeigeinformationen“ {#display-information-panel}

Im Bedienfeld **ANZEIGEINFORMATIONEN** werden die Anzeigeeigenschaften angezeigt.

Klicken Sie auf (**...**) oben rechts in der **ANZEIGEINFORMATIONEN** -Bedienfeld, damit Sie die Eigenschaften anzeigen und eine Vorschau der Anzeige anzeigen können.


#### Anzeigen von Eigenschaften {#viewing-properties}

Klicks **Eigenschaften** sodass Sie die Eigenschaften Ihrer Anzeige anzeigen oder ändern können.

Außerdem können Sie den Ereignis-Timer-Wert für Ihren interaktiven Kanal im **Anzeige** Registerkarte. Der Standardwert ist auf *300 Sekunden* eingestellt.

Verwendung **CRXDE Lite**, um auf die **idleTimeout** -Eigenschaft, also `http://localhost:4502/crx/de/index.jsp#/content/screens/we-retail/locations/demo/flagship/single/jcr%3Acontent/channels`.


### Bedienfeld „Zugewiesene Kanäle“ {#assigned-channels-panel}

Das Bedienfeld **ZUGEWIESENE KANÄLE** zeigt die zugewiesenen Kanäle des Geräts an.


### Bedienfeld „Geräte“ {#devices-panel}

Die **Geräte** Bedienfeld enthält Informationen zu den Gerätekonfigurationen.

Klicken Sie auf (**...**) oben rechts in der **Geräte** -Bedienfeld, damit Sie Gerätekonfigurationen hinzufügen und Geräte aktualisieren können.

Klicken Sie außerdem auf die Gerätekonfiguration, um Eigenschaften anzuzeigen, ein Gerät zuzuweisen oder es vollständig zu löschen.

![chlimage_1-13](assets/chlimage_1-13.png)

#### Die nächsten Schritte {#the-next-steps}

Wenn Sie die Erstellung einer Anzeige für Ihren Standort abgeschlossen haben, weisen Sie Ihrer Anzeige einen Kanal zu.

Weitere Informationen finden Sie unter [Zuweisen von Kanälen](channel-assignment.md).
