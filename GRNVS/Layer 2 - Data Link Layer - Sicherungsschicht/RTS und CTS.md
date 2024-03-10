[[Zeitmultiplexverfahren]].

**Request to send** and **Clear to send**.

- Bevor ein Knoten eine Nachricht übertragt, wird ein RTS an die Basisstation geschickt.
- Nur wenn die Basisstation mit einem CTS antwortet, darf dir Übertragung beginnen.
 
 ##### Vorteile: 
 - kollisionen werden reduziert.
 ##### Nachteile:
 * Wenn CTS nicht empfangen ist, können kollisionen noch auftreten.
 * RTS/CTS nimmt vorab Zeit in Anspruch, was die maximal erzielbare datenrate reduziert.
 