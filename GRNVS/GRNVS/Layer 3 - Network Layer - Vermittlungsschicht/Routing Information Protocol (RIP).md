[[Wegwahl (Routing)]].

#### Eigenschaften:
- Einfaches Distanz-Vektor-Protokoll
- Einzige Metrik: **Hop Count**. **{Bellman-Ford}**
- **Hop Count** Limit von 15, weitere entfernte Ziele sind nicht erreichbar.

#### Funktionsweise:
- Router senden in regelmäßigen Abständen (standard = **je 30s**) den Inhalt ihrer Routingtabelle an die Multicast-Adresse **==224.0.0.9==** .
- Alle Geräte mit dieser Multicast-Adresse akzeptieren das Update.
- Jeder RIP Router akzeptiert diese Update nachrichten, inkrementiert die Kosten der Routen um 1 und vergleicht die Routen mit bereits vorhandenen Routen aus seiner Routingtabelle.
- Bleiben fünf aufeinanderfolgende Updates von einem Nachbarn aus, so werden alle Routen über diesen next Hop aus der routingtabelle entfernt.

**==> jeder Router wird eine kürzeste Route zu jedem anderen Router kennenlernen**.


#### Probleme:
- Bis jeder Router den besten Next Hop bestimmen kann, dauert es mehrer Runden.
- Die maximale entfernung zwischen zwei Routern beträgt **15 Hops** bei RIP.
- Da upodates nur alle 30s verschickt werden, ergibt sich eine maximale Verzögerung von 15*30=7,5min.
- **[[Counnt to infinity]]**.

 ==> **Lösung**: **==Triggered Updates==**.
	 - Sobald ein Router eine Änderung an seiner Routingtabelle vornimmt, sendet er sofort ein Update.
	 - Dies führt zu einer Welle von Updates durch das Netzwerk.
	 - Konvergenzzeit wird reduziert, aber das Netzwerk während der Updates stark belastet.

 ###### <u>Lösungsansätze</u> für Count-to-Infinity:
 ![[Lösungsansätze für Count-to-Infinity.png]]