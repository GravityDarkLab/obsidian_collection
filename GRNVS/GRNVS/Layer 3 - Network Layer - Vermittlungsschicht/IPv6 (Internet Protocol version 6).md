[[Adressierung im Internet]].
[[Adressierungsarten]].

### Änderungen gegenüber IPv4:
- **Der sender fragmentiert bevor er sendet**
- Größere Adressraums von 2³² aud 2¹²⁸.
- Vereinfachung des headformats.
- Änderung bei der IP-Fragmentierung.
- Flexibilität durch Extension Header.
- Stateless Address Autoconfiguration (SLAAC) mittels ICMPv6
- Möglichkeit für Stateful Autoconfiguration (DHCPv6)
- Nativer Multicast.

==**Shreibweise: 
	- IPv4 : je eine 8 bit lange gruppe kommt ein Punkt (.) und je Gruppe wird in dezimal dargestellt.
	- IPv6 : je 16 bit lange grupe kommt ein ( : )  und je Gruppe wird in Hex dargestellt.**==

![[IPv6 Aufbau.png]]
![[Notation.png]]

#### Headerformat:
![[IPv6 Header.png]]
- Version : 6
- Traffic Class: = TOS beim IPv4 -> wird zur Verkehrspriorisierung und Quality of Service verwendet.
- Flow Label: wird für von Routern verwendet, um Zusammengehörende Pakete (Flows) auf Sicht 3 zu erkennen.
- Payload Length : Totale grosse ( Header + Extension Header) -> vielfachen von 8 B.
- Next Header: Kann ein L4-Header (TCP/UDP), ein ICMPv6 Header oder ein IPv6 Extension Header.
- Hop Limit: =TTL beim IPv6 (weiterleiten -> dekrementiert) :: Time To Live
- Src : 128bit
- Dest : 128bit

#### Extension Header:
- Erlauben es zusätzliche Layer 3 Informationen in einem IPv6 packet hinzufügen.


### Fragment Header:
==**MTU**== : **Maximum Transmission Unit (MTU)**
--> Überschreitet eine L3-PDU diese Größe, muss die L3-SDU fragmentiert.
--> Dazu gibt einem **Fragment header**: 
![[IPv6 fragment header.png]]
- Fragment Offset muss ein vielfach von 8 B sein.

### Besondere IPv6-Adressen:

![[besondere ipv6 Adressen.png]]![[IPv6 Multicast.png]]

### Mapping von Multicast IPv6 Adressen auf MAC-Adressen:
- IPv6 Adressen haben den Präfix ff00 :: /8
1. Die ersten Oktette der MAC-Adresse werden auf 33:33 gesetzt.
2. Die letzten 4 Oktette der Ethernetadresse werden die letzten 4 Oktette der IPv6.
	==**Beispiel**: ff02::1:ffc6:938b ---> **33:33**:ff:c6:93:8b==


**IPv6 erlaubt eine automatische Konfiguration von Hosts innerhalb eines einzelnen Subnetzes ==> [[Stateless Address Autoconfiguration (SLAAC)]]** .
**[[Internet Control Message Protocol v6 (ICMPv6)]]**.