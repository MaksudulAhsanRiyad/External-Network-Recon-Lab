# External Network Recon & Identity Analysis Lab

This lab focuses on external network reconnaissance and identity system analysis.

---

## Non-Microsoft 365 Domain Recon (hbhsec.com)

Command:
trevorspray --recon hbhsec.com

Findings:
- Hostinger MX records
- SPF Hostinger
- OpenID invalid tenant

Conclusion:
Non-Microsoft 365 system

---

### Screenshots

![DNS](screenshots/hbhsec_dns.png)  
![Recon](screenshots/hbhsec_recon.png)  
![OpenID](screenshots/hbhsec_openid.png)

---

## Microsoft 365 Recon (contoso.com)

Command:
trevorspray --recon contoso.com

Findings:
- Outlook MX
- Azure AD detected
- Tenant ID present
- Managed authentication system

Conclusion:
Enterprise Microsoft 365 system

---

### Screenshots

![Recon](screenshots/contoso_recon.png)  
![Tenant](screenshots/contoso_tenant.png)  
![Token Flow](screenshots/contoso_token_flow.png)

---

## Password Spraying Simulation (Lab Only)

A controlled authentication testing simulation was performed to understand login behavior differences.

Focus:
- Valid vs invalid response behavior
- Authentication flow understanding
- Security posture analysis

---

### Screenshot

![Spray Output](screenshots/spray_lab_output.png)

---

## Final Summary

Learned how DNS and identity systems help identify enterprise infrastructure and authentication mechanisms.
