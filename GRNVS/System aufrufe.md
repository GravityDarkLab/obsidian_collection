- select()
	- Überwacht mehrere Sets von Filedeskriptoren auf Aktivität.
	- Mofifiziert die Sets, sodass nur aktiv gewordene Filedeskriptoren enthalten sind.
	- Gibt Anzahl aktiv gewordenen Filedeskriptoren (-1 bei Fehler und 0 bei TimeOut) zurück.

### Socketserstellung:
- **TCP**: 
	1. socket()
	2. connect()
- **UDP**:
	1. socket()
	2. bind()