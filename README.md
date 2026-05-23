# CompTIA SecurityX (CAS-005) Domain 1.0 Governance, Risk, and Compliance

The notes are maintained by Cree Dalene, a Senior Security Architect, to support ongoing professional development and to stay current with the latest security architecture principles, frameworks, and practices relevant to senior-level roles in enterprise and defense environments.

The content strives to provide clear, structured coverage of core governance and architecture topics, including:

* Security program documentation and the governance hierarchy: Policies, Standards, Procedures, and Guidelines, along with their respective authority levels and applications
* Key DoD cybersecurity frameworks: DoDD 8000.01, DoDI 8500.01, DoDI 8510.01 (Risk Management Framework), NIST SP 800-53, NIST SP 800-171, DFARS 252.204-7012, DISA STIGs, and CJCSM 6510.01B
* Zero Trust Architecture principles based on NIST SP 800-207 and the DoD Zero Trust Reference Architecture, including considerations for SASE and hybrid cloud environments
* Risk management activities: Impact analysis, risk assessment, third-party risk, availability/confidentiality/integrity/privacy risk considerations, crisis management, and breach response
* Additional areas such as threat modeling, attack surface determination, compliance strategies, change and configuration management, RACI matrices, and information security challenges associated with artificial intelligence adoption (legal/privacy implications, AI-enabled attacks, and related risks)

All sections reference primary authoritative sources including official NIST publications, DoD Directives and Instructions, and DISA resources. Comparison tables, governance pyramids, and scenario-based explanations are used to illustrate how these components work together in practical security architecture and engineering decisions.

---

## 1.1 Given a set of organizational security requirements, implement the appropriate governance components.

### Security program documentation

#### 🏛️ The Governance Hierarchy

CompTIA views these documents as a pyramid. Each layer becomes more specific as you move from executive intent down to technical execution.

| Document Type | Level of Authority | Nature | Focus |
| :--- | :--- | :--- | :--- |
| **Policy** | High (Executive) | Mandatory | The "What" and "Why" |
| **Standard** | Mid (Technical) | Mandatory | The "How Exactly" (Specs) |
| **Procedure** | Low (Operational) | Mandatory | The "Step-by-Step" (SOP) |
| **Guideline** | Discretionary | Non-Mandatory | The "Best Practice" |

---

##### 🔍 Detailed Breakdown

###### 1. Policy (The Foundation) 📜

Senior management (CIO/CISO) issues policies as high-level statements of intent. These documents avoid technical details and establish the official "law of the land."

* **Purpose:** Policies set the organization’s security posture and assign clear responsibility.
* **CompTIA Example:** Acceptable Use Policy (AUP) or Information Security Policy.
* **Core Logic:** "The organization protects all CUI data using industry-standard encryption."

In the Department of War/Defense policies define the "what" and "why" behind executive decisions. These DoD Directives (DoDD) and Instructions (DoDI) clearly communicates the mission, and directs all subsequent standards and procedures. Some examples might include:

* **DoDD 8000.01: Management of the DoD Information Enterprise** directs DoD organizations to manage information as a strategic asset, ensuring it remains secure, available, and interoperable for the warfighter. This foundational directive establishes policy and assigns responsibilities for all information resources management activities across the DoD.
* **DoDI 8500.01 Cybersecurity** shifts the DoD from a compliance-focused Information Assurance model to a dynamic Cybersecurity model that emphasizes continuous monitoring, risk management, and integration of cybersecurity into the systems engineering lifecycle. This instruction establishes the overarching DoD cybersecurity program to protect and defend DoD information and IT systems.
* **DoDI 5200.48: Controlled Unclassified Information (CUI)** directs the DoD and its contractors to identify, mark, safeguard, share, and destroy CUI while linking protection requirements directly to NIST standards. This policy establishes the DoD CUI Program.

###### 2. Standard (The Requirement) 🛠️

Senior leadership defines standards as specific technical requirements and hardware/software specifications that fulfill policies. These documents ensure consistency and prevent configuration drift across the enterprise.

* **Purpose:** Standards maintain interoperability and enforce uniform implementation.
* **CompTIA Example:** "All laptops must use AES-256 bit encryption for data at rest."
* **Core Logic:** "If the policy requires encryption, the organization must use this exact algorithm."

In the Department of Defense, standards specify the “how” behind policy requirements. The DoD adopts external frameworks and internal instructions as mandatory standards. Key examples include:

