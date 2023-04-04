# Layer 1
## Twisted-Pair Kabel

Twisted-Pair Kabel steht für Kabel mit verdrillten Adernpaaren oder Kabel mit verdrillten Doppeladern, da in dieser Kabel die Adern paarweise miteinander verdrillt sind. Bei den Twisted-Pair Kabel wird Kupfer verwendet, um die Daten zu übertragen und als Anschluss wird standartmässig der RJ45 verwendet.
Twisted-Pair Kabel gibt es heutzutage in zwei- und vierpaariger Ausführung. Für Installationen ab Cat 6 sind vierpaarige Kabel zwingend. Es gibt auch noch Anschlussdosen, die man hergestellt hat, um mit einem Twisted-Pair Kabel zwei Anschlussdosen zu besetzen. Der grösste Nachteil dabei ist, dass egal wie viel Mbit/s oder Gbit/s übertragen werden, die maximale Geschwindigkeit der Datenübertragung pro Anschlussdose bei 100 Mbit/s liegt. 
Es gibt Bezeichnungen für die verschiedenen Zusammenstellungen der Twisted-Pair Kabeln. Je nach Anwendung spielt die Zusammenstellung eine wichtige Rolle. Im Allgemeinen gibt es drei Arten von Twisted-Pair Kabeln, die einen sind mit einem Metallgeflecht geschirmt (STP), die anderen sind mit einer Folie geschirmt (FTP) und dann gibt es noch welche, die nicht geschirmt (UTP) sind. Wieso verdrillt und geschirmt? 
Verdrillte Adern bieten einen besseren Schutz vor elektromagnetischen Störfeldern als parallel geführten Leiter (z.B. Koaxialkabel). Externe Störungen können durch zusätzliche Abschirmung und durch verdrillte Adern im Ganzen weiter reduziert werden.

### Kupfer
Die Datenübertragung in Kupferkabeln ist elektrisch. Kupfer ist ein Halbedelmetall, das beim Schmelzen von Erzen hergestellt wird. Kupferkabel zeichnen sich durch eine hohe elektrische Leitfähigkeit aus, sodass sie auch noch mit den heutigen Anforderungen mithalten können. 
In meinem Fall könnte man sagen, dass der Kupferkabel im Layer-1 für die Datenübertragung zuständig ist. 

### Bezeichnungsschema

Die Bezeichnungsschema der Form XX/YZZ, welches 2002 eingeführt wurde, wird auch noch heute aktiv genutzt. Dabei steht:

-	**XX für die Gesamtschirmung:**
    -	U = ungeschirmt (unshielded)
    -	F = Folienschirm (foiled)
    -	S = Geflechtschirm (screened)
    -	SF = Geflecht- und Folienschirm
-	**Y steht für die Aderpaarschirmung:**
    -	U = ungeschirmt
    -	F = Folienschirm
    -	S = Geflechtschirm
-	**ZZ steht für:**
    -	TP = Twisted Pair
    -	QP = Quad Pair 

### Übersicht der Schirmungsarten

![Übersicht der Schirmungsarten](../bilder/2.png){ width="100%" }

#### U/UTP

![U/UTP](../bilder/3.jpg){ width="40%" }
![U/UTP](../bilder/4.jpg){ width="50%" } 

U/UTP ist ein Kabel ohne Abschirmung (ungeschirmt), wobei die Adernpaaren auch ungeschirmt verdrillt sind (Unshielded Twisted Pair, UTP). Dieser Kabel ist die einfachste Version eines Twisted-Pair Kabels. Nachteilig ist aber, dass er am wenigsten Widerstand gegenüber externen Störungen hat. Bei den meisten UTP-Kabeln hat es noch eine Zwickelfüllung, welches die Adernpaare voneinander trennt. 

#### S/UTP

![S/UTP](../bilder/5.jpg){ width="48%" }
![S/UTP](../bilder/6.png){ width="40%" }

S/UTP ist ein Kabel mit Drahtgeflecht Gesamtabschirmung, wobei die Adernpaaren ungeschirmt verdrillt sind. Im Allgemeinen sind Kabeln mit Abschirmgeflecht flexibler als F/UTP-Kabeln und eignen sich daher besser für flexible Anwendungen.

#### F/UTP

![F/UTP](../bilder/7.jpg){ width="48%" }
![F/UTP](../bilder/8.jpg){ width="40%" }

F/UTP ist ein Kabel, welches komplett durch Folie abgeschirmt ist, wobei die Adernpaaren ungeschirmt verdrillt sind. Dieses Kabel ist dem U/UTP Kabel sehr ähnlich, nur dass es unter dem Aussenmantel des Kabels eine Folie hinzugefügt wurde, welches das Kabel etwas widerstandsfähiger macht.

#### SF/UTP

![SF/UTP](../bilder/9.jpg){ width="40%" }
![SF/UTP](../bilder/10.png){ width="50%" }

SF/UTP Kabeln sind komplett durch Folie und mit Drahtgeflecht abgeschirmt, wobei die Adernpaaren an sich ungeschirmt verdrillt sind. Dieses Kabel verhindern sehr effektiv, dass Störungen in das Kabel eindringen oder auch dieses verlassen.

#### U/FTP

![U/FTP](../bilder/11.jpg){ width="48%" }
![U/FTP](../bilder/12.jpg){ width="40%" }

U/FTP Kabeln haben keine Gesamtabschirmung, dafür sind die verdrillten Adernpaare jeweils mit einer Folie voneinander getrennt. Auch wenn der Name U/FTP sehr ähnlich wie F/UTP aussieht, ist in Wirklichkeit die Qualität von U/FTP-Kabeln weitaus grösser. Gleichzeitig sind solche Kabeln im Allgemeinen flexibler als F/UTP Kabeln.  Dieser Kabel wird häufig in 10GBASE-T Anwendungen genutzt. 

#### S/FTP

![S/FTP](../bilder/13.png){ width="45%" }
![S/FTP](../bilder/14.png){ width="45%" }

S/FTP Kabeln sind gesamthaft mit einem Drahtgeflecht abgeschirmt, wobei die verdrillten Adernpaare mit einer Folie abgeschirmt sind. S/FTP-Kabel sind häufig in der Kategorie Cat.7 und in der Kategorie der hochflexiblen Industriekabel zu finden.

#### F/FTP

![F/FTP](../bilder/15.png){ width="45%" }
![F/FTP](../bilder/16.png){ width="45%" }

F/FTP Kabeln haben eine Gesamtfolienabschirmung, wobei die verdrillten Adernpaare mit Folien abgeschirmt sind. F/FTP Kabeln sind billiger als S/FTP Kabeln, aber dafür weniger flexibel, weshalb diese Kabeln vor allem für Festinstallationen eignen. 

#### SF/FTP

![SF/FTP](../bilder/17.jpg){ width="48%" }
![SF/FTP](../bilder/18.jpg){ width="40%" }

Bei der SF/FTP Kabeln gibt es eine doppelte Gesamtabschirmung, was heisst, dass es einmal mit einer Gesamtfolie und auch mit einer Drahtgeflecht abgeschirmt ist, wobei die verdrillten Adernpaare auch noch einmal mit einer Folie abgeschirmt sind. In Bezug auf Elektromagnetische Störungen ist dieses Kabel die fortschrittlichste Version des Kupferkabels. 

### Übersicht der Klassen und Kategorien

![Klassen und Kategorien](../bilder/klassen.png){ width="100%" }

