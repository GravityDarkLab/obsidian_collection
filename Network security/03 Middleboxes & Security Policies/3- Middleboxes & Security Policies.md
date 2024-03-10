
- [[#What are they ?|What are they ?]].
- [[#3.3- Spoofing Protection]]
- [[#What Firewalls Cannot Do|What Firewalls Cannot Do]]
- [[#3.4- Bastion Hosts]]
- [[#Firewall Architectures|Firewall Architectures]]
- [[#3.5- Intrusion Detection Systems (IDS)]]


### What are they ?
- [[3.1- Middleboxes]].
- [[3.2- Security Policy]].

### 3.3- Spoofing Protection
> [[3.3- Spoofing Protection]].
- Discusses methods to prevent IP address spoofing, a technique often used in cyber attacks.


### What Firewalls Cannot Do

- Cannot protect against malicious insiders
- Cannot protect against connections that don’t go through it
- Cannot protect against completely **new threats**.
- Cannot fully protect against viruses
- **does not perform cryptographic operations**, e.g. message authentication
- cannot set itself up correctly
### [[3.4- Bastion Hosts]]

- **Concept**: Introduces the bastion host as a critical part of network defense, acting as a fortified server on the network perimeter.

### Firewall Architectures

- **Simple Packet Filter Architecture**:
	Basic firewalls that inspect packet headers and make allow/block decisions.
> It looks at the "ID" of each packet
	
	
- **Dual-Homed Host Architecture**: 
	Architectures that uses a single device with two network interfaces for more control.
> A device with two network interfaces acts as the gatekeeper between the public internet and the internal network.
	
	
- **Screened Host Architecture**: 
	Screening router and a bastion host work together for layered defense.
> Imagine a security checkpoint (the screening router) outside a secure building (the internal network) and a security guard inside (the bastion host). The screening router first filters incoming traffic with basic rules. Traffic that passes through then encounters the bastion host, which provides a second, more thorough check.


- **Screened Subnet Architecture – DMZ**: 
	Demilitarized zone (DMZ), providing an additional layer between the public internet and the internal network.
> Think of a DMZ as a buffer zone between a country's border and its internal land, where additional security checks happen. In network terms, the DMZ is a neutral area between the public internet and the internal network. It typically hosts services meant for public access (like web servers).


### 3.5- Intrusion Detection Systems (IDS)
[[3.5- Intrusion Detection Systems (IDS)]].
