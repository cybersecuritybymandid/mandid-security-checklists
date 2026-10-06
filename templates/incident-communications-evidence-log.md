# Incident Communications and Evidence Log Template

Use this template to keep incident facts, communications, decisions, actions and evidence references in one controlled record. Copy it into the organization's private incident workspace before use. Do **not** fill it with client data, credentials, personal information, indicators, internal addresses or evidence in a public repository.

> **Scope:** Defensive incident-response work on systems you own or are explicitly authorized to protect. Adapt the template to applicable legal, regulatory, contractual, insurer and retention requirements. Involve legal, privacy, HR, safety and law-enforcement contacts when the situation requires them.

## Quick-start rules

- [ ] Create a unique incident ID and assign an incident commander.
- [ ] Choose one authoritative timezone and record it on every entry.
- [ ] Store this record in an access-controlled case location.
- [ ] Use approved out-of-band communications if primary systems may be compromised.
- [ ] Record facts separately from assumptions, hypotheses and unverified reports.
- [ ] Preserve original evidence before analysis or remediation when it is safe to do so.
- [ ] Keep secrets and sensitive evidence out of ordinary chat, email and public tickets.
- [ ] Record who approved every high-impact containment or recovery action.
- [ ] Define the next update time even when there is no material change.

## 1. Incident header

| Field | Value |
|---|---|
| Incident ID | `[INC-YYYY-NNN]` |
| Incident title | `[Short factual title]` |
| Status | `[Investigating / Contained / Recovering / Monitoring / Closed]` |
| Severity | `[SEV-1 / SEV-2 / SEV-3 / SEV-4]` |
| Record classification | `[Internal handling label and/or TLP label]` |
| Authoritative timezone | `[UTC or named timezone]` |
| Earliest known activity | `[YYYY-MM-DD HH:MM TZ / Unknown]` |
| Detection time | `[YYYY-MM-DD HH:MM TZ]` |
| Incident opened | `[YYYY-MM-DD HH:MM TZ]` |
| Incident commander | `[Name / role / contact method]` |
| Technical lead | `[Name / role / contact method]` |
| Communications lead | `[Name / role / contact method]` |
| Legal/privacy contact | `[Name / role / contact method]` |
| Evidence custodian | `[Name / role / contact method]` |
| Executive owner | `[Name / role / contact method]` |
| Affected services | `[Systems, regions, tenants or business processes]` |
| Current business impact | `[Availability, confidentiality, integrity, safety, revenue or customer impact]` |
| Next review/update | `[YYYY-MM-DD HH:MM TZ]` |

## 2. Coordination and communications plan

### Approved channels

| Purpose | Approved channel | Owner | Backup channel | Access reviewed? |
|---|---|---|---|---|
| Incident command | `[Private bridge/channel]` | `[Owner]` | `[Backup]` | `[Yes/No]` |
| Technical response | `[Private technical channel]` | `[Owner]` | `[Backup]` | `[Yes/No]` |
| Evidence transfer | `[Approved secure case system]` | `[Custodian]` | `[Backup]` | `[Yes/No]` |
| Executive updates | `[Approved channel]` | `[Owner]` | `[Backup]` | `[Yes/No]` |
| Customer/status updates | `[Status page/support process]` | `[Owner]` | `[Backup]` | `[Yes/No]` |

### Update cadence

| Audience | Cadence | Owner | Required content | Approval required |
|---|---|---|---|---|
| Response team | `[e.g., every 30 minutes]` | `[Owner]` | Impact, facts, actions, blockers, next steps | `[Role]` |
| Leadership | `[e.g., hourly]` | `[Owner]` | Business impact, risk, decisions needed | `[Role]` |
| Customers/users | `[When material / scheduled]` | `[Owner]` | Confirmed impact, mitigation, next update | `[Role]` |
| Regulators/insurer/partners | `[Per obligation]` | `[Owner]` | Approved facts and required fields | `[Role]` |

### Stakeholder directory

| Stakeholder | Role in incident | Primary contact | Backup contact | Notification threshold | Status |
|---|---|---|---|---|---|
| `[Team/vendor/authority]` | `[Responsibility]` | `[Approved route]` | `[Approved route]` | `[Condition]` | `[Not contacted / Contacted / Engaged]` |

## 3. Current situation board

### Confirmed facts

- `[Timestamp — fact and evidence reference]`

### Unverified reports or hypotheses

- `[Timestamp — statement, confidence, owner and validation plan]`

### Known impact

- `[Affected service/user/data/business process and evidence reference]`

### Unknowns

- `[Question — owner — expected answer time]`

### Actions in progress

- `[Action — owner — start time — expected completion — risk/rollback]`

### Decisions needed

