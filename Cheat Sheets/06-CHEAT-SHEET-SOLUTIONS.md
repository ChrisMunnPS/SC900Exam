# SC-900 cheat sheet 3/4 — Microsoft security solutions

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Microsoft Defender XDR

| Capability | What it does |
|---|---|
| **Incident correlation** | Groups related alerts from endpoint, email, identity, and cloud apps into one incident and timeline. |
| **Automated investigation and response** | Investigates alerts, gathers evidence, and can quarantine, isolate, or disable without analyst action. |
| **Advanced hunting** | KQL queries over up to **30 days** of raw telemetry; can become a custom detection. |
| **Microsoft Secure Score** | Posture percentage for Microsoft 365 workloads with improvement actions. |

**XDR family:** Defender for Endpoint, Defender for Identity, Defender for Office 365, Defender for Cloud Apps. Entra ID Protection signals also flow in.

## Defender for Endpoint

| Capability | What it does |
|---|---|
| **Endpoint protection** | Antivirus and anti-malware for Windows, macOS, Linux, and mobile. |
| **Attack surface reduction (ASR)** | Blocks risky behaviours such as Office child processes or scripts downloading executables. |
| **Endpoint detection and response (EDR)** | Behaviour-based detection and an investigation timeline; response actions such as device isolation. |
| **Threat and vulnerability management** | Prioritised missing patches, exposed software, and misconfigurations. |
| **Plan 1 vs Plan 2** | Plan 1: core protection and ASR. Plan 2 adds EDR, vulnerability management, automated investigation, advanced hunting. |

## Defender for Office 365

| Capability | What it does |
|---|---|
| **Safe Links** | Checks URLs at **click time**, including in Teams and Office documents. |
| **Safe Attachments** | Detonates attachments in a sandbox before delivery. |
| **Anti-phishing** | Impersonation protection, mailbox intelligence, and spoof intelligence. |
| **Anti-spam** | Filters spam, bulk mail, and high-confidence phishing; quarantine and allow/block lists. |
| **Attack simulation training** | Controlled phishing simulations with automatic remedial training. |
| **Plan 1 vs Plan 2** | Plan 1: Safe Links, Safe Attachments, anti-phishing. Plan 2 adds automated investigation, Threat Explorer, campaign views, attack simulation. |

## Defender for Identity

| Item | What to remember |
|---|---|
| **Purpose** | Detects identity attacks against on-premises Active Directory. |
| **Deployment** | Sensors on domain controllers, AD FS, and AD CS servers. |
| **Detections** | Reconnaissance and enumeration, compromised credentials, pass-the-hash, lateral movement paths. |
| **Not the same as** | Defender for Endpoint, which protects devices, not directory authentication. |

## Defender for Cloud Apps

| Capability | What it does |
|---|---|
| **Cloud Discovery** | Analyses firewall and proxy logs to find shadow IT; risk-scores apps. |
| **App connectors** | API access to a sanctioned SaaS app for activity, files, and governance actions. |
| **Conditional Access App Control** | Reverse proxy that blocks download, copy, or print in a SaaS session. |
| **Anomaly detection** | Flags impossible travel, unusual downloads, and new locations. |
| **CASB role** | Visibility and control of SaaS use; not infrastructure protection. |

## Defender for Cloud

| Capability | What it does |
|---|---|
| **CSPM** | Continuous posture assessment against benchmarks; recommendations; secure score; regulatory compliance dashboard. |
| **CWPP** | Workload protection plans for servers, containers, storage, SQL, App Service, Key Vault, and more. |
| **Multicloud** | Connects Azure, AWS, and GCP accounts into one posture view. |
| **Just-in-time VM access** | Closes management ports until an approved, time-limited request opens them. |
| **Not the same as** | Defender for Cloud Apps, which governs SaaS applications. |

## Microsoft Sentinel

| Capability | What it does |
|---|---|
| **SIEM** | Collects and correlates logs from Microsoft and third-party sources. |
| **SOAR** | Playbooks built on Azure Logic Apps automate response, with approvals. |
| **Data connectors** | Ingest Microsoft 365, Azure, syslog, CEF, and third-party data. |
| **Analytics rules** | Detection logic that creates alerts and incidents. |
| **Workbooks** | Dashboards for monitoring and reporting. |
| **Workspace** | Data lives in an Azure Log Analytics workspace; KQL queries it. |

**Sentinel vs Defender XDR:** XDR correlates the Microsoft security products; Sentinel is a general SIEM and SOAR platform that also ingests third-party and infrastructure logs. Many organisations send XDR incidents into Sentinel.

## Microsoft Secure Score

| Question | Answer |
|---|---|
| What is measured? | Tenant configuration against recommended Microsoft 365 controls. |
| How is it expressed? | Points achieved divided by points available, as a percentage. |
| How do you improve it? | Implement improvement actions, then wait for the next measurement. |
| Is it the same as the Defender for Cloud score? | No. Microsoft Secure Score covers Microsoft 365; Defender for Cloud score covers cloud resources. |

## Comparison table

| Pair | Distinction |
|---|---|
| **Defender XDR vs Sentinel** | Native Microsoft-product correlation vs cross-platform SIEM and SOAR. |
| **Defender for Cloud vs Cloud Apps** | Cloud **infrastructure** posture and workload protection vs **SaaS** discovery and governance. |
| **Defender for Identity vs Endpoint** | Directory authentication attacks vs device malware and behaviour. |
| **Defender for Office 365 vs Cloud Apps** | Email and collaboration content vs SaaS application use. |
| **Defender for Endpoint vs Defender for Cloud** | Device agent protection vs cloud resource assessment and workload protection. |
| **Safe Links vs Safe Attachments** | URL checked at click time vs attachment detonated in a sandbox. |
| **Analytics rule vs playbook** | Detect and create an incident vs automate the response. |
| **Alert vs incident** | One detection vs a group of related alerts describing one attack. |

## Exam traps

- All Defender products feed **XDR**; Sentinel sits above them and accepts non-Microsoft data.
- Cloud Discovery reads **traffic logs**; app connectors use **APIs**.
- Defender for Identity sensors go on **domain controllers**, not user laptops.
- Secure Score is **posture**, not the number of attacks blocked.
- "Protect virtual machines and storage" is Defender for Cloud; "discover unmanaged SaaS" is Defender for Cloud Apps.
