<div align="center">

# 🛡️ SC-900 Exam Simulator

[![Live exam](https://img.shields.io/badge/%E2%96%B6%20Take%20the%20exam-chrismunnps.github.io-0d9488?style=for-the-badge)](https://chrismunnps.github.io/exam-sim/sc-900/)
[![Questions](https://img.shields.io/badge/questions-180-2563eb?style=for-the-badge)](#-question-bank)
[![Pass mark](https://img.shields.io/badge/pass%20mark-700%20%2F%201000-7c3aed?style=for-the-badge)](#-scoring-and-review)
[![Exam time](https://img.shields.io/badge/exam%20time-60%20minutes-f59e0b?style=for-the-badge)](#-exam-at-a-glance)
[![Case studies](https://img.shields.io/badge/case%20studies-2-0891b2?style=for-the-badge)](#-case-studies)
[![Offline](https://img.shields.io/badge/offline-double--click-16a34a?style=for-the-badge)](#-run-it-locally)

### Microsoft Security, Compliance, and Identity Fundamentals · 180 questions · 2 case studies · runs entirely in the browser

**▶ Live exam: https://chrismunnps.github.io/exam-sim/sc-900/**

</div>

---

## 🚀 Executive summary

A free, full-length practice exam for **Exam SC-900: Microsoft Security, Compliance, and Identity Fundamentals**, built from the Microsoft Learn SC-900 learning paths. It recreates the real sitting closely enough to be useful: a weighted 45-question draw, a 60-minute clock, scaled scoring against the 700 pass mark, two case studies, and six concept diagrams.

Everything runs client-side. There is no account, no install, no server, no analytics, and no network call after the page loads — scores and review history stay in the visitor's own browser.

The simulator is seven runtime files, identical in the repository and on the live site:

> **🌐 Live site: https://chrismunnps.github.io/exam-sim/sc-900/**
> Served by GitHub Pages from the portfolio repo's `exam-sim/sc-900/` folder — the seven runtime files in this repository are exactly what is deployed.

It is an independent study tool. It is not affiliated with, endorsed by, or connected to Microsoft.

---

## ✨ Why this one is different

🧭 **It behaves like the real exam.** Forty-five questions drawn by domain weight, 80 seconds each, a running clock, flag-for-review, a question palette, and submit-on-timeout.

🧠 **Explanations teach, not just score.** Every item carries a rationale, a note on why each distractor is wrong, an exam tip, and the exam skill area it maps to.

🧩 **Two case studies.** Twelve questions hang off shared scenarios — Contoso Healthcare's patient-data estate and Fabrikam Financial Services' regulatory programme — so you practise holding context across a case, the way the real exam does.

🖼️ **Concept diagrams.** Six inline SVG diagrams cover Zero Trust, defence in depth, the security stack, identity risk, information protection, and the compliance lifecycle. Every diagram question also explains the concept in words.

✅ **Multi-answer items are all-or-nothing.** "Select two" questions are graded exactly as strictly as the exam grades them.

🔁 **A spaced-review queue.** Wrong answers come back on a schedule instead of disappearing, so weak domains get revisited without re-running whole exams.

🌓 **Light and dark themes.** A top-bar switch, remembered per browser, following the OS until you choose. Printing always forces black-on-white.

⌨️ **Keyboard-first.** `A`–`E` to answer, arrows to navigate, `F` to flag, plus a visible focus ring and a skip link.

📴 **Genuinely offline.** Double-click the page and it works with the network unplugged. No bundler, no local server, no runtime dependencies.

---

## 🎯 Exam at a glance

| | |
|---|---|
| **Certification** | Microsoft Certified: Security, Compliance, and Identity Fundamentals |
| **Exam** | SC-900 — Microsoft Security, Compliance, and Identity Fundamentals |
| **Questions in bank** | 180 (168 standalone + 12 case-study) |
| **Default attempt** | 45 questions: 5 security, 12 identity, 16 solutions, 12 compliance |
| **Time limit** | 80 seconds per question — 60 minutes for the default draw |
| **Passing score** | 700 / 1,000 (scaled from percentage correct) |
| **Review** | Every question after submission, with explanations and sources |
| **Prerequisites** | A browser. That is the whole list. |

---

## 📚 Question bank

| Domain | Standalone | Case items | Weight | IDs |
|---|---:|---:|---|---|
| Security concepts | 24 | 1 | 10–15% | Q1–Q24 |
| Identity and access | 43 | 2 | 25–30% | Q25–Q67 |
| Security solutions | 56 | 4 | 35–40% | Q68–Q123 |
| Compliance solutions | 45 | 5 | 25–30% | Q124–Q168 |
| Case studies | — | 12 | — | Q169–Q180 |
| **Total** | **168** | **12** | | **180** |

The domain totals — **25 security, 45 identity, 60 solutions, 50 compliance** — match the blueprint, including the case items that count towards each domain. A default draw uses the midpoints of the skills-measured ranges (12.5 / 27.5 / 37.5 / 27.5), which yields **5 / 12 / 16 / 12**.

**Question mix:** product-recognition items, scenario-led choices, "which service should you use" comparisons, eleven diagram-backed items, and sixteen `Select two` multiple-response questions.

### 🗂️ Case studies

| Case | Questions | Scenarios |
|---|---|---|
| Contoso Healthcare | Q169–Q174 | Zero Trust, phishing defence, privileged access, patient-record protection, insider risk, SIEM |
| Fabrikam Financial Services | Q175–Q180 | Credential attacks, XDR correlation, regulatory assessment, document sharing, audit retention, guest access |

The case questions carry their domain weight, so a full draw still reflects the SC-900 skills outline.

---

## 🧾 Cheat sheets

Four printable one-page refreshers, one per domain, plus a single self-contained print pack. They sit in this repository alongside the simulator; only the seven runtime files are needed to run the exam.

| File | Covers |
|---|---|
| `04-CHEAT-SHEET-SECURITY.md` | Zero Trust, defence in depth, CIA triad, authentication and authorisation, encryption, hashing, PKI, threat types |
| `05-CHEAT-SHEET-IDENTITY.md` | Entra ID, groups and guests, hybrid identity, MFA and passwordless, Conditional Access, Identity Protection, PIM, governance, SSO protocols |
| `06-CHEAT-SHEET-SOLUTIONS.md` | Defender XDR and the Defender family, Sentinel, Secure Score, and the comparison pairs that decide most answers |
| `07-CHEAT-SHEET-COMPLIANCE.md` | Purview, sensitivity labels, DLP, retention and records, insider risk, eDiscovery, audit, communication compliance, Compliance Manager |
| `08-CHEAT-SHEETS.html` | All four sheets laid out as A4 pages — open and print |

Open `08-CHEAT-SHEETS.html` in a browser and choose **Print all four sheets**. Each domain fits one A4 page at two columns, type is set for paper rather than screen, and the toolbar and background are excluded from print.

---

## 🖥️ Run it locally

**The short version:** download the repository and double-click `index.html`.

```text
index.html        – page shell, theme bootstrap
exam.config.js    – pass mark, domains, weights, timer
questions.js      – 180 questions (the whole bank)
diagrams.js       – 6 inline SVG diagrams
app.js            – exam engine
styles.css        – shared theme, light + dark
md-loader.js      – data bootstrap and friendly failure message
```

No `npm install`. No build step. No web server. The page opens from `file://`, reads the bank through a plain `<script>` tag, and starts.

> 💡 **Working in the authoring kit?** `exam-sim/index.html` temporarily loads the shared engine from `../AZ-104/exam-sim/`. Double-click `01-Package-Standalone.bat` once to copy `app.js` and `styles.css` in and rewrite the page to local paths before publishing.

---

## 🧮 Scoring and review

📊 **Scaled score.** `round(correct / total * 1000)` — the same shape Microsoft uses in the score report. Seven out of ten is a pass.

🎆 **Passing feels like passing.** Clearing 700 adds a five-second fireworks overlay to the score report. It is skipped automatically when the operating system asks for reduced motion, and never appears in print.

🔍 **Review everything.** After submitting, filter by all / incorrect / flagged. Each item shows your answer, the correct answer, the full explanation, and the source skill area.

📄 **Print or save.** "Print full review" and "Print score report" produce clean paper layouts with the light palette forced, so a dark-mode session still prints readable black text.

💾 **Resume safe.** An in-progress attempt is saved on every change. Close the tab, come back, and the clock and answers are where you left them.

---

## 🔐 Privacy

Everything is local. The simulator writes four keys to `localStorage` and nothing else:

| Key | Holds |
|---|---|
| `sc900-sim:attempt` | The in-progress attempt, for resume |
| `sc900-sim:settings` | Draw size, timer, instant-feedback preference |
| `sc900-sim:srs` | Spaced-review scheduling data |
| `sc900-sim:theme` | Light or dark choice |

No cookies, no requests to third parties, no telemetry. Clearing site data for the page resets the simulator completely.

---

## ⚠️ Disclaimer

Unofficial study material built from publicly available Microsoft Learn content. Not affiliated with or endorsed by Microsoft. Exam objectives and product behaviour change; verify the current skills measured on Microsoft Learn before sitting the exam. Facts snapshot: **November 2026**.

<div align="center">

**[▶ Start practising](https://chrismunnps.github.io/exam-sim/sc-900/)** · [Microsoft Learn SC-900](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/)

</div>
