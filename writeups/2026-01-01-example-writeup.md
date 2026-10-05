---
title: "Example Machine — SMB Misconfiguration to Domain Admin"
date: 2026-01-01
tags: [ad, network]
cvss_score: 8.8
status: draft
---

> **Scope note:** This is a placeholder example showing how to fill in the template. Delete this file once you've published your first real write-up, or keep it as a style reference with `status: draft` (draft posts won't be listed if you filter by status in your index page later).

## 1. Objective

Example: "Assess the internal network of [Lab Name] to identify paths to domain compromise."

## 2. Scope

- **Target(s):** 10.10.10.0/24 (lab range)
- **Authorization:** Self-built home lab
- **Testing window:** Jan 2026
- **Out of scope:** N/A — fully self-owned lab

## 3. Methodology

PTES-aligned: enumeration → vulnerability identification → exploitation → post-exploitation → reporting. Mapped to MITRE ATT&CK where relevant.

## 4. Findings

### 4.1 SMB Signing Disabled Enabling Relay Attack

| Field | Detail |
|---|---|
| **Severity** | High |
| **CVSS v3.1** | 8.8 (example) |
| **Affected Component** | File server, 10.10.10.5 |
| **CWE** | CWE-300 |

**Description**
SMB signing was not enforced on the target file server, allowing captured NTLM authentication to be relayed to gain access.

**Steps to Reproduce**
1. Enumerated SMB signing status with `nxc smb <range> --gen-relay-list`
2. Set up `ntlmrelayx.py` targeting the vulnerable host
3. Triggered authentication via a coerced print spooler bug
4. Relayed credentials to gain local admin on the target

**Evidence**
[Insert terminal screenshot here]

**Impact**
An attacker on the internal network could gain local admin on the file server without needing valid credentials, as a stepping stone toward domain compromise.

**Remediation**
Enforce SMB signing via Group Policy (`Microsoft network server: Digitally sign communications (always)`), and disable NTLM where Kerberos can be used instead.

---

## 5. Detection Notes

This activity generates Event ID 4624 (Logon Type 3) from an unusual source combined with Event ID 5145 (object access) on the file server — worth alerting on relay patterns specifically.

## 6. Retest Results

Not yet retested — pending remediation.

## 7. Lessons Learned

Relay attacks are high-impact but noisy; practicing the coercion + relay chain end-to-end was more valuable than reading about it.
