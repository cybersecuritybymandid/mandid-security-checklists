# Phishing Response Checklist

Use this checklist when a suspicious email, text message, collaboration message, QR code, voice request or login prompt may be part of a phishing, credential-theft, malware-delivery or business-email-compromise incident.

> **Scope:** Defensive response for accounts, devices and organizations you own or are explicitly authorized to protect. Preserve evidence before deleting messages or changing affected systems. Follow your incident-response plan and applicable legal, regulatory, contractual, insurer and law-enforcement requirements.

## 0. Open and own the incident

- [ ] Record the incident owner, reporter, date, time, timezone and communication channel.
- [ ] Assign an initial severity based on executive targeting, privileged access, financial requests, malware, data exposure and number of recipients.
- [ ] Record the potentially affected users, mailboxes, devices, applications and business processes.
- [ ] Start a timestamped incident log and preserve every decision, action and result.
- [ ] Move incident coordination to a trusted channel if email or collaboration accounts may be compromised.
- [ ] Identify who can authorize containment, credential resets, payment holds and external notifications.

## 1. Immediate action for the recipient

- [ ] Do not reply, click links, scan QR codes, open attachments, call numbers in the message or use its unsubscribe link.
- [ ] Do not forward the suspicious message normally; use the approved reporting function or attach the original message according to organizational procedure.
- [ ] Keep the message available until the security team confirms that required evidence has been preserved.
- [ ] If a link or attachment was opened, stop further interaction and report exactly what happened.
- [ ] If credentials, MFA codes, payment details or sensitive data were entered, report that immediately as a likely compromise.
- [ ] If a payment or account change was requested, verify it through a separate trusted channel.
- [ ] Disconnect an affected endpoint from untrusted networks only when the response plan calls for isolation; do not power it off if volatile evidence may matter.

## 2. Preserve the original evidence

- [ ] Preserve the original message in its native format when the platform supports it.
- [ ] Export or record full message headers and authentication results.
- [ ] Record the envelope sender, visible From address, Reply-To, Return-Path, recipients, subject and timestamps.
- [ ] Preserve the message body, displayed link text, actual link targets, QR image, attachments and embedded images.
- [ ] Calculate hashes of attachments without executing them.
- [ ] Capture screenshots for context without relying on screenshots as the only evidence.
- [ ] Preserve mail-gateway, identity-provider, endpoint, DNS, proxy, firewall and collaboration-platform logs relevant to the timeline.
- [ ] Record message IDs, campaign IDs, alert IDs and search queries used during investigation.
- [ ] Store evidence in an access-controlled case location and document chain of custody when required.

## 3. Classify the suspected lure

- [ ] Identify whether the message is credential phishing, malware delivery, QR phishing, MFA fatigue, OAuth consent abuse, invoice fraud, payroll diversion, gift-card fraud, impersonation or data theft.
- [ ] Note urgency, secrecy, emotional pressure, unusual requests and attempts to bypass normal procedure.
- [ ] Compare the sender domain with the expected domain, including lookalike characters and unexpected subdomains.
- [ ] Review whether the Reply-To or return path differs from the visible sender.
- [ ] Check SPF, DKIM and DMARC results while remembering that successful authentication does not prove benign intent.
- [ ] Identify shortened, redirected, encoded or mismatched URLs.
- [ ] Note unexpected attachments, unusual file types, password-protected archives or documents requesting macros or login.
- [ ] Determine whether the message is part of an existing conversation or a possible thread hijack.

## 4. Verify the request independently

- [ ] Contact the claimed sender through a known telephone number, directory entry or previously trusted conversation.
- [ ] Do not use contact details, links or telephone numbers supplied by the suspicious message.
- [ ] Confirm financial, payroll, banking, password-reset and vendor-detail changes with the responsible person using the approved process.
- [ ] Verify shared documents by opening the known service directly instead of following the message link.
- [ ] Record who performed the verification, which trusted channel was used and the result.

## 5. Determine delivery scope

- [ ] Search the mail or collaboration environment for the message ID, sender, subject, URLs, attachment hashes and distinctive text.
- [ ] Identify every recipient, delivery status, timestamp and mailbox folder.
- [ ] Determine whether similar messages used different senders, subjects, links or attachments.
- [ ] Check whether the campaign targeted executives, finance, administrators, developers, support staff or other high-value roles.
- [ ] Identify external recipients or partner organizations that may also be affected.
- [ ] Preserve the search criteria and result counts for the case record.

