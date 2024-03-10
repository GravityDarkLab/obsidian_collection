[[IPv4 (Internet Protocol version 4)]].

==DHCP== : **Dynamic Host Configuration Protocol**.
1. Client sendet **DHCP-Discover** (Layer 2 Broadcast).
2. DHCP-Server antwortet mit **DHCP-Offer**, wodurch er dem Client eine IP-Adresse anbietet.
3. Client antwortet mit **DHCP-Request**, wodurch er die angebotene Adresse anfordert.
4. DHCP-Server antwortet mit **DHCP-ACK** -> freigaben.
													**DHCP-NACK** -> ablehnen.
			==> **DORA** -> **D**iscover**O**ffer**R**equest**A**cknowledge.

![[Client server DHCP.png]]

- Die vom DHCP zugewiesen Adresse :: ==Lease==. Die ist zeitlich begrenzt und Client erneuern ihre Lease in regelmäßigen Abständen.