- `[Decision — decision owner — deadline — options and consequences]`

## 4. Standard internal update

Copy and complete this block for each scheduled update:

```text
INCIDENT: [ID and short title]
STATUS / SEVERITY: [Status] / [Severity]
UPDATE TIME: [YYYY-MM-DD HH:MM TZ]
NEXT UPDATE: [YYYY-MM-DD HH:MM TZ]

CURRENT IMPACT
- [Confirmed impact]

WHAT WE KNOW
- [Confirmed fact with evidence or timeline reference]

WHAT REMAINS UNKNOWN
- [Open question and owner]

ACTIONS COMPLETED SINCE LAST UPDATE
- [Action, result and change/decision reference]

ACTIONS IN PROGRESS
- [Action, owner and expected completion]

RISKS / BLOCKERS / DECISIONS NEEDED
- [Item and decision owner]

COMMUNICATIONS / NOTIFICATIONS
- [Audience, time, owner and communication-log reference]
```

## 5. External or status-page update

Use only confirmed, approved information. Do not expose indicators, internal architecture, personal data, investigative hypotheses or unsupported attribution.

```text
[Service or organization] is investigating [plain-language description of confirmed impact].

We identified the issue in [time and timezone]. Our response team is [high-level action that is safe to disclose]. [State what remains available or which users are affected, if confirmed.]

The next update will be provided by [time and timezone], or earlier if there is a material change.
```

## 6. Communications and notification log

| Entry ID | Timestamp | Direction | Audience/recipient | Channel | Summary | Approved by | Sent by | Evidence/reference | Follow-up due |
|---|---|---|---|---|---|---|---|---|---|
| `COM-001` | `[YYYY-MM-DD HH:MM TZ]` | `[Inbound/Outbound]` | `[Audience]` | `[Channel]` | `[Facts shared/request received]` | `[Role]` | `[Name]` | `[Case path or message ID]` | `[Time/None]` |

Record unsuccessful contact attempts, voicemail, ticket numbers, provider case IDs and promised response times.

## 7. Evidence handling guardrails

- [ ] Identify the legal owner and evidence custodian before collection begins.
- [ ] Preserve the original and perform analysis on a verified working copy when feasible.
- [ ] Record the system clock, timezone and time source for every collected source.
- [ ] Export native or raw data with metadata; screenshots alone are not primary evidence.
- [ ] Use approved tools and document the collection method and tool version.
- [ ] Calculate a cryptographic hash where the format and collection method support it.
- [ ] Store evidence in an access-controlled location with audit logging and backups.
- [ ] Restrict access to people with a defined incident role and business need.
- [ ] Record every transfer, export, transformation and analysis copy.
- [ ] Never alter, rename, decompress, mount or execute the original without documenting the need and authorization.
- [ ] Do not upload evidence to public scanners, consumer file-sharing sites or unapproved AI services.
- [ ] Apply retention, legal-hold, privacy and cross-border transfer requirements.
- [ ] Escalate to legal counsel or qualified forensic support when evidence may be used in litigation, insurance, employment action or law enforcement.

## 8. Evidence register

| Evidence ID | Collected at | Source/system | Description and scope | Collector | Collection method/tool | Original hash | Format/size | Secure storage location | Access/classification | Related timeline/action |
|---|---|---|---|---|---|---|---|---|---|---|
| `EVD-001` | `[YYYY-MM-DD HH:MM TZ]` | `[Hostname/account/provider]` | `[What was collected and boundaries]` | `[Name]` | `[Method and version]` | `[Algorithm:value / N/A with reason]` | `[Type/size]` | `[Case-system reference, not a public URL]` | `[Restriction]` | `[TL-001 / ACT-001]` |

### Evidence validation record

| Validation ID | Evidence ID | Timestamp | Copy/hash validated by | Result | Notes |
|---|---|---|---|---|---|
| `VAL-001` | `EVD-001` | `[YYYY-MM-DD HH:MM TZ]` | `[Name]` | `[Match / Mismatch]` | `[Details and action]` |

## 9. Chain-of-custody / transfer log

| Transfer ID | Evidence ID | Released by | Received by | Timestamp | Purpose | Transfer method | Integrity check | New storage location | Sign-off/reference |
|---|---|---|---|---|---|---|---|---|---|
| `CST-001` | `EVD-001` | `[Name]` | `[Name]` | `[YYYY-MM-DD HH:MM TZ]` | `[Analysis/legal/provider]` | `[Approved secure method]` | `[Hash/result]` | `[Case reference]` | `[Ticket/form]` |

## 10. Incident timeline

Use one row per observable event. Distinguish the time the event occurred from the time it was discovered.

