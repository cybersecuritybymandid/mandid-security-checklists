# MANDID Security Checklists

Practical, defensive checklists for website, WordPress, server, account and incident-response work.

These materials are written for system owners, administrators, defenders and security professionals working on systems they own or are explicitly authorized to protect. They are designed to support structured response and recovery; they are not a substitute for professional, legal, regulatory or insurer guidance.

## Available defensive artifacts

- [Website & WordPress Incident Response Checklist](checklists/website-wordpress-incident-response.md) — preserve evidence, contain the incident, investigate the scope, eradicate persistence, recover safely and harden the environment.
- [Compromised Account Recovery Checklist](checklists/compromised-account-recovery.md) — regain control, preserve evidence, revoke attacker persistence, restore strong authentication and check linked email, social-media, developer and cloud access.
- [Server Hardening Checklist](checklists/server-hardening.md) — reduce attack surface, secure privileged access, restrict network exposure, protect secrets, strengthen logging and validate recovery.
- [Phishing Response Checklist](checklists/phishing-response.md) — preserve the original message, verify requests safely, scope delivery and interaction, contain credential or session compromise and recover affected accounts and endpoints.
- [DDoS Initial Response Checklist](checklists/ddos-initial-response.md) — verify the outage, preserve traffic evidence, identify the exhausted resource, coordinate upstream mitigation, protect the origin and recover service deliberately.
- [Ransomware Initial Response Checklist](checklists/ransomware-initial-response.md) — isolate affected systems, protect backups, preserve evidence, contain identity and remote access, assess data theft and rebuild through a controlled recovery process.
- [Incident Communications and Evidence Log Template](templates/incident-communications-evidence-log.md) — coordinate responders, separate facts from hypotheses, track communications and decisions, preserve evidence metadata and maintain chain of custody.

## How to use this repository

1. Copy the relevant checklist into the incident record.
2. Assign an owner and timestamp to every action.
3. Preserve evidence before changing compromised systems whenever it is safe to do so.
4. Record every command, account change, file replacement and external notification.
5. Adapt the steps to the hosting architecture, business impact and applicable legal requirements.

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
- [CISA, FBI and MS-ISAC — Understanding and Responding to Distributed Denial-of-Service Attacks](https://www.cisa.gov/sites/default/files/publications/understanding-and-responding-to-ddos-attacks_508c.pdf)
- [UK National Cyber Security Centre — Denial of Service guidance](https://www.ncsc.gov.uk/collection/denial-service-dos-guidance-collection)
- [Cloudflare Developers — How to prevent DDoS attacks](https://developers.cloudflare.com/learning-paths/prevent-ddos-attacks/concepts/ddos-prevention/)
- [NIST SP 800-86 — Guide to Integrating Forensic Techniques into Incident Response](https://csrc.nist.gov/pubs/sp/800/86/final)
- [CISA — Federal Government Cybersecurity Incident and Vulnerability Response Playbooks](https://www.cisa.gov/sites/default/files/2023-01/federal_government_cybersecurity_incident_and_vulnerability_response_playbooks_508c_5.pdf)
- [FIRST — Traffic Light Protocol (TLP) Version 2.0](https://www.first.org/tlp/)
- [CISA, FBI, NSA and MS-ISAC — #StopRansomware Guide](https://www.cisa.gov/stopransomware/ransomware-guide)
- [FBI Internet Crime Complaint Center — Ransomware](https://www.ic3.gov/CrimeInfo/Ransomware)
- [UK National Cyber Security Centre — Ransomware attack](https://www.ncsc.gov.uk/section/respond-recover/ransomware-attack)
- [UK National Cyber Security Centre — Mitigating malware and ransomware attacks](https://www.ncsc.gov.uk/guidance/mitigating-malware-and-ransomware-attacks)

## Responsible use

Authorized and defensive use only. Never access, test or modify systems without the owner's explicit permission. Do not place secrets, personal data or client evidence in public issues or commits.

## License

Released under the [MIT License](LICENSE).
