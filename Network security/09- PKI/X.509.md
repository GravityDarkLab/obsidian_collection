

### Overview

X.509 is a standard that defines the format of public key certificates.
These certificates are used in various security protocols, including TLS/SSL, which is the backbone of secure communication on the internet.

### Certificate Structure

An X.509 certificate includes several key pieces of information:
   - **Subject**: The identity of the certificate holder (like a person, organization, or device).
	   - Often a certificate includes only one domain name, called common name (CN), (e.g: `net.in.tum.de`) 
	   - Optionally, it is possible to create certificates that are valid for multiple (sub-) domains. ==Wildcards:== `*.net.in.tum.de`.
   - **Issuer**: The identity of the Certification Authority (CA) that issued the certificate.
   - **Serial Number**: A unique number assigned to each certificate by the issuer.
   - **Validity Period**: The timespan during which the certificate is considered valid.
   - **Public Key**: The public key that corresponds to the private key owned by the subject.
   - **Signature Algorithm**: The algorithm used by the CA to sign the certificate.
   - **CA's Signature**: The actual signature to prove it was issued by the CA.
   - **Extensions**: Additional fields for more information and functionality.
   

#### Certificate Chains

X.509 allows the creation of certificate chains. This means a certificate can be validated by tracing its issuance lineage back to a trusted root CA. It's the structure used in hierarchical PKIs.

#### Trust Model

X.509 certificates are based on a trust model. If you trust the CA (because its root certificate is in your system's trust store), and the CA vouches for the subject's certificate, then you trust the subject's certificate.

#### Usage in SSL/TLS

When you visit an HTTPS website, your browser checks the website's SSL/TLS certificate, which is an X.509 certificate. The browser verifies this certificate against a list of known CAs. If the certificate is valid and trusted, a secure connection is established.

#### Revocation:

X.509 includes provisions for certificate revocation. Certificates can be revoked if compromised, and mechanisms like Certificate Revocation Lists (CRLs) or the Online Certificate Status Protocol (OCSP) are used to check the revocation status.



![[Pasted image 20240107184613.png]]


### [[X.509]] for the WWW

#### Root stores

- Every application that uses [[X.509]] has to have a root store, i.e. a set of trusted certificates from the CA.
- Root certificates are self assigned.

#### Intermediates Certificates

- Part of a certificate chain, but neither a root certificate nor an end-entity certificate.
- There are two primary reasons to use intermediate certificates:
	- Protect your main root certificate:
		- Intermediate cert is operated by the same organization - Intermediate certs have the same signing authority as root certs.
		- Allows to store root cert in the root store, but private key may remain offline in some secure location
		- Online day-to-day operations can be done using the private key of the intermediate cert
		- Also makes it very easy to replace the intermediate cert in case of compromise, or crypto breakthroughs (e.g. Hash algorithms) etc.
	- To delegate signing authority to another organization: sub-CA
##### Cross-signing
- A special case of [[#Intermediates Certificates]].
- In a business-to-business model, this makes sense:
	- Two businesses wishing to cooperate cross-sign each other
	- Makes it easy to design business processes that access each others’ resources via SSL/TLS
- For the WWW, it completely breaks the root store model
- A new CA can be introduced, subverting control of the root store vendor