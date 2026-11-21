# SC-900 cheat sheet 1/4 — Security, compliance, and identity concepts

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Zero Trust

| Principle | What it means | Typical control |
|---|---|---|
| **Verify explicitly** | Authenticate and authorise every request using all available signals: identity, device, location, data, and risk. | Multi-factor authentication, Conditional Access |
| **Least privilege** | Grant the minimum access needed, for the shortest time, with just-in-time elevation. | RBAC, PIM, access reviews |
| **Assume breach** | Design as if an attacker is already inside: segment, monitor, and limit blast radius. | Network segmentation, micro-segmentation, Sentinel, XDR |

**Zero Trust is a strategy, not a product.** It replaces the idea of a trusted corporate network with per-request decisions.

## Defence in depth

| Layer | Protects | Examples |
|---|---|---|
| **Physical** | Buildings, rooms, racks, hardware | Badges, guards, locks, cameras |
| **Identity** | Users, accounts, sign-in | MFA, Conditional Access, PIM |
| **Perimeter** | The network edge | Firewalls, DDoS protection, WAF |
| **Network** | Traffic between systems | Segmentation, NSGs, encryption in transit |
| **Compute** | Servers and workloads | Patching, hardening, endpoint protection |
| **Application** | The software itself | Secure code, input validation, app auth |
| **Data** | The information attackers want | Encryption, classification, access control, backup |

The layers are independent: if one fails, the next still applies. **Data is the centre** — every other layer exists to protect it.

## The CIA triad

| Element | Question it answers | Controls |
|---|---|---|
| **Confidentiality** | Who may read it? | Encryption, access control, classification, least privilege |
| **Integrity** | Is it accurate and unaltered? | Hashing, digital signatures, version control, audit |
| **Availability** | Can I reach it when needed? | Redundancy, zones, backups, DDoS protection |

## Core security terms

| Term | Meaning | Remember |
|---|---|---|
| **Authentication (authN)** | Proves who or what is connecting. | Password, certificate, token, biometric |
| **Authorisation (authZ)** | Decides what that identity may do. | Role assignment, permission, policy |
| **Accounting** | Records what happened. | Audit logs, sign-in logs |
| **Non-repudiation** | A person cannot credibly deny an action. | Digital signature, tamper-evident audit trail |
| **Threat** | Something that could cause harm. | Attacker, malware, flood |
| **Vulnerability** | A weakness that could be exploited. | Unpatched server, weak password policy |
| **Risk** | Likelihood × impact of exploitation. | Used to prioritise remediation |

**Exam trap:** authentication comes before authorisation. A valid sign-in does not grant permission.

## Encryption, hashing, and PKI

| Concept | What it does | Key facts |
|---|---|---|
| **Symmetric encryption** | Same key encrypts and decrypts. | Fast; used for bulk data. Key distribution is the challenge. |
| **Asymmetric encryption** | Public key encrypts, private key decrypts (and vice versa for signing). | Slower; used to exchange keys and sign. |
| **Encryption at rest** | Protects stored data. | Disk, database, backup encryption |
| **Encryption in transit** | Protects data moving on a network. | TLS, HTTPS, VPN |
| **Hashing** | One-way fixed-length digest. | Cannot be reversed; verifies integrity; salt passwords |
| **Digital signature** | Hash encrypted with a private key. | Proves origin and integrity; supports non-repudiation |
| **PKI** | Trust system for keys and certificates. | A certificate authority binds a public key to an identity |
| **Certificate** | Signed statement linking a key to a name or service. | Used by TLS and certificate authentication |

**Exam trap:** hashing is **one-way**; encryption is **reversible with the right key**. Hashing does not hide data by itself.

## Threat types

| Threat | Description |
|---|---|
| **Virus** | Attaches to a file or program; spreads when that file is opened. |
| **Worm** | Self-replicates across networks with no user action. |
| **Trojan** | Disguises itself as legitimate software; needs a user to run it. |
| **Ransomware** | Encrypts or steals data and demands payment. Backups are the recovery answer. |
| **Phishing** | Fraudulent message impersonating a trusted person or brand. Spear phishing is targeted; smishing is SMS; vishing is voice. |
| **DDoS** | Many sources flood a service and make it unavailable. An availability attack. |
| **Brute force** | Tries many password combinations against an account. |
| **Credential stuffing** | Reuses credentials leaked from another site. MFA breaks it. |
| **Privilege escalation** | Raises an attacker's level of access. |
| **Lateral movement** | Moves from one compromised system to another. |
| **Social engineering** | Manipulates a person into breaking procedure or revealing information. |
| **Insider threat** | A trusted person misuses access, accidentally or deliberately. |

## Shared responsibility

| Layer | IaaS | PaaS | SaaS |
|---|---|---|---|
| Physical datacenter and network | Microsoft | Microsoft | Microsoft |
| Hypervisor and host OS | Microsoft | Microsoft | Microsoft |
| Guest OS and runtime | **Customer** | Microsoft | Microsoft |
| Application code | **Customer** | **Customer** | Microsoft |
| Data, identities, access | **Customer** | **Customer** | **Customer** |

**Always customer:** data, identities, permissions, and configuration. **Always Microsoft:** the physical and virtualisation layer.

## Exam traps

- Zero Trust does not mean "trust nothing"; it means **verify everything** and grant least privilege.
- "Assume breach" is about containment and detection, not about accepting that you will be hacked.
- Defence in depth is **layered independent controls**, not one very strong control.
- Confidentiality is not the same as integrity: encryption hides data; hashing proves it was not changed.
- Availability attacks (DDoS, ransomware) target uptime and access, not secrecy.
- A firewall is not a substitute for identity controls; a compromised credential can pass through it.
