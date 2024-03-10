[[IPv6 (Internet Protocol version 6)]].


![[SLAAC.png]]

- **SLAAC** heißt ==**stateless**==, da die Adressen nicht von einem Server vergeben werden(Globale Adressen können auch über DHCPv6 vergeben werden).

### Bestimmung:
1. Präfix fe80::/10 --> Subnet ID (54 bit auf 0 Setzen) --> /64
3. SubnetID + Ersten 3B aus MAC + **ff:fe** + 3 letzten B aus MAC.
4. Das vorletzte Bit in ersten Byte der MAC OUI wird invertiert wegen : 
	- MAC : 0 -> global unique.
				  1 -> Localy administrated.
	- IPv6 : 0 -> Localy administrated.
				  1 -> global unique.