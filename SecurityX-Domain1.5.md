# SecurityX (CAS-005) Domain 1.5: Information Security Challenges with Artificial Intelligence (AI) Adoption

**Summarize the information security challenges associated with artificial intelligence (AI) adoption.**

## 📋 Table of Contents

- [Legal and Privacy Implications](#legal-and-privacy-implications)
- [Threats to the Modeling](#threats-to-the-modeling)
- [AI-Enabled Attacks](#ai-enabled-attacks)
- [Risks of AI Usage](#risks-of-ai-usage)
- [AI-Enabled Assistants and Digital Workers](#ai-enabled-assistants-and-digital-workers)
- [AI Security Challenges in DoD Environments](#ai-security-challenges-in-dod-environments)

---

## Legal and Privacy Implications

**Legal and privacy implications** arise when organizations adopt AI systems that process large amounts of data, make automated decisions, or interact with users. These challenges require balancing innovation with compliance, ethics, and risk management.

- **Potential Misuse:** AI systems can be exploited for harmful purposes such as generating disinformation or automating cyberattacks.  
- **Explainable vs. Non-Explainable Models:** Explainable AI (XAI) allows humans to understand how decisions are made, while "black box" models are opaque and harder to audit for bias or errors.  
- **Organizational Policies on the Use of AI:** Clear internal rules governing acceptable AI tools, data usage, and oversight.  
- **Ethical Governance:** Frameworks that ensure fairness, transparency, and accountability in AI deployment.

**Corporate Example:** A financial institution implements strict policies and explainable models to avoid regulatory fines when using AI for loan approvals.  
**DoD Example:** Military AI systems for targeting or intelligence analysis must adhere to ethical guidelines and explainability requirements to maintain human oversight and comply with laws of armed conflict.

---

## Threats to the Modeling

**Threats to the modeling** target the AI system itself — its training data, algorithms, or outputs — rather than using AI as a tool for attacks.

- **Prompt Injection:** Attackers craft malicious inputs to bypass safeguards and make the model perform unauthorized actions.  
- **Insecure Output Handling:** Failing to validate or sanitize AI-generated content before using it in critical systems.  
- **Training Data Poisoning:** Deliberately corrupting datasets used to train the model, causing it to learn incorrect or biased behaviors.  
- **Model Denial of Service (DoS):** Overloading the model with requests to degrade performance or increase costs.  
- **Supply Chain Vulnerabilities:** Compromised third-party datasets, libraries, or pre-trained models.  
- **Model Theft:** Extracting or reverse-engineering proprietary models through queries.  
- **Model Inversion:** Reconstructing sensitive training data by analyzing model outputs.

**Corporate Example:** An e-commerce company discovers poisoned training data leading to biased product recommendations.  
**DoD Example:** Adversaries attempt prompt injection against intelligence analysis tools or poison datasets used in autonomous systems.

---

## AI-Enabled Attacks

**AI-enabled attacks** use artificial intelligence to enhance or automate traditional cyberattacks, making them faster, more scalable, and harder to detect.

- **Insecure Plug-in Design:** Poorly secured AI extensions that grant excessive privileges.  
- **Deepfake:**  
  - **Digital Media:** AI-generated fake images, videos, or audio used for deception.  
  - **Interactivity:** Real-time deepfakes for live video calls or voice impersonation.  
- **AI Pipeline Injections:** Compromising the workflow where data moves between AI components.  
- **Social Engineering:** AI-powered phishing emails, chatbots, or voice clones that appear highly personalized.  
- **Automated Exploit Generation:** AI systems that discover and weaponize vulnerabilities at machine speed.

**Corporate Example:** Attackers use deepfake audio to impersonate executives in business email compromise (BEC) scams.  
**DoD Example:** Adversaries deploy AI-generated deepfakes to spread disinformation during operations or use automated tools to rapidly exploit vulnerabilities in tactical networks.

---

## Risks of AI Usage

**Risks of AI usage** stem from how organizations and individuals interact with AI systems in daily operations.

- **Overreliance:** Depending too heavily on AI recommendations without human verification, leading to poor decisions.  
- **Sensitive Information Disclosure:**  
  - **To the Model:** Accidentally feeding confidential data into public AI tools.  
  - **From the Model:** The AI leaking sensitive information in its responses.  
- **Excessive Agency of the AI:** Giving AI systems too much autonomy to act without proper oversight or guardrails.

**Corporate Example:** Employees pasting proprietary code into a public LLM, resulting in intellectual property exposure.  
**DoD Example:** Overreliance on AI analysis tools without proper validation could lead to flawed intelligence assessments affecting mission outcomes.

---

## AI-Enabled Assistants and Digital Workers

**AI-enabled assistants and digital workers** are autonomous or semi-autonomous systems that perform tasks traditionally done by humans.

- **Access/Permissions:** Managing what data and systems these agents can reach.  
- **Guardrails:** Technical and policy controls that limit harmful or unintended actions.  
- **Data Loss Prevention (DLP):** Monitoring and blocking sensitive data from being processed or shared by AI agents.  
- **Disclosure of AI Usage:** Being transparent when users or customers are interacting with AI rather than humans.

**Corporate Example:** A customer service AI assistant must have strict DLP controls and clearly disclose it is not a human agent.  
**DoD Example:** AI digital workers assisting with logistics or maintenance require rigorous access controls, audit logging, and human-in-the-loop approval for critical decisions.

---

## AI Security Challenges in DoD Environments

The Department of Defense faces unique challenges when adopting AI due to national security implications, classified data, and mission-critical applications. Key guidance includes:

- Integration with the **Risk Management Framework (RMF)** (`DoDI 8510.01`) for AI systems.  
- Strict controls on training data to prevent poisoning or leakage of `CUI` and classified information.  
- Emphasis on explainable AI for command-level decision support.  
- Protection against adversarial AI attacks under initiatives like the DoD AI Strategy and `NIST SP 800-53` controls tailored for AI/ML systems.  
- Use of `eMASS` for documenting AI-related risks and controls.

**Corporate vs. DoD Context:** While commercial organizations focus primarily on regulatory compliance, customer trust, and financial risk, DoD AI adoption prioritizes mission assurance, ethical use in warfare, and resilience against nation-state adversaries.

**Exam Tip:** Be prepared to discuss how specific AI threats map to RMF steps, STRIDE threat modeling, or existing controls like input validation and continuous monitoring.

---

*This document is a living set of notes, and there will be future revisions.*
