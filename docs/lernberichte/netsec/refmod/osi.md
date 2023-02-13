# OSI/ISO Referenzmodell
#### KW6

Das Open Systems Interconnection (OSI)-Modell ist ein Referenzmodell für Netzwerkprotokolle, welches festlegt, wie Netzwerke miteinander kommunizieren und Daten von einem Sender zu einem Empfänger senden und umgekehrt. 
Bei einer Kommunikation zwischen zwei Systemen wird die Kommunikation oder der Datenfluss mindestens zwei Mal alle Schichten durchlaufen. Zuerst wird beim ersten System von Layer 7 bis Layer 1 alle Schichten durchgeführt und dabei ein Paket erstellt. Danach wird das (Bit-)Paket versendet und beim Endsystem wieder entpackt. Dabei werden die Schichten nochmals durchlaufen, aber dies Mal von Layer 1 bis Layer 7, damit es in den ursprünglichen Zustand kommt. 
Die Schichten 1 bis 4 sind die transportorientierten Schichten und die Schichten von 5 bis 7 sind die anwendungsorientierten Schichten des OSI-Modells.

![OSI-Referenzmodell](../bilder/osi/OSI-Modell2.png)

Wenn eine Nachricht von einem PC über ein Netzwerk, z.B. mit Übermittlern wie Switch und Router zu einem PC eines anderen Netzwerkes übertragen wird, dann werden bei den Übermittlern nur die ersten drei Schichten (Layer 1 – Layer 3) angesehen. Wie auf der «Abbildung 1» dargestellt, dienen die ersten drei Schichten nur der Datenübertragung von «Punkt zu Punkt». Die restlichen Schichten (Layer 4 – Layer 7) sind «Ende zu Ende» orientiert. Das bedeutet, dass die «Ende zu Ende» orientierten Schichten erst beim Empfänger-PC erreicht werden. 

![Kommunikation_OSI-Referenzmodell](../bilder/osi/OSI-Modell3.png)

