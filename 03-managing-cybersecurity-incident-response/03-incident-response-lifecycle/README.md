# Module 3 — The Incident Response Lifecycle

[← Back to Section Overview](../README.md)

---

## Overview

This is the module where something has gotten through. However strong the proactive work, incidents happen — and when they do, the response follows a recognized lifecycle. This module covers the active heart of that lifecycle: understanding the attacker's methodology, **detecting and analyzing** what is happening, and then **containing, eradicating, and recovering** from it. (The bookends — preparation before and learning after — are covered in [Module 4](../04-preparation-and-post-incident/README.md).)

---

## 1. Attack Methodology Frameworks

Effective detection starts with understanding how attacks are structured. Several frameworks give responders a shared model of adversary behavior, letting them recognize where in an attack they are looking and what is likely to come next:

- **Cyber Kill Chain** — Lockheed Martin's seven-stage model of an attack's progression
- **MITRE ATT&CK** — a detailed catalog of real-world adversary tactics and techniques
- **Open Source Security Testing Methodology Manual (OSSTMM)** — a peer-reviewed methodology for repeatable, measurable security testing
- **OWASP Testing Guide** — the web-application testing standard for finding and validating vulnerabilities

> **A framework turns scattered alerts into a story.** Individually, a phishing email, an odd login, and a spike in outbound traffic are three disconnected events. Mapped onto the Kill Chain or ATT&CK, they become recognizable stages of one intrusion — which tells a responder not just what has happened, but what the attacker is likely to do next. That predictive value is why these models are the backbone of analysis.
>
> These frameworks are applied hands-on — profiling a threat group in ATT&CK Navigator and fingerprinting a target — in [Attack Methodology Frameworks](../../01-attack-methodology-frameworks/README.md), the first section of this portfolio.

---

## 2. Detection & Analysis

The detection-and-analysis phase is where an organization determines that something is actually wrong and works out what it is. The core activity is recognizing **indicators of compromise (IoCs)** — the observable signs that a system has been breached. They fall into three families by where they show up.

### Network-related indicators

| Indicator | What It Suggests |
|-----------|------------------|
| **Bandwidth** anomalies | Unusual data volumes, often signaling exfiltration |
| **Beaconing** | Regular call-outs from a host to a command-and-control server |
| **Irregular peer-to-peer** communication | Hosts talking to each other in ways they normally would not |
| **Rogue devices** | Unknown hardware appearing on the network |
| **Common protocols over nonstandard ports** | An attempt to disguise malicious traffic as something routine |

### Host-related indicators

Signs on an individual machine include unexpected **capacity consumption**, **unauthorized software** or **malicious processes**, suspicious **memory contents**, **unauthorized changes** to the **file system** or **registry**, **unauthorized privileges** or **scheduled tasks**, evidence of **data exfiltration**, and gaps revealed by application **whitelisting**.

### Application-related indicators

Within applications, watch for **anomalous activity**, **new accounts** appearing unexpectedly, **unexpected output** or **outbound communication**, **service interruptions**, **memory overflows**, and telltale entries in **application logs**.

### Evidence acquisition

Analysis frequently produces evidence that may later matter legally, so how it is handled is as important as what it shows. The discipline rests on four practices:

- **Chain of custody** — an unbroken record of who handled evidence, when, and how
- **Validating data integrity** — proving the evidence has not changed, typically with cryptographic hashing
- **Preservation** — protecting evidence from alteration or loss
- **Legal hold** — formally suspending any routine deletion that would destroy relevant data

All of it comes together in **data and log analysis** — correlating these indicators and sources into a coherent picture of what happened.

> **Handle every investigation as if it will end up in court.** At the moment an analyst first examines a compromised machine, no one yet knows whether the incident will lead to prosecution, an insurance claim, or a regulator's inquiry. Treating evidence properly from the very first step — chain of custody, integrity validation, preservation — costs little and keeps every option open. Skipping it can render otherwise-solid evidence worthless, and the omission cannot be undone later.

---

## 3. Containment, Eradication & Recovery

Once an incident is understood, the response moves to stopping it and restoring normal operation. This phase has three distinct stages, performed in order:

1. **Containment** — reduce or eliminate the spread of the incident, isolating affected systems to keep it from reaching more of the environment. Critically, containment is done in a way that **preserves evidence**, so stopping the bleeding does not destroy the record of what happened.
2. **Eradication** — return all affected systems to a known-good state, removing the attacker's foothold entirely. In practice this often means rebuilding systems from clean sources rather than trying to clean them in place.
3. **Recovery** — identify the attack vectors that were used and implement countermeasures, then restore systems to full operation with confidence that the same door will not simply be reopened.

> **Speed and evidence are in tension — plan for both.** The instinct under pressure is to wipe and rebuild as fast as possible. But pulling the plug too hastily can erase the forensic trail needed to understand the breach and prevent the next one. Good containment deliberately balances the two: isolate quickly to stop the spread, but capture the evidence — memory, logs, disk images — before eradicating. The order matters, and rushing it is a decision with consequences.
>
> **Eradication without root cause is a reset, not a fix.** Rebuilding a compromised server feels like resolution, but if the vector that let the attacker in is still open, the clean system will be compromised again. Recovery explicitly includes identifying the attack vector and closing it — which is why this phase hands off directly to the root-cause analysis in [Module 4](../04-preparation-and-post-incident/README.md).

---

> ### Stakeholder Takeaway
>
> "When an incident is live, a calm, practiced sequence replaces panic. We recognize what we're seeing by mapping it to how attacks actually unfold. We read the signs across our network, our machines, and our applications to understand the full scope — and we handle what we find as evidence from the very first minute, because we may need it later. Then we stop the spread, remove the attacker completely, and bring systems back only after we've closed the door they came through. The goal isn't just to make the alert stop; it's to make sure the same attack can't simply happen again tomorrow."

---

[← Previous: Module 2 — Security Program Operations](../02-security-program-operations/README.md) | [Back to Section Overview](../README.md) | [Next: Module 4 — Preparation & Post-Incident →](../04-preparation-and-post-incident/README.md)
