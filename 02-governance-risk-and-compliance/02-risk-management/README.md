# Pillar 2 — Risk Management

[← Back to GRC Overview](../README.md)

---

## Overview

If governance decides *how much* risk an organization will accept, risk management is the machinery that finds the risks, measures them, and acts on them. It is the most quantitative pillar of GRC — the place where security learns to express itself in probabilities and dollars rather than adjectives — and it is also the most continuous, because the risk landscape never stops moving.

The discipline rests on a simple definition: **risk** is the possibility that a threat will exploit a vulnerability and cause harm to an asset. Everything that follows — assessment, prioritization, treatment — is an effort to understand that possibility well enough to make a deliberate decision about it. The goal is never to eliminate risk, which is impossible, but to reduce it to the level governance has declared acceptable, and to be able to prove that is what happened.

---

## 1. The Four Risk Handling Strategies

Once a risk is understood, an organization has exactly four ways to treat it. They are not mutually exclusive — most real risks are handled with a combination — but every treatment decision reduces to some mix of these:

- **Avoid** — step away from the activity entirely. Declining to use an unreliable cloud provider, or retiring an exposed service, removes the risk by removing its source.
- **Accept** — knowingly bear the risk because the benefit outweighs the potential loss. Acceptance is a legitimate strategy *only when it is documented*, so that the decision was made consciously rather than by neglect.
- **Transfer** — shift the responsibility to a third party. Insurance is the classic example; the shared-responsibility model with a cloud service provider is the modern one.
- **Mitigate** — reduce the likelihood or impact with controls, countermeasures, and safeguards. Patch management, firewalls, and access controls are all mitigation.

Whatever strategy is applied, some risk almost always remains afterward. That leftover is **residual risk** — and it is residual risk, not the original risk, that leadership ultimately chooses to accept or reject.


---

## 2. Assessing Risk — Qualitative and Quantitative

Before a risk can be treated it has to be measured, and there are two complementary ways to do that.

**Quantitative analysis** puts numbers on risk, which makes it directly comparable to cost. The core formulas are:

- **Single Loss Expectancy (SLE)** = Asset Value (AV) × Exposure Factor (EF) — the expected loss from one occurrence.
- **Annualized Loss Expectancy (ALE)** = SLE × Annualized Rate of Occurrence (ARO) — the expected loss per year.

The ALE is the number that justifies a control: if a safeguard costs less per year than the ALE it reduces, it pays for itself.

**Qualitative analysis** uses descriptive categories — high / medium / low, or a likelihood-by-impact matrix — when hard numbers are unavailable or impractical. A **semi-quantitative** approach blends the two, attaching rough numeric scores to qualitative bands.

Two kinds of ongoing measurement keep risk visible between formal assessments:

- **Key Performance Indicators (KPIs)** — measurable outcomes that show whether controls are achieving their goals.
- **Key Risk Indicators (KRIs)** — early-warning signals that a risk is trending toward a threshold before it materializes.

It is also worth distinguishing **inherent risk** (the risk before any controls are applied) from **residual risk** (what remains after). When even residual risk exceeds what standard controls can bring down, a formal **risk exception** — approved by senior leadership — documents the deliberate decision to operate anyway.

Everything identified lands in the **risk register**: a living document recording each risk, its likely impact, the controls applied, and the planned response. The register is the single source of truth that turns risk management from a series of disconnected judgments into a program that can be reviewed, tracked, and audited over time.

---

## 3. Business Impact Analysis (BIA)

A **Business Impact Analysis** answers a question risk assessment alone does not: *if this system goes down, how badly and how quickly does it hurt the business?* It connects each system to the critical processes it supports, so that recovery can be prioritized by business consequence rather than by technical convenience.

A BIA produces a set of recovery metrics that drive every continuity decision downstream:

| Metric | Defines |
|--------|---------|
| **Maximum Tolerable Downtime (MTD)** | The absolute longest a function can be unavailable before the damage becomes unacceptable (also called Maximum Allowable Downtime) |
| **Recovery Time Objective (RTO)** | How quickly the system *must* be restored — must fall within the MTD |
| **Recovery Point Objective (RPO)** | How much data, measured in time, the business can afford to lose |
| **Work Recovery Time (WRT)** | The time needed after restoration to return to full operational integrity |
| **Recovery Service Level (RSL)** | The level of service expected during recovery (often a percentage of normal capacity) |

The BIA also identifies the resources each recovery depends on — personnel, equipment, and upstream/downstream dependencies — so that a recovery plan is not written around a system that silently relies on three others.


The BIA feeds the **Business Continuity Plan** — the subject of [Pillar 3](../03-compliance-and-resilience/README.md) — which is the broader strategy for keeping the organization running through a disruption.

---

## 4. Privacy Impact Assessment (PIA)

Where a BIA protects the organization, a **Privacy Impact Assessment** protects the people whose data the organization holds. A PIA is a structured process for identifying and mitigating the privacy risks of handling **Personally Identifiable Information (PII)** across its lifecycle.

