# Compromised Account Recovery Checklist

Use this checklist when an email, social-media, cloud, developer, business or other online account shows signs of unauthorized access: unfamiliar sign-ins, changed recovery details, unexpected messages or posts, unknown devices, new applications or tokens, suspicious password-reset notices, unauthorized purchases, or loss of access.

> **Scope:** Defensive response for accounts you own, administer or are explicitly authorized to protect. Use only the provider's official recovery process. Never ask a victim to disclose a password, MFA code, recovery code, session cookie or private key. If the incident may involve fraud, regulated data, identity theft, extortion or significant business harm, involve the provider and qualified legal, privacy, insurance and incident-response professionals.

## 0. Start an incident record

- [ ] Record the date, time, time zone, reporter and first observed symptom.
- [ ] Identify the affected account, provider, username, linked email addresses and business assets.
- [ ] Record whether access is available, partially available or completely lost.
- [ ] List known administrators, owners, recovery contacts and connected services.
- [ ] Start a protected timeline of alerts, sign-ins, settings changes, posts, messages, transactions and response actions.
- [ ] Keep passwords, MFA codes, recovery codes, session data, identity documents and client evidence out of public tickets, repositories and chat rooms.

## 1. Move recovery to a trusted environment

- [ ] Use a known-clean, fully updated device and browser for recovery work.
- [ ] If credential-stealing malware is possible, disconnect the suspected device from sensitive accounts until it is examined or rebuilt.
- [ ] Secure the primary email account first if it controls password resets for other services.
- [ ] Secure the mobile number or carrier account if SMS recovery, SIM swapping or number porting may be involved.
- [ ] Use a separate trusted communication channel for the response team.
- [ ] Navigate directly to the provider's official website or app; do not use recovery links supplied by unknown contacts.

## 2. Preserve evidence before cleanup

- [ ] Capture screenshots of security alerts, unfamiliar devices, sessions, recovery-detail changes, posts, messages and transactions.
- [ ] Save original alert emails with full headers when available.
- [ ] Export or record the provider's sign-in, security, administrator and audit logs before retention windows expire.
- [ ] Record suspicious IP addresses, approximate locations, device names, user agents, timestamps and application names.
- [ ] Preserve URLs, message IDs, transaction IDs, support case numbers and copies of attacker communications.
- [ ] Distinguish confirmed facts from assumptions in the incident timeline.

Do not delete the first suspicious message, session or application you find and assume the incident is over. Premature cleanup can destroy evidence and leave other persistence paths active.

## 3. Regain and stabilize access

- [ ] If locked out, start the provider's official account-recovery workflow.
- [ ] If still signed in on a trusted device, do not sign out until you understand which recovery methods remain available.
- [ ] Follow provider instructions for identity verification; do not hire unofficial “recovery” services that request credentials or payment for access.
- [ ] Change the account password to a long, unique value stored in a trusted password manager.
- [ ] Change any other account that reused the old password, starting with email, password managers, financial services and administrator accounts.
- [ ] Restore the legitimate primary email address, phone number, recovery contacts and account owner.
- [ ] Remove unfamiliar recovery methods only after preserving evidence.
- [ ] Confirm that the attacker did not change the display name, username, profile details, payment destination or business ownership.

## 4. Revoke attacker access and persistence

- [ ] Sign out unfamiliar devices and sessions; where supported, use “sign out everywhere.”
- [ ] Revoke unknown OAuth applications, connected apps, browser extensions, bots and integrations.
- [ ] Revoke and replace exposed API tokens, personal access tokens, app passwords, webhooks and automation secrets.
- [ ] Remove unfamiliar passkeys, security keys, authenticator enrollments and trusted devices.
- [ ] Generate new recovery codes and invalidate the previous set.
- [ ] Review delegated access, shared mailboxes, page roles, business managers, organization members and third-party administrators.
- [ ] Remove unknown forwarding rules, inbox filters, delegates, aliases, blocked addresses and automatic replies.
- [ ] Review active subscriptions, advertising accounts, payment methods and payout details for unauthorized changes.

## 5. Restore strong authentication

- [ ] Enable MFA after unauthorized factors have been removed.
- [ ] Prefer phishing-resistant MFA such as a passkey or FIDO security key when the provider supports it.
- [ ] If phishing-resistant MFA is unavailable, use a reputable authenticator application rather than relying only on SMS.
- [ ] Register at least two controlled recovery methods where supported.
- [ ] Store recovery codes offline or in a secure password manager; never share them.
- [ ] Confirm that every privileged administrator uses an individual account with MFA.
- [ ] Remove dormant, shared or unnecessary privileged accounts.

## 6. Check email and identity-provider persistence

