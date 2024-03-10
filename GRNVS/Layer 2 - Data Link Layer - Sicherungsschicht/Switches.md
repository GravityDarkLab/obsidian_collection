[[Hubs, Bridges und Switches]].

 ==> **Verteiler an die Ziel-adresse**. 
 ==> für Hosts transparent.
 ==> **Ein Broadcast (ff:ff:ff:ff:ff:ff) die wir von allen Hosts empfangen**
 ==> benötigt keine eigene MAC-Adresse.
 ==> 2 Typen : **Store-and-Forward** | **Cut-Through**.
 ==> Eine Lösung für [[Schleifen]], da sie das **Spanning Tree Protocol** unterstützen. 

- Zwei gruppen von Hosts, die jeweils über Hubs verbunden sind, werden durch einen **Switch** gekoppelt.
- Ein Switch mit **nur 2 Ports**, nennt man auch ==[[Bridges]]==.

##### Verfahren:
1. Learning-Phase: Der Switch verhalt wie ein Hub mit 2 Ports und merkt sich über welchen Port ein Rahmen empfangen wurde.
2. Der Switch ordnet den **Port 0 und 1** die **MAC-Adressen der Knoten** zu, die an den jeweiligen port angeschlossen sind.
3. Die Ziel-Adresse eingehender Rahmen wird mit den Einträgen in der **Switching-table** verglichen.
4. Ist die vorhanden, wird sie an an den betreffenden Ziel-Port weitergeleitet sonst an alle Ports außer der sender.

##### Warum benutzen wir ein Switch?
**Bild 1:** (auch [[Bridges]])
- ==unterbricht **Kollisiondomänen**== (Segmentierung).
- Wenn der Switch alle angeschlossenen Geräte kennt, darf in jedem der beiden segmente ==jeweils ein Knoten zur selben Zeit senden==.
-  Ist pro Switchport genau ein Host angeschlossen, spricht man von **Microsegmentation** oder einem **vollständig geswitchtem Netz** (heute der Regelfall).
- In diesem Fall können ==jeweils== **zwei beliebige Hosts** gleichzeitig miteineinander kommunizieren.

![[Switches.png]]

#### Anwendung:
- Netzsegmente mit **unterschiedlichen Zugriffsverfahren** zu koppeln (transparent).
	- FDDI-Ethernet-Switch : Token Passing <-> CSMA/CD
	- WLAN Access Point : CSMA/CD <-> CSMA/CA


##### Was bedeutet transparent?
Angeschlossene Stationen bemerken **nicht**, dass ein Switch verwendet wird.

**==Voraussetzung==: Die MAC-Adressen müssen „kompatibel“ sein, um den jeweiligen Empfänger über seine MAC-Adresse identifizieren zu können**.