---
title: "[Target Name] — [One-line description, e.g. 'IDOR to Full Account Takeover']"
date: 2026-01-01
tags: [web, ad, exploit-dev, cloud]   # keep only the relevant tags
cvss_score: 0.0                       # overall/highest finding score, if applicable
status: draft                         # draft | published
---

> **Scope note:** This engagement was performed against [TryHackMe/HackTheBox machine name, a program I own, or an authorized bug bounty target]. No production systems outside this authorization were tested.

## 1. Objective

One or two sentences: what was the goal of this engagement/exercise? (e.g. "Assess the authentication and access control mechanisms of X application to identify exploitable vulnerabilities.")

## 2. Scope

- **Target(s):** 
- **Authorization:** (lab environment / bug bounty program name / self-owned)
- **Testing window:** 
- **Out of scope:** 

## 3. Methodology

Briefly state the framework/approach followed (e.g. OWASP WSTG, PTES, MITRE ATT&CK mapping). List the phases you went through:

1. Reconnaissance / enumeration
2. Vulnerability identification
3. Exploitation
4. Post-exploitation / impact validation
5. Reporting

## 4. Findings

> Repeat this block for each finding. Order findings by severity, highest first.

### 4.1 [Finding Title]

| Field | Detail |
|---|---|
| **Severity** | Critical / High / Medium / Low |
| **CVSS v3.1** | 0.0 (vector string) |
| **Affected Component** | |
| **CWE** | |

**Description**
What is the vulnerability, in plain technical terms?

**Steps to Reproduce**
1. 
2. 
3. 

**Evidence**
(Screenshots, request/response pairs, terminal output — redact anything sensitive)

**Impact**
What can an attacker actually do with this? Be concrete, not generic ("read other users' private messages" not "sensitive data exposure").

**Remediation**
Specific, actionable fix — not "implement proper validation" but what validation, where, and how.

---

## 5. Detection Notes (optional but recommended)

What would a defender have seen? Relevant log sources, event IDs, SIEM alerts, or EDR telemetry this activity would generate.

## 6. Retest Results (if applicable)

Were the findings fixed? Re-verify and document the outcome.

## 7. Lessons Learned

What did you learn technically, or about your own process, that you'd apply next time?