* **DoDI 8510.01: Risk Management Framework (RMF) for DoD Information Technology (IT)** establishes the RMF process for the DoD. This standard mandates the exact lifecycle for authorizing IT systems on DoD networks, replaces the old DIACAP system, and ties directly to NIST SP 800-37 and 800-53.
* **NIST Special Publications (SP 800-53 and SP 800-171)** serve as mandatory standards for the DoD. NIST SP 800-53 provides the catalog of security and privacy controls for federal information systems, while NIST SP 800-171 mandates protection requirements for defense contractors handling CUI on non-federal systems.
* **DFARS 252.204-7012 (Safeguarding Covered Defense Information)** applies as a contractual standard to defense contractors. This clause legally requires contractors to implement NIST SP 800-171 and report cyber incidents to the DoD Cyber Crime Center (DC3) within 72 hours.

###### 3. Procedure (The Steps) 📋

Senior leadership and technical teams create procedures, also known as Standard Operating Procedures (SOPs), as granular step-by-step instructions for specific tasks. These documents enable any qualified technician to produce consistent, repeatable results.

* **Purpose:** Procedures minimize human error and deliver reliable outcomes.
* **CompTIA Example:** The Incident Response Procedure directs teams to identify the breach, isolate the host, and notify the SOC Lead.
* **Core Logic:** "Follow these exact steps in this exact order to isolate the host."

In the Department of Defense, procedures provide the detailed execution guidance that turns policy and standards into action. The DoD maintains several key procedural frameworks and execution guides. Important examples include:

* **DISA STIGs (Security Technical Implementation Guides)** serve as the primary step-by-step procedures for securing software, hardware, and networks. Developed by the Defense Information Systems Agency (DISA), STIGs function as exhaustive, product-specific checklists (e.g., Windows Server 2022 STIG, Cisco IOS Router STIG). Each STIG organizes actionable rules by severity: Category I (CAT I) for immediate high-severity actions, Category II (CAT II) for medium-severity requirements, and Category III (CAT III) for lower-priority baseline enhancements. `https://www.cyber.mil/stigs`
* **CJCSM 6510.01B: Cyber Incident Handling Program** delivers exact tactical procedures for responding to network intrusions, data breaches, and insider threats. This manual establishes a mandatory pipeline that includes triage, categorization, isolation and containment, and timely reporting to USCYBERCOM and JFHQ-DODIN. `https://www.jcs.mil/Library/` 
* **IAVM (Information Assurance Vulnerability Management)** outlines mandatory procedures for patching vulnerabilities across the DoD. The program converts CVE data into actionable orders through IAVA (immediate patching) and IAVB (scheduled maintenance) alerts. System administrators run automated scans, apply verified patches, and report compliance back to USCYBERCOM. `https://iavm.csd.disa.mil/` 
* **CCRI (Command Cyber Readiness Inspection)** provides the formal audit procedure to verify compliance with policies and standards. Inspection teams conduct on-site reviews of networks, systems, and RMF packages using automated checklists to confirm STIG application and physical security controls. `https://integrate.diat.mil/public`

###### 4. Guideline (The Recommendation) 💡

Senior leadership and architects issue guidelines as suggested actions and best practices. These documents offer flexibility when no strict standard or procedure applies. Guidelines represent the only non-mandatory element in the governance hierarchy.

* **Purpose:** Guidelines provide practical advice and adaptability.
* **CompTIA Example:** "It is recommended to use a passphrase of at least 15 characters for improved entropy."
* **Core Logic:** "The organization does not require this approach, but it delivers strong benefits when feasible."

> CompTIA's example of 15 characters being a guideline is laughable here, it should be updated, as that's actually a STIG required in the DoD/W.

In the Department of Defense, guidelines appear as Reference Architectures (RA), Reference Designs (RD), or Information Guides. These discretionary documents help organizations implement policies and standards effectively. Key examples include:

* **DoD Zero Trust Reference Architecture (ZT RA)** serves as the primary guidance document for transitioning to zero-trust models. It outlines the 7 Zero Trust Pillars (Identity, Devices, Network, Applications, Data, Visibility/Analytics, Automation/Orchestration) and supplies design patterns without mandating specific tools or commands. This architecture guides mission owners away from traditional perimeter-based defense toward dynamic, data-centric security.
* **DoD ICAM Reference Design (Identity, Credential, & Access Management)** delivers design guidance for modernizing identity management across the enterprise. It establishes blueprints for secure multi-factor authentication (MFA) and non-person entity (NPE) credentialing to address challenges in tactical environments.
* **DoD Cloud Computing Security Requirements Guide (SRG)** provides comprehensive guidance for integrating commercial cloud services into the DoD Information Network (DoDIN). It supplies architectural patterns for securely segmenting and protecting data across Impact Levels 2 through 5 (including CUI and National Security Systems).
* **NIST Special Publication 800-207 (Zero Trust Architecture)** functions as an authoritative external guideline. The DoD recognizes this vendor-neutral publication as a roadmap that helps security architects understand and implement zero-trust principles in both enterprise and unclassified environments.

