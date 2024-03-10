# Table of content

- [[#AS/ISP|AS/ISP]]
- [[#Attacker Models|Attacker Models]]
		- [[#Capabilities of Attackers|Capabilities of Attackers]]
		- [[#Model|Model]]
		- [[#The Attacker’s Position in the Network Determines their Capabilities|The Attacker’s Position in the Network Determines their Capabilities]]
- [[#Security Goals|Security Goals]]
- [[#Threats|Threats]]

## AS/ISP

- An Internet Service Provider (ISP) is a business entity.
- An Autonomous System is a construct of the BGP protocol. 
- **An ISP can own several AS's or only one**. 
- An autonomous system is a set of routers under a single technical administration [RFC 1930]

## Attacker Models
#### Capabilities of Attackers
- **Passive attacks** = observation
	- Eavesdropping of messages 
	- Traffic Analysis
- **Active attacks** = observation + manipulation 
	- Replay, Delay, Delete, Refactor messages, Create...
#### Model
>  `Definition of what a attacker can do`
- [[Dolev-Yao attacker model]].
#### The Attacker’s Position in the Network Determines their Capabilities
1. **==Attacker is close to the client==**:
	- The attacker can perform any active/passive attack on you
	- **Defense**:
		- Establish a secure tunnel to a server in the Internet : [[8- Secure Channels]].
		- Route all your packets over the secure tunnel
		--> The attacker can now perform only DoS (Denial Of Service) attacks against you, collect meta data, etc.
2. **==Attacker is in the internet==**:
	- End-user/attacker has no control how packets are routed → “Lottery of Doom”
	- NSA/GCHQ/ have black boxes basically everywhere → only end-to-end encryption helps...
3. **==Attacker is close to the server==**:
	- The attacker could try to perform timing attacks against your server: work by measuring how long certain operations (operation successfully completed, operation failed) Take at your server - `Only works if the server is vulnerable to side-channel attacks`.

## Security Goals
- [[1.1- Security Goals]]

## Threats

> A threat in a communication network is any possible event or sequence of actions that might ==exploit a vulnerability==, leading to a **violation of one or more security goals**.

- **Vulnerability**: A design flaw in a cryptographic protocol, a programming error, etc. Which exists in a system.
- **Threat**: The possibility that somebody abuses a vulnerability.

- **Classification**:
	- ==Impersonation==: An entity claims to be another entity (also called “masquerade”)
	- ==Forgery of information==: An entity creates new information in the name of another entity.
	- ==Modification or loss of (transmitted) information==: Data is being altered or destroyed
	- ==Repudiation==: An entity falsely denies its participation in a communication act
	- ==Eavesdropping==: An entity reads information it is not intended to read
	- ==Authorization Violation==: An entity uses a service or resources it is not intended to use
	- ==Denial of Service (Sabotage)==: Any action that aims to reduce the availability and / or correct functioning of services or systems.

