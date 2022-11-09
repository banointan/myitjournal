# Projekt Minesweeper
## Einleitung
Ich habe mit Timm und Rico eine Projektidee gesucht, welches nicht zu einfach, aber auch nicht zu schwierig sein würde und welches aber auch mir in der verbleibenden Zeit bei der AI Gruppe zu beenden sein sollte. Schlussendlich kam Rico auf die Projektidee Minesweeper, welches wir dann ausgewählt haben und an welchem ich in den nächsten Wochen arbeiten durfte. Bei diesem Projekt geht es darum, das Spiel Minesweeper zu programmieren. 

## Konzept
Zuerst die Durchführbarkeit überprüfen auf Aufwand, Zeit, Schwierigkeitsgrad und Ressourcen. Nach dem wir einen Teil-Schritte definiert haben, habe ich dies Umgesetzt und danach erst die nächsten Teil-Schritte definiert. 
### Weiter Wichtige Punkte:

*	Zeit: bis Ende Juli (ca. 13 Tage)
*	Terminal-Spiel (ohne Grafisches Fenster)
*	Programmiersprache: Java
*	Programmier-Tool: IntelliJ IDEA Community Edition

### Die ersten Teil-Schritte überlegen, besprechen und umsetzen:
*	Schritt 1: Array erstellen mit einer definierten Grösse erstellen
*	Schritt 2: Koordinaten des Arrays ausgeben
*	Schritt 3: Array Grösse durch Eingabe des Benutzers ersetzten
*	Schritt 4: Grafisches Feld erstellen mit Strichen ( _ , | )
*	Schritt 5: An zufälligen stellen Bomben Platzieren mit einer definierten Anzahl von Bomben
*	Schritt 6: Anzahl Bomben durch Eingabe des Benutzers definieren
*	Schritt 7: Die Nachbarfelder von den Bomben füllen, in dem das Skript nach Bomben sucht      und die Felder rechts und links um eins erhöht ( + 1 )

Umsetzung Tag 1 – 5 

### Die zweiten Teil-Schritte überlegen, besprechen und umsetzen:
*	Schritt 1: Zwei Dimensionales Array kennenlernen
*	Schritt 2: Im Skript das normale Array durch das zweidimensionale Array ersetzen
*	Schritt 3: Das Skript anpassen, damit es mit dem zweidimensionalen Array funktioniert
*	Schritt 4: Grafisches Feld mit dem zweidimensionalen Array anpassen erstellen 
*	Schritt 5: An zufälligen stellen Bomben Platzieren
*	Schritt 6: Die Nachbarfelder von den Bomben füllen, in dem das Skript nach Bomben sucht und die Felder ringsum um eins erhöht

Umsetzung Tag 6 – 8  

### Den letzten Teil-Schritt überlegen, besprechen und umsetzen:
*	Schritt 1: Das Spielfeld ausgeben und anstelle von Zahlen verdeckte Felder ausgeben
*	Schritt 2: Dem Benutzer erlauben Felder aufzudecken, in dem er die Koordinaten des Feldes eingibt
*	Schritt 3: Wenn alle Felder aufgedeckt sind, das Spiel beenden
*	Schritt 4: Wenn alle Felder aufgedeckt sind, äussert die Bomben, das Spiel Beenden und die Ausgabe “Spiel gewonnen” ausgaben
*	Schritt 5: Wenn eine Bombe aufgedeckt wird, das Spiel Beenden und die Ausgabe “Spiel verloren” ausgaben
Zum Schluss noch das Skript strukturieren und einiges kommentieren

Umsetzung Tag 9 – 13 

## Umsetzung
**Tag 1 - 2022-07-07 - Anointan Balasingam - TB**

Heute habe ich mit der Realisierung vom Konzept Minesweeper begonnen. Dabei habe ich erstmals den Array erstellt und dies ausgegeben. 

**Tag 2 - 2022-07-08 - Anointan Balasingam - TB**

