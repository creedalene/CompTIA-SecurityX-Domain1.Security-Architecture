# SecurityX (CAS-005) Domain 1.2: Risk Management Activities

**Given a set of organizational security requirements, perform risk management activities.**

## 📋 Table of Contents

- [Impact Analysis](#impact-analysis)
- [Risk Assessment and Management](#risk-assessment-and-management)
- [Third-Party Risk Management](#third-party-risk-management)
- [Availability Risk Considerations](#availability-risk-considerations)
- [Confidentiality Risk Considerations](#confidentiality-risk-considerations)
- [Integrity Risk Considerations](#integrity-risk-considerations)
- [Privacy Risk Considerations](#privacy-risk-considerations)
- [Crisis Management](#crisis-management)
- [Breach Response](#breach-response)
- [Risk Management in DoD Environments](#risk-management-in-dod-environments)

---

## Impact Analysis

**Impact analysis** is the process of determining how badly a potential security incident (risk event) could affect the organization. Think of it as asking: "If this bad thing happens, how much damage are we looking at?"

Security architects evaluate **extreme but plausible scenarios** — realistic worst-case situations that could actually occur — across multiple categories.

### Key Impact Categories
| Category | Simple Explanation | Corporate Example | DoD Example |
|----------|--------------------|-------------------|-------------|
| **Financial** | Direct money loss | Ransomware demanding millions and halting e-commerce sales for days | $10M+ ransom on a logistics system plus contract penalties |
| **Operational** | Day-to-day work stops | Vendor attack disrupts customer support systems | 72+ hour outage of mission-critical supply chain systems |
| **Reputational** | Damage to public image | Leak of customer data leads to bad press and lost trust | High-profile breach exposing service member data triggers congressional hearings |
| **Regulatory/Legal** | Fines or legal trouble | GDPR fine for data mishandling | Contract termination under `DFARS 252.204-7012` and potential debarment |
| **Mission** | Core purpose is harmed | Loss of intellectual property slows product development | Compromise of tactical networks reduces warfighter situational awareness |

**Best Practice (for both environments):** Perform a **Business Impact Analysis (BIA)** using a simple 1–5 scoring scale for likelihood × impact. This helps prioritize what to protect first.

---

## Risk Assessment and Management

**Risk assessment** means systematically finding, studying, and ranking risks. **Risk management** is the broader process of deciding what to do about those risks (fix them, accept them, etc.).

### Quantitative vs. Qualitative Analysis

| Approach | Simple Explanation | When to Use | Key Metrics / Tools |
|----------|--------------------|-------------|---------------------|
| **Quantitative** | Uses numbers and math for precise estimates | When you have good data (finance-heavy decisions) | **ALE** = Single Loss Expectancy (SLE) × Annual Rate of Occurrence (ARO)<br>Example: Asset worth $500k × 40% exposure × 0.3 occurrences/year = **$60,000 ALE** |
| **Qualitative** | Uses words like Low/Medium/High | Quick assessments or limited data | Risk matrices, expert workshops (Delphi technique) |

### Risk Assessment Frameworks
- **`NIST SP 800-30`**: Core guide for conducting risk assessments (used in both corporate and government).
- **`ISO 31000`**: International standard for overall risk management.
- **DoD RMF (`DoDI 8510.01`)**: The mandatory lifecycle process for DoD systems.

### Risk Appetite, Tolerance, Prioritization, Remediation & Validation
- **Risk Appetite**: How much risk leadership is willing to take on purpose (e.g., "We accept moderate innovation risk").
- **Risk Tolerance**: The acceptable variation around that appetite (e.g., "We cannot tolerate any risk to classified data").
- **Prioritization**: Rank risks in a **risk register** using heat maps (red = high priority).
- **Remediation Strategies**:
  1. **Mitigate** — Add controls (most common).
  2. **Accept** — Leadership formally acknowledges and signs off.
  3. **Avoid** — Stop the risky activity.
  4. **Transfer** — Use insurance or contracts.
- **Validation**: Test controls through scans, penetration tests, and continuous monitoring to prove they actually work.

**Corporate Example**: A bank uses quantitative ALE to decide whether to invest in advanced fraud detection.  
**DoD Example**: The Authorizing Official (AO) accepts residual risk after reviewing an RMF package in `eMASS`.

---

## Third-Party Risk Management

**Third-party risk management (TPRM)** focuses on risks coming from outside vendors, suppliers, and partners.

### Key Areas
- **Supply Chain Risk**: Threats hidden in hardware/software you buy (e.g., SolarWinds-style backdoors).
- **Vendor Risk**: Risks from cloud providers, MSSPs, or service contractors.
- **Subprocessor Risk**: Risks from a vendor’s own subcontractors (data may travel further than you expect).

**TPRM Process (works in both worlds):**
1. **Due Diligence** — Check SOC 2, ISO 27001, or `CMMC` reports before signing contracts.
2. **Contractual Controls** — Require flow-down clauses, audit rights, and fast incident notification.
3. **Ongoing Monitoring** — Regular reviews and scorecards.
4. **Exit Strategy** — Ensure data is returned or destroyed when the relationship ends.

**Corporate Example**: A retailer assesses a payment processor’s security before integration.  
**DoD Example**: Contractors must flow down `NIST SP 800-171` requirements to subcontractors per `DFARS 252.204-7012`.

---

## Availability Risk Considerations

**Availability** means ensuring systems and data are accessible when needed.

### Business Continuity / Disaster Recovery (BCP/DR)
- **BCP**: Keeps critical business functions running during a disruption.
- **DR**: Focuses on restoring IT systems after a major event.

**Key Metrics**:
- **RTO (Recovery Time Objective)**: Maximum acceptable downtime.
- **RPO (Recovery Point Objective)**: Maximum acceptable data loss.

### Testing
- Tabletop exercises (discussion-based)
- Walkthroughs
- Parallel testing
- Full interruption testing (most realistic)

### Backups
- **Connected (Online)**: Fast recovery but vulnerable to ransomware.
- **Disconnected (Air-Gapped/Offline)**: Much safer — follow the **3-2-1-1 rule** (3 copies, 2 media types, 1 offsite, 1 immutable/air-gapped).
- Always use encryption and test restore processes.

**Corporate Example**: An e-commerce site tests DR plans to meet customer SLAs.  
**DoD Example**: Mission systems maintain air-gapped backups to survive advanced persistent threats.

---

## Confidentiality Risk Considerations

**Confidentiality** protects data from unauthorized viewing.

- **Data Leak Response**: Detect, contain, and notify quickly.
- **Sensitive/Privileged Data Breach**: Extra care for CUI, classified, or PII.
- **Incident Response Testing**: Regular tabletop and simulated attacks.
- **Reporting**: Meet legal timelines (e.g., 72 hours for DoD contractors).
- **Encryption**: Use strong standards (`AES-256` at rest, `TLS 1.3` in transit).

**Corporate Example**: A healthcare company encrypts patient records and has a leak response playbook.  
**DoD Example**: Strict marking and handling rules under `DoDI 5200.48` for CUI.

---

## Integrity Risk Considerations

**Integrity** ensures data is accurate and unchanged by unauthorized parties.

- **Remote Journaling**: Real-time secure logging to a secondary site for recovery.
- **Hashing**: Use strong algorithms like `SHA-384/512` to verify files haven’t been altered (never use MD5 in production).
- **Interference Protection**: Defend against man-in-the-middle attacks.
- **Antitampering**: Code signing, File Integrity Monitoring (FIM), and TPM measurements.

**Corporate Example**: A financial firm uses hashing to verify transaction logs.  
**DoD Example**: STIGs require file integrity monitoring on critical servers.

---

## Privacy Risk Considerations

**Privacy** focuses on protecting individuals’ personal information and their rights.

- **Data Subject Rights**: Rights to access, correct, or delete personal data (influenced by GDPR/CCPA).
- **Data Sovereignty**: Rules about where data can be stored (e.g., cannot move EU citizen data to certain countries).
- **Biometrics**: Extra protections because fingerprints or facial data cannot be changed if compromised (requires strong consent and storage controls).

**Key Guidance**: `NIST SP 800-53` privacy controls and `DoDI 5400.16` for DoD privacy programs.

**Corporate Example**: A retail company honors customer deletion requests promptly.  
**DoD Example**: Strict rules on handling service member personal data across systems.

---

## Crisis Management

**Crisis management** is the structured approach to preparing for, responding to, and recovering from major events that threaten the organization’s survival or mission.

### Detailed Breakdown
1. **Preparation**
   - Form a Crisis Management Team (CMT) with clear RACI responsibilities.
   - Develop pre-approved messaging templates and a "war room" (physical or virtual).
   - Conduct regular war-gaming and scenario planning.

2. **Detection & Activation**
   - Define clear triggers (major breach, natural disaster, insider threat).
   - Have 24/7 escalation paths to senior leaders.

3. **Response**
   - Coordinate containment, stakeholder communication (employees, customers, media, Congress).
   - Involve Legal, Public Affairs, and technical teams simultaneously.

4. **Recovery & After-Action**
   - Safely return to normal operations.
   - Perform Root Cause Analysis (RCA).
   - Document lessons learned and update plans.

**Corporate Example**: A Fortune 500 company activates its CMT after a ransomware attack hits headquarters.  
**DoD Example**: Aligns with `CJCSM 6510.01B` and integrates with Continuity of Operations (COOP) planning during major cyber incidents.

---

## Breach Response

**Breach response** follows a proven lifecycle to handle security incidents effectively.

### NIST / DoD-Aligned Phases
1. **Preparation** — Build the IR plan, team, tools, and playbooks in advance.
2. **Identification** — Confirm the breach using logs, EDR, and SIEM alerts.
3. **Containment** — Stop the bleeding (short-term isolation, long-term fixes).
4. **Eradication** — Remove malware and close vulnerabilities.
5. **Recovery** — Restore from clean backups and monitor for re-attack.
6. **Lessons Learned** — Improve policies and training.

**Key Considerations**:
- **Notification**: Follow legal/contractual rules (72-hour reporting to DoD via `https://dibnet.dod.mil` under `DFARS 252.204-7012`).
- **Forensics**: Maintain strict chain of custody for evidence.
- **Communication**: Be transparent but controlled.
- **Post-Breach**: Offer credit monitoring if PII is involved and re-authorize systems via RMF.

**Corporate Example**: A company follows NIST phases after a phishing-led breach.  
**DoD Example**: Contractor must report to DC3 within 72 hours and support potential CORA inspection.

---

## Risk Management in DoD Environments

The DoD uses a formal **Risk Management Framework (RMF)** defined in **`DoDI 8510.01`** (July 2022):

- **7 Steps**: Prepare → Categorize → Select → Implement → Assess → Authorize → Monitor.
- **Primary Tool**: `eMASS` for documentation and tracking.
- **Controls**: Based on `NIST SP 800-53`, tailored via `CNSSI 1253`.
- **Accountability**: The **Authorizing Official (AO)** makes final risk decisions.

**Integration Tip**: RMF runs alongside STIGs, continuous monitoring, and supply chain risk processes.

> **Exam Tip:** In scenarios, map the situation to the correct RMF step and recommend supporting governance documents.

---

*This document will be expanded with diagrams, templates, and labs in future revisions.*
