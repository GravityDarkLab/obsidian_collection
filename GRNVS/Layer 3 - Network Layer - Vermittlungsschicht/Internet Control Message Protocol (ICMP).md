[[IPv4 (Internet Protocol version 4)]].

- Benachrichtigt der Absender über solche Fehlern.
- Erreichbarkeit prüfen --> **Ping**.
- Redirect.


![[Allgemeiner ICMP-Header mit vorangestelltem IP-Header.png]]

### Ping:
- Echo Request + Echo Reply
- Sender wählt ein zufälliger ID der für jedes Echo Request inkrementiert wird.
- Fehlgeschlagen --> ICMP mit entsprechende Fehlercode Zurückgeschickt.

### ICMP Time Exceeded.
- wenn der TTL-Feld 0 erreicht wird der packet weggeworfen.

### Traceroute mit ICMP:
- Host 1 sendet ICMP Echo Request an Host 2
- TTL der ICMP Echo Request wird auf 1 gesetzt.
- danach schrittweise um 1 erhöht.
- Router entlang des Pfads von Host 1 zu 2 werden schrittweise die Pakete verwerfen und ein TTL Exceeded an Host 1 schicken -> Anhand der IP-Quelladresse diser Fehlernachrichten kann Host 1 den Pfad hin zu Host 2 nachvollziehen.  **--> benutzt für [[Routing Information Protocol (RIP)]].