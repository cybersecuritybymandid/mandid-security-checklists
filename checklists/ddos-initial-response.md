# DDoS Initial Response Checklist

Use this checklist when a website, API, DNS service, remote-access gateway or other internet-facing service becomes unusually slow, intermittent or unavailable and a denial-of-service attack is suspected.

> **Scope:** Defensive response for systems and services you own or are explicitly authorized to protect. Do not retaliate, probe suspected sources or make unsupported attribution claims. Coordinate disruptive changes with the service owner and upstream providers. Follow applicable legal, regulatory, contractual, insurer and incident-notification requirements.

## 0. Open and own the incident

- [ ] Record the incident owner, technical lead, communications lead, start time and timezone.
- [ ] Open a timestamped incident log and record every action, observation, decision and result.
- [ ] Identify who can authorize provider escalation, emergency configuration changes, traffic filtering and service degradation.
- [ ] List the affected services, domains, IP addresses, regions, customer groups and business processes.
- [ ] Assign an initial severity based on availability, safety, revenue, contractual obligations and dependency impact.
- [ ] Move incident coordination to a trusted channel that does not depend on the affected service.
- [ ] Confirm emergency contacts for the ISP, hosting provider, CDN, DNS provider, DDoS-protection provider and critical vendors.

## 1. Confirm what is failing

- [ ] Test the service from more than one trusted external network and geographic location.
- [ ] Separate complete outage, intermittent failure, high latency, elevated error rate and partial functional degradation.
- [ ] Check whether the problem affects the public hostname, origin IP, API, authentication, DNS, database or a third-party dependency.
- [ ] Record HTTP status codes, connection errors, DNS responses, latency and packet loss from approved monitoring systems.
- [ ] Compare current traffic, request rate and resource consumption with a known normal baseline.
- [ ] Check status dashboards and maintenance records for the ISP, cloud, CDN, DNS and application providers.
- [ ] Determine whether a legitimate traffic spike, release, campaign, crawler, retry storm or configuration error could explain the symptoms.
- [ ] Do not label the event a DDoS attack until evidence supports that assessment.

## 2. Preserve evidence and telemetry

- [ ] Preserve edge, CDN, WAF, load-balancer, reverse-proxy, firewall, DNS, application and infrastructure telemetry.
- [ ] Record traffic volume, packets per second, requests per second, concurrent connections, bandwidth and error rates.
- [ ] Record affected protocols, ports, methods, paths, hostnames, autonomous systems, countries and user-agent patterns where available.
- [ ] Preserve sampled packet or flow data only through approved systems and within privacy and retention requirements.
- [ ] Export provider event identifiers, mitigation notices, rule changes and attack summaries.
- [ ] Preserve application, database and operating-system metrics showing the bottleneck or cascade failure.
- [ ] Record screenshots for context, but retain machine-readable logs and metrics as the primary evidence.
- [ ] Synchronize timestamps and record the time source used by each relevant system.
- [ ] Store evidence in an access-controlled case location and document who collected it.

## 3. Identify the exhausted resource

- [ ] Determine whether external bandwidth or an upstream link is saturated.
- [ ] Check whether packet-processing capacity, connection tables or load balancers are exhausted.
- [ ] Check CPU, memory, worker pools, queues, file descriptors, sockets and thread limits.
- [ ] Check application endpoints for expensive queries, searches, exports, logins, uploads or cache misses.
- [ ] Check database connections, query latency, locks, storage latency and replication health.
- [ ] Check whether logs, temporary files, upload areas or queues are consuming storage.
- [ ] Check DNS availability, authoritative-server health and query patterns.
- [ ] Look for cascading failures caused by retries, health checks, autoscaling or dependent services.
- [ ] Identify which component fails first and which controls remain reachable.

## 4. Classify the likely traffic pattern

- [ ] Determine whether the event is primarily volumetric, protocol/state exhaustion, application-layer abuse or a combination.
- [ ] Identify whether traffic is concentrated on one IP, hostname, port, method, path or application function.
- [ ] Check for unusually high connection creation, incomplete handshakes, long-lived connections or reset patterns.
- [ ] Check for repetitive requests that bypass cache or trigger expensive backend work.
- [ ] Check for reflected or amplified UDP traffic using provider and flow telemetry.
- [ ] Check whether attackers rotate source addresses, networks, countries, headers, paths or client fingerprints.
- [ ] Distinguish apparent source addresses from verified actor infrastructure; spoofing and compromised devices are common.
- [ ] Record confidence and uncertainty instead of making premature attribution claims.