##### 🛡️ Practical Application: The "Data Breach" Scenario

When applying this to the SecurityX exam, it's helpful for to think through a scenario:

1.  **Policy:** "Management" has decreed that all data breaches must be reported within 1 hour (Mandatory).
2.  **Standard:** The organization uses the *STIX/TAXII* format for sharing threat intelligence (Mandatory Spec).
3.  **Procedure:** The technician follows the "Forensic Image Acquisition" document to pull a bit-by-bit copy of the drive (Mandatory Steps).
4.  **Guideline:** The technician is *advised* to use a write-blocker, but if one is unavailable in a tactical environment, they may proceed with caution (Discretionary).

> I used "Management" here for applicability, but in a military context it would be commander or communications officer.

---

### Security program management

Senior leaders build effective security programs through structured awareness initiatives, clear communication channels, robust reporting mechanisms, and strong management commitment. These elements ensure the organization translates policy into consistent daily practice.

**Awareness and Training**  
Organizations deliver ongoing security awareness and training programs to equip personnel with the knowledge and skills needed to protect information assets. Effective programs address multiple threat vectors through targeted modules:

* **Phishing Awareness:** Training helps employees recognize and report suspicious emails, malicious links, and credential harvesting attempts.
* **General Security Awareness:** Programs cover password hygiene, device security, and safe internet practices.
* **Social Engineering:** Training teaches personnel to identify manipulation tactics such as pretexting, baiting, and tailgating.
* **Privacy Awareness:** Modules explain proper handling of personal and sensitive data in compliance with regulations.
* **Operational Security (OPSEC):** Training emphasizes protection of critical information, indicators, and mission details from adversaries.
* **Situational Awareness:** Programs develop the ability to recognize anomalous behavior and emerging threats in dynamic environments.

**Communication**  
Leaders establish clear, multi-channel communication processes that keep security objectives, expectations, and updates visible across all organizational levels.

**Reporting**  
Organizations implement straightforward mechanisms for personnel to report security incidents, concerns, and near-misses without fear of retaliation. Effective reporting systems enable rapid response and continuous program improvement.

**Management Commitment**  
Senior executives demonstrate visible support for the security program through resource allocation, policy endorsement, and active participation in security initiatives. This commitment sets the tone for the entire organization and reinforces accountability.

**RACI Matrix**  
Teams use a Responsible, Accountable, Consulted, and Informed (RACI) matrix to clearly define roles and responsibilities within the security program. This tool eliminates confusion by mapping:

* **Responsible:** The individual or team that performs the work.
* **Accountable:** The person ultimately answerable for completion and quality.
* **Consulted:** Stakeholders whose input is actively sought.
* **Informed:** Individuals kept updated on progress and outcomes.

| Activity                          | CISO / Security Director | Security Architect | Security Operations Team | IT Operations | Compliance Officer | Business Unit Leads |
|---------------------------|--------------------------|--------------------|---------------------------|---------------|--------------------|---------------------|
| Develop Security Policy           | A / R                    | R                  | C                         | I             | C                  | C                   |
| Approve Security Standards        | A                        | R                  | C                         | I             | C                  | I                   |
| Conduct Risk Assessment           | A                        | R                  | C                         | C             | C                  | C                   |
| Implement Technical Controls      | I                        | A                  | R                         | R             | I                  | I                   |
| Deliver Security Awareness Training | A                      | C                  | R                         | I             | C                  | I                   |
| Review Incident Reports           | A                        | C                  | R                         | I             | C                  | I                   |
| Perform Third-Party Risk Review   | A                        | R                  | C                         | I             | R                  | C                   |
| Update RMF / System Security Plan | A                        | R                  | C                         | C             | C                  | I                   |

#### 🛡️ Security Program Management in DoD Environments

The Department of Defense integrates these management elements into formal programs to maintain readiness and compliance. Leadership enforces mandatory annual security awareness training, implements structured incident reporting through defined channels, and maintains visible command-level commitment to cybersecurity. DoD organizations frequently use RACI matrices within RMF packages and system security plans to ensure clear accountability across commands, contractors, and support teams.

> **Notes for DoD candidates:**
> - In DoD environments, the **Authorizing Official (AO)** typically remains **Accountable** for authorization decisions and risk acceptance.
> - The **ISSO (Information System Security Officer)** often performs much of the hands-on RMF documentation and coordination within eMASS.
> - This structure supports the continuous monitoring requirements of RMF Step 6 and ensures clear accountability during CCRIs and audits.

---

