[[Sicherungsschicht (Data Link Layer)]].

- Eindeutige Identifizierung der Knoten innerhalb des Direktverbindungsnetzes.
- **Broadcast-Adresse**, Welche alle Knoten im Direktverbindungsnetz anspricht.
	- ff:ff:ff:ff:ff:ff -> 255.255.255
- **Multicast-Adressen** für bestimmte Gruppen von Knoten.
- `Adressen in der Sicht 2 bezeichnet man als MAC-Adressen: Media Access Control.`
- Netzwerkarten besitzen eine ab Werk im ROM hintergelegte MAC-Adresse.
![[MAC-Adressen Aufbau.png]]
- OUI : Organizationally Unique Identifier + Device ID --> Eindeutige MAC-Adressen 
 
 #### Verfahren:
 - [[CRC - Cyclic Redundancy Check]]. (**CRC32 für Ethernet**).
	 -> Ist ein Fehlererkennung verfahren **aber** durch ein passender Wahl des reduktionspolynoms und entsprechendem Verhältnis von Nutzdaten kann er auch bestimmte Fehler korrigieren ( ATM oder Bluetooth)