## 6. Determine user interaction

- [ ] Ask recipients whether they viewed the message, clicked, scanned a QR code, opened an attachment, enabled content, replied, called a number or entered information.
- [ ] Correlate user reports with safe-link, proxy, DNS, browser, endpoint and identity-provider telemetry.
- [ ] Record the destination, time, device, browser and account used for each interaction.
- [ ] Determine whether a login completed, MFA was approved, a file executed or an OAuth application was granted access.
- [ ] Identify any payment, account-profile, forwarding, recovery or security-setting change made after the interaction.
- [ ] Treat uncertainty as unresolved risk rather than assuming no interaction occurred.

## 7. Contain the message and campaign

- [ ] Use approved administrative tools to quarantine or remove confirmed phishing messages from mailboxes.
- [ ] Block malicious sender addresses, domains, URLs and attachment hashes at appropriate controls when evidence supports it.
- [ ] Preserve at least one controlled evidence copy before mass removal.
- [ ] Disable malicious inbox rules, transport rules, connectors or forwarding discovered during the response.
- [ ] Warn targeted users through a trusted channel with clear indicators and reporting instructions.
- [ ] Coordinate blocks across email, web proxy, DNS, endpoint and collaboration controls without disrupting legitimate services unnecessarily.
- [ ] Monitor for revised lures that reuse the same infrastructure or impersonated business process.

## 8. If credentials or MFA were exposed

- [ ] Reset the affected password through the trusted service, not through a link in the suspicious message.
- [ ] Revoke active sessions, refresh tokens, application passwords and remembered-browser sessions.
- [ ] Review recent sign-ins, source locations, devices, user agents and authentication methods.
- [ ] Remove unknown MFA methods, recovery addresses, telephone numbers, passkeys and trusted devices.
- [ ] Re-register strong MFA when compromise is suspected; prefer phishing-resistant methods where supported.
- [ ] Reset reused credentials on other services and prioritize email, identity, finance, cloud, developer and administrative accounts.
- [ ] Review password-reset events and security-setting changes around the incident timeline.
- [ ] Increase monitoring for repeated login attempts, MFA prompts and session reuse.

## 9. If OAuth or delegated access was granted

- [ ] Identify the application, publisher, requested permissions, consent time and consenting account.
- [ ] Revoke the malicious or unapproved grant and related refresh tokens.
- [ ] Review tenant-wide and user-level application consent for similar grants.
- [ ] Check mailbox, files, contacts, calendars, chats and cloud resources accessible through the granted scopes.
- [ ] Restrict user consent according to organizational policy and require review for high-risk permissions.
- [ ] Preserve consent and audit logs before retention windows expire.

## 10. If an attachment or payload executed

- [ ] Isolate the affected endpoint using approved tooling while preserving needed evidence.
- [ ] Preserve endpoint alerts, process trees, command lines, file hashes, downloaded files and network connections.
- [ ] Identify child processes, persistence changes, new services, scheduled tasks and security-tool exclusions.
- [ ] Search other endpoints for matching hashes, filenames, domains, processes and behaviors.
- [ ] Reimage or restore from a known-good source when system integrity cannot be established confidently.
- [ ] Rotate credentials used on the affected device after containment from a clean device.
- [ ] Validate that endpoint protection, logging and updates are functioning before returning the device to service.

## 11. If payment or business-process fraud is involved

- [ ] Contact the bank or payment provider immediately through a verified channel to request a hold or recall when applicable.
- [ ] Notify authorized finance, legal, fraud and executive stakeholders according to the response plan.
- [ ] Preserve invoices, account-change requests, approvals, call records and transaction identifiers.
- [ ] Independently verify vendor and employee banking details before any replacement payment.
- [ ] Review related mailboxes for thread hijacking, deleted messages, forwarding and impersonation.
- [ ] Do not negotiate with or alert the suspected attacker from a potentially compromised account.
- [ ] Record required insurer, regulator and law-enforcement notifications and their deadlines.

## 12. Hunt for mailbox and account persistence

