---
layout: page
title: Learning Log
permalink: /learning-log/
---

# Learning Log

Quick notes from guided rooms and courses (TryHackMe, PortSwigger Academy, etc.) — not full client-style reports.

Full reports live in [Write-ups](/writeups/) for self-directed work like HackTheBox machines and lab engagements.

---

## Offensive Security Intro — TryHackMe

**Concept:** 
The room simulated a vulnerable banking web application (FakeBank). The goal was to use directory enumeration to discover a hidden admin panel, then use that panel to manipulate the account balance directly.

**Commands/tools used:**
- dirb http://fakebank.thm — brute-forced the web server for hidden directories not linked anywhere on the visible site; this surfaced /bank-transfer, an unprotected admin endpoint for depositing funds.
  
- Navigated directly to fakebank.thm/bank-transfer in the browser and used it to deposit funds into account 8881, turning a negative balance positive with no authentication required.

**What tripped me up:**
Nothing significant this time.

**Real-world link:** 
This demonstrates two real and common issues together: (1) sensitive admin functionality hidden only through an obscure URL rather than actual authentication ("security by obscurity"), and (2) a complete lack of access control on that endpoint, allowing anyone who finds it to directly modify financial data. In a real engagement, this combination would be reported as a critical finding — missing authentication on a privileged function.

**Proof Of Concept:**
![Figure 1: Directory enumeration via dirb](/writeups/images/offensive-security-into/Figure 1)
---
