# Architecture Decision Records Starter Kit

A practical, lightweight starter kit for documenting, reviewing, and maintaining **Architecture Decision Records (ADRs)**.

---

## Why ADRs?

Teams make consequential technical decisions every day:

- Should we build a modular monolith or microservices?
- Do we use REST, GraphQL, or asynchronous messaging?
- How will we isolate tenants?
- Which database model best fits the workload?
- What security, deployment, and observability standards are mandatory?

Without a concise written record, the rationale is often lost in meetings, tickets, chat threads, or the memory of a few individuals.

An ADR records:

1. **The context** — What problem or constraint led to the decision?
2. **The decision** — What did we choose?
3. **The consequences** — What becomes easier, harder, more expensive, or riskier?
4. **The alternatives** — What was considered and why was it not selected?

ADRs should be short enough to read, useful enough to guide implementation, and durable enough to explain a system months or years later.

---

## What’s Included

- A ready-to-use ADR directory structure
- General-purpose and specialized ADR templates
- Example ADRs covering common architecture decisions
- Decision status and lifecycle conventions
- Naming and numbering guidance
- Optional scripts for creating and validating ADRs
- GitHub Actions examples for enforcing ADR practices in pull requests
- Guidance for using ADRs in agile delivery, architecture reviews, and consulting engagements

---

## Quick Start

### 1. Use this repository as a template

Select **Use this template** on GitHub, or copy the `docs/adr` directory into your own repository.

### 2. Create your first ADR

```bash
./scripts/new-adr.sh "Choose API style for partner integrations"
