[[Sicherungsschicht (Data Link Layer)]]
#### Graphtheorie:
- Gerichtete & Ungerichtete Graphen.
- Symmetrisch -> ungerichtete Graph.
- Asymmetrisch -> gerichtete Graph.
- Pfad
- Pfadkosten
- Knoten
- Kanten
- Durch Matrizen beschrieben:
	- Adjazenzmatrix. (0 und 1)
	- Distanzmatrix (0 : sich selbst ; c : pfad kosten ; ∞ : keine direkte verbindung.)
- **Shortest Path Tree (SPT).
	- Dijkstra’s Shortest Path Algorithm
	- Bellman-Ford
	- Verbindet einen Wurzelknoten mit jeweils minimalen kosten mit jedem anderen knoten des Netzwerks.
- **Minimum Spanning Tree (MST).
	- Prim's Algorithm
	- Verbindet alle Knoten des Netzwerks mit insgesamt minimale kosten.

#### Wichtige Topologien:
- `Point-to-Point`.
- `Kette`.
- `Stern`.
- `Vermaschung (Mesh)`.
- `Baum`.
- `Bus`.