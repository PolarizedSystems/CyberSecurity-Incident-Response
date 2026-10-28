# Module 2 — Communicating Incident Response

[← Back to Section Overview](../README.md)

---

## Overview

When an incident happens, the technical response is only half the work; the other half is communicating it — to the people who must make decisions, meet legal obligations, protect the organization's reputation, and learn from what happened. This module covers the reactive stream of communication: who needs to hear about an incident and what they need, how an incident report is structured, how root-cause findings and lessons learned are conveyed, and the metrics that measure how well the response performed.

---

## 1. Incident Response Reports & Their Stakeholders

An incident draws in a wide range of stakeholders, each needing a different cut of the same event. Communicating to the wrong level — burying an executive in packet captures, or giving the legal team only a technical summary — fails all of them.

| Stakeholder | What They Need |
|-------------|----------------|
| **IT security team** | The technical aspects — who is authoritative to declare the incident, who handles the response (names, positions, contact info), and the escalation process |
| **Executives** (CTO, CISO) | A higher-level view that supports key decisions — summarized key events, not the minutiae |
| **Legal** (local to federal) | Confirmation that the response strategy complies with laws, regulations, and contractual obligations (MOU, SLA) — especially for customer-data or payment-card breaches |
| **Public relations** | What to tell support services, customer service, and the public media — particularly where SLAs were missed, data was breached, or outages occurred |
| **Regulatory authorities** (local to federal) | Required notifications — for example, a potential HIPAA or GDPR violation |
| **Law enforcement** (local to federal) | Involvement where civil or criminal liabilities arise |

The report itself follows a consistent structure, built so any of those audiences can find what they need:

- **Executive summary** — a high-level summarization of the key findings
- **The 5 W's** — **Who** (threat actor), **What** (type of occurrence, vector/method), **When** (time of occurrence), **Where** (the system, process, application, or physical location affected), and **Why** (the vulnerability or vulnerabilities exploited)
- **Recommendations** — strategic advice on controls and countermeasures to deploy
- **Timeline** — a complete record of the event from detection to remediation
- **Impact** — the effect of the incident on the organization
- **Scope** — the range of that effect
- **Evidence** — preservation of all documentation for later examination (chain of custody, timestamps, and the like)


## 2. Communicating Root-Cause Analysis & Lessons Learned

Once the incident is closed, the organization owes itself an honest account of why it happened and what to change. Both are communication products as much as analytical ones.

### Root-Cause Analysis (RCA)

A root-cause analysis is an investigation to discover the underlying cause or causes of a security incident — identifying the vulnerabilities and contributing factors, and presenting a clear, concise breakdown of the underlying circumstances, including a **timeline of events**. A thorough RCA also recognizes that the circumstances it uncovers may affect other systems — a missing control on the compromised system is often missing elsewhere too — and it ends by recommending strategic controls and countermeasures to reduce future impact and avoid recurrence.

An **RCA report** may itself be required for compliance purposes, and typically records:

- The **date and time** the incident occurred
- **What event** happened
- **How** the incident was discovered
- **Who** reported it

### Lessons Learned

The lessons-learned process brings together the Incident Response Team and everyone involved, in formal session(s), to ask three plain questions: **what went right, what went wrong, and where can we improve?** It identifies the roadblocks that slowed remediation and recovery, surfaces changes needed in the **incident response plan (IRP)**, and documents any **new indicators of compromise (IoCs)** discovered during the incident — feeding them straight back into detection.


> The performance of this post-incident work is covered from the response side in [Managing Cybersecurity Incident Response — Preparation & Post-Incident](../../03-managing-cybersecurity-incident-response/04-preparation-and-post-incident/README.md).

---

## 3. Incident Response Metrics & KPIs

Finally, the response itself is measured — and these metrics, communicated over time, show whether the program is improving. Most are "mean-time" measures that track how quickly the organization moves through each phase of a response:

| Metric | Measures |
|--------|----------|
| **Mean Time to Detect (MTTD)** | Average time from when an incident starts to when the organization becomes aware of it |
| **Mean Time to Identify** | Average time to identify the nature of the incident once detected |
| **Mean Time to Respond** | Average time to mount an initial response to a potential incident |
| **Mean Time to Contain** | Average time to quarantine a potential incident |
| **Mean Time to Remediate** | Average time to close the vulnerability that triggered the response |
| **Mean Time to Recovery** | Average time to restore operations to their pre-incident state |

One further metric stands apart: **alert volume** — the number of notifications indicating a potential incident. A high volume leads to **alert fatigue**, where the sheer quantity of notifications makes it hard to separate the critical few from the low-priority many.

>  **Alert fatigue is a metric that measures your other metrics' blind spot.** Fast detection times look impressive until you realize the team is drowning — thousands of alerts a day means the one that matters is easily missed, and a low mean-time-to-detect on paper can hide a real-world failure to notice the alert that counts. Tracking alert volume alongside the mean-time metrics keeps the picture honest: speed means little if the signal is buried in noise.


---

[← Previous: Module 1 — Vulnerability & Compliance Findings](../01-communicating-vulnerability-and-compliance-findings/README.md) | [Back to Section Overview](../README.md)
