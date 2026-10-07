# Ransomware Initial Response Checklist

Use this checklist when ransomware, destructive encryption, a ransom note or data-extortion activity is suspected or confirmed. The first hours should reduce further harm, preserve evidence and establish a controlled path to recovery.

> **Scope:** Defensive response for systems, accounts and data you own or are explicitly authorized to protect. Do not retaliate, contact suspected infrastructure, run untrusted decryptors or make unsupported attribution claims. Coordinate destructive actions, legal decisions, regulatory reporting and any ransom-related decision with authorized leadership, counsel, insurers and law enforcement as applicable.

## 0. Open and own the incident

- [ ] Record the incident owner, technical lead, evidence lead, communications lead, executive decision-maker, start time and timezone.
- [ ] Open a timestamped incident record and document every observation, action, approval, command and result.
- [ ] Use an out-of-band communication channel that does not depend on potentially compromised identity, email or collaboration systems.
- [ ] Confirm who can authorize network isolation, account suspension, backup protection, emergency downtime and external notifications.
- [ ] Identify immediate safety, health, operational, financial and customer impacts.
- [ ] Assign an initial severity and state what evidence supports it.
- [ ] Record what is known, what is suspected and what remains unknown; do not convert assumptions into facts.
- [ ] Link or copy the [Incident Communications and Evidence Log Template](../templates/incident-communications-evidence-log.md) into the restricted case record.

## 1. Capture the first report

- [ ] Record who reported the incident and how they discovered it.
- [ ] Record the earliest known abnormal time and the time the incident was declared.
- [ ] Record affected device names, accounts, business services, locations and network segments.
- [ ] Photograph or securely capture the ransom note without clicking links, scanning QR codes or contacting the actor.
- [ ] Preserve the exact note text, filenames, extensions, contact addresses, chat URLs, email addresses and cryptocurrency addresses.
- [ ] Preserve one or more encrypted sample files together with known clean originals when available.
- [ ] Record visible error messages, encryption progress, unusual processes and unavailable services.
- [ ] Ask whether files were encrypted, deleted, renamed, exfiltrated or merely made inaccessible.
- [ ] Ask whether the organization received earlier phishing, credential, remote-access, EDR, backup or data-leak warnings.

## 2. Protect people and critical operations

- [ ] Prioritize human safety and continuity of essential services over evidence collection.
- [ ] Identify services that must remain available for health, safety, physical security, communications, payroll or regulated operations.
- [ ] Activate approved business-continuity procedures for critical processes.
- [ ] Move essential work to known-clean alternatives without copying suspicious executables, scripts or credentials.
- [ ] Prevent staff from reconnecting isolated devices or using compromised accounts.
- [ ] Tell staff not to forward ransom notes, samples or sensitive screenshots through ordinary email or chat.
- [ ] Establish a trusted route for new incident reports and urgent operational requests.

## 3. Isolate affected systems in sequence

- [ ] Identify systems showing encryption, ransom notes, suspicious remote control or destructive activity.
- [ ] Immediately isolate affected systems from wired, wireless, VPN, storage and management networks when it is safe to do so.
- [ ] If many systems or subnets are affected, coordinate isolation at the switch, firewall, wireless, VPN or cloud-control layer.
- [ ] Prioritize isolation of domain controllers, identity systems, virtualization management, backup infrastructure, file servers and remote-management platforms.
- [ ] Preserve access to logging, EDR and forensic systems when doing so does not allow further spread.
- [ ] For cloud workloads, restrict connectivity and preserve point-in-time snapshots using approved procedures.
- [ ] Use out-of-band coordination because an actor may be monitoring normal communications.
- [ ] Do not wipe, reimage, delete files or uninstall tools during initial containment.
- [ ] Do not power off an isolated system solely for convenience; volatile evidence may be lost.
- [ ] Power down only when isolation is impossible and continued operation creates greater harm, and record who authorized the decision.

## 4. Preserve volatile and durable evidence

- [ ] Select representative affected systems for memory capture and forensic imaging when qualified responders and approved tools are available.
- [ ] Preserve EDR alerts, process trees, command lines, network connections and isolation events.
- [ ] Preserve identity-provider, Active Directory, VPN, RDP, SSH, email, cloud, SaaS and privileged-access logs.
- [ ] Preserve firewall, proxy, DNS, DHCP, WAF, remote-monitoring, virtualization, storage and backup logs.
- [ ] Preserve relevant Windows Event Logs, PowerShell logs, scheduled-task data, services, autoruns and registry artifacts.
- [ ] Preserve suspicious scripts, binaries, archives and tools without executing them.
- [ ] Hash collected files and images using an approved algorithm and record the tool, time and collector.
- [ ] Record source path, hostname, account, collection method, time and chain of custody for each item.
- [ ] Export short-retention cloud and security logs before they roll over.
- [ ] Protect evidence in a restricted location separate from the compromised environment.
- [ ] Preserve screenshots for context, but retain machine-readable logs and forensic artifacts as primary evidence.

