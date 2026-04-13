# External Attack Surface Recon & Identity Analysis Lab

## Objective

This lab demonstrates how an attacker performs external reconnaissance to identify a target’s identity infrastructure and determine whether Microsoft 365 (Azure AD) is in use.

This directly affects the attack strategy, especially for password spraying.

---

## Attack Scenario

An attacker aims to gain initial access by:

1. Identifying the email/identity provider  
2. Checking Microsoft 365 usage  
3. Enumerating valid users  
4. Performing password spraying  

---

## Phase 1: Non-Microsoft 365 Target Analysis (hbhsec.com)

Command:
trevorspray --recon hbhsec.com

Findings:
- Hostinger MX records detected  
- SPF configured for Hostinger  
- OpenID returned invalid tenant  

Analysis:
- Email system is hosted on Hostinger  
- No Microsoft 365 or Azure AD detected  

Attacker Insight:
- Microsoft-specific attacks will not work  
- Alternative targets may include:
  - Web login panels  
  - Hosting control panels  

Conclusion:
Target does not use Microsoft 365.

---

Screenshots:

![DNS](screenshots/hbhsec_dns.png)  
![Recon](screenshots/hbhsec_recon.png)  
![OpenID](screenshots/hbhsec_openid.png)

---

## Phase 2: Microsoft 365 Target Identification (contoso.com)

Command:
trevorspray --recon contoso.com

Findings:
- Outlook MX records detected  
- Azure AD identified  
- Tenant ID present  
- Managed authentication system  

Analysis:
- Target uses Microsoft 365 (Azure AD)  
- Tenant ID confirms identity integration  

Attacker Insight:
- Suitable for password spraying  
- User enumeration may be possible  
- Centralized login increases attack impact  

Conclusion:
Valid Microsoft 365 target.

---

Screenshots:

![Recon](screenshots/contoso_recon.png)  
![Tenant](screenshots/contoso_tenant.png)  
![Token Flow](screenshots/contoso_token_flow.png)

---

## Phase 3: User Enumeration (Concept)

After confirming Microsoft 365 usage:

Approach:
- Identify email patterns  
- Generate potential usernames  

Attacker Insight:
- Valid users can be identified via authentication responses  
- This improves attack accuracy  

---

## Phase 4: Password Spraying Simulation (Lab Only)

A controlled test was performed to analyze authentication behavior.

Focus:
- Valid vs invalid username responses  
- Authentication flow differences  

Observation:
- Valid users showed different response patterns compared to invalid users  

Security Risk:
- Attackers can identify valid users  
- Targeted password spraying becomes possible  

Impact:
- Account takeover risk  
- Unauthorized access  

Mitigation:
- Enable Multi-Factor Authentication (MFA)  
- Apply account lockout policies  
- Monitor login attempts  

---

Screenshot:

![Spray Output](screenshots/spray_lab_output.png)

---

## Final Summary

- DNS and MX records reveal email infrastructure  
- Microsoft 365 detection is critical for attack planning  
- Authentication responses can leak valid user info  
- Password spraying is effective if protections are weak  

---

## Disclaimer

This lab was conducted for educational purposes in a controlled environment. No real systems were targeted.

---
