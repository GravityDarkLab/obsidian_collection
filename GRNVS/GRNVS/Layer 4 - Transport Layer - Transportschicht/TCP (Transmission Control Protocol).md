[[Transportschicht (Transport Layer)]].
[[UDP vs TCP]].
[[Verbindungsorientiert]].


**Bei TCP wird das Sendfenster (ws) in Abhängigkeit des Empfangsfenester (wr) sowie des Staukontrollfenesters (wc) gewählt. ==> Ws = min(Wr,Wc)**.

	Da das Sendefenster als Minimum aus Empfangs- und Staukontrollfenster gewählt wird und der Empfänger dem Sender sein Empfangsfenster über das **Receive-Window-Feld **mitteilt, welches auf 16 bit beschränkt ist, ist auch das Sendefenster auf einen Maximalwert von (2^16 − 1) B = 65535 B beschränkt.

- Ist ein [[Verbindungsorientiert]]e Übertragung.
- Gesichert / stromorientierte Übertragung mittels **Sliding-Window** und **Selective Repeat** sowie **Fluss-** und **Staukontrolle**.
- Es werden bei TCP nicht ganze Segmente sondern einzelne Byte bestätigt -> **Stromorientiert**.

![[TCP-Header.png]]
- **Src und Dest Port**gleich als bei UPD.
- S**equence Number** und **Ack Numbe**r dienen der gesicherten Übertragung. 
- ACK number gibt das nächste erwartete Byte an.
- **Offset** -> TCP-Header Length (Vielfachen von 4B)
- **Reserved** = 0
- **URG** -> Urgent Flag.
- **ACK** -> Acknowledgement Flag
- **PSH** -> Push
- **RST** -> Reset => Abbruch einer TCP-Verbindung.
- **SYN** -> synchronization => Inkrementiert Sequenz- und Bestätigungsnummern um 1 obwohl keine Nutzdaten transportiert werden.
- **FIN** -> Finish => Verbindungsabbau ( Inkrementiert Sequenz- und Bestätigungsnummern um 1 obwohl keine Nutzdaten transportiert werden).
- **Window** => Größe des aktuellen Empfangsfenesters in Byte.
- **Checksum** => braucht ein Pseudo header.
- **Urgent Pointer**.
- **Options** : zb Window Scaling / Maximum Segment Size (MSS).

**MSS : gibt die maximale Größe eines TCP-Segments (Nutzdaten ohne TCP header) an. ≠ MTU (Layer 2) die maximale Größe (mit Header) angibt.**
**=> MSS sollte so gewählt werden, dass keine IP-Fragmentierung beim Senden notwendig ist.

![[TCP Beispiel.png]]

## TCP-Flusskontrolle:
![[TCP-Flusskontrolle.png]]

## TCP-Staukontrolle:
![[TCP-Staukontrolle.png]]
**Verlauf**:
1. **Slow-Start**:
	- Für jedes bestätigte Segment wird Wc um **eine** MSS Vergrössert. (und dann vedoppelt)-> **Exp(x) Wachstum** bis **Congestion Threshold** erreicht ist.
2. **Congestion Avoidance**:
	- Für jedes bestätigte Segment wird Wc um (**1/Wc**) MSS vergrössert -> **Linearem Wachstum** des Staukontrollfenesters in der RTT.

## TCP-Varianten:
- Tahoe
- Reno
- New Reno
- Cubic
- ...

## TCP RENO:
![[TCP RENO.png]]![[TCP Anmerkungen.png]]