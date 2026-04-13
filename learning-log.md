This lab focuses on external network reconnaissance and identity system analysis.
## Non-M365 Domain Recon (hbhsec.com)

Command:
trevorspray --recon hbhsec.com

Findings:
- Hostinger MX records
- SPF Hostinger
- OpenID invalid tenant

Conclusion:
Non-Microsoft 365 system

### Screenshots:
- hbhsec_dns.png
- hbhsec_recon.png
- hbhsec_openid.png
## Microsoft 365 Recon (contoso.com)

Command:
trevorspray --recon contoso.com

Findings:
- Outlook MX
- Azure AD detected
- Tenant ID present
- Managed authentication

Conclusion:
Enterprise Microsoft 365 system

### Screenshots:
- contoso_recon.png
- contoso_tenant.png
- contoso_token_flow.png
## Password Spraying Simulation (Lab Only)

A controlled authentication testing simulation was performed to understand login behavior differences.

Focus:
- Valid vs invalid response behavior
- Authentication flow understanding
- Security posture analysis

### Screenshot:
- spray_lab_output.png
Learned how DNS and identity systems help identify enterprise infrastructure and authentication mechanisms.
