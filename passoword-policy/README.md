# Project 1 — Okta Password Policy (Hands-On)

**Purpose.** Implement a standard small-business style password policy in **Active Directory** and **Okta** to simulate baseline IAM controls. The intent is to show how directory policies are applied and enforced across a hybrid AD/Okta environment.

**NIST context.** This guideline draws from **NIST SP 800-63B (Digital Identity Guidelines – Authentication & Lifecycle Management)**, esp. the **Memorized Secrets** requirements (§5.1.1.1/§5.1.1.2).  
> Note: The policy below **partially aligns** with NIST (length emphasis and blocked/common password screening) but **intentionally deviates** in two areas common to small businesses: **composition rules** and **90-day expiration**, which NIST generally discourages in favor of longer passwords and breach screening.

---

## Scope
- Applies to all workforce users in AD and Okta (employees and contractors).  
## Policy Summary (Implemented)
- **Minimum length:** 15 characters  
- **Composition:** require uppercase, lowercase, number, and special character  
- **Disallow personal data:** username, first name, and last name not permitted in the password  
- **Common/breached passwords:** blocked (deny list/screening enabled)  
- **Password history:** remember last 4 passwords  
- **Expiration:** 90 days; **reminder:** 5 days before expiry  
- **Lockout/Throttle:** lock account after **5** failed attempts; user receives a lockout email notification

> **Why this lab policy:** Mirrors a typical, conservative AD baseline many small organizations still run. It’s useful to demonstrate control coverage and helpdesk workflows (expiry reminders, lockouts), even though a modern NIST-aligned stance would remove routine rotation and most composition rules in favor of length + breach checks.
