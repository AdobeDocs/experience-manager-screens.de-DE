---
title: Geräteregistrierung
description: Erfahren Sie mehr über den Prozess zur Geräteregistrierung in einem AEM Screens-Projekt.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
docset: aem65
feature: Administering Screens, Device Registration
role: Admin
level: Intermediate
exl-id: b2d3a2cd-263f-4142-80da-29ce54cbf391
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 31%

---

# Geräteregistrierung {#device-registration}

Auf der folgenden Seite wird der Prozess zur Geräteregistrierung in einem AEM Screens-Projekt beschrieben.

## Registrieren von Geräten {#registering-a-device}

Der Prozess zur Geräteregistrierung erfolgt auf zwei separaten Geräten:

* Das tatsächliche Gerät, das registriert werden soll, z. B. Ihre Signage-Anzeige
* Der AEM-Server, der zum Registrieren des Geräts verwendet wird

>[!NOTE]
>
>Nach dem Herunterladen des neuesten Windows-Players (*.exe*), von [AEM 6.4 Player-Downloads](https://download.macromedia.com/screens/) Führen Sie die Schritte im Player aus, um die Ad-hoc-Installation abzuschließen:
>
>1. Halten Sie die linke obere Ecke gedrückt, um das Admin-Bedienfeld zu öffnen.
>1. Navigieren Sie zu **Konfiguration** aus dem linken Aktionsmenü aus und geben Sie die Standortadresse der AEM Instanz in **Server** und wählen **Speichern**.
>1. Wählen Sie die **Registrierung** über den Link im linken Aktionsmenü und die folgenden Schritte, um den Prozess zur Geräteregistrierung abzuschließen.
>

![screen_shot_2018-11-26at12118pm](assets/screen_shot_2018-11-26at12118pm.png)

1. Starten Sie auf Ihrem Gerät den AEM Screens-Player. Die Registrierungs-Benutzeroberfläche wird angezeigt.

   ![screen_shot_2018-11-26at104230am](assets/screen_shot_2018-11-26at104230am.png)

1. Navigieren Sie in AEM zum Ordner **Geräte** Ihres Projekts.

   >[!NOTE]
   >
   >Weitere Informationen zum Erstellen eines Projekts für Screens im AEM-Dashboard finden Sie unter [Erstellen und Verwalten von Screens-Projekten](creating-a-screens-project.md).

1. Wählen Sie die **Geräte-Manager** in der Aktionsleiste.

   ![screen_shot_2018-11-26at104702am](assets/screen_shot_2018-11-26at104702am.png)

1. Wählen Sie die **Geräteregistrierung** rechts oben.

   ![screen_shot_2018-11-26at104815am](assets/screen_shot_2018-11-26at104815am.png)

1. Wählen Sie das gewünschte Gerät aus (wie in Schritt 1) und wählen Sie **Gerät registrieren**.

   ![screen_shot_2018-11-26at105112am](assets/screen_shot_2018-11-26at105112am.png)

1. Warten Sie in AEM darauf, dass das Gerät seinen Registrierungs-Code sendet.

   ![screen_shot_2018-11-26at105150am](assets/screen_shot_2018-11-26at105150am.png)

1. Prüfen Sie den **Registrierungs-Code** auf Ihrem Gerät.

   ![screen_shot_2018-11-26at105227am](assets/screen_shot_2018-11-26at105227am.png)

1. Wenn die Variable **Registrierungs-Code** auf beiden Computern identisch ist, wählen Sie **Bestätigen** in AEM, wie im Schritt (6) gezeigt.
1. Legen Sie den gewünschten Namen für das Gerät fest und wählen Sie **registrieren**.

   ![screen_shot_2018-11-26at105357am](assets/screen_shot_2018-11-26at105357am.png)

1. Auswählen **Beenden** , um den Registrierungsprozess abzuschließen.

   ![screen_shot_2018-11-26at105456am](assets/screen_shot_2018-11-26at105456am.png)

   >[!NOTE]
   >
   >Die **Neu registrieren** ermöglicht die Registrierung eines neuen Geräts.
   >
   >Mit **Anzeige zuweisen** können Sie das Gerät direkt einer Anzeige hinzufügen.

   Wenn Sie **Beenden**, weisen Sie das Gerät einer Anzeige zu.

   ![screen_shot_2018-11-26at105740am](assets/screen_shot_2018-11-26at105740am.png)

   >[!NOTE]
   >
   >Weitere Informationen zum Erstellen und Verwalten einer Anzeige für Ihr Screens-Projekt finden Sie unter [Erstellen und Verwalten von Anzeigen](managing-displays.md).

### Zuweisen eines Geräts zu einer Anzeige {#assigning-device-to-a-display}

Wenn Sie das Gerät nicht einer Anzeige zugewiesen haben, führen Sie die folgenden Schritte aus, um das Gerät einer Anzeige in Ihrem AEM Screens-Projekt zuzuweisen:

1. Wählen Sie das Gerät aus und wählen Sie **Gerät zuweisen** in der Aktionsleiste aus.

   ![screen_shot_2018-11-26at111026am](assets/screen_shot_2018-11-26at111026am.png)

1. Wählen Sie den Pfad der Anzeige unter **Anzeige-/Gerätekonfiguration** aus.

   ![screen_shot_2018-11-26at111252am](assets/screen_shot_2018-11-26at111252am.png)

1. Auswählen **Zuweisen** wenn Sie den Pfad auswählen.

   ![screen_shot_2018-11-26at111722am](assets/screen_shot_2018-11-26at111722am.png)

1. Auswählen **Beenden** nachdem das Gerät erfolgreich zugewiesen wurde, wie in der folgenden Abbildung dargestellt.

   ![screen_shot_2018-11-26at112041am](assets/screen_shot_2018-11-26at112041am.png)

   Sie können das Anzeigen-Dashboard auch bei Auswahl anzeigen **Beenden**.

   ![screen_shot_2018-11-26at112154am](assets/screen_shot_2018-11-26at112154am.png)

## Suchen eines Geräts über den Geräte-Manager {#search-device}

Wenn Sie Geräte für Ihren Player registriert haben, können Sie alle Geräte über die Benutzeroberfläche des Geräte-Managers anzeigen.

1. Navigieren Sie von Ihrem AEM Screens-Projekt aus zur Benutzeroberfläche des Geräte-Managers, z. B.: **DemoScreens** > **Geräte**.

1. Wählen Sie die **Geräte** Ordner und auswählen **Geräte-Manager** in der Aktionsleiste aus.

   ![image](/help/user-guide/assets/device-manager/device-manager-1.png)

1. Die Liste der registrierten Geräte wird angezeigt.

1. Wenn die Liste der registrierten Geräte sehr lang ist, können Sie nun über das Suchsymbol in der Aktionsleiste suchen.

   ![image](/help/user-guide/assets/device-manager/device-manager-2.png)

   Oder

   Auswählen `/` (Schrägstrich) zum Aufrufen der Suchfunktion.

   ![Bild](/help/user-guide/assets/device-manager/device-manager-3.png)


### Einschränkungen bei der Suchfunktion {#limitations}

* Der Benutzer kann jedes in der Variablen *Geräte-ID* oder *Gerätename*.

  >[!NOTE]
  >Es wird empfohlen, die Gerätenamen in mehreren Wörtern zu erstellen, z. B. *Boston Store Lobby* und nicht *BostonStoreLobby*.

* Wenn Sie Gerätenamen wie *Boston Store Lobby*, sucht es nach einem beliebigen Wort *Boston*, *store* oder *Lobby*. Wenn der Gerätename jedoch *BostonStoreLobby*, suchen Sie dann nach *Boston* zeigt keine Ergebnisse an.

* Der Platzhalter `*` wird für die Suche unterstützt. Wenn Sie alle Geräte mit Namen finden möchten, die mit *Boston*, können Sie *Boston**.

* Wenn der Gerätename *BostonStoreLobby* und die Suche nach *Boston* gibt das Ergebnis nicht zurück, indem Sie *Boston** in Ihren Suchkriterien gibt das Ergebnis zurück.

## Einschränkungen bei der Geräteregistrierung {#limitations-on-device-registration}

Systemweite Einschränkungen des Benutzerkennworts können zu Fehlern bei der Geräteregistrierung führen. Die Geräteregistrierung verwendet ein zufällig generiertes Kennwort, um den Gerätebenutzer zu erstellen.

Wenn das Kennwort durch die Variable *AuthorizableActionProvider* -Konfiguration kann das Erstellen des Gerätebenutzers fehlschlagen.

>[!NOTE]
>
>Das derzeit generierte zufällige Passwort besteht aus 36 ASCII-Zeichen im Bereich von 33 bis 122 (enthält fast alle Sonderzeichen).

```java
25.09.2016 16:54:03.140 *ERROR* [59.100.121.82 [1474844043109] POST /content/screens/svc/registration HTTP/1.1] com.adobe.cq.screens.device.registration.impl.RegistrationServlet Error during device registration
javax.jcr.nodetype.ConstraintViolationException: Password violates password constraint (^(?=.*\d).{7,9}$).
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.validatePassword(PasswordValidationAction.java:105)
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.onPasswordChange(PasswordValidationAction.java:76)
        at org.apache.jackrabbit.oak.security.user.UserManagerImpl.onPasswordChange(UserManagerImpl.java:308)
```

### Sonstige Ressourcen {#additional-resources}

Weitere Informationen zum AEM Screens-Player finden Sie unter [AEM Screens-Player](working-with-screens-player.md).
