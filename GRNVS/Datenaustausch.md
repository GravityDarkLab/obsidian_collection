[[ISO_OSI-Modell]].

![[DatenAustausch.png]]

1. Die (N+1)-Schicht nimmt Diesnte der N-Schicht in Anspruch: 
2. Die N-Schicht erhält eine **Interface Data Unit** von der (N+1-Schicht). -> ==N-IDU==.
3. N-IDU enthält aus Sicht der N-Schicht:
	- Nutzdaten -> **Service Data unit (SDU)** -> ==N-SDU==
	- Kontrollinformationen -> **Interface Control Information (ICI)** -> ==N-ICI==.
	zb Länge der SDU oder Adressinformationen.
4. N-Schicht fügt der **Protocol Control Inforamtion (PCI)** für die N-Schicht. -> ==N-PCI==.
5. N-Schicht erzeugt aus PCI und SDU ein **Protocol Data Unit (PDU)** -> ==N-PDU==.
6. Die N Sichit nutzt den Dienst der (N-1)-Schicht und erzeugt ein ==(N-1)-ICI== und übergibt diese zusammen mit mit der ==N-PDU als (N-1)-IDU==.

#### PDU:
Transportschicht ==> **Segmenten**
Vermittelungsschicht ==> **Paketen**
Sicherungsschicht  ==> **Rahmen (Frames)** 


![[Pasted image 20220728170027.png]]

PDUs auf den vier ersten Schichten des OSI-Modells:

1.  Im Layer 4 (Transport Layer) entspricht die PDU dem Segment
2.  Im Layer 3 (Network Layer) entspricht die PDU dem Paket("Datenpaket")
3.  Im Layer 2 ("Data Link Layer") (Data Link Layer) entspricht die PDU dem Frame
4.  Im Layer 1 ("Physical Layer") (Physical Layer) entspricht die PDU dem Bit
5. Ab Layer 5 werden übertragene Inhalte als Daten bezeichnet.
