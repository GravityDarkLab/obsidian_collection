[[Multiplexing]].
[[Medienzugriff]].

### Konkurrierender zugriff:
- **ALOHA** : 
	- jede Station sendet an eine zentrale Station, sobald Daten vorliegen.
	- Senden zwei Stationen gleichzeitig -> Kollisionen.
	- out-of-band Bestätigungsverfahren.

- **Sloted ALOHA**
	- **Sende nur zu Zeitslots**.
	- Station beginnt im nächsten Zeitslot zu senden, ungeachtet dessen, ob bereits eine Übertragung staatfindet.
- **Vorteile gegenüber ALOHA:**
	- Kollisionen finden nur innerhalb eines Zeitslots statt.
	- Geringe Kollisionswahrscheinlichkeit.

- **[[CSMA]].**  
	- Listen Before Talk.
	==> **nicht derterministsche** Verfahren und ist der zugrund liegende Medienzugriffsverfahren für **Ethernet**.
- **[[CSMA-CD]]** ==> IEEE 802.3 Ethernet.
- **[[CSMA-CA]]** ==> IEEE 802.11 WLAN.
- **[[RTS und CTS ]]**

### Geregelter zugriff:
- **CSMA/CA mit [[RTS und CTS]]** ==> IEEE 802.11 WLAN.
- **[[Token Passing]]** ==> IEEE 802.5 Token Ring, Fiber Distributed Interface (FDDI


### ALOHA vs CSMA:

- Bei ALOHA wird der Verlust eines Rahmens dadurch erkannt, dass der Absender keine Bestätigung erhält. Ein derartiges Quittungsverfahren gibt es bei CSMA/CD nicht. Stattdessen nimmt ein Sender bei CSMA/CD an, dass ein Rahmen erfolgreich übertragen wurde, falls während der Übertragung keine Kollision aufgetreten ist.

- Im konkreten Fall hat PC1 allerdings die Übertragung abgeschlossen, bevor ihn die Übertragung bzw. das JAM-Signal von PC3 erreicht.PC1 erkennt daher die Kollision nicht und geht fälschlicherweise von einer erfolgreichen Übertragung aus.

### Wie lautet für CSMA/CD die Bedingung, dass ein Knoten eine Kollision rechtzeitig erkennen kann?
- **ts ≧ 2.tp_max*** Nur so ist sichergestellt, dass ein Knoten noch sendet, wenn er das „**Störsignal --> JAM**“ des am weitesten von ihm entfernten Knoten empfängt, der seinerseits unmittelbar vor der „Ankunft des ersten Bits“ selbst angefangen hat zu senden.


### Simplex vs Half-Duplex:
- Simplex : Handelt sich um eine unidirektionale Anwendung der Medium.
- Half-Plex : handelt sich um eine bideriktionale Anwendung der Medium.