# Website & WordPress Incident Response Checklist

Use this checklist when a website shows signs of compromise: malicious redirects, unknown administrator accounts, injected pages or scripts, unexpected file changes, spam, malware warnings, credential theft, suspicious server activity or unexplained availability problems.

> **Scope:** Defensive response on systems you own or are explicitly authorized to protect. If the incident may involve regulated data, criminal activity, contractual notification duties or significant financial harm, involve qualified legal, privacy, insurance and incident-response professionals.

## 0. Start an incident record

- [ ] Record the date, time, time zone, reporter and observed symptoms.
- [ ] Assign an incident lead, technical owner and business contact.
- [ ] Create a protected timeline of every action and decision.
- [ ] Record affected domains, hosts, IPs, WordPress instances and third-party services.
- [ ] Keep credentials, tokens, customer data and raw evidence out of public tickets and chat rooms.

## 1. Preserve evidence before cleanup

- [ ] Capture screenshots and exact URLs for visible symptoms.
- [ ] Save hosting, web server, PHP, WordPress, WAF/CDN, DNS, authentication and control-panel logs.
- [ ] Create a snapshot or forensic copy of website files and the database before modifying them, when operationally safe.
- [ ] Record file hashes, timestamps, ownership and permissions for suspicious files.
- [ ] Export the current WordPress user list, roles, active plugins, themes, must-use plugins and scheduled tasks.
- [ ] Preserve relevant email alerts, malware warnings and provider notifications.
- [ ] Note the earliest known suspicious event and the last known-good state.

Do not delete the first web shell or injected file you find and assume the incident is over. Premature cleanup can destroy evidence and leave other persistence mechanisms active.

## 2. Contain the incident

- [ ] If there is active harm, place the site in maintenance mode or restrict access at the load balancer, CDN, WAF or web server.
- [ ] Block confirmed malicious indicators without locking out responders or destroying evidence.
- [ ] Restrict administrative surfaces to trusted networks or IPs where feasible.
- [ ] Disable or suspend confirmed malicious accounts and revoke their active sessions.
- [ ] Pause unsafe deployments, automated jobs and integrations that could spread the compromise.
- [ ] Contact the hosting provider if server isolation, snapshots or upstream logs are required.
- [ ] Keep a safe communication channel that does not depend on the potentially compromised site or mailbox.

## 3. Establish scope and initial access

- [ ] Review access and error logs for suspicious requests, uploads, authentication attempts and abnormal response patterns.
- [ ] Review WordPress administrator creation, role changes, password resets and application-password activity.
- [ ] Inspect WordPress core, plugins, themes, `mu-plugins`, drop-ins, upload directories, `.htaccess`, web server configuration and `wp-config.php`.
- [ ] Look for recently modified PHP/JavaScript files, obfuscated code, unexpected executables, hidden files and writable directories.
- [ ] Review cron jobs, scheduled tasks, startup services and control-panel automation for persistence.
- [ ] Check database content for injected administrators, malicious options, spam pages, redirects and stored scripts.
- [ ] Examine hosting, SSH/SFTP, database, CDN/WAF, DNS, registrar, email and API access for related compromise.
- [ ] Determine whether the entry point was a vulnerable component, stolen credential, compromised administrator device, exposed service or unsafe deployment secret.
- [ ] Identify every site or service that shares credentials, hosting accounts, databases, plugins, themes or deployment pipelines with the affected system.

## 4. Eradicate the compromise

- [ ] Reinstall WordPress core from an official trusted release or verify it against official checksums.
- [ ] Replace plugins and themes with clean copies from trusted sources; do not reuse unknown archives from the compromised host.
- [ ] Remove unused, abandoned or untrusted plugins and themes.
- [ ] Remove confirmed malicious files, database records, accounts, scheduled tasks, services and access keys only after evidence is preserved.
- [ ] Patch the operating system, web server, PHP, WordPress core, plugins, themes and supporting services.
- [ ] Correct unsafe file ownership and permissions.
- [ ] Disable dashboard file editing unless the business workflow explicitly requires it.
- [ ] Close the initial access path and search other systems for the same indicators.

## 5. Reset trust and credentials

- [ ] Reset all WordPress administrator passwords and invalidate active sessions.
- [ ] Rotate WordPress security keys and salts to force cookie invalidation.
- [ ] Rotate exposed or potentially exposed hosting, SSH/SFTP, database, deployment, API, CDN/WAF, DNS, registrar and email credentials.
- [ ] Replace compromised SSH keys, application passwords, webhooks and service tokens.
- [ ] Require unique passwords and multi-factor authentication for privileged accounts where supported.
- [ ] Review every privileged account and remove access that is no longer required.
- [ ] Treat credentials stored on a compromised host as exposed unless evidence shows otherwise.

## 6. Recover safely

- [ ] Restore from a known-good backup only after validating its date, integrity and absence of the original weakness.
- [ ] If system integrity cannot be trusted, rebuild on a clean environment instead of relying on partial cleanup.
- [ ] Test the recovered site in an isolated or restricted environment.
- [ ] Verify content, forms, authentication, payment flows, integrations, redirects, DNS and TLS behavior.
- [ ] Scan from both server-side and external perspectives.
- [ ] Return traffic in controlled stages while monitoring logs, file changes, accounts and outbound connections.
- [ ] Keep the compromised snapshot and incident record according to retention and legal requirements.

## 7. Validate hardening and monitoring

- [ ] Apply least privilege to WordPress roles, hosting accounts, database users and deployment credentials.
- [ ] Enable multi-factor authentication for privileged accounts.
- [ ] Keep WordPress core, plugins, themes and the server stack on supported versions.
- [ ] Configure tested, versioned and isolated backups with a documented restoration procedure.
- [ ] Enable useful logging and preserve it outside the affected host when possible.
- [ ] Alert on new administrators, unexpected file changes, authentication anomalies and security-control changes.
- [ ] Restrict executable content in upload directories and limit write access to what the application requires.
- [ ] Review WAF/CDN, rate-limiting and administrative-access controls.
- [ ] Confirm that administrator workstations and browsers are updated and free of credential-stealing malware.
- [ ] Schedule a follow-up review to confirm that indicators and persistence have not returned.

## 8. Communications and lessons learned

- [ ] Determine whether customers, partners, authorities, regulators, insurers or service providers must be notified.
- [ ] Communicate confirmed facts, impact and protective actions; distinguish evidence from assumptions.
- [ ] Document the root cause, affected assets, exposed data, dwell time, containment actions and recovery decisions.
- [ ] Record which controls failed and assign owners and deadlines for improvements.
- [ ] Update the incident-response plan, architecture diagrams, asset inventory and contact list.

## Fast escalation triggers

Escalate to experienced incident responders when any of the following applies:

- the attacker may have server or hosting-account access;
- customer, payment, identity or regulated data may be exposed;
- multiple sites or business systems are affected;
- logs are missing, altered or insufficient;
- the attacker returns after cleanup;
- ransomware, destructive activity, extortion or law-enforcement contact is involved;
- there is no reliable known-good backup or rebuild path.

## References

- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations for Cybersecurity Risk Management](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [WordPress — FAQ: My site was hacked](https://wordpress.org/documentation/article/faq-my-site-was-hacked/)
- [WordPress — Hardening WordPress](https://developer.wordpress.org/advanced-administration/security/hardening/)

Need help containing or recovering from a website incident? [Contact MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=website-wordpress-incident-response).
