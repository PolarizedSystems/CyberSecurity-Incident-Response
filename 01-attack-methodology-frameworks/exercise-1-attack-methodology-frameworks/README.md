# Exercise 1 – Attack Methodology Frameworks

[← Back to Lab Overview](../README.md)

---

## Overview

Understanding how adversaries operate is essential to **proactive threat detection and incident response**. In this exercise, I explore two complementary attack methodology frameworks used to analyze cyberattacks and strengthen defensive strategies.

| Framework | Security Application |
|---|---|
| **Lockheed Martin Cyber Kill Chain** | Identifies the stages of an attack and opportunities to detect, disrupt, or prevent an intrusion. |
| **MITRE ATT&CK** | Maps real-world adversary tactics and techniques to support threat analysis, detection engineering, and incident investigation. |

Together, these frameworks help security teams understand **when attackers operate, how they execute attacks, and where defensive controls can be applied**.

## Devices

- **corp-wks-001** – Windows 11 – Microsoft Edge (192.168.30.3)

---

## Part 1 – Lockheed Martin Cyber Kill Chain®

1. Browse to Lockheed Martin's Cyber Kill Chain page:

   ```
   https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html
   ```

   ![Cyber Kill Chain page](../screenshots/exercise-1/e1-01-lm-kill-chain-page.png)

2. Review the overview. The Cyber Kill Chain is part of Lockheed Martin's **Intelligence Driven Defense®** model. It identifies what an adversary must complete to achieve their objective and frames the threat as an **APT**: *Advanced* and *Persistent* (targeted, coordinated, purposeful) with a *Threat* actor who has intent, opportunity and capability.

   ![Kill Chain overview](../screenshots/exercise-1/e1-02-lm-kill-chain-overview.png)

3. Review the seven phases:

   | # | Phase | What the adversary does |
   |---|-------|-------------------------|
   | 1 | **Reconnaissance** | Researches and selects targets: harvesting email addresses, conference details and other public information |
   | 2 | **Weaponization** | Couples an exploit with a backdoor into a deliverable payload |
   | 3 | **Delivery** | Sends the weapon to the victim by email, web or USB |
   | 4 | **Exploitation** | Exploits a vulnerability to execute code on the victim's system |
   | 5 | **Installation** | Installs malware to maintain persistence |
   | 6 | **Command & Control (C2)** | Opens a channel to control the victim remotely |
   | 7 | **Actions on Objectives** | With "hands on keyboard" access, accomplishes the original goal |

   ![Seven phases](../screenshots/exercise-1/e1-03-lm-seven-phases.png)

4. Open the original Lockheed Martin white paper that introduced the model, *Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains*:

   ```
   https://www.lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf
   ```

   ![White paper](../screenshots/exercise-1/e1-04-lm-white-paper.png)

5. Review **Section 3.2, Intrusion Kill Chain**. The model adapts U.S. military targeting doctrine: it is called a *chain* because interrupting any one step interrupts the entire intrusion. The paper notes that email attachments, websites and USB media were the most common delivery vectors observed by Lockheed Martin's incident response team.

   ![Phases 1–4](../screenshots/exercise-1/e1-05-white-paper-phases-1-4.png)

   ![Phases 5–7](../screenshots/exercise-1/e1-06-white-paper-phases-5-7.png)

6. Review **Section 3.3, Courses of Action**. The **Courses of Action Matrix** maps each phase to six defensive actions (**Detect, Deny, Disrupt, Degrade, Deceive, Destroy**) and the controls that deliver them:

   | Phase | Example controls |
   |-------|------------------|
   | Reconnaissance | Web analytics (detect), firewall ACL (deny) |
   | Delivery | Vigilant users (detect), proxy filter (deny), inline AV (disrupt) |
   | Exploitation | HIDS (detect), **patching (deny)**, DEP (disrupt) |
   | Command & Control | NIDS (detect), firewall ACL (deny), DNS redirect (deceive) |
   | Actions on Objectives | Audit logs (detect), honeypot (deceive) |


   ![Courses of Action Matrix](../screenshots/exercise-1/e1-07-courses-of-action-matrix.png)