## 5. Protect backups and recovery infrastructure

- [ ] Alert the backup and disaster-recovery owners immediately.
- [ ] Prevent affected systems and compromised accounts from deleting, encrypting or expiring backups.
- [ ] Pause replication or synchronization when it is copying encrypted, deleted or corrupted data into recovery sets.
- [ ] Preserve immutable, offline and historical backup versions.
- [ ] Do not connect offline backups to a network that is not yet known to be clean.
- [ ] Do not perform a test restore onto a potentially compromised administrative system.
- [ ] Review backup-console logins, configuration changes, retention changes and deletion attempts.
- [ ] Protect backup administration with known-clean accounts, devices and strong authentication.
- [ ] Record the latest backup time for each critical service and the last successful restoration test.
- [ ] Identify backup dependencies, encryption keys, licenses, installation media and infrastructure-as-code needed for rebuilds.

## 6. Establish a known-clean response environment

- [ ] Use known-clean responder workstations and a separate recovery network.
- [ ] Verify that administrative tools, software packages and operating-system images come from trusted sources.
- [ ] Restrict recovery administration to named responders using separate privileged accounts.
- [ ] Enable logging for all recovery and containment actions.
- [ ] Protect emergency credentials and recovery keys outside the compromised identity plane.
- [ ] Confirm that time synchronization works across evidence, recovery and monitoring systems.
- [ ] Do not reuse credentials, tokens, SSH keys, certificates or secrets taken from affected systems.

## 7. Determine the scope

- [ ] Build an asset list of confirmed affected, suspected affected, exposed and currently clean systems.
- [ ] Map affected business services to identity, network, application, database, storage, backup and third-party dependencies.
- [ ] Identify the earliest confirmed malicious activity, not only the time encryption began.
- [ ] Search for precursor access such as phishing, stolen credentials, exposed remote services, exploited vulnerabilities or third-party access.
- [ ] Review anomalous VPN, RDP, SSH, SSO, cloud-console and remote-monitoring logins.
- [ ] Review newly created or reactivated accounts and recent privilege changes.
- [ ] Check for changes to domain policies, MFA, federation, conditional access, mailbox rules and application consent.
- [ ] Check for lateral movement, remote execution, administrative shares, scripting and credential access.
- [ ] Check for disabled security tools, cleared logs, backup deletion, shadow-copy changes and recovery inhibition.
- [ ] Check for staging, compression, large outbound transfers and cloud-storage or file-transfer activity.
- [ ] Identify whether operational technology, safety systems, customer environments or trusted partners are connected to the affected scope.
- [ ] Track confidence and evidence for every scope decision.

## 8. Contain identity and remote access

- [ ] Identify accounts, sessions, tokens, keys and applications used during the intrusion.
- [ ] Disable or restrict confirmed compromised accounts using a known-clean administrative path.
- [ ] Revoke active sessions, refresh tokens and unauthorized OAuth or application grants where supported.
- [ ] Restrict remote access, VPN, RDP, SSH and remote-management tools according to the approved containment plan.
- [ ] Protect break-glass accounts and verify they were not exposed or altered.
- [ ] Prioritize identity administrators, backup administrators, virtualization administrators and service accounts.
- [ ] Rotate credentials in a controlled sequence so responders do not lock themselves out of recovery systems.
- [ ] Rotate API keys, certificates and service secrets only after their dependencies and compromise scope are understood.
- [ ] Do not perform a broad password reset from compromised endpoints or before persistence is contained.
- [ ] Monitor for reuse of revoked credentials and attempts to create replacement access.

## 9. Stop spread and destructive activity

- [ ] Use EDR or approved controls to isolate hosts and block verified malicious hashes, paths, processes and destinations.
- [ ] Disable confirmed malicious scheduled tasks, services, startup items and remote-management jobs after evidence is preserved.
- [ ] Block confirmed malicious command-and-control and exfiltration destinations at appropriate control points.
- [ ] Close or restrict the verified initial-access path when doing so will not destroy evidence or critical operations.
- [ ] Patch or mitigate the exploited vulnerability before restored systems are exposed.
- [ ] Restrict administrative shares and lateral protocols according to business need and the containment plan.
- [ ] Remove unauthorized tools and persistence only after documenting them and confirming the removal sequence.
- [ ] Measure the effect of each containment action and watch for actor adaptation.
- [ ] Avoid broad blocks or shutdowns that create more harm without reducing attacker access.

