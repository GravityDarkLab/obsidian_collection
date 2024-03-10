Part of: [[11.6- Domain Name System Security Extensions (DNSSEC)]].

### How NSEC works and why it's important:

1. **Authenticated Denial of Existence**: When a DNS resolver asks for a record that doesn't exist in a DNSSEC-protected zone, the DNS server can't just say "No, that doesn't exist" without proving it, because an attacker could easily forge such responses. NSEC solves this by providing a way for the server to prove that a name doesn't exist in a secure and authenticated manner.
2. **NSEC Records**: An NSEC record for a given domain name points to the next domain name in the DNS zone file in alphabetical order. Along with this, the NSEC record lists all the DNS record types (like A, MX, TXT) that exist for that domain name. This helps in proving not only the non-existence of the requested domain but also the non-existence of specific types of records for existing domains.
3. **Chain of Non-Existing Domains**: By linking domain names in the zone in a sort of chain from one to the next, NSEC records create a complete map of existing domain names within the zone. This makes it possible to verify that a specific domain or record type doesn't exist between two known points.

4. **Drawbacks**: One notable downside of NSEC is that it can inadvertently reveal the existence of all domain names in a zone because of the way it links records together. This can lead to zone walking, where an attacker methodically queries the DNS to map out all the domain names in a zone. (we can enumerate all domains in the zone)
 
> Because of this, a successor called **NSEC 3** was developed, which offers the same benefits as NSEC but ==with additional protections against zone walking by hashing the domain names==.


