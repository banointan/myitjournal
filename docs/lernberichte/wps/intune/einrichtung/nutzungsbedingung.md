# Einrichten der Intune Umgebung 

**KW41-2023**

## Terms and Conditions (for your End-users)

Die Konfiguration von den Nutzungsbedingungen für Endbenutzer ist nicht notwendig, aber wenn man es einrichtet, wird es den Benutzern beim Registrieren angezeigt. Daher kann das Einrichten der Nutzungsbedingungen sehr nützlich sein, da wir als Administratoren dem Benutzer einige Informationen und Regeln für sein/ihr neues Gerät zur Verfügung stellen können.

Es gibt zwei Varianten, um die Nutzungsbedingung zu erstellen

-	Intune
-	Azure AD / Entra ID


### Nutzungsbedingung über Intune einrichten

Um die Nutzungsbedingung über Intune einzurichten, muss man zu «Intune > Tenant administration > Terms and conditions» navigieren und dann auf «Create» klicken.

![image](https://github.com/banointan/myitjournal/assets/117153686/e3adcd6f-6a7c-4aa7-babe-7a5e7a123a1e)

Schritt 1. Anzeigename eingeben (wenn nötig Beschreibung hinzufügen)

Schritt 2. Titel vom Nutzungsbedingung hinzufügen

Schritt 3. Nutzungsbedingung definieren und anschliessend eine Zusammenfassung davon schreiben

Schritt 4. Die Bedingung einer Gruppe oder allen Benutzern zuweisen

### Nutzungsbedingung über Azure AD / Entra ID einrichten

Bei der Einrichtung der Bedingung über Entra ID hat man mehr Flexibilität und mehr Optionen zur Formatierung. 

Um die Nutzungsbedingung über Entra einzurichten, muss man zu «Protection > Conditional Access > Terms of use» navigieren.  Bei dieser Konfiguration wird ein PDF benötigt, welches die Nutzungsbedingung beinhaltet. Ich habe dazu ein Word-Datei mit der Bedingungen erstellt und dies dann als PDF exportiert.  

Schritt Auf «New terms» klicken
Schritt 2. Name eingeben, PDF hochladen, Sprache auswählen und Display Name definieren

![image](https://github.com/banointan/myitjournal/assets/117153686/74b3fb76-4b33-4a93-b6a4-a1a62e682a32)

Schritt 3. «Require users to expand the terms of use» auswählen

![image](https://github.com/banointan/myitjournal/assets/117153686/779582cf-f756-4061-95b7-9b74849c44c7)

Schritt 4. Unter «Conditional access» «Custom policy» auswählen und auf «Create» klicken

Nun sollte man weitergeleitet werden, wo man die «Conditional Access policy» erstellen kann.

Schritt 5. «Grant» auswählen, dann die beim Schritt 2 eingegebene Name suchen und auswählen

![image](https://github.com/banointan/myitjournal/assets/117153686/ab4181f7-cf02-4fae-ac81-543b31ecbba3)