## 10. Assess data theft and extortion exposure

- [ ] Determine whether the incident includes encryption, data theft, leak threats, destruction or multiple forms of extortion.
- [ ] Identify repositories, mailboxes, databases and file shares the actor accessed.
- [ ] Identify data that may involve personal, customer, employee, health, payment, confidential or regulated information.
- [ ] Preserve evidence of collection, staging, compression, transfer and deletion.
- [ ] Record claimed stolen-data samples without downloading additional material from attacker-controlled sites unless authorized and safely handled.
- [ ] Do not accept the actor's claims as proof; compare them with logs and known data.
- [ ] Involve privacy, legal and regulatory specialists in breach-scope decisions.
- [ ] Track affected jurisdictions, contracts and notification deadlines.

## 11. Coordinate reporting and communications

- [ ] Notify authorized leadership, legal counsel, privacy, risk and business-continuity owners.
- [ ] Notify the cyber insurer through the approved channel before retaining vendors or taking actions that could affect coverage.
- [ ] Contact qualified incident-response and forensic support when internal capability is insufficient.
- [ ] Report to appropriate national or local cyber authorities and law enforcement according to jurisdiction and policy.
- [ ] Give external responders the incident timeline, affected services, indicators and evidence through an approved secure channel.
- [ ] Prepare factual internal and external updates that separate confirmed facts from uncertainty.
- [ ] Do not publish attacker indicators, sensitive architecture, personal data or negotiation details without authorization.
- [ ] Preserve every notification, case number, recipient, time and response.
- [ ] Maintain a regular update cadence even when there is no major change.

## 12. Handle the ransom demand safely

- [ ] Preserve the demand, payment instructions, deadlines, negotiation portal and all identifiers as evidence.
- [ ] Do not contact the actor from ordinary corporate accounts or compromised systems.
- [ ] Do not promise, negotiate or pay without the organization's explicitly authorized decision process.
- [ ] Record that payment does not guarantee decryption, deletion of stolen data or an end to the incident.
- [ ] Check applicable sanctions, criminal, regulatory, contractual and insurer requirements with qualified counsel.
- [ ] Coordinate with law enforcement about known decryptors, recovered keys and related cases.
- [ ] Verify any proposed decryptor only in an isolated test environment using copies of data.
- [ ] Never upload confidential samples to an unknown decryption or identification service.
- [ ] Treat claimed deletion proofs and recovery guarantees as unverified attacker statements.
- [ ] Document the decision, authority, evidence, risks and alternatives whether payment is rejected or considered.

## 13. Plan eradication and rebuild

- [ ] Identify the initial-access route, persistence mechanisms, privileged access and all affected trust relationships.
- [ ] Define eradication criteria before reconnecting any system.
- [ ] Prefer rebuilding compromised systems from trusted images over attempting to clean them in place.
- [ ] Validate golden images, installation media, infrastructure-as-code and software packages before use.
- [ ] Patch vulnerabilities and correct exposed services, weak controls and misconfigurations that enabled the incident.
- [ ] Remove unauthorized accounts, application grants, keys, certificates, scheduled tasks, services and tools.
- [ ] Rebuild the identity control plane first when it cannot be trusted, following specialist guidance.
- [ ] Establish a credential-rotation order for users, administrators, services, applications and partners.
- [ ] Define the clean network, recovery zones and temporary access controls.
- [ ] Prioritize systems by safety, essential operations, revenue, dependencies and validated backup availability.
- [ ] Assign an owner, validation test and rollback plan to every recovery wave.

## 14. Restore from known-good sources

- [ ] Confirm the selected backup predates the compromise and is not only older than the encryption event.
- [ ] Scan and validate backups in the isolated recovery environment before restoration.
- [ ] Restore operating systems and applications from trusted sources, then restore required data.
- [ ] Apply current security updates and hardened configuration before production exposure.
- [ ] Restore identity, DNS, logging, EDR, backup and management services in a controlled dependency order.
- [ ] Restore critical business services in small waves rather than reconnecting everything at once.
- [ ] Validate application function, data integrity, permissions, integrations and transaction consistency.
- [ ] Reconcile transactions and records created while systems were unavailable.
- [ ] Keep the compromised environment segregated for evidence and controlled reference.
- [ ] Record exactly which image, backup, configuration and credential set was used for each restored system.

