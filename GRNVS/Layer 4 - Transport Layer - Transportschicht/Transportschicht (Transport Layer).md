[[ISO_OSI-Modell]].

- **Hauptaufgabe**: 
	- ==[[Multiplexing]]== von Datenströmen unterschiedlicher Anwendungen bzw. Anwendungsinstanzen.
	- Bereitstellung  von **Transportdienste**.
	- Bereitstellung von Mechanismen zur **Stau-** und **Flusskontrolle**.


-------------------------------------------------------------------------------
#### Transportdienste:
- **Verbindungslos -> Best Effort**: => [[UDP (User Datagram Protocol)]].
	- Keine Sequenznummern, keine Wiederholung und keine Garantie der richtigen Reihenfolge.
- **[[Verbindungsorientiert]]**: => [[TCP (Transmission Control Protocol)]].
	- Wiederholung bei Fehlern.
	- Garantie der richtigen Reihenfolge.
- [[UDP vs TCP]].

-------------------------------------------------------------------------------
#### Stau- und Flusskontrolle:
- **Staukontrolle (Congestion Control): =>** Reaktion auf drohende Überlast im Netz.
- **Flusskontrolle (Flow Control): =>** Laststeuerung durch den Empfänger.

-------------------------------------------------------------------------------
- **[[NAT (Networ Address Translation)]]**.