[[Transportschicht (Transport Layer)]].
[[TCP (Transmission Control Protocol)]].

- **Verbindungsphasen**:
1. Verbindungsaufbau -> **Handshake**.
2. Datenübertragung
3. Verbindungsabbau -> **Teardown**.

- **3-Way-Handshake**:	
![[3-Way-Handshake.png]]

### Round Trip Time (RTT): => Umlaufverzögerung zwischen Sender und Empfänger.

# Sliding-Window-Verfahren:
- **Idee**: Teile dem Sender mit, wie viele Segmente nach dem letzten bestätigten Segment auf einmal übertragen werden dürfen, ohne dass er auf eine Bestätigung warten muss.
- **Vorteile**: 
	- RTT kann effizienter benutzt sein.
	- Flusskontrolle -> datenrate steuern.
	- Staukontrolle -> durch Algorithmen verhindert man eine Überlastung der netz.
- **Probleme**:
	- Sender und Empfänger müssen mehr Zustand halten.
	- Der Sequenznummernraum ist endlich.

![[Sliding-Window-Verfahren.png]]

## Wie wird mit Segmentverlusten umgegangen?
- **Go-Back-N**.
	- Akzeptiere nur die nächste erwartete Sequenznummer.
	- Alle anderen Segmente werden verworfen.
	- ![[Go-Back-N.png]]

- **Selective-Repeat**.
	- Akzeptiere alle Sequenznummern, die in das aktuelle Empfangsfenester fallen.
	- Diese müssen gepuffert werden, bis fehlende Segmente erneut übertragen wurden.
	- ![[Selective-Repeat 1.png]]
- ![[Selective-Repeat 2.png]]

**=> Sequenznummernraum muss so gewählt, dass wiederholte Segmente von neuen Sgmenten unterschieden werden können**.

