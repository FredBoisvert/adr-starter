# ADR-XXXX: [Short security decision title]

- **Status:** Proposed
- **Date:** YYYY-MM-DD
- **Decision owners:** [Names, team, or role]
- **Scope:** [Systems, services, data, environments, or integrations affected]
- **Related:** [Threat model, tickets, diagrams, PRs, related ADRs]
- **Supersedes:** [ADR-XXXX, if applicable]
- **Review date:** YYYY-MM-DD

## Context

Describe the security decision, its business and technical context, and why it is needed.

Include relevant constraints such as:

- Data classification or sensitivity
- Regulatory, privacy, contractual, or internal-policy requirements
- Existing platforms, legacy dependencies, delivery deadlines, or budget
- Assumptions that could affect this decision

### Assets and Security Objectives

| Asset / Data | Classification | Security Objective |
|---|---|---|
| [Customer data] | Confidential | Confidentiality, privacy |
| [Service credentials] | Restricted | Confidentiality, integrity |
| [Orders / transactions] | Confidential | Integrity, availability |
| [Audit logs] | Internal | Integrity, accountability |

---

## STRIDE Threat Assessment

Identify the material threats relevant to this decision. Link to a fuller threat model if needed.

| STRIDE Category | Threat Scenario | Affected Asset / Flow | Mitigation / Control | Residual Risk |
|---|---|---|---|---|
| **Spoofing** | [Attacker impersonates a user or service] | [Authentication flow] | [MFA, OIDC, workload identity] | [Low / Medium / High] |
| **Tampering** | [Request, event, or record is changed] | [API / data store] | [Authorization, signatures, integrity checks] | [Low / Medium / High] |
| **Repudiation** | [Actor denies performing an action] | [Privileged operation] | [Immutable audit trail, timestamps] | [Low / Medium / High] |
| **Information Disclosure** | [Sensitive data is exposed] | [Logs, API response, storage] | [Encryption, masking, access controls] | [Low / Medium / High] |
| **Denial of Service** | [Service is exhausted or unavailable] | [Public endpoint / dependency] | [Rate limits, quotas, resilience controls] | [Low / Medium / High] |
| **Elevation of Privilege** | [Actor gains unauthorized permissions] | [Admin functions / IAM] | [Least privilege, server-side authorization] | [Low / Medium / High] |

---

## Decision

State the decision directly.

> We will [chosen security approach] for [scope].

Specify mandatory boundaries or requirements. For example:

> We will use OpenID Connect with a managed identity provider for customer authentication. APIs will validate access tokens and enforce tenant-aware authorization server-side.

---

## Decision Drivers

- [Protection of sensitive data or critical operations]
- [Compliance or contractual obligation]
- [Least privilege and auditability]
- [Operational reliability and incident response]
- [Delivery complexity, cost, and team capability]
- [Compatibility with existing systems]

---

## Considered Options

1. **[Option A]** — [Brief description]
2. **[Option B]** — [Brief description]
3. **[Option C / retain existing approach]** — [Brief description]

| Criteria | Option A | Option B | Option C |
|---|---|---|---|
| STRIDE risk reduction |  |  |  |
| Compliance fit |  |  |  |
| Operational effort |  |  |  |
| Delivery complexity |  |  |  |
| Cost / vendor dependency |  |  |  |

---

## Rationale

Explain why the selected option best addresses the decision drivers and material STRIDE threats.

Include:

- Why the primary alternatives were not selected
- Important assumptions and trade-offs
- Compensating controls needed for remaining risks
- Any temporary exceptions or migration constraints

---

## Required Controls

List only the controls essential to this decision.

- [ ] Authentication and authorization approach is defined and enforced server-side.
- [ ] Access follows least privilege; privileged access is logged.
- [ ] Sensitive data is encrypted in transit and at rest where required.
- [ ] Secrets use an approved secrets-management mechanism and are not committed to source control.
- [ ] Security-relevant events are logged without exposing sensitive values.
- [ ] Dependencies, infrastructure, and configuration are subject to appropriate review or automated scanning.

---

## Consequences

### Positive

- [Risk reduced or capability gained]
- [Compliance or audit requirement addressed]
- [Improved security consistency or operational visibility]

### Negative

- [New complexity, cost, latency, training, or vendor dependency]
- [Migration effort or user-experience impact]

### Residual Risks and Follow-ups

| Residual Risk / Action | Owner | Due / Review Date |
|---|---|---|
| [Accepted risk or required follow-up] | [Team / role] | YYYY-MM-DD |

---

## Validation

Describe how compliance with the decision will be checked.

| Requirement | Validation | Owner |
|---|---|---|
| [Authorization is enforced] | [Automated integration tests] | [Team] |
| [Secrets are not committed] | [Secret scanning in CI] | [Team] |
| [Security events are auditable] | [Log and alert verification] | [Team] |

---

## References

- [Threat model](../threat-models/[name].md)
- [Architecture diagram](../diagrams/[name].md)
- [Security policy or standard](https://example.com)
- [Related ADR](0000-related-decision.md)