A PIA pursues four goals: confirming conformance with legal and regulatory requirements, reinforcing accountability for privacy controls, determining where privacy risk lives, and evaluating whether protections actually mitigate that risk. The risks it surfaces come in two flavors — **quantitative** (measurable costs such as regulatory fines) and **qualitative** (reputational damage and lost customer trust, which are harder to price but often larger).

A PIA is **triggered** whenever privacy exposure changes: a new system or technology that handles PII, a new program with privacy implications, a significant update to an existing system, or a new rule set governing PII. Because retrofitting privacy is expensive and often incomplete, PIAs are meant to be **proactive** — run before a system goes live, not after a complaint — and reviewed at least annually to keep pace with a shifting environment and regulatory landscape.


---

## 5. Threat Modeling

Threat modeling is the structured practice of thinking like an attacker *before* an attack happens — asking who might target a system, why, and how, so defenses can be built against realistic adversaries rather than imagined ones. It begins by understanding the range of **threat actors**, each with different motives and capabilities:

- **Script kiddies** — low-skill attackers using others' tools
- **Hacktivists** — ideologically motivated
- **Organized crime** — financially motivated and well-resourced
- **Nation-states / APTs** — highly capable, patient, and strategically targeted
- **Insider threats** — trusted people misusing their access
- **Supply-chain threats** — adversaries reaching a target through a weaker partner

The process itself is systematic: identify the assets worth protecting, map the paths an attacker could take to reach them, prioritize those paths by risk, apply controls to the highest-priority paths, and document and review the model as the system evolves.

The structured frameworks that support this work — the **Cyber Kill Chain** and **MITRE ATT&CK** — are examined hands-on in [Attack Methodology Frameworks](../../01-attack-methodology-frameworks/README.md) of this portfolio. In a GRC context, the point is that threat modeling turns those frameworks into a *governance input*: a repeatable way to decide where defensive effort and budget should go.


---

## 6. Vendor & Supply-Chain Risk

Few organizations run entirely on their own systems, and every third party is an extension of the organization's own attack surface. **Vendor assessment** is the discipline of looking past price to judge whether a provider's capabilities, stability, and security actually align with the business's needs.

Key considerations include:

- **Vendor viability** — is the provider financially stable enough to still exist in three years? For high-value systems, **source code escrow** provides a contingency if the vendor fails.
- **Lock-in and lock-out** — proprietary formats or poor interoperability can trap an organization with a provider it has outgrown, or make leaving prohibitively costly.
- **Support and SLAs** — what support tiers exist, and what uptime, response times, and penalties are actually guaranteed in writing.
- **Data and geography** — where data will reside and move, and the legal and compliance implications of that location.
- **Supply-chain depth** — a vendor's own subcontractors, hosting providers, and payment processors are *also* part of the risk. **Subprocessor risk** is the exposure that flows from a vendor's partners, and it is a common vector for supply-chain attacks.

Rather than take a vendor's claims on faith, organizations rely on **independent third-party assessments** to validate security and operational maturity:

| Assessment | What It Validates |
|------------|-------------------|
| **SOC 2 report** | Controls around security, availability, and confidentiality at a service provider |
| **ISO 27001 certification** | A formally audited information-security management system |
| **CSA STAR** | Cloud-specific security posture |
| **CMMC** | Cybersecurity maturity for government-contracting supply chains |

---

## 7. Assessment Documentation & Legal Controls

Security assessments — penetration tests and vulnerability assessments especially — are legally sensitive activities, because the tester is doing things that would be crimes without permission. Two documents govern them:

- **Statement of Work (SOW)** — defines what the assessment will cover and deliver.
- **Rules of Engagement (ROE)** — defines *how* it will be conducted: the scope of systems, whether the environment is unknown, known, or partially known to the tester, any after-hours constraints, and which systems are strictly off-limits.

Above both sits **formal written authorization** — often called the "get-out-of-jail-free card" — the explicit, signed permission that distinguishes an authorized assessment from a criminal intrusion and protects the tester from legal consequence. Supporting controls cover the physical and remote realities of an engagement: building access and escorts, badge control, NDAs, visitor logs, sandboxes, and VPNs, along with post-engagement clauses defining retest and remediation-validation windows.

When an assessment or an incident turns into evidence, a further set of controls preserves its integrity:

- **Chain of custody** — a formal, unbroken record of who accessed evidence, when, and what they did with it.
- **Forensic imaging** — using tools such as `dd` to make a bit-for-bit replica so the original is never altered.
- **Hashing** — computing a value such as **SHA-256** before and after to prove the evidence was not changed.
- **Fuzzy hashing (ssdeep)** — comparing *similar-but-not-identical* files, which is how obfuscated malware variants are matched to known samples.

---

[← Previous: Pillar 1 — Governance](../01-governance/README.md) | [Back to GRC Overview](../README.md) | [Next: Pillar 3 — Compliance & Resilience →](../03-compliance-and-resilience/README.md)
