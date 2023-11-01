# Einrichten der Intune Umgebung 

**KW38-2023**

## Enrollment device platform restrictions

Wenn man die Beschränkungen für die Geräteanmeldung von Anfang an klar und ordnungsmässig definiert, kann das in Zukunft viele Probleme sowie Diskussionen ersparen. Anders gesagt, bei dieser  Konfiguration wird definiert, welche Geräte in die Intune-Umgebung aufgenommen werden können. Dabei ist jedes Intune kompatible Betriebssystem nach Betriebssystem-Typen «Zulassen (ja/nein)» sowie «Persönlich Zulassen (ja/nein)» unterteilt. 

Wenn man die persönlichen Geräte blockiert, stellt man sicher, dass man keine Diskussion mit Benutzern über das Verwalten ihrer privaten Geräte haben muss. Dennoch kann es bei Bedarf oder bei Ausnahmefällen für spezifische Geräte erlaubt werden. 

Um diese Einstellungen zu bearbeiten, muss man wie folgt vorgehen:

Schritt 1. [Intune](https://endpoint.microsoft.com/) öffnen 

Schritt 2. Zu «Devices > Enrollment device platform restrictions» navigieren und auf «All Users» klicken

![image](https://github.com/banointan/myitjournal/assets/117153686/ab680285-6afb-4299-92b2-90ef19dca517)

Das hier Abgebildete Bild ist meine Standardrichtlinie, um alle persönlichen Geräte zu blockieren:

![image](https://github.com/banointan/myitjournal/assets/117153686/b0240846-3527-47e1-9231-6fc612bc411e)