## 5. Engage upstream providers early

- [ ] Open the appropriate severity case with the ISP, host, CDN or DDoS-protection provider.
- [ ] Provide the affected services, incident start time, current impact, traffic characteristics and case contact.
- [ ] Share only the evidence required for mitigation and use the provider's approved secure channel.
- [ ] Ask whether automatic protections triggered and request the relevant event or mitigation identifier.
- [ ] Confirm which protections the provider can apply upstream before traffic reaches the constrained link or origin.
- [ ] Agree on who will change filters, routes, scrubbing, rate limits, caching and origin access controls.
- [ ] Record every provider recommendation, action, timestamp and observed result.
- [ ] Escalate when capacity is saturated, mitigation is ineffective or the provider response does not match business impact.

## 6. Protect administrative access and the response team

- [ ] Confirm that responders retain secure out-of-band access to critical infrastructure.
- [ ] Keep management interfaces off the public path where the architecture permits it.
- [ ] Verify that emergency access does not bypass authentication, logging or change control.
- [ ] Protect monitoring, logging, DNS administration, status pages and communication channels from the same failure mode.
- [ ] Ensure rate limits or blocks do not lock out trusted responders, monitoring systems or providers.
- [ ] Use a second reviewer for broad or high-impact traffic-control changes whenever time permits.
- [ ] Record an owner and rollback condition for every emergency change.

## 7. Apply edge and network mitigations safely

- [ ] Prefer upstream, CDN or scrubbing controls when local bandwidth is already saturated.
- [ ] Enable or tune provider DDoS protections according to the approved response plan.
- [ ] Apply narrowly scoped rate limits using verified attack characteristics.
- [ ] Use WAF, firewall, load-balancer or provider filters only when the matching signal is reliable enough.
- [ ] Consider temporary geographic, network or client restrictions only after evaluating legitimate-user impact.
- [ ] Cache safe static and anonymous content at the edge where business and security requirements allow it.
- [ ] Restrict direct origin access so legitimate traffic reaches the origin through approved edge services.
- [ ] Verify that origin addresses have not been exposed through DNS history, alternate records or direct links.
- [ ] Avoid indiscriminate source-IP blocking when addresses are spoofed, shared or rapidly rotating.
- [ ] Treat blackholing as a last-resort availability trade-off and coordinate it with the provider and service owner.
- [ ] Measure the effect after each change before adding another broad control.

## 8. Reduce application-layer pressure

- [ ] Identify endpoints with disproportionate request volume, compute cost or database impact.
- [ ] Temporarily disable or restrict nonessential expensive functions using approved feature controls.
- [ ] Apply endpoint-specific rate limits, concurrency limits and queue limits.
- [ ] Require stronger validation or authentication for functions that should not be publicly anonymous.
- [ ] Increase safe caching for content that does not contain user-specific or sensitive data.
- [ ] Use graceful degradation to preserve critical transactions while reducing nonessential features.
- [ ] Review retries and timeouts so failed dependencies do not amplify load.
- [ ] Confirm that autoscaling is helping rather than increasing cost or overloading downstream systems.
- [ ] Ensure bot challenges and client checks remain accessible and do not block legitimate automation unexpectedly.
- [ ] Monitor false positives, customer impact and attacker adaptation after every rule change.

## 9. Check DNS and external dependencies

- [ ] Verify authoritative DNS availability from multiple trusted resolvers and regions.
- [ ] Check nameserver delegation, record integrity, DNSSEC status and provider health.
- [ ] Confirm that emergency DNS changes will not expose the origin or bypass DDoS protection.
- [ ] Account for TTL and cache propagation before expecting a DNS change to take effect.
- [ ] Check authentication, payment, messaging, API and identity dependencies for independent outages or overload.
- [ ] Avoid moving traffic to an unprotected fallback that cannot absorb the attack.
- [ ] Record dependency contacts, case numbers and recovery estimates.

## 10. Communicate accurately

- [ ] Provide responders and leadership with a regular update cadence.
- [ ] State what is affected, what remains available, what is known, what is uncertain and what actions are underway.
- [ ] Publish customer updates through a status channel that remains available during the incident.
- [ ] Avoid unsupported attribution, attacker engagement and speculation about ransom or motive.
- [ ] Coordinate legal, privacy, regulatory, contractual and insurer notifications when applicable.
- [ ] Give support teams a consistent message and a route for escalating high-impact customer reports.
- [ ] Preserve copies and timestamps of all external and internal communications.

## 11. Watch cost, capacity and secondary risk

