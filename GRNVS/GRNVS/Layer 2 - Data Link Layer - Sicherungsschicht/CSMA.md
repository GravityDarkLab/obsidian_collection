[[Zeitmultiplexverfahren]].
[[Binary Exponential Backoff]].

CSMA : **Carrier Sense Multiple Access**

**-> Beginne erst dann zu senden, wenn das Medium frei ist <-**

**Typen:**
* ==1-persistentes== CSMA :
				1. Medium frei -> Begine übertragung. ( übertrage mit (p=1) oder verzögere mit (1-p = 0))
				2. Medium belegt -> warte bis wieder frei.
* ==p-persistentes== CSMA :
				1. frei -> übertrage mit (p) oder verzögere mit (1-p)
				2. belegt -> warte bis frei.
* ==nicht-persistences== CSMA:
				4. frei -> Übertragen
				5. belegt -> Warte eine Zufällige Zeitspanne.