- [ ] Review recent sign-ins, devices and security events for the primary email and identity provider.
- [ ] Inspect mail forwarding, filters, rules, delegates, POP/IMAP access and connected applications.
- [ ] Search sent, deleted, archived and draft folders for attacker activity.
- [ ] Review password-reset and MFA-change messages for other accounts.
- [ ] Check whether cloud storage, calendars, contacts or address books were accessed or shared.
- [ ] Rotate credentials for services whose reset links, secrets or passwords may have been exposed through the mailbox.

## 7. Social-media and business-account checks

- [ ] Review page, channel, group, ad-account, catalog and business-manager ownership.
- [ ] Remove unfamiliar administrators, partners, agencies, apps and scheduled-posting tools.
- [ ] Review recent posts, messages, comments, ads, campaigns and audience changes.
- [ ] Stop unauthorized ads or promotions and preserve their identifiers before removal.
- [ ] Check verified status, monetization, payout, billing and recovery settings.
- [ ] Warn contacts about confirmed malicious messages or impersonation without overstating unverified impact.
- [ ] Report impersonation, fraudulent ads or platform abuse through the provider's official process.

## 8. Developer, cloud and infrastructure-account checks

- [ ] Review organization membership, repository visibility, collaborators and administrative roles.
- [ ] Inspect recent commits, releases, packages, workflow runs, runner registrations and deployment activity.
- [ ] Review and rotate personal access tokens, API keys, SSH keys, GPG or signing keys, deploy keys and webhook secrets.
- [ ] Review OAuth and GitHub/GitLab applications, cloud service accounts and CI/CD integrations.
- [ ] Check secrets, environment variables, artifact registries and deployment credentials for exposure.
- [ ] Validate branch protections, required reviews, environment approvals and audit-log retention.
- [ ] Treat secrets accessible to the compromised account as exposed unless evidence shows otherwise.

## 9. Determine scope and initial access

- [ ] Establish the earliest known unauthorized event and the last known-good state.
- [ ] Determine whether the likely cause was password reuse, phishing, device-code phishing, malware, session theft, malicious OAuth consent, SIM swap, social engineering or insider access.
- [ ] Identify every account, device and service that shared passwords, sessions, recovery channels or secrets with the affected account.
- [ ] Review endpoint security telemetry and browser extensions on devices used during the suspected compromise window.
- [ ] Check whether the attacker exported data, downloaded archives, changed permissions, created persistence or contacted other victims.
- [ ] If business data or customer information may be affected, begin the appropriate privacy, legal and contractual assessment.

## 10. Repair harm and communicate

- [ ] Remove confirmed malicious content only after evidence is preserved.
- [ ] Reverse unauthorized role, sharing, billing and payout changes.
- [ ] Notify affected contacts, customers, partners or administrators with confirmed facts and protective actions.
- [ ] Contact the bank, card issuer or payment provider immediately for unauthorized financial activity.
- [ ] Report identity theft, fraud, threats or criminal activity to the appropriate provider and authorities for the relevant jurisdiction.
- [ ] Preserve provider case numbers and all notification decisions in the incident record.

## 11. Monitor and learn

- [ ] Monitor security alerts, sign-ins, devices, tokens, posts, messages, transactions and recovery changes for recurrence.
- [ ] Set alerts for new administrators, security-setting changes and suspicious authentication where supported.
- [ ] Schedule a follow-up review after the immediate recovery period.
- [ ] Document root cause, affected data, attacker actions, containment steps and remaining uncertainty.
- [ ] Fix the control failures that enabled the incident: password reuse, weak recovery, excessive privilege, missing MFA, unmanaged integrations or insufficient logging.
- [ ] Update the account inventory, recovery contacts, incident-response plan and staff guidance.

## Fast escalation triggers

Escalate to the provider and experienced incident responders when any of the following applies:

- the primary email, password manager or identity provider is compromised;
- the attacker retains access after password and session resets;
- financial, identity, customer or regulated data may be affected;
- an administrator, business-manager, cloud or developer account is involved;
- tokens, signing keys, deployment credentials or production secrets may be exposed;
- malware or session-cookie theft is suspected on a device;
- the account is being used for fraud, extortion, impersonation or attacks on others;
- logs are missing, altered or insufficient to establish scope.

## Authoritative references

- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations for Cybersecurity Risk Management](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [Google Account Help — Secure a hacked or compromised Google Account](https://support.google.com/accounts/answer/6294825?hl=en)
- [GitHub Docs — Preventing unauthorized access](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/preventing-unauthorized-access)
- [CISA — Turn On MFA](https://www.cisa.gov/secure-our-world/turn-mfa)

Need help investigating or recovering a compromised online account? [Contact MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=compromised-account-recovery).
