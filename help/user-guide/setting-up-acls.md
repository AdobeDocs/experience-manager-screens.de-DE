---
title: Einrichten von ACLs
description: Erfahren Sie, wie Sie Projekte mithilfe von ACLs separieren können, sodass jede Person bzw. jedes Team ein eigenes Projekt erhält.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: b40bcc9f-307c-422c-8abb-5c15965772d4
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 96%

---

# Einrichten von ACLs {#setting-up-acls}

Im folgenden Abschnitt wird erläutert, wie Sie Projekte mithilfe von ACLs separieren können, sodass jede Person bzw. jedes Team ein eigenes Projekt erhält.

Als AEM-Admin möchten Sie sicherstellen, dass für ein bestimmtes Projekt zuständige Team-Mitglieder nicht in andere Projekte eingreifen und dass den Benutzenden je nach Projektanforderungen spezifische Rollen zugewiesen werden.

## Einrichten von Berechtigungen {#setting-up-permissions}

Die folgenden Schritte fassen die Vorgehensweise zum Einrichten von ACLs für ein Projekt zusammen:

1. Melden Sie sich bei AEM an und navigieren Sie zu **Tools** > **Sicherheit**.

   ![screen_shot_2018-02-16at10156pm](assets/screen_shot_2018-02-16at10156pm.png)

1. Klicken Sie auf **Gruppen** und geben Sie eine ID ein (zum Beispiel „Acme“).

   Alternativ können Sie diesen Link verwenden: `http://localhost:4502/libs/granite/security/content/groupadmin.html`.

   Klicken Sie anschließend auf **Speichern**.

   ![screen_shot_2018-02-16at12648pm](assets/screen_shot_2018-02-16at12648pm.png)

1. Klicks **Mitarbeiter** aus der Liste aus und doppelklicken Sie darauf.

   ![screen_shot_2018-02-18at33938pm](assets/screen_shot_2018-02-18at33938pm.png)

1. Fügen Sie **Acme** (das von Ihnen erstellte Projekt) zu **Mitglieder zu Gruppe hinzufügen** hinzu. Klicken Sie auf **Speichern**.

   ![screen_shot_2018-02-18at35630pm](assets/screen_shot_2018-02-18at35630pm.png)

   >[!NOTE]
   >
   >Wenn Sie möchten, dass Mitglieder aus Projekt-Teams Player registrieren (was die Erstellung eines Benutzers für jeden Player umfasst), suchen Sie nach der Gruppe „user-administrators“ und fügen Sie die ACME-Gruppe zu „user-administrators“ hinzu.

1. Fügen Sie alle Benutzenden, die am Projekt **Acme** arbeiten, zur Gruppe **Acme** hinzu.

   ![screen_shot_2018-02-18at41320pm](assets/screen_shot_2018-02-18at41320pm.png)

1. Richten Sie die Berechtigungen für die Gruppe **Acme** über `(http://localhost:4502/useradmin)` ein.

   Klicken Sie auf die Gruppe **Acme** und klicken Sie auf **Berechtigungen**.

   ![screen_shot_2018-02-18at41534pm](assets/screen_shot_2018-02-18at41534pm.png)

### Berechtigungen {#permissions}

Die folgende Tabelle fasst den Pfad mit den Berechtigungen auf Projektebene zusammen:

| **Pfad** | **Berechtigung** | **Beschreibung** |
|---|---|---|
| `/apps/<project>` | LESEN | Ermöglicht ggf. Zugriff auf Projektdateien |
| `/content/dam/<project>` | ALLE | Ermöglicht Zugriff zum Speichern von Projekt-Assets wie Bildern oder Videos in DAM. |
| `/content/screens/<project>` | ALLE | Entfernt den Zugriff auf alle anderen Projekte unter „/content/screens“. |
| `/content/screens/svc` | LESEN | Ermöglicht Zugriff auf den Registrierungsdienst. |
| `/libs/screens` | LESEN | Bietet DCC-Zugriff. |
| `/var/contentsync/content/screens/` | ALLE | Ermöglicht die Aktualisierung von Offline-Inhalten für das Projekt. |

>[!NOTE]
>
>Unter Umständen möchten Sie separate Autorenfunktionen (wie das Verwalten von Assets und das Erstellen von Kanälen) von den Administratorfunktionen (wie dem Registrieren von Playern) trennen. Erstellen Sie bei solchen Szenarien zwei Gruppen, fügen Sie die Gruppe „authors“ zu „contributors“ hinzu und fügen Sie die Gruppe „admin“ sowohl zu „contributors“ als auch zu „user-administrators“ hinzu.

### Erstellen von Gruppen {#creating-groups}

Bei der Erstellung eines Projekts sollten auch Standardbenutzergruppen erstellt werden, denen eine Reihe grundlegender Berechtigungen zugewiesen ist. Erweitern Sie die Berechtigungen auf die typischen, in AEM Screens definierten Rollen.

Sie können beispielsweise die folgende projektspezifischen Gruppen erstellen:

* Screens-Projektadministratoren
* Operatorinnen und Operatoren von Screens-Projekten (registrieren Player und verwalten Standorte und Geräte)
* Benutzerinnen und Benutzer von Screens-Projekten (arbeiten mit Kanälen, Zeitplänen und Kanalzuweisungen)

Die folgende Tabelle fasst bei einem AEM Screens-Projekt die Gruppen mit Beschreibungen und Berechtigungen zusammen:

<table>
 <tbody>
  <tr>
   <td><strong>Gruppenname</strong></td>
   <td><strong>Beschreibung</strong></td>
   <td><strong>Berechtigungen</strong></td>
  </tr>
  <tr>
   <td>Screens-Administratorinnen und -Administratoren<br /> <em><code>screens-admins</code></em></td>
   <td>Zugriff auf AEM Screens-Funktionen auf Administratorebene</td>
   <td>
    <ul>
     <li>Mitglied von „contributors“</li>
     <li>Mitglied von „user-administrators“</li>
     <li>ALLES unter „/content/screens“</li>
     <li>ALLES unter „/content/dam“</li>
     <li>ALLES unter „/content/experience-fragments“</li>
     <li>ALLES unter „/etc/design/screens“</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Screens-Benutzerinnen und -Benutzer<br /> <em><code>screens-users</code></em></td>
   <td>Erstellen und Aktualisieren von Kanälen und Zeitplänen und Zuweisen zu Standorten in AEM Screens</td>
   <td>
    <ul>
     <li>Mitglied von „contributors“</li>
     <li><code>&lt;project&gt; /content/screens</code></li>
     <li><code>&lt;project&gt; /content/dam</code></li>
     <li><code>&lt;project&gt; /content/experience-fragments</code></li>
    </ul> </td>
  </tr>
  <tr>
   <td>Screens-Operatorinnen und -Operatoren<br /> <em><code>screens-operators</code></em></td>
   <td>Erstellen und Aktualisieren der Ortsstruktur und Registrieren der Player in AEM Screens</td>
   <td>
    <ul>
     <li>Mitglied von „contributors“</li>
     <li><code>jcr:all /home/users/screens</code></li>
     <li><code>jcr:all /home/groups/screens</code></li>
     <li><code>&lt;project&gt; /content/screens</code></li>
    </ul> </td>
  </tr>
  <tr>
   <td>Screens-Player<br /> <em><code>screens-&lt;project&gt;-devices</code></em></td>
   <td>Gruppieren aller Player; alle Player/Geräte automatisch Mitglied von „contributors“.</td>
   <td><p> Mitglied von „contributors“</p> </td>
  </tr>
 </tbody>
</table>
