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
![Figure 1: Directory enumeration via dirb](/writeups/images/offensive-security-intro/Figure 1.png)
*Figure 1: Directory enumeration via dirb. Scanning http://fakebank.thm surfaced the undisclosed /bank-transfer endpoint, not linked anywhere in the site's visible navigation.*
![Figure 2: Account balance prior to exploitation](/writeups/images/offensive-security-intro/Figure 2.png)
*Figure 2: Account balance prior to exploitation. The FakeBank account (#8881) shows a negative balance of -$1,232.32, confirmed before accessing the unauthenticated /bank-transfer endpoint.*
![Figure 3: Unauthenticated access to the bank-transfer endpoint](/writeups/images/offensive-security-intro/03-bank-transfer.png)
*Figure 3: Unauthenticated access to /bank-transfer. The admin deposit function was reachable directly by URL, with no login prompt or session check at any point.*
![Figure 4: Account balance after exploitation](/writeups/images/offensive-security-intro/04-balance-after.png)
*Figure 4: Account balance after exploitation. The balance is now positive, confirming the deposit succeeded without authentication.*

---
