# Module 2 — Security Program Operations

[← Back to Section Overview](../README.md)

---

## Overview

Between the big moments — the design review and the live incident — sits the daily work that keeps a security program healthy. It is unglamorous and continuous: keeping systems patched, deciding which risks to treat and how, writing the policies everyone works to, triaging what matters when something goes wrong, watching the organization's exposed edges, and holding developers to secure standards. This module covers those operational mechanics, the machinery that a well-run program runs on every day.

---

## 1. System Maintenance Procedures

Systems drift out of a secure state the moment they are deployed — new vulnerabilities are disclosed, configurations change, and software ages. Disciplined maintenance is what holds that drift in check.

**Patching** is the most visible of these procedures, and doing it safely is a process rather than a single action:

1. **Testing** — validate the patch in a non-production environment first
2. **Implementation** — deploy it to production in a controlled way
3. **Rollback** — keep a tested path to reverse the change if it breaks something
4. **Validation** — confirm the patch applied correctly and the issue is resolved

Surrounding that core loop are three supporting practices: **configuration management** (maintaining a known, documented state for every system so unauthorized change stands out), **maintenance windows** (scheduled periods when disruptive work can happen with the least business impact), and **exceptions** (a formal, documented process for the systems that genuinely cannot be patched on the standard schedule).

> **A rollback plan is not optional — it is the patch.** The riskiest patch is the one deployed with no way back. Production systems fail in ways a test environment never reveals, and when a patch takes a critical service down, the question is measured in minutes: *can we reverse this?* Treating rollback as a required step, not an afterthought, is the difference between a brief blip and a self-inflicted outage.

---

## 2. Risk Management Principles

Every security decision is ultimately a risk decision, and an organization has four ways to treat any given risk:

- **Avoid** — identify the risk and change course to steer clear of it entirely
- **Transfer** — shift responsibility to another party, often a specialist outside the organization (insurance being the classic example)
- **Mitigate** — apply controls to stop the risk before it can make an impact
- **Accept** — knowingly bear the risk when it is low enough, or the assets minor enough, that treatment is not warranted — while still planning for incident response in case it materializes

> **Even an accepted risk needs a response plan.** Accepting a risk is not the same as ignoring it. The decision to accept means the organization has judged the cost of treatment higher than the expected loss — but "unlikely" is not "impossible," so a sound acceptance still carries a plan for what happens if the risk comes true anyway.
>
> These four strategies are examined in greater depth, with the quantitative models (SLE, ALE) that justify them, in [Governance, Risk & Compliance — Risk Management](../../02-governance-risk-and-compliance/02-risk-management/README.md).

---

## 3. Policies, Governance & Service-Level Objectives

Three related concepts give a program its structure and its accountability:

- **Policies** are the organization's rules of conduct — the documented expectations that define acceptable behavior and required practice.
- **Governance** is the authority that sets and enforces direction. It has an internal face (corporate governance — the leadership structures that steer the organization) and an external face (regulators and governments imposing requirements from outside).
- **Service-Level Objectives (SLOs)** are specific, measurable targets for how a service should perform. They are the building blocks of a **Service-Level Agreement (SLA)** — the SLOs define the goals, and the SLA formalizes them into a contract with consequences.

> **SLOs turn "good service" into a number you can manage.** An objective like "99.9% availability" or "critical tickets acknowledged within 15 minutes" is something a team can actually measure, report, and be held to. Without SLOs, service quality is a matter of opinion; with them, it becomes a managed metric — and it is those metrics that an SLA then promises to a customer.
>
> The contract types that build on these objectives — SLAs, MSAs, and more — are detailed in [Governance, Risk & Compliance — Governance](../../02-governance-risk-and-compliance/01-governance/README.md).

---

## 4. Prioritization & Escalation

When several things are wrong at once, the ability to decide *what matters most* is what keeps a response effective. The federal incident-handling guidance (**NIST SP 800-61**) offers a model for prioritizing incidents along three dimensions:

| Dimension | Scale |
|-----------|-------|
| **Functional impact** — effect on business operations | None · Low · Medium · High |
| **Information impact** — effect on data confidentiality and integrity | None · Privacy breach · Proprietary breach · Integrity loss |
| **Recoverability** — effort required to recover | Regular · Supplemented · Extended · Not recoverable |

Scoring an incident across all three gives an objective basis for triage, rather than responding to whichever alarm is loudest.

**Escalation** is the companion discipline: knowing when and how to hand an incident up the chain. A sound incident-response policy spells out the **escalation points** in the process, the **procedures** for escalating, up-to-date **on-call information**, and — critically — the **acceptable and expected wait times** at each step, so nothing stalls while everyone assumes someone else has it.

> **"Not recoverable" changes everything about a response.** The recoverability dimension is easy to overlook, but it reshapes the whole plan. An incident that is recoverable with normal effort is a technical task; one that is *not recoverable* — where data or systems cannot be restored — becomes a business-continuity and communications event. Scoring recoverability early tells responders which kind of incident they are actually in.

---

## 5. Attack Surface Management

An organization's **attack surface** is the sum of every point where it could be attacked — and managing it means continuously discovering, testing, and shrinking that exposure. The practice draws on several complementary activities:

- **Edge discovery** — finding the internet-facing assets that form the outer boundary
- **Passive discovery** — mapping exposure without actively probing, using existing data and observation
- **Security controls testing** — verifying that the defenses in place actually work
- **Penetration testing and adversary emulation** — actively attempting to breach the environment the way a real attacker would
- **Bug bounty** — paying external researchers for vulnerabilities they find and report
- **Attack surface reduction** — the ultimate goal: removing, consolidating, or hardening exposed assets so there is less to attack in the first place

> **You cannot defend what you do not know you have.** The most dangerous asset is the forgotten one — a test server left internet-facing, a shadow-IT application, a service no one remembers deploying. Attack-surface management exists because environments grow faster than inventories, and the first job of defense is simply knowing the full extent of what has to be defended.

---

## 6. Secure Coding Best Practices

Much of an organization's attack surface is its own software, and secure coding is how that surface is kept small at the source. A core set of practices addresses the most common classes of vulnerability:

- **Input validation** — never trust input; check it before acting on it, which closes off most injection attacks
- **Output encoding** — encode data before rendering it, defeating cross-site scripting and similar flaws
- **Session management** — handle authentication tokens and sessions securely so they cannot be hijacked
- **Authentication** — verify identity robustly before granting access
- **Data protection** — encrypt and guard sensitive data in storage and transit
- **Parameterized queries** — separate code from data in database calls, which is the definitive defense against SQL injection

> **Most breaches exploit a handful of avoidable coding flaws.** The vulnerabilities that attackers rely on most — injection, cross-site scripting, broken authentication — are the ones this short list prevents. Secure coding is not esoteric; it is a small set of disciplined habits that, applied consistently, eliminate the majority of the web-application weaknesses attackers count on.

---

> ### Stakeholder Takeaway
>
> "A security program lives or dies on its daily operations. We patch in a way that we can safely reverse. We make deliberate, documented choices about every risk — treat it, transfer it, or accept it with eyes open. We set measurable service targets so performance is a fact, not an opinion. When several things break at once, we triage by real business impact instead of noise. We keep a live map of everything we expose to the world, and we hold our own code to standards that shut down the most common attacks. None of this is dramatic — it's the steady discipline that means the dramatic days are rare."

---

[← Previous: Module 1 — Building Security In](../01-building-security-in/README.md) | [Back to Section Overview](../README.md) | [Next: Module 3 — The Incident Response Lifecycle →](../03-incident-response-lifecycle/README.md)
