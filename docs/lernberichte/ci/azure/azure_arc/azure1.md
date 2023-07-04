# Projekt Azure Arc

Heute habe ich mit Constantin das Azure Arc Projekt begonnen, besser gesagt, ich bin dazugestossene. Heute fand noch eine Besprechung mit allen beteiligten Mitarbeiter statt. Dabei haben wir die Projekt Ziele definiert. 

### Was ist Azure?

Microsoft Azure ist eine skalierbare Cloud-Computing-Plattform von Microsoft, die Cloud-Dienste wie IaaS, PaaS und SaaS sowie weitere Services weltweit bereitstellt. Microsoft erweitert Azure kontinuierlich mit neuen Diensten.

Azure ist eine riesige Sammlung von Servern und Netzwerkhardware-Komponenten, auf denen ein komplexer Satz verteilter Anwendungen ausgeführt wird. Diese Anwendungen orchestrieren die Konfiguration und den Betrieb der virtualisierten Hardware und Software auf diesen Servern. Die Orchestrierung dieser Server macht Azure so leistungsstark. Mit Azure müssen Benutzer die Hardware nicht warten und aktualisieren, dies wird von Azure im Hintergrund durchgeführt.

### Was ist Azure Arc?

Azure Arc ist der Name einer Managementlösung von Microsoft. Sie erweitert das Azure Management auf lokale On-Premises-Ressourcen und Ressourcen anderer Cloud-Umgebungen. Microsoft stellt mit Azure Arc eine einheitliche Control Plane und Management-Oberfläche zur Verfügung, die sich zur Verwaltung hybrider Cloud-Umgebungen, Multi-Cloud- und Edge-Computing-Umgebungen einsetzen lässt.

### Wichtige Begriffe

**Subscription(ID):** Was ist eine Subscription, welche mit der SubscriptionID identifiziert wird? Auf welcher Flughöhe werden, die in der ID vergeben? Service-basiert oder wie leider üblich Gruppen- basiert oder eine Subscription wie die ID?

**Service Principal Name (SP Name):** Bezeichnet ... (Erklärung für Nicht-Azure-Kenner).... Wir in Anleitungen mit dem Platzhalter <Unique SP Name> angetroffen. Es wird empfohlen, sich an eine Namenskonvention zu halten, siehe (TODO: Namenskonvention für SP Names verlinken)

**Resource Groups:** Was sind das, wofür werden sie gebraucht und auch hier, wie sollen wir diese sinnvoll bennen? Lassen sie sich hierarchiesch verschachteln oder ist es eine flache Liste pro Subscription

