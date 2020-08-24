---
title: Zuweisung von Kanälen - neueste RP
seo-title: Zuweisung von Kanälen - neueste RP
description: Folgen Sie dieser Seite, um mehr über die Zuweisung von Kanälen und die Tagesaufteilung zu erfahren.
translation-type: tm+mt
source-git-commit: 963262bb4b7b26aa1e9fbf1be2362c7029818789
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 79%

---


# Kanalzuweisung {#channel-assignment}

>[!IMPORTANT]
>In diesem Abschnitt werden die Zuweisung und Planung von Kanälen für Kanal AEM 6.5.5 Screens Feature Pack und höher erläutert.

Nachdem Sie eine Anzeige eingerichtet haben, müssen Sie einem Display einen Kanal zuweisen, um den Inhalt Ansicht.

Diese Seite zeigt, wie Sie Ihrem Display einen Kanal zuweisen.

>[!NOTE]
>Sie können einer Anzeige mehrere Kanal zuweisen.

## Zuweisen von Kanälen {#assign-a-channel-new-release}

Gehen Sie wie folgt vor, um einer Anzeige einen Kanal zuzuweisen:

1. Navigieren Sie zur gewünschten Anzeige, z. B. **DemoProject** > **Standorte** > **SanJose** > **StoreDisplay**.


1. Tap/click **Assign Channel** from the action bar

   Oder

   Tap/click **Dashboard** and click **+Assign Channel** from the **ASSIGNED CHANNNELS &amp; SCHEDULES** panel to open the **Channel Assignment** dialog box.

1. Wählen Sie unter &quot;Einstellung&quot;den Kanal nach Pfad oder Namen aus, geben Sie die Rolle &quot;Kanal&quot;, &quot;Priorität&quot;und &quot;Unterstützte Ereignis&quot;ein.

   >[!NOTE]
   >Weitere Informationen zu den Eigenschaften von Kanälen finden Sie im Abschnitt [Kanal-Eigenschaften](#channel-properties) .

1. Wählen Sie unter **Zeitpläne** die Option **Referenz-Zeitzone**, **Aktivierung-Fenster** und **Zeitplan** für Wiederholungen aus.

1. Klicken Sie auf **Speichern** , nachdem Sie Ihre Voreinstellungen konfiguriert haben.

## Verstehen der Kanal-Eigenschaften bei Kanalzuweisung {#channel-properties}

### Kanal referenzieren {#ref-channel}

Diese Option ermöglicht es Ihnen, einen Verweis zum gewünschten Kanal bereitzustellen, entweder in Form des Namens oder des Pfads des Kanals.

* **nach Pfad**: Sie stellen einen expliziten Verweis durch Angabe des absoluten Pfads des Kanals bereit.

* **nach Name**: Sie geben den Namen des Kanals ein, der entsprechend dem Kontext zu einem tatsächlichen Kanal führt. Mit dieser Funktion können Sie eine lokale Version eines Kanals erstellen, um standortspezifischen Inhalt dynamisch aufzulösen. Beispiel: ein Kanal mit dem Namen *Tagesangebote*, bei dem der eigentliche Inhalt in zwei Städten zwar unterschiedlich ist, aber bei allen Anzeigen dieselbe Kanalrolle vorhanden ist.

### Kanalrolle {#role-channel}

In „Kanalrolle“ wird der Kontext der Anzeige definiert. Die Rolle kann durch verschiedene Aktionen festgelegt werden und ist unabhängig vom eigentlichen Kanal, der der Rolle entspricht.

### Priorität {#priority-channel}

Mit „Priorität“ können Zuweisungen geordnet werden, falls mehrere die Wiedergabekriterien erfüllen. Höhere Werte haben stets Vorrang vor niedrigeren Werten. Wenn es beispielsweise die beiden Kanäle A und B gibt und A eine Priorität von 1 und B eine Priorität von 2 hat, wird Kanal B angezeigt, da er eine höhere Priorität als A hat.

>[!NOTE]
>Die Priorität eines Kanals wird als Zahl (1 für Minimum) im Dialogfeld **Kanalzuweisung** festgelegt, wie oben angegeben. Darüber hinaus werden die zugewiesenen Kanäle nach absteigender Priorität sortiert.

### Unterstützte Ereignisse {#supported-events-channel}

* **Erster Ladevorgang**: Lädt den Kanal, wenn der Player gestartet wird. Dies kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden.
* **Bildschirm bei Untätigkeit**: Lädt, wenn der Bildschirm inaktiv ist. Dies kann in Kombination mit einem Zeitplan mehreren Kanälen zugewiesen werden.
* **Timer**: Muss eingestellt werden, wenn ein Zeitplan vorhanden ist
* **Benutzerinteraktion**: Der Player wechselt in den angegebenen Kanal, wenn in einem inaktiven Kanal auf dem Bildschirm (Touch) eine Benutzerinteraktion stattfindet, und wird geladen, wenn der Bildschirm berührt wird.

### Unterbrechungsmethode {#interruption-method-channel}

>[!IMPORTANT]
>
> Diese Option ist nur mit AEM 6.4 Feature Pack 8 oder AEM 6.5 Feature Pack 4 verfügbar.

Als Autor von Inhalten sollten Sie festlegen können, wann ein Kanal unterbrochen wird, damit nicht kritische Inhalte abgeschnitten werden können, wichtige Inhalte jedoch vollständig abgespielt werden, bevor die Wiedergabe aufgrund der Zeitplanung abgebrochen wird.

Wählen Sie eine der folgenden Optionen aus, die zum Festlegen der Unterbrechungsmethode im Dialogfeld **Kanalzuweisung** verfügbar sind:

* **Sofort**: Wenn der Zeitplan aktiviert oder eine Aktualisierung empfangen wird, können Sie die Wiedergabe abbrechen und den neuen Inhalt sofort aktualisieren oder wiedergeben.
* **Am Ende des aktuellen Elements**: Wenn ein neuer Zeitplan aktiviert wird oder eine Aktualisierung empfangen wird, haben Sie die Möglichkeit zu warten, bis die Wiedergabe des aktuellen Elements in der Sequenz abgeschlossen ist. Danach aktualisieren Sie den neuen Inhalt und geben ihn wieder.
   >[!NOTE]
   >Standardmäßig ist diese Option aktiviert.
* **Am Ende der Sequenz**: Wenn ein neuer Zeitplan aktiviert oder eine Aktualisierung empfangen wird, haben Sie die Möglichkeit zu warten, bis die gesamte Sequenz ihr Ende erreicht. Kurz vor der gewünschten Sequenz kehren Sie zurück zum ersten Element, aktualisieren den neuen Inhalt oder spielen diesen ab.

   >[!NOTE]
   >Die Verwendung der zweiten oder dritten Option kann dazu führen, dass die für die Zuweisung festgelegten Zeiträume geringfügig verschoben werden, da der Player vor dem Aktualisieren auf das Ende des Elements oder der Sequenz (nach der angegebenen Zeit) wartet. Die Verzögerung hängt von der Wiedergabedauer des Elements ab.