---
lab:
  title: 'Lab 2: - Erstellen und Verwalten einer Zugriffsüberprüfung'
  module: 'Module : Deploying access using Microsoft Entra entitlement management'
---

# Lab 2: Zugriffsüberprüfung erstellen und verwalten

## Labszenario

Zugriffsüberprüfungen helfen sicherzustellen, dass nur die richtigen Personen Zugang zu sicheren Ressourcen und Informationen haben. Eine Zugriffsüberprüfung kann für einmalige oder wiederkehrende Zeiträume eingerichtet werden, und sie ermöglicht es den Prüfenden, den Zugriff auf der Grundlage von Faktoren wie Benutzerrolle, letzte Anmeldung oder Risikostufe zu genehmigen oder zu verweigern. Die Ergebnisse dieser Überprüfungen können dann verwendet werden, um die Zugriffsrechte der Benutzenden zu aktualisieren und sicherzustellen, dass sie mit den Unternehmensrichtlinien und Compliance-Anforderungen übereinstimmen. In diesem Unternehmen wird eine Zugangsüberprüfung durchgeführt, wenn Mitarbeitende die Rolle innerhalb des Unternehmens wechseln. Wechseln Mitarbeiternde beispielsweise von einer Vertriebsrolle in eine Marketingrolle, benötigen sie möglicherweise keinen Zugriff mehr zu bestimmten Vertriebsdatenbanken oder -anwendungen. Eine Zugriffsüberprüfung würde dazu beitragen, diese unnötigen Berechtigungen zu ermitteln und dem Unternehmen die Möglichkeit geben, sie zu widerrufen, wodurch das Risiko eines unbefugten Zugriffs oder eines Datenlecks verringert wird.

#### Geschätzte Dauer: 15 Minuten

### Übung 1 - Vergewissern Sie sich, dass keine Benutzenden auf LinkedIn zugreifen, die diese Ressource nicht nutzen sollten.

#### Aufgabe 1 - Erstellen einer Zugriffsüberprüfung - Prüfungsart

