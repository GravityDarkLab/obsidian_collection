[[Vermittlungsschicht (Network Layer)]].
[[Autonome Systeme (AS)]].

### Routing Table:
In der **Routing-Tabelle** speichert ein Router (oder Host):
- die Netzadresse eines Ziels.
- die Länge des Präfixes.
- den zugehörigen Next-Hop (**Gateways**).
- das Interface, über welches dieser Next-Hop erreichbar ist
- die kosten bis zum Ziel.
![[Beispiel routing-tabelle.png]]

## Statisches Routing:
### Longest Prefix Matching:
- Die Routingtabelle wird von längeren Präfixen hin zu kürzeren Präfixen durchgesucht. Der erste passende Eintrag liefert das Gateway (Next-Hop) eines Pakets. Diesen Prozess bezeichnet man als **==Longest Prefix Matching==**.
- Die Default Route 0.0.0.0/0 liefert immer einen Match => Aber es ist nicht garantiert, dass das gateway (**Gateway of last resort**) eine Route zum Ziel kennt.
- Routen zu **direkt verbundenen** netzen können automatisch erzeugt werden. Der **NextHop** ist in diesem Fall die unspezifizierte Adresse.
- Routen zu entferten Netzen müssen **gelernt** werden - entweder durch **==Statisches Routing (per hand)==** oder durch **==Dynamisches Routing (Routing Protokolle)==**.


![[Longest Präfix matching.png]]
![[longest präfix matching 2.png]]


## Dynamisches Routing:
- **Distanz-Vektor-Protokolle**:
	- Router kennen nur Richtung (**NextHope**) und Entfernung (**Kosten**) zu einem Ziel.
	- keine Information über die Netztopologie.
	- Router tauschen untereinander kumulierte kosten aus.
	- ==Bellman-Forrd== Algorithmus.
	- Beispiel **[[Routing Information Protocol (RIP)]]**.
![[Bellman-Forrd.png]]
![[Distanz-Vektor-Protokolle.png]]


- **Link-State-Protokolle**:
	- Router tauschen untereinander kumulierte kosten und wege aus.
	- Komplexe Nachbarschaftsbeziehungen und Update-Nachrichten.
	- Router kennen die Netztopologie.
	- ==Dijkstras== Algorithmus.


	![[Dijkstras.png]]
![[Link-State-Protokolle.png]]