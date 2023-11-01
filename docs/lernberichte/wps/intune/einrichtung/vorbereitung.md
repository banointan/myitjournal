# Einrichten der Intune Umgebung 

## Vorbereitung

Um mit Intune arbeiten zu können, muss man zuerst einen Microsoft 365 Tenant mit einem Abonnement erstellen. Schliesslich muss überprüft werden, ob das Abonnement eine Intune-Lizenz hat. Unter «M365 Maps» kann nachgeschlagen werden, welche Lizenzen Intune beinhaltet. 
Bei dieser Intune Projekt habe ich diese Webseite als Hilfe genutzt: [Setting Up](https://scloud.work/)

Weblinks
Unter diesen drei Links werde ich hautsächlich arbeiten:
-	[Intune](https://endpoint.microsoft.com/) 
-	[Admin Center](https://admin.microsoft.com/) 
-	[Azure Portal](https://portal.azure.com) 
-	[Entra](https://entra.microsoft.com/) 

### Namenskonzept der Geräte

![image](https://github.com/banointan/myitjournal/assets/117153686/0282bdfe-299c-4d13-944e-af713dbbc1c0)

### User im Azure AD (Entra ID) erstellen

Schritt 1. Azure Portal öffnen

![image](https://github.com/banointan/myitjournal/assets/117153686/bee74935-f155-4fb2-896f-e4e453ab1eaf)

Schritt 2. Im Suchfenster AAD eingeben und dann im Menu User auswählen

Schritt 3. Auf «Neuer Benutzer erstellen» klicken

![image](https://github.com/banointan/myitjournal/assets/117153686/60888859-fb72-408d-af92-9cec74a2182a)

Schritt 4. Benutzerprinzipalname und Anzeigename eingeben

![image](https://github.com/banointan/myitjournal/assets/117153686/942afd9e-07b4-46cb-8949-aaf19e164891)

Schritt 5. Unter Zuweisung der zugewiesenen Gruppe hinzufügen und Rolle verteilen

![image](https://github.com/banointan/myitjournal/assets/117153686/901c1906-073b-4216-b06f-a55f62fdec09)

Schritt 6. Benutzer erstellen

Schritt 7. Nach einer Aktualisierung sollte nun der erstellte Benutzer angezeigt werden

![image](https://github.com/banointan/myitjournal/assets/117153686/a2efa3ca-385f-428d-a5eb-558068ba9337)


