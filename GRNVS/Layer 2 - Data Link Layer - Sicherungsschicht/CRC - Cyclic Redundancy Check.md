[[Adressierung und Fehlererkennung]].

- Ist ein **Fehlererkennender** Code aber **NICHT Korrigierend**.

###### Vorteile:
Viele Fehlermuster werden erkannt.
1 Bit und kurze Fehler gut erkennbar.
Einfach in Hardware zu implementieren.

##### Nachteile:
Fehler die Vilefach des Relationspolynoms sind, werden nicht erkennt.
Brust Fehler i.A nicht erkennt.

#### Verfahren:
- Man kann der Fehler erkennen, in dem man den rest der polynomdivision != 0 ist. (Nachricht XOR Fehler dann division.)
1. Nachricht um deg(r(x)) padden
2. Binäre Polynomdivision durch r(x) : **XOR** --> Ergebnisse ist die Check summe 😁.

##### Zeigen dass selbst 1 bit-fehler nicht korrigierbar ist :
1. Wie viele Fehler Muster haben wir ? ( bei zb 1 bit fehler haben wir 11 Fehler Muster).
2. reduktionspolynom grad ? (zb deg(r(x))=3 -> 2³ -1 = 7 < 11 => **keine eindeutige Zuordnung.** )

##### Wofür brauchen wir r(x) ?
=> fehler in der durch die Checksumme gesicherte Nachricht werden auf Rest modulo r(x) abgebildet.

##### Wann ist r(x) irreduzibel ?
=> Gdw es sich nicht durch die Multiplikation (modulo 2) aus zwei kleineren Polynom darstellen lässt.
	zb : ( x² + 1 )² mod 2 = (x²+2x+1) mod 2 = x²+1

**Wählt man ein irreduzible r(x)** dann gilt, dass modulo r(x) die Großmöglichte Anzahl von resten in Körper der restklassen modulo r(x) liegen.

##### Weswegen bei bei einem Reduktionspolynom für CRC häufig kein irreduzibles polynom wählt ?
=> Durch spezielles Wahl des reduktionspolynomes können bestimmte fehlermuster besser oder Schlechter erkannt werden.

##### Welche Fehler erkennet CRC nicht zuverlässig oder gar nicht ?
- Fehler die länger sind als n.
- Fehler, die aus mehreren [[Brusts]] bestehen.
- Alle Fehler, die ein Vielfaches des reduktionspolynomes sind.