| Timeline ID | Event time | Discovery time | Source | Event | Confidence | Evidence ID | Analyst/owner |
|---|---|---|---|---|---|---|---|
| `TL-001` | `[YYYY-MM-DD HH:MM TZ]` | `[YYYY-MM-DD HH:MM TZ]` | `[Log/provider/person]` | `[Factual event]` | `[High/Medium/Low]` | `EVD-001` | `[Name]` |

## 11. Decision and change log

| Decision ID | Timestamp | Decision/change | Reason and evidence | Approved by | Implemented by | Expected effect | Risk | Rollback condition | Result |
|---|---|---|---|---|---|---|---|---|---|
| `DEC-001` | `[YYYY-MM-DD HH:MM TZ]` | `[Decision or change]` | `[Reason/reference]` | `[Name/role]` | `[Name]` | `[Expected outcome]` | `[Customer/security risk]` | `[Trigger and method]` | `[Observed result]` |

## 12. Action tracker

| Action ID | Action | Owner | Priority | Started | Due | Dependencies | Status | Completion evidence | Follow-up |
|---|---|---|---|---|---|---|---|---|---|
| `ACT-001` | `[Concrete action]` | `[Name]` | `[P0-P3]` | `[Time]` | `[Time]` | `[IDs/teams]` | `[Open/In progress/Blocked/Done]` | `[Evidence or change reference]` | `[Item/None]` |

## 13. Indicators and sensitive artifacts

Keep sensitive indicators, credentials, personal data, malware samples and infrastructure details in a separate restricted appendix or approved case system. Reference them here only by case identifier.

| Restricted reference | Type | Relevance | Confidence | First seen | Last seen | Owner | Sharing restriction |
|---|---|---|---|---|---|---|---|
| `[IOC-001]` | `[Hash/domain/account/etc.]` | `[Why it matters]` | `[High/Medium/Low]` | `[Time]` | `[Time]` | `[Name]` | `[Policy/TLP/legal restriction]` |

## 14. Shift handoff

```text
HANDOFF TIME: [YYYY-MM-DD HH:MM TZ]
OUTGOING / INCOMING LEAD: [Names]

CURRENT STATUS AND IMPACT
- [Summary]

ACTIVE CONTAINMENT / RECOVERY CONTROLS
- [Control, owner, start time and rollback condition]

TOP OPEN ACTIONS
- [Action ID, owner and due time]

KEY UNKNOWNS / RISKS
- [Item and validation plan]

PENDING COMMUNICATIONS / NOTIFICATIONS
- [Audience, owner and deadline]

NEXT DECISION / UPDATE
- [Time and required participants]
```

## 15. Closure and post-incident record

- [ ] Service owners have accepted current health and residual risk.
- [ ] Temporary access, accounts, bypasses, firewall/WAF rules and elevated permissions are removed or formally accepted.
- [ ] All external and internal communications are preserved in the case record.
- [ ] Evidence retention, legal hold and deletion dates are assigned.
- [ ] Required customer, regulator, insurer, contractual and law-enforcement follow-ups are tracked.
- [ ] The final timeline separates confirmed events from unresolved hypotheses.
- [ ] Root causes, contributing factors and control gaps are documented without unsupported attribution.
- [ ] Corrective actions have owners, priorities, target dates and validation criteria.
- [ ] A post-incident review date and audience are scheduled.
- [ ] A sanitized lessons-learned summary is prepared without exposing client or operationally sensitive data.

## Escalate immediately when

- Safety, health, identity, payment, regulated or other critical services are affected.
- There is confirmed or suspected exposure of personal, confidential, regulated or client data.
- Privileged, cloud, identity-provider, backup, logging or security-tool access may be compromised.
- Evidence may be needed for litigation, insurance, employment action or law enforcement.
- Ransomware, extortion, destructive activity, insider involvement or coordinated fraud is suspected.
- The team lacks the authority, access, telemetry or expertise needed to contain the event safely.
- A notification deadline may apply or the incident crosses jurisdictions.

## Authoritative references

- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [NIST SP 800-86 — Guide to Integrating Forensic Techniques into Incident Response](https://csrc.nist.gov/pubs/sp/800/86/final)
- [CISA — Federal Government Cybersecurity Incident and Vulnerability Response Playbooks](https://www.cisa.gov/sites/default/files/2023-01/federal_government_cybersecurity_incident_and_vulnerability_response_playbooks_508c_5.pdf)
- [FIRST — Traffic Light Protocol (TLP) Version 2.0](https://www.first.org/tlp/)

## Need help?

MANDID supports remote incident containment, investigation, recovery and hardening for websites, web applications, servers and online accounts.

[Request cybersecurity help from MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=incident-communications-evidence-log)