1. Melden Sie sich mit einem globalen Administratorkonto bei [https://entra.microsoft.com](https://entra.microsoft.com) an.

1. Öffnen Sie das Menü **Identität** und wählen Sie dann  **Identity Governance**.

1. Wählen Sie im linken Menü **Zugriffsüberprüfungen**.

1. Wählen Sie im oberen Menü **+ Neue Zugriffsüberprüfung**.

1. Wählen Sie im Bereich Neue Zugriffsüberprüfung das Element **Anwendungen** im Dropdown-Menü Zu überprüfende Elemente auswählen.

1. Verwenden Sie die Tasten **+ Anwendungen auswählen**, um das **LinkedIn** aus der Liste auszuwählen.

1. Für den **Umfang** wählen Sie **Alle Benutzenden**.

1. Wählen Sie die Taste **Weiter: Überprüfungen** am unteren Rand des Bildschirms.

#### Aufgabe 2 - Erstellen einer Zugriffsüberprüfung - Überprüfungen

1. Markieren Sie vorübergehend das Kästchen **Mehrstufige Überprüfung** mit einem Haken.

 **Notiz** - Hier können Sie wählen, ob Ihre Zugriffsüberprüfung mehrere Ebenen haben soll.  Verwenden Sie dies für sehr wichtige Ressourcen, damit die Überprüfung durch eine einzelne Person nicht dazu führt, dass eine kritische Ressource dem Benutzerzugang hinzugefügt oder entzogen wird.  Wir werden keine mehrstufigen Komponenten erstellen/ testen; aber der Prozess ist sehr ähnlich.

1. Deaktivieren Sie das Kontrollkästchen **Mehrstufige Überprüfung**.

1. Füllen Sie die Seite Überprüfung mit den unten stehenden Werten aus:

| Feldname | Wert |
| :--- | :--- |
| Prüfer auswählen | Ausgewählte Benutzende oder Gruppe(n) -- Adele Vance |
| Dauer (in Tagen) | 5 |
| Wiederholung der Überprüfung | Monatlich |
| Startdatum | Datum von heute |
| ENDE | Nach Anzahl von Vorkommen beenden |
| Vorkommen | 3 |
| | |

1. Wählen Sie die Taste **Weiter: Einstellungen** aus.

#### Aufgabe 3 - Erstellen einer Zugriffsüberprüfung - Einstellungen

1. Lassen Sie das Kästchen **Ergebnisse automatisch auf Ressourcen anwenden** nicht markiert.

 **Hinweis** - Wir wollen sicherstellen, dass wir die Ergebnisse nach Abschluss der Überprüfung validieren.

1. Wählen Sie die Option **Zugriff entfernen** für die Option **Wenn der Prüfende nicht antwortet**.

 **Hinweis** - dies ist eine Einstellung, mit der Sie Ihre Sicherheitsstufe kontrollieren können.  Wenn keine Überprüfung auf eine weniger sichere Sicherheitslage reagiert, können Sie den Zugriff genehmigen.  In einem sehr sicheren Sicherheitsstatus können Sie die Funktion Zugriff entfernen verwenden.  Wählen Sie bei der Implementierung Ihrer eigenen Lösungen aus, was für Ihr Unternehmen am besten geeignet ist.

1. Wählen Sie für **Benachrichtigung am Ende der Überprüfung senden an** das Administratorkonto, das Sie für dieses Lab verwenden.

1. Lassen Sie die **Entscheidungshilfen für die Überprüfung aktivieren** auf ihren Standardwerten.

1. Legen Sie den **Zusätzlichen Inhalt für Reviewer-E-Mail** fest und geben Sie den Wert `Please complete your Access Review as soon as you can.` ein.

1. Wählen Sie **Weiter: Überprüfen + Erstellen**.

1. Geben Sie die folgenden Werte für den Namen und die Beschreibung ein:

| Feldname | Wert |
| :--- | :--- |
| Name der Überprüfung | `Check LinkedIn` |
| Beschreibung | `In this access review, we check to see if the right people have access to LinkedIn.` |
| | | 

1. Klicken Sie auf **Erstellen**.

#### Aufgabe 4 - Melden Sie sich als Adele an, um die Zugriffsüberprüfung durchzuführen

1. Schließen Sie Ihren Browser, falls Sie ihn geöffnet haben.

1. Öffnen Sie den Browser und stellen Sie eine Verbindung zu `https://outlook.office.com/` her.

1. Wenn Sie sich als Adele anmelden, werden Sie aufgefordert, Ihr Passwort zu ändern.

1. Melden Sie sich basierend auf Ihrem Mandanten als Adele Vance an.

 **Hinweis** - Sie sollten eine E-Mail von **Microsoft Security** mit einem Betreff von **Aktion erforderlic: Überprüfen Sie den Zugriff auf LinkedIn...**. Es kann bis zu 10 Minuten dauern, bis diese E-Mail eintrifft.

1. Wählen Sie die Schaltfläche **Überprüfung starten >**.

 ![Screenshot der Seite Zugriffsüberprüfung, die AdeleV erhält, wenn sie den Link in der E-Mail aufruft.  Beachten Sie, dass empfohlen wird, Christopher Green zu entfernen.](./Media/access-review-page.png)

1. Setzen Sie einen Haken in den Kreis neben **Christopher Green**.

1. Wählen Sie die Option **Verweigern** aus dem oberen Menü.

1. Geben Sie einen Grund ein, um den Zugriff auf die Ressource zu verweigern. Beispiel: `The sales campaign is over and Christopher does not need access any more`.

1. Wählen Sie die Schaltfläche **Absenden**, um Ihre Empfehlung abzusenden.

#### Aufgabe 5 - Bestätigen Sie die Ergebnisse der Zugriffsüberprüfung

1. Schließen Sie Ihren Browser, falls Sie ihn geöffnet haben.

1. Öffnen Sie den Browser und stellen Sie eine Verbindung zu `https://Entra.Microsoft.com/` her.

1. Melden Sie sich bei Microsoft Entra mit Ihrem Administratorkonto an.

1. Öffnen Sie im Menü auf der linken Seite **Identity Governance**.

1. Wählen Sie **Zugriffsüberprüfungen**.

1. Wählen Sie die Überprüfung **LinkedIn prüfen**, die wir in diesem Lab erstellt haben.

1. Überprüfen Sie die Antwort von AdeleV.
