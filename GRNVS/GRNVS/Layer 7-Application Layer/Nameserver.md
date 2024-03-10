[[DNS]].

- Ist eine verteilte Datenbank die von einer großen Anzahl von servern gespeichert, wobei jeder Server nur einen kleinen Teil des gesamten namespaces kennt.
- Ist in **==Zonen==** unterteilt:
	- Teilbäume
	- Nameserver bezeichnet man als autorativ für die jeweiligen Zonen
	- Diselbe Zone kann auf mehrern Nameserver gespeichert sein.
	- es gibt einen **primären Nameserver**, auf dem Änderungen an einer Zone vorgenommen werden können, sowie beliebig viele **sekundäre Nameserver**, welche über Kopien der Zone verfügen.

--> ==Nameserver erwarten eingehende verbindungen auf **Port UDP/TCP 53**==.
		- Anfragen : UDP 53
		- Anfragen größer als 512B -> TCP 53
		- Zone transfer -> TCP 53