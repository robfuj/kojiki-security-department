# 14 — Security

> Part of the **Kojiki Decision System**. This repo is the
> **Security** line. It references the shared ontology in
> [`00-kojiki-ontology`](https://github.com/robfuj/kojiki-ontology) for the
> canonical schemas, taxonomy, decision-rights, and handoff standards.

## Primary question
> What must be protected, how can it be compromised, and which controls reduce risk most?

## Purpose
Protect assets, detect threats, respond to incidents, and reduce risk.

## Sub-functions
Security Operations, Threat Intelligence, Vulnerability Management, Identity Security, Incident Response, Security Engineering, Governance

## Typical roles
CISO, VP Security, Security Director, Security Engineer, Threat Analyst, Incident Response Lead

## Inputs
Assets, threats, vulnerabilities, telemetry, audit logs, intelligence.

## Outputs
Risk assessments, controls, detections, incident responses, hardening, metrics.

## Learning focus
Attack patterns; vulnerability patterns; control failures; false positives; incident precursors.

## Operating tree
```text
ASSET →
    VALUE →
    THREAT →
    VULNERABILITY →
    RISK →
    CONTROL →
    DETECTION →
    RESPONSE →
    RECOVERY →
    POST-INCIDENT LEARNING
```

## Decision states
```text
INVENTORIED → VALUED → THREAT-MODELED → VULN-ASSESSED → RISK-RATED → CONTROLLED → DETECTING → RESPONDING → RECOVERING → LEARNED
```

## Decision outputs
`Accept · Mitigate · Transfer · Avoid · Escalate · Respond · Recover`

## Critical prompts (what this function thinks about)
> What are we protecting?
> Why is it valuable?
> What threats exist?
> What vulnerabilities exist?
> How likely is exploitation?
> What is the potential impact?
> What controls exist?
> Where are the gaps?
> How would we detect an incident?
> What is the response?
> Who owns the response?
> How do we recover?
> What evidence proves the control works?
> What changed after the incident?
> What should be automated?
> What should be tested?

## Canonical record schema (docx Learning Ledger + Decision Object Fields)
Every decision in this line is recorded as:
- a **Decision Object** (docx S9) — see `schema/decision-object.json`
- a **Learning Ledger** entry (docx S7) — see `schema/learning-ledger.json`

and the agent must run the **Orientation Protocol** first (see `AGENT.md`).

## How this line runs on SYNAPSIS (the cognitive substrate)
Every decision in this line is decomposed through the shared SYNAPSIS transformation
chain ([`00-kojiki-ontology/synapsis`](https://github.com/robfuj/kojiki-ontology/synapsis)):
```
SOURCE → RECORD → EVIDENCE → INTERPRETATION → STRATEGY → INTERACTION → OUTPUT → OUTCOME → LEARNING
```
- **Three steps are dedicated niche bots**: `bots/evidence/` (this line's extraction
  specialist); the shared `synapsis/audit-bot/` (independent audit, org-wide) and
  `synapsis/learning-bot/` (cross-line memory). See `AGENT.md` for the full contract.
- The rest run inline inside this line's agent, each bounded to one authority.
- Meta-rule: *evidence ≠ interpretation ≠ belief ≠ doctrine.* Validate with
  `python3 synapsis/validate.py <record.json>` (in the ontology repo).

## How to use
1. Read `AGENT.md` — the first-run Orientation Protocol.
2. Read `SCHEMA.md` — how this line maps to the universal schema.
3. Read `data/14-security.json` — the machine-readable spec.
4. See `data/example.json` — one fully worked decision (Decision Object + Ledger).
5. Use `decision-graph.mmd` — agent-decodable operating tree + state model.
6. Validate new records: `python3 tools/validate.py data/<name>.json`
