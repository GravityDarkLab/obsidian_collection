[[DNS]].

![[Resource Records.png]]

![[Record beispiel.png]]
- TTL : Time to live in **sec**.
- **SOA** record for grnvs.net.
- **serial** = version : muss inkrementiert werden für jede Anderung.
- **nxdomain**: gibt an wie lange anfragend Resolver in ihrem Cache halten dürfen, dass ein angefragter Resource Record nicht existiert.
- **NS** records geben die FQDNs der autoritativen Nameserver für dise Zone an.
- **A** gibt die IP adresse der FQDN **grnvs.net.** .
- **$ORIGIN** Spart Schreibarbeit bei den nachfolgenden Resource Records, die alle auf **grnvs.net.** enden.