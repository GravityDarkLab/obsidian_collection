[[Verbindungscharakterisierung]] **&** [[Transportschicht (Transport Layer)]].

# Für die Sicherungsschicht (Layer 2):

- **Zeitmultiplex**  : Time Division Multiplex , **TDM** 
	- Deterministische Verfahren.
	- Nichtdeterministische Verfahren.
		-> [[Zeitmultiplexverfahren]].
- **Frequenzmultiplex** : Frequency Division Multiplex, **FDM**
	- Radiosender
-  **Raummultiplex** : Space Division Multiplex , **SDM**
- **Codemultiiplex** : Code Division Multiplex , **CDM**


_Multiplexing beschreibt den **Mehrfachzugriff** von Teilnehmern auf ein **geteiltes** Medium. Offen bleibt dabei **wie das Medium zwischen den Teilnehmern aufgeteilt wird**. So gilt, beispielsweise:
- **Codemultiplex** Teilnehmer verwenden für ihre Nachrichten zueinander orthogonale Alphabete.
- **Zeitmultiplex** Teilnehmern werden Zeitslots zugeteilt in denen diese das Medium nutzen dürfen.


# Für die Transportschicht (Layer 4):
- **Multiplexing** ist :
	- **Anwendungsbeispiel** : Streaming.
	- der segmentierung der Datenströme unterschiedlicher Anwendungen. (-> jedes Segment hat einem **Header**).
	- **Header ->** ein **5-Tupel** : ==(**SrcIPAddr**, **SrcPort**, **DstIPAddr**, **DstPort**, **Protocol**)==. || **Portnummern sind 16 bit**.
	- die Segmente werden in jeweils unabhängigen IP-Paketen zum Empfänger geroutet.
	- Empfänger muss die Segmente den einzelnen Datenstömen zuordnen und an die Jeweiligen Anwendung weiterreichen.

- **Verlauf**:
	1. Betriebssystem verwendet das 5-Tupel um **Sockets** bereitzustellen.
	2. Eine Annwendung adressiert **Sockets** mittles **File-Deskriptors**.
		- Verbindungsorientiert -> **read()** und **write()**
		- Verbindungslos -> **sendto(Addr)** und **recvfrom(Addr)**.