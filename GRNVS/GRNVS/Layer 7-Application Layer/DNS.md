[[Anwendungsschicht (Application Layer)]].

- Besteht aus:
	- Der **[[Domain Namespace]]**. -> hat eine Baumstruktur.
	- **[[Nameserver]]**. -> Speichert informationen über den Namensraum.
	- **[[Resolver]]**. -> Durch Anfragen an Nameserver Informationen aus dem Namespace extrahieren 


- **[[Resource Record]]**.

- **[[Reverse DNS]]**.

### Was versteht man unter DNS?
Entweder Ein Resolver oder ein Namenserver.

### Wozu Dient das DNS?
Auflösung von Fully Qualified Domain Names (FQDNs) zu IP-Adressen.

### Was ist ein Nameserver:
Ein Nameserver ist ein Autorativer server für eine DNS Zone, der alle Nameserver unter dieser Zone kennt und diesem vertraut.

### Was ist ein Resolver:
Ein Resolver stellt Anfragen per iterative Namenauslösung an der Nameserver und gibt die aufgelösten Ressource zurück --> **Rekursive DNS**.

### FQDNs?
Ein Domain Name der Relativ zum Root eingegeben ist.

### Was ist ein MX-Recrod?
Angabe eines Mailserver als FQDNs.

### Was für Transportsprotocol benutzt der DNS?
- Es wird gewöhnlich der UDP benutzt da der TCP verbindung zusätzliche Zeit braucht wegen der **3-way-handshake**. 
- Bei größere als 512B Payloads wird der TCP benutzt, da der erneute übertragung von 512B zeit brauchen wird.

### Prozess der Iterativen namensauslösung:
Ein Resolver löst DNS Requests Zone für Zone beginnend beim Root durch iterative Anfragen an die jeweils authoritativen Nameserver auf, welche jweils entweder mit den autoritativen Nameservern der nächsten Zone oder (sofern schlussendlich bekannt) die Antwort auf die die Anfrage liefern.

### Wie ist das Domain Name System hinsichtlich der Privatsphäre der Nutzer zu bewerten?
Das DNS arbeitet unverschlüsselt und erlaubt es so allen Parteien, die Netzwerkverkehr mitschneiden können, umfangreiche Nutzungsprofilezu erstellen.

### Wie ist eine iterativen Namensauflösung hinsichtlich Vertrauenswürdigkeit und Resistenz gegen Manipulation zu bewerte?
Da ein Resolver prinzipiell nur vertrauenswürdige Nameserver anfrägt, sollte auch die Namensauflösung vertrauenswürdig sein. Eine Manipulation auf dem Weg durch das Internet der Anfragen/Antworten kann dabei natürlich nicht ausgeschlossen werden.

### Welche Auswirkung könnte eine komplette Verschlüsselung des DNS-Datenverkehrs auf die verschiedenen Parteien im Internet haben?
Nur noch Resolver können Nutzerprofile erstellen. Durch diese Zentralisierung der Daten werden diese wertvoller