7. Open Lockheed Martin's analyst guide, *Gaining the Advantage: Applying Cyber Kill Chain® Methodology to Network Defense*:

   ```
   https://www.lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/Gaining_the_Advantage_Cyber_Kill_Chain.pdf
   ```

   ![Gaining the Advantage](../screenshots/exercise-1/e1-08-gaining-the-advantage.png)

8. Review **The Modern Day Attacker**: adversaries are sophisticated, well-resourced and motivated, and their tools and techniques can defeat most common network defenses.

   ![Modern day attacker](../screenshots/exercise-1/e1-09-modern-day-attacker.png)

9. Review the model's core principle: an intruder succeeds **only if they complete all seven steps**. The defender only needs to block one.

   ![Kill Chain model](../screenshots/exercise-1/e1-10-kill-chain-model.png)

10. Review **Actions on Objectives**, which pairs the adversary's goals (credential theft, privilege escalation, lateral movement, data exfiltration, destruction) with the defender's response, including an *incident response playbook with executive engagement and a communications plan*, rapid forensic triage and damage assessment.

    ![Actions on Objectives](../screenshots/exercise-1/e1-11-actions-on-objectives.png)

11. Review the **Conclusion**: the defender has seven opportunities to break the chain, and *"there is no such thing as secure, only defendable."*

    ![Conclusion](../screenshots/exercise-1/e1-12-conclusion.png)

---

## Part 2 – MITRE ATT&CK®

1. Browse to MITRE ATT&CK:

   ```
   https://attack.mitre.org/
   ```

   ATT&CK is a globally accessible knowledge base of adversary tactics and techniques based on real-world observations. The **Enterprise Matrix** organizes techniques under 15 tactics, from Reconnaissance through Impact.

   > **Note:** The knowledge base was on **ATT&CK v20** at the time of this lab.

   ![ATT&CK home](../screenshots/exercise-1/e1-13-attack-home.png)

2. Hover over **CTI** and select **Groups**.

   ![CTI menu](../screenshots/exercise-1/e1-14-cti-groups-menu.png)

3. The Groups page lists the tracked threat groups (182 at the time of this lab), each with an ID, associated group names and a description. Select **Ajax Security Team**.

   ![Groups list](../screenshots/exercise-1/e1-15-groups-list.png)

4. Review the group profile. **Ajax Security Team (G0130)** has been active since at least 2010 and is believed to operate out of Iran. By 2014, it had moved from website defacement to malware-based cyber espionage targeting the U.S. defense industrial base and Iranian users of anti-censorship technologies.


   ![Ajax Security Team](../screenshots/exercise-1/e1-16-ajax-security-team.png)

5. Hover over **Matrices** and select **Enterprise**. The Enterprise Matrix covers Windows, macOS, Linux, cloud, identity providers, network devices, containers and more.

   ![Enterprise Matrix](../screenshots/exercise-1/e1-17-enterprise-matrix.png)

6. Select **View on the ATT&CK® Navigator**.

   ![View on Navigator](../screenshots/exercise-1/e1-18-view-on-navigator.png)

7. The **ATT&CK Navigator** is a web-based tool for annotating and exploring ATT&CK matrices, used to visualize defensive coverage, plan red and blue team activity and track detected techniques. Under **Create New Layer**, select **Enterprise ATT&CK**.

   ![Create layer](../screenshots/exercise-1/e1-19-navigator-create-layer.png)

8. Open the **search** pane and expand **Threat Groups**.

   ![Threat Groups](../screenshots/exercise-1/e1-20-navigator-threat-groups.png)

9. Find **APT19** and click **select**.

   ![Select APT19](../screenshots/exercise-1/e1-21-select-apt19.png)

10. Close the search pane. The matrix now highlights every technique attributed to **APT19 (G0073)**, a China-based threat group, including **Drive-by Compromise**, **Command and Scripting Interpreter**, **Modify Registry** and **Deobfuscate/Decode Files or Information**.

    
    ![APT19 techniques](../screenshots/exercise-1/e1-22-apt19-techniques.png)

---

[← Back to Lab Overview](../README.md) | [Next: Exercise 2 – OWASP Testing Framework →](../exercise-2-owasp-testing-framework/README.md)
