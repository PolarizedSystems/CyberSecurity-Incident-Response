# Pillar 3 — Compliance & Resilience

[← Back to GRC Overview](../README.md)

---

## Overview

The first two pillars set direction and manage uncertainty. This third pillar is where the program proves itself on two fronts: **compliance** — demonstrating, to auditors and regulators, that the organization actually meets the obligations it is bound by — and **resilience** — the ability to keep operating, or recover quickly, when something goes wrong anyway.

The two belong together because they answer the same underlying challenge from opposite directions. Compliance is largely about readiness *on paper and in practice* before anything happens; resilience is about what the organization can actually do *when it does*. A program strong in one and weak in the other is brittle: perfectly documented but unable to recover, or technically resilient but unable to show a regulator it did the right things. This pillar is also where incident response and GRC meet most directly, because the plans tested here are the plans a response depends on.

---

## 1. Compliance, Training & Regulatory Alignment

Compliance begins with the people inside the organization. **Security awareness training** teaches staff to recognize phishing, use strong authentication, and resist social engineering — and because people are the most frequently targeted part of any environment, this training is one of the highest-leverage controls available.

Governance also follows the **employment lifecycle**. Onboarding grants the right access, assigns responsibilities, and delivers initial training; offboarding reliably removes access, recovers assets, and performs final checks. The offboarding half matters most to security — an account that outlives its owner's employment is a standing, unmonitored way in.

Organizations are bound by a web of **privacy regulations**, each with its own requirements for consent, access, erasure, and breach notification:

| Regulation | Scope |
|------------|-------|
| **HIPAA** | Protected health information in the United States |
| **GDPR** | Personal data of individuals in the European Union, with strong consent and erasure rights |
| **CCPA** | Consumer data privacy rights in California |
| **COPPA** | Online collection of data from children |

When these regimes **conflict** — and multinationals routinely face obligations that do not perfectly align — the practical answer is to hold a consistent, high-baseline security policy and to keep meticulous records: training logs, access reviews, and audit trails that demonstrate good faith to any regulator who asks.

Alongside privacy law sit the **industry standards and frameworks** that define best practice — **ISO 27001**, **PCI DSS** (cardholder data), and the Cloud Security Alliance's **STAR** and **Cloud Controls Matrix (CCM)**. Formal **Certification and Accreditation (C&A)** then validates and authorizes a system to operate: the system is assessed against its controls, a decision-maker accepts the residual risk, and the result is an **Authority to Operate (ATO)**, backed by continuous monitoring to keep that authorization honest over time.

> **Compliance is not the same as security — but it is how security is proven.** Meeting a standard does not guarantee an organization is safe, and chasing a checkbox can even distract from real risk. But compliance is the language regulators, customers, and partners trust, and a well-run program treats the two as reinforcing: strong security makes compliance easy to demonstrate, and compliance gives security a documented, defensible shape.

---

## 2. Business Continuity & Disaster Recovery (BCDR)

Resilience is planned in two complementary layers. The **Business Continuity Plan (BCP)** is the broad strategy for keeping the whole organization functioning through a disruption — people, processes, and facilities, not just technology. The **Disaster Recovery Plan (DRP)** is the narrower, IT-focused plan for restoring systems and data. The BCP is the umbrella; the DRP is one critical part of it.

The core concepts BCDR is built to deliver are **high availability**, **continuous operations**, and **disaster recovery** — and the recovery goals are expressed in the same **RTO** and **RPO** metrics produced by the Business Impact Analysis in [Pillar 2](../02-risk-management/README.md).

A central disaster-recovery decision is the **recovery site** — the standby location the organization fails over to. The choice is a direct trade between cost and recovery speed:

| Site Type | Readiness | Recovery Time | Cost |
|-----------|-----------|---------------|------|
| **Cold site** | Empty space with basic utilities only | Weeks to months | Lowest |
| **Warm site** | Pre-configured space with equipment and power | Hours to a few days | Moderate |
| **Hot site** | Fully configured, continuously updated mirror | Minutes — near-instant | Highest |
| **Mobile site** | Portable data center (container or trailer) deployed on location | Days | Varies |

A modern alternative is **Disaster Recovery as a Service (DRaaS)**, which uses public cloud providers to deliver recovery capability with minimal upfront investment, shifting the cost and maintenance of standby infrastructure to a third party.

For guidance, organizations lean on **NIST Special Publication 800-34** (the *Contingency Planning Guide for Federal Information Systems*), the recognized reference for building these plans.

---

## 3. Testing the Plans

A continuity or incident-response plan that has never been tested is a hypothesis, not a capability. Testing is also frequently a **legal or regulatory requirement**, not merely good practice. The methods form a spectrum from least to most disruptive, letting an organization build confidence without gambling production systems on an untested plan:

| Test | What Happens | Intrusiveness |
|------|--------------|---------------|
| **Checklist test** | The plan is reviewed on paper for accuracy and outdated information | Least intrusive |
| **Walkthrough test** | Representatives gather to discuss and talk through the plan, adding group dynamics | Low |
| **Tabletop exercise (TTX)** | A facilitator guides the team through a realistic scenario, discussing responses — without touching live systems | Moderate |
| **Parallel test** | The recovery site is brought online in isolation and selected departments actually operate from it, while production keeps running | High |
| **Full interruption test** | A complete failover of all systems and data to the recovery site, simulating a real disaster | Most intrusive |

Incident response is explicitly a **collaborative, whole-organization effort** — the recognized federal guidance (**NIST SP 800-61**, the *Computer Security Incident Handling Guide*) stresses that it draws in senior management, information assurance, IT, legal, HR, business continuity, and physical security, not just the security team. A companion reference, **NIST SP 800-84**, provides guidance and templates specifically for test, training, and exercise programs.

Every meaningful test ends with an **After Action Report (AAR)** — a structured document capturing the exercise's introduction, scope, objectives, scenario, and, most importantly, its findings and recommendations. The AAR is what turns a test from a box-ticking event into genuine improvement: it names what broke, what to fix, and who owns the fix.

>  **A tabletop exercise is the cheapest incident you will ever have.** Walking a team through a ransomware scenario around a conference table surfaces the same gaps a real attack would — the contact list that is out of date, the backup no one has actually restored, the decision no one is sure they're authorized to make — but it does so with no damage, no downtime, and time to fix them. The organizations that handle real incidents well are almost always the ones that rehearsed.

This closes the loop with the rest of this portfolio: the plans tested here are the same ones a responder executes under pressure, and the lessons captured in an AAR feed directly back into the governance decisions of [Pillar 1](../01-governance/README.md), restarting the cycle.

---

[← Previous: Pillar 2 — Risk Management](../02-risk-management/README.md) | [Back to GRC Overview](../README.md)
