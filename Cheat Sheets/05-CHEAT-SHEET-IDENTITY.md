# SC-900 cheat sheet 2/4 — Identity and access management

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Microsoft Entra ID

| Concept | What to remember |
|---|---|
| **Tenant** | A dedicated directory instance for one organisation (for example `contoso.onmicrosoft.com`). The identity boundary; can contain many Azure subscriptions. |
| **User** | A member account in the tenant. |
| **Security group** | Used to assign permissions to resources. No collaboration workload. |
| **Microsoft 365 group** | Creates a shared mailbox, calendar, SharePoint site, and Teams team. |
| **Dynamic group** | Membership from an attribute rule, such as department equals Sales. Requires Entra ID P1. |
| **Guest (B2B)** | An external partner invited into your tenant; authenticates with their home credentials. |
| **External ID (B2C)** | Consumer identity for public apps, with local and social accounts. Customers, not partners. |
| **Hybrid identity** | On-premises Active Directory synchronised to Entra ID with Microsoft Entra Connect. |

**One tenant, many subscriptions.** A subscription is a billing and resource boundary, not an identity boundary.

## Hybrid identity options

| Option | How it validates | Notes |
|---|---|---|
| **Password hash synchronisation** | Entra ID checks a hash of the on-premises hash. | Simplest; enables leaked-credential detection. |
| **Pass-through authentication** | Agents validate against on-premises AD in real time. | No password hash in the cloud; depends on agents. |
| **Federation (AD FS)** | On-premises federation server issues claims. | More infrastructure; useful for complex requirements. |
| **Seamless SSO** | Kerberos ticket signs in domain-joined devices automatically. | Removes prompts; policies still apply. |

## Authentication

| Method | Factor | Notes |
|---|---|---|
| Password | Something you know | Weakest; reuse and phishing are the risks. |
| Authenticator app code | Something you have | Common second factor. |
| SMS or voice | Something you have | Convenient but interceptable; prefer stronger methods. |
| **FIDO2 security key** | Something you have | Phishing-resistant; bound to the site origin. |
| **Windows Hello for Business** | Device-bound key plus PIN or biometric | Phishing-resistant; protected by the TPM. |
| **Certificate-based** | Something you have | Strong; used in regulated and high-assurance scenarios. |
| **Temporary Access Pass** | Time-limited code | Onboarding or recovery when the user has no method yet. |

| Term | Meaning |
|---|---|
| **MFA** | Two or more factors from **different** categories: know, have, are. |
| **Passwordless** | Removes the password entirely: WHfB, Authenticator phone sign-in, or FIDO2. |
| **SSPR** | Users reset or unlock their own password after proving identity. Password writeback extends it to AD. |
| **Password Protection** | Blocks weak and banned passwords, including a custom banned list. |

## Conditional Access

An **if-then** policy engine: signals are evaluated, then a decision is enforced.

| Part | Examples |
|---|---|
| **Assignments (who/what)** | Users or groups, cloud apps, workload identities |
| **Conditions (context)** | Sign-in risk, user risk, location, device platform and state, client app |
| **Grant controls** | Block, require MFA, require compliant or hybrid-joined device, require approved app, require password change, terms of use |
| **Session controls** | Sign-in frequency, persistent browser session, app-enforced restrictions, Defender for Cloud Apps proxy |

**Key point:** Conditional Access controls **how a sign-in proceeds**. It does not assign permissions to resources. Requires Entra ID P1.

## Identity Protection

| Risk | Question | Typical response |
|---|---|---|
| **User risk** | Are this account's credentials probably compromised? | Require a secure password change |
| **Sign-in risk** | Does this specific attempt look anomalous? | Require MFA |

Signals include leaked credentials, anonymous IP use, atypical travel, malware-linked IPs, and unfamiliar sign-in properties. Risk policies can allow, block, or challenge. Requires Entra ID P2.

**Exam trap:** Identity Protection **detects** risk; Conditional Access **enforces** the response to it.

## Access control

| Capability | Purpose |
|---|---|
| **Microsoft Entra roles** | Manage directory objects: users, groups, apps, identity policies. Examples: Global Administrator, User Administrator. |
| **Azure RBAC** | Manage Azure resources at management group, subscription, resource group, or resource scope. Examples: Owner, Contributor, Reader. |
| **Scope inheritance** | An assignment applies to everything beneath its scope. |
| **Administrative units** | A container that scopes an administrator to a subset of users, groups, or devices. |
| **PIM** | Eligible, time-bound activation of a privileged role with approval, MFA, justification, and audit. Requires P2. |

**Exam trap:** directory object equals Entra role; Azure resource equals Azure RBAC role. PIM does not define permissions — it governs **when** a role is active.

## Governance

| Capability | What it does |
|---|---|
| **Access reviews** | Recurring recertification: reviewers confirm or remove access. Good for guests and privileged roles. |
| **Entitlement management** | Access packages bundle resources with request, approval, expiry, and review policy. |
| **Lifecycle workflows** | Event-driven automation for joiners, movers, and leavers: assign groups, send email, disable account. |
| **Cross-tenant access settings** | Control B2B collaboration and trust MFA or device claims from a partner tenant. |

## Single sign-on protocols

| Protocol | Purpose | Remember |
|---|---|---|
| **SAML 2.0** | Enterprise SSO using XML assertions. | XML, signed assertion, identity provider and service provider. |
| **OpenID Connect (OIDC)** | Authentication layer on top of OAuth 2.0. | Returns an **ID token** with user claims. |
| **OAuth 2.0** | Delegated authorisation. | Returns an **access token** for a resource; not authentication by itself. |
| **Federation** | Trust another identity provider's assertions. | Enables SSO across organisations. |

## Application identities

| Concept | Meaning |
|---|---|
| **App registration** | The application definition in the tenant. |
| **Service principal** | The local identity of that app in the tenant; permissions are granted to it. |
| **Managed identity** | An Azure-managed identity for a workload, with no secret to store or rotate. |

## Exam traps

- A guest is a **partner** (B2B); a customer is **External ID** (B2C).
- Dynamic groups use **attributes**, not manual lists, and need P1.
- MFA needs different **categories**, not two passwords.
- SSPR recovers an account; PIM elevates a role.
- Access reviews recertify access; entitlement management **packages** access; lifecycle workflows **automate** joiner-mover-leaver tasks.
- Conditional Access needs P1; Identity Protection, PIM, access reviews, entitlement management, and lifecycle workflows need P2.