## 15. Monitor controlled reconnection

- [ ] Enable EDR, centralized logging, identity monitoring and network visibility before reconnecting restored systems.
- [ ] Monitor for known indicators, repeated initial-access attempts and old credentials.
- [ ] Watch privileged-account use, service-account behavior and changes to security controls.
- [ ] Validate that backups, retention and restoration jobs operate normally after recovery.
- [ ] Increase monitoring for data transfer, remote access, scripting, scheduled tasks and newly created accounts.
- [ ] Reconnect by approved recovery wave and stop when validation fails.
- [ ] Keep temporary segmentation and egress restrictions until the incident owner accepts residual risk.
- [ ] Confirm that emergency accounts, firewall rules, bypasses and vendor access are documented and time-limited.
- [ ] Obtain service-owner acceptance before declaring a system recovered.

## 16. Close the incident deliberately

- [ ] Confirm that affected services meet defined recovery and security criteria.
- [ ] Confirm that the known access path and persistence mechanisms are removed or mitigated.
- [ ] Confirm that credential, token, key and certificate rotations are complete for the verified scope.
- [ ] Confirm that legal, privacy, regulatory, contractual, insurer and customer actions are tracked to completion.
- [ ] Preserve the final evidence inventory, decision log, communications record and recovery record.
- [ ] Document remaining uncertainty and residual risk for the authorized decision-maker.
- [ ] Record who declared containment, recovery and closure, with timestamps and supporting evidence.

## 17. Review and improve

- [ ] Build a verified timeline from initial access through detection, containment, recovery and closure.
- [ ] Document the root cause, contributing control failures and business impact.
- [ ] Record which actions helped, which failed, which caused delay and which evidence was missing.
- [ ] Update asset inventories, architecture diagrams, logging, EDR coverage and retention.
- [ ] Improve network segmentation, privileged access, remote access and identity protections.
- [ ] Improve immutable or offline backups and test full restoration against realistic recovery objectives.
- [ ] Update the incident-response, communications, legal, insurer and business-continuity playbooks.
- [ ] Exercise the revised ransomware scenario with technical teams and leadership.
- [ ] Assign every corrective action an owner, priority, target date and verification method.
- [ ] Share sanitized lessons learned without exposing client data, credentials, sensitive infrastructure or live indicators.

## Escalate immediately when

- [ ] Human safety, healthcare, physical security or essential public services may be affected.
- [ ] Encryption or destructive activity is still spreading.
- [ ] Domain controllers, identity systems, backup systems, virtualization platforms or cloud control planes are affected.
- [ ] The organization cannot establish a trusted communication or administrative channel.
- [ ] Sensitive or regulated data may have been stolen.
- [ ] The actor threatens publication, contacts customers or employees, or attempts payment fraud.
- [ ] Critical operations cannot meet recovery objectives.
- [ ] The organization lacks the evidence, authority, staffing or technical capability to contain the incident safely.

## Minimum evidence to capture quickly

- [ ] Incident start and discovery times, with timezone.
- [ ] Hostnames, accounts, IP addresses, network segments and cloud resources affected.
- [ ] Ransom note, encrypted-file extension, attacker contacts and payment identifiers.
- [ ] Representative encrypted files and known clean originals.
- [ ] EDR alerts, process trees and suspicious command lines.
- [ ] Identity, VPN, remote-access, cloud, firewall, DNS and backup logs.
- [ ] Security-control changes, new accounts, privilege changes and session activity.
- [ ] Suspected initial-access vector and earliest confirmed malicious activity.
- [ ] Data-staging or exfiltration evidence.
- [ ] Every containment, credential, recovery and notification action.

## Authoritative references

- [CISA, FBI, NSA and MS-ISAC — #StopRansomware Guide](https://www.cisa.gov/stopransomware/ransomware-guide)
- [FBI Internet Crime Complaint Center — Ransomware](https://www.ic3.gov/CrimeInfo/Ransomware)
- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [UK National Cyber Security Centre — Ransomware attack](https://www.ncsc.gov.uk/section/respond-recover/ransomware-attack)
- [UK National Cyber Security Centre — Mitigating malware and ransomware attacks](https://www.ncsc.gov.uk/guidance/mitigating-malware-and-ransomware-attacks)

## Need help?

MANDID supports remote incident containment, investigation, recovery and hardening for websites, web applications, servers and online accounts.

[Request cybersecurity help from MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=ransomware-initial-response)
