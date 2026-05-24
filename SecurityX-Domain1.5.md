# SecurityX (CAS-005) Domain 1.4: Threat Modeling Activities

**Given a scenario, perform threat-modeling activities.**

## 📋 Table of Contents

- [Actor Characteristics](#actor-characteristics)
- [Attack Patterns](#attack-patterns)
- [Frameworks](#frameworks)
- [Attack Surface Determination](#attack-surface-determination)
- [Methods](#methods)
- [Modeling Applicability of Threats to the Organization/Environment](#modeling-applicability-of-threats-to-the-organizationenvironment)
- [Threat Modeling in DoD Environments](#threat-modeling-in-dod-environments)

---

## Actor Characteristics

**Threat actors** are the individuals, groups, or organizations that pose risks to systems and data. Understanding their characteristics helps security architects predict likely attack methods and prioritize defenses.

### Motivation
**Motivation** describes why an actor targets an organization.  
- **Financial:** Seeking monetary gain through ransomware, fraud, or data theft.  
- **Geopolitical:** Nation-state actors advancing political or military objectives.  
- **Activism:** Hacktivists aiming to expose issues or disrupt operations for a cause.  
- **Notoriety:** Individuals seeking fame or recognition in hacker communities.  
- **Espionage:** Stealing sensitive information for competitive or intelligence advantages.

**Corporate Example:** A retail company faces financially motivated ransomware groups targeting payment systems.  
**DoD Example:** Adversaries with geopolitical motivations conduct espionage against defense contractors to obtain classified or CUI data.

### Resources
**Resources** refer to the time, money, and infrastructure an actor can dedicate to an attack.  
- **Time:** Sophisticated actors may spend months in reconnaissance.  
- **Money:** Well-funded groups can purchase zero-days or custom tools.

**Corporate Example:** A small business may only face low-resource script kiddies, while large enterprises attract well-funded organized crime.  
**DoD Example:** Nation-state actors with significant budgets and time can develop advanced persistent threats (APTs) targeting military supply chains.

### Capabilities
**Capabilities** define what technical skills and access an actor possesses.  
- **Supply Chain Access:** Ability to compromise vendors or third-party components.  
- **Vulnerability Creation:** Discovering or developing new exploits.  
- **Knowledge:** Deep understanding of target systems and networks.  
- **Exploit Creation:** Building custom malware or tools.

**Corporate Example:** A capable actor might exploit a known vulnerability in a widely used SaaS platform.  
**DoD Example:** Advanced actors with supply chain access insert backdoors into hardware destined for tactical networks.

---

## Attack Patterns

**Attack patterns** are reusable descriptions of common methods adversaries use to compromise systems. They document the steps, techniques, and conditions that enable successful attacks, allowing defenders to recognize and prevent them proactively.

At a basic level, attack patterns help new professionals understand "how" bad actors operate. For advanced practitioners, they provide structured intelligence that can be mapped to controls, detection rules, and architectural decisions. Common patterns include initial access via phishing, lateral movement through compromised credentials, and data exfiltration using encrypted channels.

Security architects use attack patterns during design reviews to identify weak points. For example, a pattern involving credential dumping might lead to implementing privileged access workstations and just-in-time administration. In practice, tracking evolving patterns through threat intelligence feeds enables continuous improvement of defenses.

**Corporate Example:** Retail organizations analyze ransomware attack patterns to strengthen backup strategies and segmentation.  
**DoD Example:** Defense systems study supply chain attack patterns to enforce strict hardware provenance and continuous monitoring requirements.

---

## Frameworks

**Threat modeling frameworks** provide standardized methodologies and knowledge bases for identifying and analyzing threats systematically.

- **MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK):** A globally accessible knowledge base of adversary tactics and techniques across enterprise, mobile, ICS, and cloud environments. `https://attack.mitre.org`  
- **Common Attack Pattern Enumeration and Classification (CAPEC):** A dictionary of known attack patterns with detailed descriptions and mitigation strategies.  
- **Cyber Kill Chain:** A Lockheed Martin model describing the stages of a cyber intrusion (Reconnaissance → Weaponization → Delivery → Exploitation → Installation → Command & Control → Actions on Objectives).  
- **Diamond Model of Intrusion Analysis:** Focuses on four interconnected elements (Adversary, Capability, Infrastructure, Victim) to analyze intrusions.  
- **STRIDE:** A mnemonic (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege) used to identify threats during system design.  
- **Open Web Application Security Project (OWASP):** Provides resources like the OWASP Top 10 for web application security risks and detailed threat modeling guidance.

**Corporate Example:** Development teams use STRIDE during code reviews and OWASP for web apps.  
**DoD Example:** Analysts map observed activity to MITRE ATT&CK for reporting and RMF control selection.

---

## Attack Surface Determination

**Attack surface determination** is the process of identifying all possible points where an unauthorized user can attempt to compromise a system. A smaller, well-understood attack surface is easier to defend.

### Key Activities
- **Architecture Reviews:** High-level examination of system design and interconnections.  
- **Data Flows:** Mapping how data moves through the environment to spot exposure points.  
- **Trust Boundaries:** Identifying where trust levels change (e.g., internal vs. external networks).  
- **Code Reviews:** Static and dynamic analysis for vulnerabilities.  
- **User Factors:** Considering human elements like privileged users or social engineering risks.  
- **Organizational Change:** Evaluating impacts from mergers, acquisitions, divestitures, or staffing changes that may introduce new risks.  
- **Enumeration/Discovery:**  
  - Internally and externally facing assets  
  - Third-party connections  
  - Unsanctioned assets/accounts (shadow IT)  
  - Cloud services discovery  
  - Public digital presence (websites, DNS records, employee profiles)

**Corporate Example:** After an acquisition, a company performs discovery to identify and secure newly inherited cloud instances.  
**DoD Example:** Regular attack surface reviews ensure that tactical edge devices and contractor connections do not expand the mission network’s exposure.

---

## Methods

**Threat modeling methods** are practical techniques used to visualize and analyze potential attacks.

- **Abuse Cases:** Describe how legitimate functionality could be misused by an attacker.  
- **Antipatterns:** Common insecure design or implementation mistakes to avoid.  
- **Attack Trees/Graphs:** Visual diagrams showing possible attack paths from initial access to ultimate goals, with branches representing different techniques.

These methods help teams move from abstract risk discussions to concrete, actionable security requirements.

**Corporate Example:** Using attack trees to model ransomware paths in an enterprise environment.  
**DoD Example:** Developing abuse cases for mission-critical applications to ensure robust controls in RMF packages.

---

## Modeling Applicability of Threats to the Organization/Environment

**Modeling applicability** involves determining which threats are most relevant to a specific organization or system and deciding how to address them.

### With an Existing System in Place
- Review current architecture and controls.  
- Map identified threats to existing mitigations.  
- Select appropriate additional controls based on residual risk.  
- Update documentation (e.g., System Security Plan).

### Without an Existing System in Place
- Start with business objectives and data sensitivity.  
- Use frameworks like STRIDE or ATT&CK to identify likely threats early.  
- Design security controls into the architecture from the beginning (secure by design).

**Corporate Example:** A fintech startup models threats during initial platform design using OWASP and STRIDE.  
**DoD Example:** New systems follow RMF Step 2 (Categorize) and Step 3 (Select Controls) to model threats before implementation.

---

## Threat Modeling in DoD Environments

The DoD integrates threat modeling throughout the **Risk Management Framework (RMF)** (`DoDI 8510.01`). Key practices include:

- Using MITRE ATT&CK for adversary emulation and reporting.  
- Incorporating threat modeling into system categorization and control selection.  
- Leveraging intelligence from USCYBERCOM and DIA to tailor models to specific mission environments.  
- Continuous reevaluation during RMF Step 6 (Monitor) as threats evolve.

**Integration with Governance:** Threat models inform STIG application, Zero Trust implementation, and supply chain risk management under `DFARS 252.204-7012` and `NIST SP 800-171`.

> **Exam Tip:** In scenarios, demonstrate how you would use a specific framework (e.g., STRIDE during design or ATT&CK for an existing system) and link it to appropriate controls or RMF steps.

---

