[[IPv4 (Internet Protocol version 4)]].

Host 1 will eine nachricht an Host 2 senden. Host 1 kennt die IP-Adresse der Host 2.
- Host 1 sendet einen **ARP (Adress Resolution Protocol)** Request.
- Host 2 antwortet mit einem **ARP Reply**.

- ARP Request wird an die MAC-Broadcast-Adresse ff:ff:ff:ff:ff:ff geschickt und an alle angeschlossenen Hosts weitergeleitet.
- Der ARP-Reply wird als MAC-Unicast versendet (Adressiert an Host 1).

![[ARP-Paket IPv4 Ethernet.png]]


