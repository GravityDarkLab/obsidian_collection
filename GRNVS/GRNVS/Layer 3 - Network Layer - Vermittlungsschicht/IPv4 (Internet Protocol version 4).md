[[Adressierung im Internet]].
[[Adressierungsarten]].

zb **192.168.1.3**
- 192 / 168 ... = **Oktett**
- 3 -> Identifiziert einem Host innerhalb einem Netzwerk.
- 192.168.1 -> Netzwerksadresse

 ![[Layer 3 PDU.png]]
 
 ![[IPv4 Header.png]]
 - Version : 4 oder 6
 - IHL : IP Header length (x4B)
 - TOS : Type of service :: 0x00 for ICMP
 - Total Length : IHL + Daten 
	- max : 65 535 B 
- Identification  : ID
- Flags : 0 | DF | MF
- Fragment offset : muss vielfachen von 8 sein
- TTL : time to live --> verhindert endlos kreisende Paketet infolge von Routin Loops.
- Protocol : 
	- 0x06 -> TCP
	- 0x11 -> UDP
	- 0x0001 -> ICMP
- Checksum :  TTL-- => Checksum++

 ==> **==IP-Header length muss ein vilfachen von 4B sein==**.


#### Host-Byte-Order und Network-Byte-Order:
- Big Endian : 256 = 0x100
- Little Endian : 256 = 0x001
==> Vor dem Versenden (Empfangen) müssen Daten aus der Host-Byte-Order (little Endian bei x86) in Network-Byte-order (big endian) konvertiert werden.
- ==Konvertierung betrifft nicht die 1 B lange Felder (src und dest Adrressen)==.
- 16 bit : 
	- ntohs(0x100) = 0x001
	- htns(0x001) = 0x100
- 32 bit :
	- ntohl()
	- htonl()

#### Fragen : 
Angenommen der Sender kennt nur die IP-Adresse des Ziels :
- MAC Adresse des Next-Hops bestimmen --> **[[Adressauflösung]]**. (auf [[Sicherungsschicht (Data Link Layer)]]).
- woher weiß Host A1, dass er B über R erreichen kann ? --> **Routing Table**.
- falls der Ziel nicht direkt an R angeschlossen --> **Routing Table**.
- Erzeugung der **Routing Table** --> **Statisches Routing / Routing-Protokolle.**
- Falls R mehrere Wege zu einem Ziel kennt --> **Longest Prefix Matching**.
- Unterteilung eine IP-Adresse --> **[[Classful Routing]], [[Classless Routing]], [[Supernetting]]**.
- Woher kennt der Sender die IP Adresse des Ziels --> **[[DNS]]**.


#### Ziel nicht im selben Netz:
- Jeder Host sollte einen Router zum Internet :: **Default Gateway** :: kennen an das er alle Pakete schickt.
1. Host A1 erkennt, dass 192.168.2.2 nicht im eigenen Netz liegt. Sein Default-Gateway ist 192.168.1.254
2. Host 1 löst die MAC-Adresse zu 192.168.1.254 auf --> [[Adressauflösung]].  (**ARP**).
3. Host 1 sendet das Datenpaket an R : ( MAC von R + Ziel IP von Host 2)
4. R akzeptiert das Paket, bestimmt das ausgehende Interface und leitet das Packt weiter an Host 2 (**[[Adressauflösung]]** nochmals).

![[Merke.png]]


- IP-Protokoll unterstützt das Senden von Paketen. Dabei kann es zu fehlern kommen:
	- Routing-Schleife.
	- Router kennt keinen Weg zum Zielnetz.
	- MAC adresse auflösungsfehler.
**==>Lösung:  [[Internet Control Message Protocol (ICMP)]].**

#### Woher bekommen Hosts eigentlich ihre IP-Adresse?
- Statische Konfiguration.
- Dynamisch von einem **[[DHCP]]-Server**.