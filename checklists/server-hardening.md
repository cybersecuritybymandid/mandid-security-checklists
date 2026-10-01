# Server Hardening Checklist

Use this checklist when deploying a new server, reviewing an existing host, recovering from an incident, or preparing an internet-facing system for production. Adapt every control to the operating system, workload, business impact and recovery requirements.

> **Scope:** Defensive administration of servers you own or are explicitly authorized to protect. Test changes in a safe environment and maintain a documented rollback path. A generic checklist does not replace the vendor's current hardening guide, an applicable CIS Benchmark, regulatory requirements or an architecture-specific security review.

## 0. Establish ownership and a baseline

- [ ] Record the server owner, technical administrator, business purpose, environment and data classification.
- [ ] Document the operating system, version, role, hostname, IP addresses, cloud account, region and network segment.
- [ ] List every required service, port, protocol, administrator interface and external dependency.
- [ ] Record the approved maintenance window, recovery time objective and recovery point objective.
- [ ] Create a protected inventory of installed packages, services, scheduled tasks, users, groups and listening ports.
- [ ] Confirm that security changes, exceptions and rollback decisions will be recorded.

## 1. Minimize the attack surface

- [ ] Use a supported operating-system release and a minimal installation appropriate for the server role.
- [ ] Remove or disable unused packages, services, protocols, sample applications, default sites and management agents.
- [ ] Do not install general browsing, office, development or messaging software on production servers unless the workload requires it.
- [ ] Disable legacy and insecure protocols that are not explicitly required.
- [ ] Bind services only to required interfaces and addresses.
- [ ] Keep administrative interfaces off the public internet whenever possible.
- [ ] Separate production, staging, development and management environments.
- [ ] Reconfirm the business owner for every exposed port and service.

## 2. Patch and lifecycle management

- [ ] Enable a documented process for operating-system, application, firmware, runtime and dependency updates.
- [ ] Prioritize actively exploited and internet-facing vulnerabilities.
- [ ] Subscribe to vendor security advisories for the operating system and critical server software.
- [ ] Test significant updates and define a rollback plan before production deployment.
- [ ] Track end-of-life dates and replace unsupported operating systems, packages and appliances.
- [ ] Scan for missing patches and known vulnerabilities after deployment and on a recurring schedule.
- [ ] Verify that updates actually installed and that required reboots were completed.

## 3. Accounts, privileges and authentication

- [ ] Remove or disable default, dormant, shared and unnecessary accounts.
- [ ] Assign administrators individual named accounts; do not use shared privileged credentials.
- [ ] Separate normal user activity from privileged administration.
- [ ] Apply least privilege to users, groups, service accounts and application identities.
- [ ] Require MFA for administrative access where the platform supports it.
- [ ] Enforce strong, unique credentials and store them in an approved password manager or secrets system.
- [ ] Rotate default, exposed or inherited credentials before production use.
- [ ] Disable direct remote login for highly privileged built-in accounts where feasible.
- [ ] Review sudoers, local administrators, privileged groups and delegated rights.
- [ ] Give service accounts only the permissions, logon methods and network access their workload requires.
- [ ] Define an emergency-access process and monitor every use of break-glass accounts.

## 4. Secure SSH, RDP and management access

- [ ] Restrict management access to trusted networks, a VPN, bastion host or zero-trust access layer.
- [ ] Allowlist administrative source addresses when operationally practical.
- [ ] Prefer managed keys or certificates over reusable passwords for SSH.
- [ ] Remove unauthorized SSH keys and review key ownership, age and purpose.
- [ ] Disable obsolete cryptographic algorithms and protocol versions according to current vendor guidance.
- [ ] Protect RDP with MFA and a controlled gateway; do not expose it directly to the internet.
- [ ] Set reasonable idle-session and authentication-attempt limits.
- [ ] Log successful and failed administrative sessions.
- [ ] Review remote-management tools, web panels, hypervisor consoles and cloud serial consoles.

## 5. Host firewall and network exposure

- [ ] Use a default-deny inbound policy and permit only documented traffic.
- [ ] Restrict outbound traffic where the server role allows it.
- [ ] Separate public services, application tiers, databases, backups and management networks.
- [ ] Prevent databases, caches, message brokers and internal APIs from being publicly reachable unless explicitly designed for it.
- [ ] Review cloud security groups, network ACLs, load balancers, NAT rules and provider firewalls together with the host firewall.
- [ ] Verify exposure from an external perspective after every network change.
- [ ] Document temporary firewall exceptions with an owner and expiration date.

## 6. Service and application configuration

- [ ] Replace default configurations, example content and vendor test credentials.
- [ ] Run services under dedicated non-privileged identities.
- [ ] Restrict file, directory, registry and configuration permissions to the minimum required.
- [ ] Store application data outside publicly served directories when possible.
- [ ] Disable directory listing, verbose production errors, debug interfaces and unnecessary status pages.
- [ ] Set safe upload limits, file-type controls and execution restrictions for web-facing workloads.
- [ ] Protect administrative routes separately from public application traffic.
- [ ] Review containers, orchestration agents, databases, web servers and runtimes against their current vendor or CIS hardening guidance.
- [ ] Ensure one compromised service cannot freely access unrelated secrets or workloads.

