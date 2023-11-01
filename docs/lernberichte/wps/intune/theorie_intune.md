# Microsoft Intune

**KW37-2023**

## Was ist Intune?

Intune ist ein Cloud-basierter Service, welches z.B. den Administratoren erlaubt, die Gräte eines Unternehmens über einer Konsole zu verwalten. Dies ermöglicht die Konfiguration von Geräteeinstellungen, Bereitstellung von Software und Updates, Schutz der Unternehmensdaten sowie die Einhaltung von Sicherheitsrechtlinien zu gewährleisten. 

![image](https://github.com/banointan/myitjournal/assets/117153686/601f0060-d62e-42da-a84c-e8d639d47cba)

### Welche Vorteile bietet Intune?

- Fernverwaltungsfunktion (Remote Management) für Mitarbeiter 
-	Support für mehrere Gerätetypen wie Android, Windows, macOS, iOS und einiges mehr
-	Die Möglichkeit, neue Software-Updates, Patches und Rechtlinien auf die Geräte zu übertragen
-	Verwaltung von Sicherheitseinstellungen

### Funktionen von Intune

-	Mobile Device Management (MDM): wird für die Konfiguration von Geräteeinstellungen und Sicherheitsrichtlinien verwendet
-	Mobile Application Management (MAM): wird für die Verwaltung von Anwendungsbeschränkungen und Anwendungsrichtlinien verwendet
-	Windows Autopilot: werden für die Registrierung neuer Geräte und die Bereitstellung benutzerdefinierter Einstellungen verwendet
-	Entpoint Schutz: wird für den Schutz von PCs vor Bedrohungen und Malware verwendet (Endpunkte sind physische Geräte, die sich mit einem Computernetzwerk verbinden und Informationen austauschen)

## Active Directory Guppen Typen

Bei AD gibt es drei Gruppen Typen. Die Security, Distribution und Microsoft 365 Gruppe. Bei AAD gibt es auch die Security Gruppe und Microsoft 365 Gruppe.

### Security Group 
Diese Gruppe wird verwendet, um den Zugang den Ressourcen zu gewährleisten. Zum Beispiel wenn man einige Benutzer im AD Lizenzieren möchte, kann man eine Security Group erstellen, diese Gruppe die benötigten Lizenzen zuweisen und Mitglieder hinzufügen.

### Distribution Group

Die Gruppe wird vor allem in Microsoft Exchange Server und in Outlook verwendet, welches das Senden eines E-Mails an eine Gruppe ermöglich. 

### Microsoft 365

Diese Gruppe wird für die Zusammenarbeit verwendet und ermöglicht den Mitgliedern den Zugriff auf ein Postfach, einen Kalender, Dateien und einiges mehr, der anderen Mitgliedern dieser Gruppe.

## Office vs Microsoft

Office ist die Lizenzierung, welches man einmalig bezahlen muss, jedoch man für immer dieselbe Version haben wird. Microsoft 365 ist ein Abonnement, welches man monatlich/jährlich bezahlen muss, dafür bekommt man immer die neusten Versionen/Updates.
