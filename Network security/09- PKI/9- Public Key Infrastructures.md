PKI is all about managing digital certificates and public-key encryption. It's a **framework** used to create, distribute, manage, store, and revoke digital certificates. In essence, PKI is the backbone of secure communication on the internet.

`A PKI reduces the number of long-term keys in the system to the number of trusted CA (Root CAs)`.
`Trust anchor: (Root) CA Certificates in root store`.
## In Nutshell 

> - Problem: We can exchange public keys without security.
> - But: We do not know who owns the public key.
> - Solution: We Need to bind the public key to an identity - [[#Certificates]].

- "Notary" verifies the identity of the entity who owns a public/private key pair (and verifies additional info like the correctness of this entities mail address).
- Notary creates data structure that binds the public key to the identity of the entity (+ additional info)
- Notary signs this data structure with her private key to make it verifiable → **certificate**
- Who ever wants to use the cert and trusts the notaries assertions and can verify her signatures can trust the Public key contained in the certificate

## Certificates

> These are electronic documents that use a digital signature to bind a public key with an identity — this identity could be an organization, individual, or server. Think of it like a digital ID card.

`The users can verify the certificate. If they trust the issuer, they can trust the certificate and use the public key in it`.

## How is it created

- Entity responsible for creating a certificate: the issuer I. (could be a person, organisation...)
- I has a public key, $K_{I-pub}$ , and private key, $K_{I-priv}$ .
- X is an identifier to be bound to a public key, $K_{X-pub}$.
- Submission to Certificate Authority (CA).
- The Certificate Authority (CA) processes CSR (Certificate submission request) - [[9.2- Issuance]].
- Let I create a signature: $Sig_{K_{I-priv}}(X |K_{X -pub})$
- The tuple $(X , K_{X -pub} , Sig_{K_{I-priv}} (X |K_{X -pub }))$ is then a certificate.
- In practice, we add (much) more information.

> Note:
> - Depending on the PKI, different words for "issuer" exist
> 	- Often in **[[9.1- Hierarchical PKIs]]**: “==Certification Authority==” (CA)
> 	- In **non-hierarchical** PKIs sometimes: “==Endorser==” - **webTrust** - Certificates are issued by many endorsers. Like OpenPGP
- These words often hint at the role (power) of the issuers.
- Certificates are uploaded to key servers which acts as a lookup service.