# Managing Cybersecurity Incident Response

[← Back to Portfolio Overview](../README.md)

---

## Overview

Responding to an incident well is not a single skill exercised in a crisis — it is the visible moment of a discipline that runs continuously in the background. The organizations that handle incidents calmly are the ones that built security into their systems before anything broke, that operate a well-governed program day to day, that know exactly what to do when an alarm sounds, and that treat every incident as a lesson rather than an embarrassment.

This section covers that full discipline: **managing** incident response, not just performing it. Where [Attack Methodology Frameworks](../01-attack-methodology-frameworks/README.md) looks at how adversaries operate and [Governance, Risk & Compliance](../02-governance-risk-and-compliance/README.md) establishes the program's scaffolding, this section is the operational core — the proactive engineering, the program mechanics, the response lifecycle, and the learning loop that together make up a mature incident-response capability.

It is organized into four modules that follow the natural arc of the work, from *before* an incident to *after* it:

| Module | Focus | What It Covers |
|--------|-------|----------------|
| **[1 · Building Security In](01-building-security-in/README.md)** | Prevention by design | Secure SDLC · threat modeling (STRIDE, PASTA) · the control families |
| **[2 · Security Program Operations](02-security-program-operations/README.md)** | Running the program | System maintenance & patching · risk principles · policies, governance & SLOs · prioritization & escalation · attack-surface management · secure coding |
| **[3 · The Incident Response Lifecycle](03-incident-response-lifecycle/README.md)** | Active response | Attack methodology frameworks · detection & analysis (indicators of compromise) · containment, eradication & recovery |
| **[4 · Preparation & Post-Incident](04-preparation-and-post-incident/README.md)** | Readiness & learning | The preparation phase · forensic and root-cause analysis · lessons learned |

### Learning Outcomes

This section covers the following modules:

- Module 1 – Building Security In
- Module 2 – Security Program Operations
- Module 3 – The Incident Response Lifecycle
- Module 4 – Preparation & Post-Incident

After completing this section, you should be able to:

- Embed security into the software development lifecycle and review it at each phase
- Threat-model with structured frameworks (STRIDE, PASTA) early and often
- Select and combine control families — preventative, detective, corrective and compensating
- Operate disciplined patching, configuration-management and maintenance-window processes
- Prioritize and escalate incidents using the NIST SP 800-61 impact model
- Recognize network, host and application indicators of compromise
- Execute containment, eradication and recovery while preserving evidence
- Run forensic and root-cause analysis and produce actionable lessons-learned reports

---

## Downloadable Reference

- 📄 [**Managing Cybersecurity Incident Response** (branded PDF)](Polarized-Systems-Managing-Cybersecurity-Incident-Response.pdf) — the full four-module reference as a single branded document, in the same letterhead format as the Polarized Systems SOPs and the [Governance, Risk & Compliance](../02-governance-risk-and-compliance/Polarized-Systems-Governance-Risk-and-Compliance-Reference.pdf) reference.

---

## The Incident Response Lifecycle at a Glance

The federal reference for incident handling (**NIST SP 800-61**) frames the response as a repeating four-phase cycle. This section maps to it directly:

```
   ┌──────────────┐     ┌────────────────────┐     ┌─────────────────────────────┐     ┌──────────────────┐
   │ Preparation  │ --> │ Detection &        │ --> │ Containment, Eradication    │ --> │ Post-Incident    │
   │              │     │ Analysis           │     │ & Recovery                  │     │ Activity         │
   └──────────────┘     └────────────────────┘     └─────────────────────────────┘     └──────────────────┘
          ▲                                                                                      │
          └──────────────────────────── lessons learned feed back ───────────────────────────────┘
```

Preparation and post-incident activity are covered in [Module 4](04-preparation-and-post-incident/README.md); the active middle phases in [Module 3](03-incident-response-lifecycle/README.md). The loop is deliberate — the output of one incident's post-mortem becomes the input to the next incident's preparation.

---

## Related Work

-  [**Attack Methodology Frameworks**](../01-attack-methodology-frameworks/README.md) — the adversary-facing frameworks applied hands-on
-  [**Governance, Risk & Compliance**](../02-governance-risk-and-compliance/README.md) — the governance, risk, and compliance scaffolding this program runs on
-  [**Incident Response Process** (SOP)](../process/README.md) — the standard operating procedure that turns this discipline into a repeatable workflow

---

[← Back to Portfolio Overview](../README.md) | [Begin with Module 1 — Building Security In →](01-building-security-in/README.md)