## 7. Secrets, certificates and encryption

- [ ] Keep passwords, API keys, private keys and tokens out of source code, images, logs and public repositories.
- [ ] Use a managed secrets store where practical and restrict which workloads can retrieve each secret.
- [ ] Rotate deployment, database, cloud and integration secrets on a defined schedule and after suspected exposure.
- [ ] Inventory TLS certificates, private keys, issuers, expiration dates and renewal ownership.
- [ ] Use current TLS configurations and disable deprecated protocols and weak cipher suites according to vendor guidance.
- [ ] Encrypt sensitive data at rest and protect encryption keys separately from the data.
- [ ] Review backup encryption and recovery-key access.

## 8. Logging, monitoring and time

- [ ] Enable authentication, privilege, service, configuration, firewall and security-control logging.
- [ ] Forward important logs to a protected remote system so an attacker cannot erase the only copy.
- [ ] Synchronize time with approved reliable sources and monitor time drift.
- [ ] Define retention periods based on investigation and compliance needs.
- [ ] Alert on new privileged accounts, repeated authentication failures, service changes, unexpected listening ports and security-control changes.
- [ ] Monitor suspicious outbound connections, DNS activity, resource spikes and unusual child processes.
- [ ] Test that alerts reach an accountable responder and include enough context to act.
- [ ] Keep sensitive data and secrets out of logs whenever possible.

## 9. Integrity and endpoint protection

- [ ] Deploy supported endpoint detection, anti-malware or workload-protection controls when appropriate for the platform.
- [ ] Establish file-integrity or configuration-drift monitoring for critical paths.
- [ ] Monitor startup items, scheduled tasks, system services, kernel modules and administrative tools.
- [ ] Protect security agents and logging services from unauthorized disabling.
- [ ] Baseline expected processes, network listeners and resource use.
- [ ] Investigate unexpected exclusions, unsigned binaries and changes to security tooling.

## 10. Backups and recovery

- [ ] Maintain versioned backups of required data, configurations and infrastructure definitions.
- [ ] Keep at least one recovery copy isolated from normal administrator and production credentials.
- [ ] Protect backup consoles and repositories with MFA, least privilege and logging.
- [ ] Define what must be rebuilt from clean media instead of restored from a potentially compromised image.
- [ ] Test restoration regularly and record the last successful recovery test.
- [ ] Confirm that backups include required encryption keys, certificates and configuration data without exposing them unnecessarily.
- [ ] Document the clean rebuild procedure and dependencies.

## 11. Cloud, virtual and container hosts

- [ ] Use separate cloud roles and service identities instead of long-lived shared access keys.
- [ ] Review instance metadata access, workload identity and token permissions.
- [ ] Restrict snapshot, image, console, serial-port and disk-attachment permissions.
- [ ] Keep base images minimal, patched, reproducible and traceable to an approved source.
- [ ] Scan images and dependencies before deployment and on a recurring schedule.
- [ ] Do not expose container engines, orchestration dashboards or node-management ports publicly.
- [ ] Review host-to-container, container-to-container and control-plane network boundaries.
- [ ] Record whether provider-native logging, threat detection and configuration monitoring are enabled.

## 12. Validate before production

- [ ] Compare the final configuration with the applicable vendor guide and current CIS Benchmark.
- [ ] Run authenticated vulnerability and configuration assessments with explicit authorization.
- [ ] Confirm that only approved ports are reachable from each relevant network zone.
- [ ] Test administrator access, application health, logging, alerting, backup and restoration.
- [ ] Verify that emergency access works and is monitored.
- [ ] Record accepted risks, compensating controls, owners and review dates.
- [ ] Obtain technical and business approval before exposing the workload.

## 13. Maintain the hardened state

- [ ] Review privileged access, exposed services, firewall rules and security exceptions regularly.
- [ ] Reassess hardening after major upgrades, migrations, role changes and security incidents.
- [ ] Detect and investigate configuration drift.
- [ ] Repeat vulnerability scanning and remediate findings according to risk.
- [ ] Retire unused servers securely and revoke their accounts, keys, certificates, DNS records and integrations.
- [ ] Schedule the next hardening review and assign an owner.

## Fast escalation triggers

Escalate to experienced incident responders or platform specialists when:

- an internet-facing service shows evidence of exploitation;
- an unknown privileged account, key, service or scheduled task is discovered;
- important logs are missing, altered or unexpectedly disabled;
- suspicious outbound traffic or persistence returns after remediation;
- domain, identity, backup, hypervisor or cloud control-plane access may be compromised;
- regulated, customer, payment or identity data may be exposed;
- the system cannot be confidently restored to a known-good state.

## Authoritative references

- [NIST SP 800-123 — Guide to General Server Security](https://csrc.nist.gov/pubs/sp/800/123/final)
- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations for Cybersecurity Risk Management](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [CIS Benchmarks — Secure configuration recommendations](https://www.cisecurity.org/cis-benchmarks-overview)
- [CISA — Secure Our World](https://www.cisa.gov/secure-our-world)

Need help assessing, hardening or recovering a server? [Contact MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=server-hardening).
