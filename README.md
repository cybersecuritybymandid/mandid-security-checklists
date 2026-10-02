# MANDID Security Checklists

Practical, defensive checklists for website, WordPress, server, account and incident-response work.

These materials are written for system owners, administrators, defenders and security professionals working on systems they own or are explicitly authorized to protect. They are designed to support structured response and recovery; they are not a substitute for professional, legal, regulatory or insurer guidance.

## Available checklists

- [Website & WordPress Incident Response Checklist](checklists/website-wordpress-incident-response.md) — preserve evidence, contain the incident, investigate the scope, eradicate persistence, recover safely and harden the environment.
- [Compromised Account Recovery Checklist](checklists/compromised-account-recovery.md) — regain control, preserve evidence, revoke attacker persistence, restore strong authentication and check linked email, social-media, developer and cloud access.
- [Server Hardening Checklist](checklists/server-hardening.md) — reduce attack surface, secure privileged access, restrict network exposure, protect secrets, strengthen logging and validate recovery.
- [Phishing Response Checklist](checklists/phishing-response.md) — preserve the original message, verify requests safely, scope delivery and interaction, contain credential or session compromise and recover affected accounts and endpoints.

## How to use this repository

1. Copy the relevant checklist into the incident record.
2. Assign an owner and timestamp to every action.
3. Preserve evidence before changing compromised systems whenever it is safe to do so.
4. Record every command, account change, file replacement and external notification.
5. Adapt the steps to the hosting architecture, business impact and applicable legal requirements.

## Planned checklists

- DDoS Initial Response

## Need help with an active incident?

MANDID supports remote incident containment, investigation, recovery and hardening for websites, web applications, servers and online accounts.

[Request cybersecurity help from MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=readme)

## Authoritative references

- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [WordPress — FAQ: My site was hacked](https://wordpress.org/documentation/article/faq-my-site-was-hacked/)
- [WordPress — Hardening WordPress](https://developer.wordpress.org/advanced-administration/security/hardening/)
- [Google Account Help — Secure a hacked or compromised Google Account](https://support.google.com/accounts/answer/6294825?hl=en)
- [GitHub Docs — Preventing unauthorized access](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/preventing-unauthorized-access)
- [NIST SP 800-123 — Guide to General Server Security](https://csrc.nist.gov/pubs/sp/800/123/final)
- [CIS Benchmarks — Secure configuration recommendations](https://www.cisecurity.org/cis-benchmarks-overview)
- [CISA — Secure Our World: Recognize and Report Phishing](https://www.cisa.gov/secure-our-world)
- [NIST — Phishing guidance for small businesses](https://www.nist.gov/itl/smallbusinesscyber/guidance-topic/phishing)
- [Microsoft Support — Protect yourself from phishing](https://support.microsoft.com/en-us/security/protect-yourself-from-phishing)
- [Google Gmail Help — Avoid and report phishing emails](https://support.google.com/mail/answer/8253?hl=en)

## Responsible use

Authorized and defensive use only. Never access, test or modify systems without the owner's explicit permission. Do not place secrets, personal data or client evidence in public issues or commits.

## License

Released under the [MIT License](LICENSE).
