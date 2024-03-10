[[Zeitmultiplexverfahren]]

- Kollisionsfreie Übertragung durch Weitergabe eines **Tokens**.
- Logischen **Ring**.
- Will eine Station senden, so nimmt sie das Token vom Ring und darf danach als **einzige** station im Ring übertragen.
- Es gibt eine **Monitor-station**.

###### Vorteile:
- Sehr effizient, da keine kollisionsbedingten Wiederholungen gibt.
- Garantierte maximale Verzögerung (Determinismus)

###### Nachteile:
- Fehlarhaftes verhalten eines Knotens stört die gesamte Kommunikation im Ring.
- Zusammenschaltung der Stationen zu einem Ring ist aufwendig.
- Geht das Token verloren, muss es durch ein Neues ersetzt werden.
- Übertragungsverzögerung gröser als bei CSMA, da Sender auf Token warten muss.