- [ ] Review inbox, forwarding, redirect, deletion and hidden rules.
- [ ] Check delegates, shared-mailbox permissions, aliases and send-as or send-on-behalf permissions.
- [ ] Review suspicious sent, deleted, archived and draft messages.
- [ ] Check recent OAuth grants, application passwords, API tokens and connected applications.
- [ ] Review recovery information, MFA methods and security notifications.
- [ ] Search for attacker-created contacts, signatures, filters or templates used for continued impersonation.
- [ ] Inspect administrative changes affecting mail flow, federation, domains or identity policies.

## 13. Assess data access and lateral movement

- [ ] Determine which mail, files, contacts, chats, cloud resources and applications the compromised identity could access.
- [ ] Review downloads, searches, sharing changes, mailbox access and unusual API activity.
- [ ] Identify privileged roles, service accounts, developer tokens and business systems reachable from the account.
- [ ] Check whether the attacker sent internal or external phishing from the compromised account.
- [ ] Identify newly targeted users and repeat the scope and interaction review for them.
- [ ] Determine whether regulated, customer, employee, financial, authentication or intellectual-property data may have been exposed.

## 14. Recover and validate

- [ ] Confirm malicious messages, rules, grants, sessions, persistence and payloads have been removed or revoked.
- [ ] Validate account ownership and security settings with the legitimate user.
- [ ] Confirm the user can sign in only with approved devices and authentication methods.
- [ ] Monitor the affected identities and endpoints for renewed access attempts and related campaigns.
- [ ] Restore business processes carefully and re-verify payment or vendor changes.
- [ ] Record residual risk, compensating controls, owners and review dates.
- [ ] Obtain technical and business approval before closing the incident.

## 15. Communicate and notify

- [ ] Give affected users factual instructions without forwarding live malicious links or attachments.
- [ ] Notify external organizations through verified security or abuse contacts when their brand or infrastructure is involved.
- [ ] Coordinate customer, partner, insurer, legal, regulator and law-enforcement communication with authorized stakeholders.
- [ ] Preserve consistent timestamps, facts and decisions across technical and executive updates.
- [ ] Avoid unverified attribution and do not expose personal data or sensitive indicators unnecessarily.

## 16. Improve defenses after the incident

- [ ] Document root causes, detection gaps, response delays and business-process weaknesses.
- [ ] Tune mail, identity, endpoint, DNS and web controls using validated indicators and behaviors.
- [ ] Strengthen phishing-resistant MFA, conditional access and session controls for high-risk accounts.
- [ ] Require independent verification for payment, payroll, banking and sensitive account changes.
- [ ] Improve reporting buttons, escalation paths and training using sanitized lessons from the incident.
- [ ] Test mailbox auditing, log retention, message search and mass-removal procedures.
- [ ] Run a follow-up exercise and assign owners and due dates for corrective actions.

## Fast escalation triggers

Escalate immediately to experienced incident responders and the appropriate business stakeholders when:

- a privileged, executive, finance, administrator, developer or identity-provider account may be compromised;
- a user approved MFA, entered credentials, granted OAuth permissions or executed a payload;
- unauthorized payments, payroll changes, banking-detail changes or sensitive-data disclosure may have occurred;
- attacker-created forwarding, inbox rules, delegates, sessions or persistence are found;
- phishing was sent from an internal account or the campaign reached multiple recipients;
- malware, lateral movement, cloud access or data exfiltration is suspected;
- legal, regulatory, insurer, customer or law-enforcement notification may be required;
- the scope cannot be established confidently with available logs.

## Authoritative references

- [CISA — Secure Our World: Recognize and Report Phishing](https://www.cisa.gov/secure-our-world)
- [NIST — Phishing guidance for small businesses](https://www.nist.gov/itl/smallbusinesscyber/guidance-topic/phishing)
- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations for Cybersecurity Risk Management](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [Microsoft Support — Protect yourself from phishing](https://support.microsoft.com/en-us/security/protect-yourself-from-phishing)
- [Google Gmail Help — Avoid and report phishing emails](https://support.google.com/mail/answer/8253?hl=en)

## Need help with an active phishing incident?

MANDID supports remote incident containment, investigation, account recovery and security hardening for email, online accounts, endpoints, websites and business systems.

[Contact MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=phishing-response)

---

**Responsible use:** Defensive and authorized use only. Do not place live credentials, personal data, client evidence or malicious payloads in public repositories or issue trackers.
