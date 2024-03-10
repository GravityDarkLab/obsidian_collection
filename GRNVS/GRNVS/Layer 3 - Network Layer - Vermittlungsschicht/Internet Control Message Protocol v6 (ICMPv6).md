[[IPv6 (Internet Protocol version 6)]].

- Die ersten 32bit sind immer vorhanden.
- Gesamtlänge der Nachricht hängt von Type und Code der ICMPv6 Nachricht ab.

![[ICMPv6 header.png]]

- IPv6 bietet mit seiner **Neighbor Discovery** eine Reihe von Funktionalitäten :
	- Adressauflösung, Duplicate Address Detection und Neighbor Unreachability Detection
		--> **==Neighbor Solicitaion==** and **==Neighbor Advertisements==**.
	- Automatisches Auffinden von Routern innerhalb des lokalen Netzsegments, **Adress-Präfixen** und Parameter konfiguration:
		--> ==**Router Discovery**== and ==**Router Advertisements**==.
	- Umleitung zu anderen Gateways: **==Redirects==**.
	
	
	![[ICMPv6 Discovery.png]]
![[ICMPv6 Reply.png]]