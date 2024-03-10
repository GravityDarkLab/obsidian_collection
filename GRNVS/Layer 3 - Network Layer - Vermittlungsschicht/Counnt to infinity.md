[[Routing Information Protocol (RIP)]].

### Lösung:
1. **Split Horizon**:
	„Bewerbe eine Route nicht über das Interface, über das die Route ursprünglich gelernt wurde.“
	Im konkreten Fall würden also Router A und B keine Route zu D an C schicken.
	Durch die ringförmige Topologie wird das Problem dadurch jedoch noch nicht behoben.

2. **Triggered Update**:
	Anstelle Routing-Updates nur in periodischen Zeitabständen zu versenden 
	(bei RIP standardmäßig 30 s), werden Updates sofort geschickt, wenn Topologieänderungen erkannt werden. ==Dies löst das Count-to-Infinity-Problem zwar nicht==, beschleunigt den Vorgang aber. Das Problem besteht darin, dass kurzzeitig viel Datenverkehr durch Routingupdates verursacht wird. 
	Triggered Updates werden von den meisten Routingprotokollen unterstützt (RIP erst ab Version 2).

3. **Path Vector**:
Es wäre möglich, dass sich jeder Router bei einem Update merkt, woher das Update kam und diese Information bei Routing-Updates mit einschließt. Auf diese Weise könnte jeder Router den vollständigen Pfad nachvollziehen, den ein Paket zum jeweiligen Ziel nehmen wird.
Entdeckt ein Router sich selbst in diesem Pfad, so weiß er, dass eine Schleife vorhanden ist. Er kann das Update in diesem Fall verwerfen. **Dieses Verfahren wird von BGP eingesetzt**.