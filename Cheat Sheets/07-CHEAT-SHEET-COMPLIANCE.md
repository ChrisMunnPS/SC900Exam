# SC-900 cheat sheet 4/4 — Microsoft compliance solutions

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Microsoft Purview

| Capability | What it does |
|---|---|
| **Data Map** | Scans Microsoft 365, Azure, on-premises, and multicloud sources and records where data lives. |
| **Data Catalogue** | Searchable inventory with classifications, glossary terms, and ownership. |
| **Sensitive information types** | Pattern detectors for credit cards, national IDs, and other data classes. |
| **Trainable classifiers** | Learn categories such as contracts or harassment from examples. |
| **Purview scope** | Data governance plus compliance: labels, DLP, retention, insider risk, eDiscovery, audit, communication compliance, Compliance Manager. |

## Sensitivity labels

| Setting | Effect |
|---|---|
| **Classification** | Names the confidentiality level, such as Confidential. |
| **Encryption** | Azure Rights Management attaches usage rights that travel with the file. |
| **Content marking** | Header, footer, or watermark on supported content. |
| **Label policy** | Publishes labels to users or groups; sets default and mandatory labelling. |
| **Auto-labelling** | Applies or recommends a label using sensitive information types, classifiers, or exact data match. |
| **Priority** | Lower order number wins when several labels could apply. |

Labels persist with the item and are enforced in Office apps, email, Teams, SharePoint, and on devices.

## Data Loss Prevention (DLP)

| Item | What to remember |
|---|---|
| **Purpose** | Detect sensitive content and prevent or warn about sharing it. |
| **Locations** | Exchange, SharePoint, OneDrive, Teams, and Windows/macOS endpoints. |
| **Actions** | Audit, policy tip, block, block with override and justification, restrict non-Microsoft apps. |
| **Policy tips** | Explain the rule to the user and record overrides. |
| **Endpoint DLP** | Controls USB copy, print, upload, and clipboard for sensitive items. |
| **Alerts** | Record user, location, data type, action, and policy match. |

## Retention and records

| Concept | Applies to | Key facts |
|---|---|---|
| **Retention policy** | A whole location, such as every mailbox | Applies uniformly; retain, delete, or retain then delete. |
| **Retention label** | An individual item | Travels with the item; can trigger disposition review or a record. |
| **Record** | A labelled item | Content is locked; editing and deletion are prevented. |
| **Regulatory record** | A stricter record | The label itself cannot be changed or removed. |
| **Disposition review** | End of retention | A reviewer confirms deletion or extends retention. |

Retention starts from creation, last modification, or labelling, depending on the rule.

## Insider Risk Management

| Item | What to remember |
|---|---|
| **Purpose** | Detect and investigate risky insider activity, such as data theft before departure. |
| **Signals** | Downloads, USB activity, print jobs, unusual access, HR events. |
| **Templates** | Departing employee data theft, data leaks, priority user leaks, security policy violations, patient data misuse. |
| **Workflow** | Alert, triage, case, investigate, act. |
| **Privacy** | Role-based access and pseudonymised usernames; identity revealed only when required. |

## eDiscovery

| Feature | Standard | Premium |
|---|---|---|
| Search and hold | Yes | Yes |
| Export | Yes | Yes |
| Custodians and hold notifications | No | Yes |
| Review sets with analytics | Limited | Yes: near-duplicate, threading, predictive coding |
| Remediation | No | Yes |

**Workflow:** identify and search, preserve with a hold, collect into a review set, review and tag, export.

**Litigation hold:** preserves content in place even if a user deletes it; independent of retention settings.

## Audit

| Feature | Audit Standard | Audit Premium |
|---|---|---|
| Default retention | **180 days** | **1 year** |
| Custom retention | No | Up to **10 years** |
| High-value events | Limited | Yes, such as MailItemsAccessed |
| Search and export | Yes | Yes |

Audit records who did what, when, and where across Microsoft 365. Use audit log search to reconstruct administrator activity, permission changes, and file access.

## Communication compliance

| Item | What to remember |
|---|---|
| **Purpose** | Review messages for policy violations such as harassment or regulatory breaches. |
| **Detection** | Trainable classifiers, sensitive information types, keyword and custom lists. |
| **Scope** | Exchange, Teams, Viva Engage, and other channels. |
| **Timing** | Reviews after messages are sent; it is not a real-time block. |
| **Reviewers** | Role-based reviewers work a queue and can escalate or remediate. |

## Compliance Manager

| Item | What to remember |
|---|---|
| **Purpose** | Assess, track, and improve compliance against regulations and standards. |
| **Assessment** | One standard or regulation, built from a template or custom controls. |
| **Compliance score** | Points achieved against points available for assessed controls. |
| **Improvement actions** | The work items behind the score, with guidance and status. |
| **Shared responsibility** | Microsoft-managed controls count automatically; customer controls need evidence. |

## Comparison tables

| Pair | Distinction |
|---|---|
| **Sensitivity label vs DLP** | Classify and protect the item persistently vs detect and prevent a sharing action. |
| **Retention policy vs retention label** | Whole location vs individual item. |
| **eDiscovery Standard vs Premium** | Search, hold, export vs custodians, notifications, review analytics, remediation. |
| **Audit Standard vs Premium** | 180 days vs 1 year default and up to 10 years, plus high-value events. |
| **Retention vs eDiscovery hold** | Lifetime management vs legal preservation for a case. |
| **Communication compliance vs DLP** | Review conduct after sending vs block sensitive sharing in real time. |

## Exam traps

- A sensitivity label does not set how long content is kept; that is retention.
- DLP can block sharing; a retention label cannot.
- Deleting a user's items does not remove an eDiscovery hold.
- Audit Standard is 180 days; long regulatory retention needs Premium.
- Compliance Manager scores **controls**, not user training or incident counts.
- Insider Risk Management investigates behaviour; DLP enforces a sharing rule.
