[[Transportschicht (Transport Layer)]].


IP-Adressen mussen nicht eindeutig sein wenn :
	- Keine Kommunikation mit im Internet befindlichen Hosts möglich sein muss.
	- Die Nicht eindeutigen **privaten IP-Adressen** auf geeignete Weise in **öffentliche Adressen** überstezt werden.

![[NAT Def.png]]

## Was sind private IP-Adressen?
- Sind spezielle Adressbereiche, welche:
	- **Zur privaten Nutzung ohne vorherige Registrierung freigegeben sind**,
	- kommen in unterschiedlichen Netzen.
	- sind auf diesem Grund, weder eindeutig noch zur Ende-zu-Ende-Adressierung zwischen öffentlichen Netzen geeignet sind. (-> **Pakete werden nicht weitergeleitet)**.
-  ![[private IP-Adressen.png]]
- 169.254.0.0/16 **=> Automatic Private IP Adressing**.![[169.254.0.0.png]]

### Verlauf:
![[NAT_Verlauf_1.png]]
![[NAT_Verlauf_2.png]]

**In Allgemein:**
1. PC sendet ein TCP SYN Paket an den Server.
2. Adressüberstezung findet im R statt.
3. R leitet die Nachricht am Server. => Auf Sicht der Server hat der Computer R ein TCP-Verbindung aufgebaut.
4. Server antwortet der Router.
5. Router übersetzt nochmals (anhand der Port Eintrag im NAT-Tabelle) und schickt weiter zur PC.

**==> In Abhängigkeit der gespeicherten Informationen unterscheidet man unterschiedliche Zypen von NAT:**
- **Full Cone NAT:** Speichert Local IP Addr. + Local Prot + Global Port
	-> keine Prüfung der Absender-IP_Adresse oder Ports
- Port Restricted NAT
- Address Restricted NAT
- Port und Adress Restricted NAT
- Symmetric NAT


#### Anmerkungen:
- NAT ist kein Firewall.
- zb. der **Full Cone NAT** kann 2¹⁶ Enträge im NAT-Tabelle haben. Aber hängt grundsätzlich von Router ab.
- Dynamische erzeugte Mappings werden nach einer gewissen Inaktivitätszeit gelöscht.
- Man kann die Mappings statisch erzeugen -> **Port Forwarding**.
