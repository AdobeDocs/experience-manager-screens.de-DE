---
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 69%

---
# Richtlinien für Beiträge zur Adobe Experience Manager-Dokumentation

## Dokumentationsphilosophie

Adobe Experience Manager-Benutzende arbeiten in extrem wettbewerbsorientierten Umgebungen, um digitale Erlebnisse zu erstellen, die sie von ihren Wettbewerbern abheben. Wenn Adobe erweiterte Tools in AEM bereitstellt, werden diese durch eine genaue und klare Dokumentation ergänzt. Dadurch können Kunden ihre AEM sofort nutzen und ihre Rendite maximieren.

Das Ziel der AEM-Dokumentation besteht darin, AEM-Benutzende schnellstmöglich mit der Dokumentation vertraut zu machen. Daher priorisiert Adobe die genaue, nutzbare Dokumentation und bemüht sich, sie kontinuierlich zu aktualisieren und zu verbessern.

## Beiträge zur Dokumentation

Zur stetigen Verbesserung der AEM-Dokumentation ist die gesamte Community von AEM-Benutzern herzlich eingeladen, zur Dokumentation beizutragen. Sei es durch Pull-Anfragen oder Tickets, bei den Verbesserungen der Dokumentation kann es sich um Korrekturen, Klarstellungen, Erweiterungen und weitere Beispiele handeln.

## Dokumentationsstandards

Während Adobe Beiträge zu seiner Dokumentation begrüßt, sollte jeder Beitrag zur AEM Dokumentation in einer Pull-Anfrage oder einem Problem mit Adobe-Beitrags- und Dokumentationsstandards übereinstimmen.

Beiträge, die diesen Standards nicht entsprechen, können abgelehnt werden.

### Standardanwendungsfälle werden unter Adobe dokumentiert.

Die AEM-Dokumentation umfasst Standard-Anwendungsfälle. Anwendungsfälle, die über den Umfang der standardmäßigen Installation und Nutzung des Produkts hinausgehen, sind nicht Teil der AEM-Dokumentation.

### Adobe dokumentiert in der Regel keine Fehler oder deren Umgehungsmöglichkeiten.

Die AEM-Dokumentation umfasst Standard-Anwendungsfälle. Aus diesem Grund werden Fehler, durch Fehler verursachte Effekte und Problemumgehungen für Fehler nicht dokumentiert.

Ausnahmen gelten für die Versionshinweise, in denen bekannte Probleme mit möglichen Lösungen aufgelistet werden können, die vom Produktmanagement genehmigt wurden.

### Dokumentationsbeiträge sind nicht zur Beantwortung technischer Fragen gedacht.

Alle Vorschläge, die Sie zur Verbesserung der AEM-Dokumentation haben, sind als Beiträge willkommen. Kommentare, Tickets und Pull-Anfragen sind jedoch nur für *Beiträge* vorgesehen. Sie dienen nicht zur Beantwortung Ihrer Fragen zur Verwendung von AEM, zur Implementierung Ihres AEM-Projekts oder zur Lösung technischer Probleme.

Sie können alle Fragen zur AEM oder zu technischen Fehlern melden. Verwenden Sie den normalen Support-Prozess über die [Experience Cloud Enterprise Support-Portal](https://experienceleague.adobe.com/de?support-solution=General#support) oder in der [Experience Manager-Community](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/ct-p/adobe-experience-manager-community?lang=de).

***AEM-Dokumentationsbeiträge sind kein Ersatz für die Adobe-Kundenunterstützung*** und Beiträge, die Antworten auf Support-bezogene Fragen suchen, werden abgelehnt.

### Die Beiträge müssen sich eindeutig auf die betroffenen Dokumentationsseiten beziehen.

Wenn Sie ein Problem erstellen, um Verbesserungen an der Dokumentation vorzuschlagen, müssen Sie Links zu den betroffenen Seiten angeben. Wenn Sie ein Problem erstellen, indem Sie den Link **Bearbeiten dieser Seite** auf einer Dokumentationsseite verwenden, wird das Problem automatisch mit einem Link zu dieser Seite erstellt.

Dieser Prozess gilt nicht für Pull-Anforderungen, da Pull-Anforderungen naturgemäß auf die betroffenen Seiten verweisen.

## Dokumentationsrichtlinien

Adobe bittet darum, dass alle Beiträge zur Dokumentation bestimmten Stilrichtlinien folgen.

Indem Sie diese Richtlinien befolgen, erleichtern Sie die Überprüfung Ihres Beitrags und beschleunigen somit dessen Aufnahme in die Adobe-Dokumentation.

### Sprache und Stil

#### Sprache

* Die AEM-Dokumentation wird in englischer Sprache verfasst und verwaltet.
* Ausdrücke sollten so einfach wie möglich sein.
* Drücken Sie sich klar und bündig aus.

Denken Sie daran, dass die Leserschaft der AEM-Dokumentation international ist und nicht erwartet werden kann, dass alle fließend Englisch beherrschen oder Muttersprachler sind. Vermeiden Sie umgangssprachliche Wendungen und verwenden Sie eine klare und einfache Sprache wie möglich.

#### Befolgen Sie das Microsoft® Manual of Style

Das [Manual of Style von Microsoft®](https://learn.microsoft.com/de-de/style-guide/welcome/) ist ein kostenloses Dokumentationshandbuch, das sich auf Software-Dokumentation konzentriert. Die AEM-Dokumentation folgt diesem Handbuch, soweit möglich.

### Formatierung

| Element | Stil |
|---|---|
| Element oder Option der Benutzeroberfläche | **fett** |
| Dateiname, Pfad, Benutzereingabe, Parameterwerte | `monospaced` |
| Code, Befehlszeile | ```Code Block``` |

### Screenshots

Screenshots sind mit Bedacht und nur dann zu verwenden, wenn eine Textbeschreibung nicht ausreicht.

Markierungen oder andere Anmerkungen in Screenshots (wie rote Rahmen, Pfeile oder Text) sollten nicht verwendet werden. Auf diese Weise können die Screenshots in lokalisierten Versionen der Dokumentation einfacher wiederverwendet oder repliziert werden.

### Versionsspezifische Verweise

Versuchen Sie nach Möglichkeit direkte Verweise auf eine bestimmte Version im gesamten Dokumentationsinhalt zu vermeiden. Diese Empfehlung macht die Dokumentation flexibler und erweiterbarer für zukünftige Versionen.

### Verwendung von Day, AEM, CQ, CRX

Verweisen Sie in einem Artikel immer auf das Produkt mit seinem vollständigen Namen. **Adobe Experience Manager** bei der ersten Verwendung. Danach kann sie als **AEM**.

Day, Day-Software, CQ und CRX sollten nur verwendet werden, wenn dies unvermeidlich ist, z. B. in Klassennamen oder bei Verweisen auf die AEM-Historie.