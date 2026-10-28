# Module 1 — Building Security In

[← Back to Section Overview](../README.md)

---

## Overview

The cheapest incident to handle is the one that never happens, and the second cheapest is the one a system was designed to withstand. Both come from the same place: security built *into* how software and systems are created, rather than bolted on after they ship. This module covers the proactive foundations — how security analysts engage with the development lifecycle, how threats are modeled before they are exploited, and the full vocabulary of controls used to reduce risk by design.

---

## 1. Securing the Software Development Lifecycle (SDLC)

Software does not appear fully formed; it moves through a lifecycle, and a security analyst is expected to provide guidance at every stage of it. While organizations use many variations, the lifecycle generally runs from the recognition of an unmet need to the eventual retirement of the software:

1. **Identify** the organizational need
2. **Design** a solution
3. **Build** the solution
4. **Test** the solution
5. **Deploy** it to production
6. **Maintain** it in operation
7. **Retire** it at end of life

Two broad philosophies govern how those phases are sequenced. The traditional **Waterfall** method moves through them in a strict, linear order — each phase completed before the next begins. More modern **Agile** approaches (of which **Scrum** is the best-known example) work in short, iterative cycles, revisiting design, build, and test repeatedly as requirements evolve.

> **Security has a job in every phase, not just testing.** It is tempting to treat security as a gate near the end — a penetration test before launch. But the highest-leverage security work happens early: threat modeling during design, secure-coding standards during the build, and dependency review before deployment. A flaw caught in design is a conversation; the same flaw caught in production is an incident. Analysts who engage across the whole SDLC prevent far more than those who only inspect the finished product.

---

## 2. Threat Modeling

Threat modeling is a structured way of testing an organization's security against the attacks it is likely to face — on paper, before an adversary does it for real. The guiding principle is to perform it **early and often**: woven into design and revisited as systems change, rather than run once and shelved. A valuable side effect is that the security team comes away understanding the system's architecture far better than before, because modeling a threat forces a careful walk through how the system actually works.

A threat model examines a consistent set of factors for each potential attack:

- **Adversary capability** — how skilled and resourced the likely attacker is
- **Total attack surface** — every point where the system could be reached
- **Attack vector** — the specific path an attacker would take
- **Impact** — the damage a successful attack would cause
- **Likelihood** — how probable that attack is

Several formal frameworks give this process repeatable structure. Two of the most widely used are:

| Framework | Emphasis |
|-----------|----------|
| **STRIDE** | Classifies threats by type — Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, and Elevation of privilege |
| **PASTA** | The Process for Attack Simulation and Threat Analysis — a risk-centric, attacker-simulation approach that ties technical threats to business impact |

> **Threat modeling is where defense gets specific.** Instead of "we should be secure," a threat model produces "an attacker of *this* capability would most likely reach *this* asset through *this* vector, so that is where our effort goes." It converts an open-ended worry into a prioritized, defensible plan — which is exactly what makes it worth doing early, when the design can still change cheaply.
>
> The adversary-facing frameworks that complement this design-time practice — the Cyber Kill Chain and MITRE ATT&CK — are applied hands-on in [Attack Methodology Frameworks](../../01-attack-methodology-frameworks/README.md), and threat actors are profiled in [Governance, Risk & Compliance](../../02-governance-risk-and-compliance/02-risk-management/README.md).

---

## 3. The Control Families

When technology alone cannot fully solve a security problem, **compensating controls** fill the gap — alternative safeguards that achieve the security objective by another means. They are one member of a broader family of control types, and a mature program deliberately combines several of them:

| Control Type | Purpose |
|--------------|---------|
| **Preventative** | Limits the possibility of an undesirable outcome before it occurs |
| **Detective** | Identifies risks and vulnerabilities, or spots an event in progress |
| **Corrective** | Fixes an undesirable outcome after it happens to reduce further risk |
| **Responsive** | Reacts to a security event or flaw as it unfolds |
| **Compensating** | Provides an alternative safeguard when a primary control is not feasible |
| **Managerial** | Policies and procedures that steer the program toward its security goals |
| **Operational** | Controls carried out by people rather than systems |
| **Technical** | Logic-based controls implemented in technology to reduce vulnerabilities |

These categories overlap by design — a single safeguard can be both technical and preventative, for instance — and the point is not to memorize labels but to think in layers. A well-designed environment does not rely on one control to do everything; it stacks preventative, detective, and corrective measures so that when one fails, another is already watching.

> **Compensating controls are how real environments cope with imperfect ones.** No organization can apply the ideal control everywhere — a legacy system may not support modern encryption, or a business process may forbid a hard lockout. A compensating control (extra monitoring, network isolation, stricter access review) achieves the same risk reduction by a different route. Recognizing when one is needed — and defending it to an auditor — is a mark of practical security maturity.

---

> ### Stakeholder Takeaway
>
> "The work that prevents incidents happens long before any incident. We put security into how our software is built, not just how it's tested — so flaws get caught when they're cheap to fix. We model the threats to a system while we're still designing it, so we're defending against realistic attacks instead of guessing. And we layer our controls, so no single failure leaves us exposed. None of this shows up as a headline, which is exactly the point: it's the quiet engineering that keeps the loud incidents from happening."

---

[← Back to Section Overview](../README.md) | [Next: Module 2 — Security Program Operations →](../02-security-program-operations/README.md)
