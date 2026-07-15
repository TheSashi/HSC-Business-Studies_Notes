---
tags: [software-engineering, year-12, hsc, security, secure-software-architecture, cia, encryption, authentication]
aliases: [SE Security, Secure Software Architecture, CIA Triad, Coding Securely]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 12 Secure Software Architecture
created: 2026-07-15
updated: 2026-07-15
---

# Secure Software Architecture — Year 12 SE

> Self-contained note on designing software for security, coding securely, security terminology, and the Australian privacy context — built ONLY from the classroom sources (SSA1/SSA2/SSA3, the SSA pptx, W3, and the student sample answers). Gaps are flagged honestly: the NESA specs PDF has no security dot points, and Privacy Act/APPs appear in only ONE student sample answer (OAIC and the NDB scheme are NOT in any provided document). No external textbook content added.

---

## 1. Designing Software for Security (SSA1)

- Security embedded from the start: "Secure Software Architecture begins when any software solution is proposed. It needs to be embedded right from the start of the first Software Development Steps." Security is a **non-functional requirement** "embedded throughout the software development lifecycle rather than added as an afterthought." [SSA1/SSA2]
- **Six fundamental security concepts** (from pptx):
  - **Confidentiality** — "how secret your data is."
  - **Integrity** — "how 'whole' or intact your data is."
  - **Availability** — "how accessible your data is."
  - **Authentication** — "method of accessing data e.g. usernames, passwords, Two Factor Authentication (2FA)."
  - **Authorisation** — "level of permission to view, edit, delete data."
  - **Accountability** — "level of responsibility to view, edit, delete data."
- Code illustrations: Confidentiality→Fernet encryption; Integrity→SHA-256 hashing; Availability→retry-on-ConnectionError; Authentication→user/pass check; Authorisation→role (`admin`/`viewer`) branching; Accountability→write `datetime`+user+action to `log.txt`. [SSA1]
- **Case studies (from student/answers):** Instagram (Nov 2024) — Confidentiality + Authorisation breached (public API exposed emails; Broken Object Property Level Authorization). TikTok (June 2024) — Confidentiality + Integrity (hijacked accounts modify content) breached; Answers also flags Availability + Authorisation.
- **SDLC with security:** Requirements (incl. security requirements) → Specifications (security specs) → Design (security controls) → Development → Integration → Testing (errors, **vulnerabilities**) → Installation → Maintenance (patch vulnerabilities). [SSA1]
- OS-level: "secure software architecture aims to ensure that the operating system is secured so that one session doesn't override another one, nor adversely affect memory." [pptx]

---

## 2. Coding Securely Always (SSA2)

- **Security by design:** "software is designed to be secure from the beginning i.e. in the needs analysis and quality criteria rather than as an afterthought." [SSA2]
- **Privacy by design:** "software is designed to control who has access to what data from the beginning." [SSA2]
- Four case studies classified: (1) Health Records App = Security by design; (2) School Attendance = Privacy by design; (3) Student Portal = **Both**; (4) Online Survey Tool = N/A. [SSA2 Answers]
- **Testing strategies:** Code review, SAST, DAST, Vulnerability assessment, Penetration testing. [SSA2/pptx]
- **Coding practices:** Memory management, Session management, Exception management. [SSA2/pptx]
- **Tram-model example (from student answer):** confidentiality/integrity/availability goals; **Authentication + Access Control + RBAC + MFA** (passwords "vulnerable to brute-force and phishing"); **Australian Privacy Act 1988 + APPs** legal obligation to "collect only necessary data, store it securely, and destroy it when no longer needed"; **privacy impact assessment** in design; **input validation/error handling** to prevent injection; code reviews, pentests, Agile sprints, **SAST**. [SSA2 student Q3]

---

## 3. Security Terminology (SSA3 + pptx + W3)

- **Cryptography:** "art and science of making data unreadable except to those who should be able to access it." Privacy="how secret data is"; Security="how safe data is"; Vulnerability="security gap"; Session="specific instance of an app and its data in memory." [pptx]
- **Encryption** = scramble into unreadable **ciphertext** decipherable only with a key. [W3]
- **Types [W3]:**
  - **Hash functions** — no key, fixed-length fingerprint, integrity + digital signatures (MD5 differs on tiny change).
  - **Symmetric-key** — same key both ways, fast, needs secure key distribution; **AES** "gold standard" 128-bit blocks.
  - **Asymmetric/public-key** — public (shareable) + private (secret); secure comms + digital signatures.
- **SSL/TLS:** SSL (1995) encrypts site↔user, replaced by **TLS**; identity verified via **handshake** ("like a digital signature"); sites show **HTTPS**. [W3] (Full TLS handshake also covered in [[SE_Web_Programming]] §7.)
- **Risks to check:** XSS, invalid forwarding/redirecting, race conditions, sandboxing. [pptx/SSA3]
- **Authentication vs Authorisation:** see [[SE_Web_Programming]] §7 (defined identically in W3).

---

## 4. Australian Legal / Privacy Context (as found in sources)

> **Limitation:** Only the SSA2 student sample answer mentions it. OAIC and the Notifiable Data Breaches scheme are **absent from every provided document**.

- "Data Protection and Privacy must comply with the **Australian Privacy Act 1988 and its Australian Privacy Principles (APPs)**." [SSA2 student Q3]
- "legal obligation under the APPs to collect only necessary data, store it securely, and destroy it when no longer needed." [SSA2 student Q3]
- "A **privacy impact assessment should be conducted during the design phase**." [SSA2 student Q3]

---

## 5. NESA Syllabus Security / Privacy Dot Points

> **Finding:** The provided NESA specs PDF (course-specifications) contains **NO security or privacy outcomes or dot points**. Its only security-adjacent lines are: "**Cross-site scripting (XSS)** involves injecting malicious code into an otherwise safe website" and a mention of "performing a **simple encryption**" in character representation. The real SSA curriculum content lives in SSA1/SSA2/SSA3/pptx/W3.

---

## 6. Honest coverage report

| Topic | In your sources? |
|---|---|
| CIA triad (Confidentiality/Integrity/Availability) | Yes (pptx) |
| Authentication / Authorisation / Accountability | Yes (pptx, W3) |
| Encryption: hash / symmetric / asymmetric; AES, SSL/TLS | Yes (W3, pptx) |
| Security by design / Privacy by design | Yes (SSA2) |
| Testing: SAST/DAST/pentest/vuln assessment | Yes (SSA2/pptx) |
| Australian Privacy Act 1988 + APPs | Yes — ONE student sample answer only |
| OAIC / Notifiable Data Breaches scheme | **No — absent from all provided docs** |
| Least privilege / defence in depth / threat modelling | **No — absent from all provided docs** |
| NESA security/privacy syllabus dot points | **No — not in the specs PDF** |

Do not add OAIC/NDB/least-privilege content to exam answers unless your teacher supplies it — it is not in the provided materials.

---

> **See also:** [[SE_Web_Programming]] | [[SE_Software_Automation]] | [[SE_Software_Dev_Process]] | [[SE_Algorithms_and_Desk_Checks]]
