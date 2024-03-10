Part of: [[11.6- Domain Name System Security Extensions (DNSSEC)]].

## Zone Signing Key

- Each Zone has Zone Signing Key pair (ZSK).
- Private keys signs RRsets
- Public keys are used for verification.
`Signature are saved in the RRSIG record`.
`The public key is given as DNSKEY record`.
> If the resolver trusts the ZSK, he can trust all records in the zone.
> ==But we still need a way to validate the ZSK==.

--> Usage of a **key signing Keys**.

### Key Signing Keys

![[Screenshot 2024-02-03 at 11.57.43.png]]