Heute habe ich versuch die Koordinaten mit auszugeben bei der Ausgabe des Arrays. Dann habe ich noch die Array Grösse durch die Eingabe des Benutzers definiert.

**Tag 3 - 2022-07-11 - Anointan Balasingam - TB**

Am Projekt habe ich heute vor allem an der Grafik, Struktur und am Array gearbeitet. Danach habe ich die durchgeführten sowie die nächsten Schritte mit Timm besprochen.

**Tag 4 - 2022-07-12 - Anointan Balasingam - TB**

Heute habe ich z.B. das automatische Erzeugen von Bomben im Spiel programmiert und dann auch mit dem Zählen der Bomben von den Nachbarfelder begonnen.

**Tag 5 - 2022-07-13 - Anointan Balasingam - TB**

Am heutigen Tag habe ich das automatische Zählen der Bomben von den Nachbarfelder, welches ich gestern begonnen habe weitergeführt und verbessert. Ich habe auch noch einiges mit Rico angeschaut. Zum Schluss habe ich kurz das geschriebene mit Timm besprochen und die nächsten Schritte festgelegt.
Somit konnten die ersten Teil-Schritte, die wir definiert hatte, fertig machen und auch schon die nächsten Schritte definieren.

**Tag 6 - 2022-07-14 - Anointan Balasingam - TB**

Heute habe ich die Zweidimensionale Array kennengelernt und habe grundsätzlich damit gearbeitet. Ich zuerst mich darüber informiert und mir überlegt, wie ich das in meinem Projekt benutzen und anpassen kann, da ich die Zweidimensionale Array brauche. Danach habe ich mir die nächsten Schritte aufgeschrieben und diesen mit Timm besprochen. Somit konnte ich dann weiter am Projekt arbeiten, indem ich das Eindimensionale Array durch die Zweidimensionale Array ersetzt habe. Dabei konnte ich schon einiges anpassen, dennoch gibt es noch vieles das ich anpassen muss.

**Tag 7 - 2022-07-18 - Anointan Balasingam - TB**

Am Projekt habe ich heute hauptsächlich mit dem Anpassen vom Zweidimensionale Array gearbeitet und einiges verbessert.

**Tag 8 - 2022-07-19 - Anointan Balasingam - TB**

Heute habe ich wieder mit den zwei Mehrdimensionale Arrrays gearbeitet und einiges im Code verbessert.

**Tag 9 - 2022-07-20 - Anointan Balasingam - TB**

Heute habe ich den ganzen Tag am Projekt gearbeitet. Dabei habe ich vor allem damit auseinandergesetzt, wie ich die Felder abdecke und bei jeder Eingabe des Benutzers die einzelnen Felder aufdecke. Schliesslich habe ich damit begonnen.

**Tag 10 - 2022-07-21 - Anointan Balasingam - TB**

Am heutigen Tag habe ich sehr viel dokumentiert und damit weitergefahren, die Felder aufzudecken.

**Tag 11 - 2022-07-26 - Anointan Balasingam – TB**

Heute habe ich weiter hin am Projekt gearbeitet. Dabei konnte ich die Funktion schreiben, welches beim Aufdecken eines Null-Feldes alle Null-Felde ringsum öffnet. Ich habe auch einiges im Programm verbessert. 

**Tag 12 - 2022-07-27 - Anointan Balasingam – TB**

Ich konnte das Spiel heute Spielbar machen. Beim Programmieren hatte ich auch Rekursion Probleme, konnte es jedoch mit Hilfe von Timm lösen. Nun muss ich noch einiges verbessern, so dass es möglichst wenige Fehlermeldungen auftauchen sowie das Programm besser Strukturieren und einiges kommentieren.

**Tag 13 - 2022-07-28 - Anointan Balasingam**

Heute habe die noch die letzten Verbesserungen durchgeführt und das Spiel benutzerfreundlicher gemacht und habe somit das Projekt Minesweeper beendet.

