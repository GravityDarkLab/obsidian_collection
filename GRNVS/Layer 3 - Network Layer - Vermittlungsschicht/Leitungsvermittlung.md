[[Vermittlungsarten]].
[[Vermittlungsschicht (Network Layer)]]

#### 3 Phasen:
1. **Verbindungsaufbau**: 
	- Austausch von ==Signalisierungsnachrichten== zum Aufbau einer dedizierten Verbindung zwischen Sender und Empfänger.
	- Dieser Schritt beinhaltet die **==Routing==**, welche **vor Beginn der Datenübertragung durchgeführt wird**.
2. **Datenaustausch**
	• Kanal steht den Kommunikationspartnern zur exklusiven Nutzung bereit.
	• Auf die Adressierung des Kommunikationspartners kann während der Übertragung weitgehend verzichtet werden (<u>Punkt-zu-Punkt-Verbindung</u>).
3. **Verbindungsabbau**
• Austausch von Signalisierungsnachrichten zum Abbau der Verbindung.
• Die durch die Verbindung belegten Ressourcen werden für nachfolgende Verbindungen freigegeben.

#### Vorteile:
• Gleichbleibende Güte der dedizierten Verbindung nach dem Verbindungsaufbau.
• Schnelle Datenübertragung.
(errinert an [[TCP (Transmission Control Protocol)]] ei [[Verbindungsorientiert]]e Protocol)
#### Nachteile:
- Ressourcenverschwendung, da leitung zur exklusiven Nutzung belegt wird.
- Verbindungsaufbau ist komplex.
- Höhere Aufwand beim Schalten physikalischer Verbindungen.


![[Leitungsvermittlung.png]]