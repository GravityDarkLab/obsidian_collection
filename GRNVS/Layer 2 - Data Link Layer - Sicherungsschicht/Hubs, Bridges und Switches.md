[[Sicherungsschicht (Data Link Layer)]].

- [[Hubs]]
- [[Switches]]
- [[Bridges]]

### Welche Einfluss haben Hubs, Brücken und Switches auf die Kollisionsdomäne?
- Hubs **verbinden** Netzsegmente auf der **physikalischen** Schicht, wodurch eine **==gemeinsame==** Kollisionsdomäne entsteht (Bus).
- Brücken und Switches **==unterbrechen==** Kollisionsdomänen, indem Rahmen nur dann in das jeweils andere Netzsegment weitergeleitet werden, wenn sich der jeweilige Empfänger in diesem Segment befindet.(Die Weiterleitungsentscheidungen werden auf Basis der Ziel-**MAC**-Adresse getroffen. **Durch Beobachtung des Datenverkehrs kann eine Brücke mit der Zeit lernen, welche Knoten sich auf welcher Seite befinden.)**
- **Switches sind im Wesentlichen Brücken mit mehr als zwei Ports**. Sie unterbrechen daher ebenfalls Kollisionsdomänen.

#### Broadcastdomäne:
- **Router** unterbrechen Broadcastsdomäne.
- **Switches und Bridges** unterbrechen es nicht.

## Bei mind. 3 verbundenen Hosts; Wann sind Kollision und Broadcastsdomäne identisch?
- Hosts verbunden über ein Router.
- Hosts verbunden durch ein Hub.
- Hosts und ein Router verbunden über ein Hub.