- [ ] Monitor bandwidth, CDN, WAF, logging, serverless, autoscaling and data-transfer cost during the event.
- [ ] Set or review approved budget alerts without disabling telemetry required for response.
- [ ] Watch for disk exhaustion caused by verbose logging or attack-generated data.
- [ ] Confirm that emergency scaling does not exhaust quotas in another region or service.
- [ ] Monitor for credential attacks, scanning, exploitation or fraud hidden behind the availability incident.
- [ ] Check whether responders are being targeted with phishing, impersonation or false mitigation instructions.
- [ ] Preserve security controls that protect confidentiality and integrity while restoring availability.

## 12. Continually reassess the attack

- [ ] Track traffic volume, request patterns, error rates, latency, capacity and legitimate-user success over time.
- [ ] Confirm whether the attacker changes vectors after each mitigation.
- [ ] Reassess the exhausted resource and business impact at agreed intervals.
- [ ] Remove ineffective emergency rules that add complexity or customer harm.
- [ ] Keep a current list of active mitigations, owners, creation times and rollback criteria.
- [ ] Validate service health from outside the protected network, not only from internal monitoring.
- [ ] Escalate when the attack exceeds provider capability, threatens safety or affects multiple critical services.

## 13. Recover deliberately

- [ ] Begin recovery when traffic and resource use remain within acceptable limits and protections are stable.
- [ ] Restore disabled features in controlled stages, starting with the most important business functions.
- [ ] Keep enhanced monitoring active while removing temporary restrictions.
- [ ] Verify application, API, DNS, authentication, database and dependency health after each recovery step.
- [ ] Check data processing queues, scheduled jobs, webhooks and retries accumulated during the outage.
- [ ] Confirm that no emergency account, route, firewall rule, WAF rule or bypass remains undocumented.
- [ ] Reconcile provider actions and obtain attack or mitigation reports when available.
- [ ] Communicate restoration and any remaining limitations through approved channels.
- [ ] Close the incident only after owners accept service health and residual risk.

## 14. Review and improve

- [ ] Build a timeline covering detection, escalation, mitigation, adaptation, recovery and communication.
- [ ] Document the attack patterns, affected bottlenecks, effective controls, ineffective controls and false positives.
- [ ] Compare actual response times and contacts with the response plan and service commitments.
- [ ] Update architecture diagrams, provider runbooks, escalation paths and emergency access procedures.
- [ ] Improve baselines, dashboards and alerts for bandwidth, connections, requests, errors and resource exhaustion.
- [ ] Close origin exposure, caching, rate-limit, capacity and dependency weaknesses discovered during the incident.
- [ ] Test the revised response plan through an authorized tabletop or provider-supported exercise.
- [ ] Track every corrective action to an owner and target date.
- [ ] Share sanitized lessons learned without publishing client data, secrets, live indicators or sensitive infrastructure details.

## Escalate immediately when

- [ ] Critical public, safety, health, payment, identity or remote-access services are unavailable.
- [ ] Upstream capacity is saturated or local controls cannot receive legitimate traffic.
- [ ] The attack affects multiple regions, providers, domains or critical dependencies.
- [ ] There are signs of simultaneous intrusion, credential compromise, data exposure, fraud or extortion.
- [ ] Emergency mitigations could materially affect customers, partners, contractual obligations or regulated services.
- [ ] The organization lacks the access, telemetry, provider support or authority needed to contain the event safely.

## Authoritative references

- [CISA, FBI and MS-ISAC — Understanding and Responding to Distributed Denial-of-Service Attacks](https://www.cisa.gov/sites/default/files/publications/understanding-and-responding-to-ddos-attacks_508c.pdf)
- [UK National Cyber Security Centre — Denial of Service guidance](https://www.ncsc.gov.uk/collection/denial-service-dos-guidance-collection)
- [UK National Cyber Security Centre — Responding to a DoS attack](https://www.ncsc.gov.uk/collection/denial-service-dos-guidance-collection/a-minimal-denial-of-service-response-plan)
- [NIST SP 800-61 Rev. 3 — Incident Response Recommendations and Considerations](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [Cloudflare Developers — How to prevent DDoS attacks](https://developers.cloudflare.com/learning-paths/prevent-ddos-attacks/concepts/ddos-prevention/)

## Need help?

MANDID supports remote incident containment, investigation, recovery and hardening for websites, web applications, servers and online accounts.

[Request cybersecurity help from MANDID](https://mandidsecurity.com/cyber-help/?utm_source=github&utm_medium=repository&utm_campaign=mandid-security-checklists&utm_content=ddos-initial-response)
