[[DNS]].

- **Resolver** sind **Server**, die die Informationen aus dem DNS extrahieren und das Ergebnis an den anfragenden Client zurückliefert.
- Resolver fragen dabei schrittweise bei den **autorativen** Nameservern der jeweiligen Zonen an.
- ==Resolver verfügen über eine statische Liste der 13 Root-Server, die für die Root-Zone autorativ sind==. 
- Es wir **Iterativ / Rekursiv** nach der autorativen Nameserver gefragt.
- **Glue Records** enthalten die IP Adresse der gesuchten Nameserver.



 
**Iterativ vs Rekursiv Namensauflösung:**
- **Iterativ:** ein server fragt nacheinander die autorativen Nameserver von der Root an um ein Domain aufzulösen.
- **Rekursiv:** Die DNS Anfrage wird an einem resolver weitergeleitet und der Resolver arbeitet iterativ nach der Namenauflösung und gibt die ergebnisse zurück.
