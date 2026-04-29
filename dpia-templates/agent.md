# DPIA Template: Autonomous AI Agent

A Data Protection Impact Assessment structure for AI agents: autonomous systems that use tools, call APIs, and make decisions across multiple systems.

This template covers what generic DPIA templates miss for agents: tool use, decision boundaries, memory, escalation triggers, and the multi-processor data flow that agents create.

## How to use

Fill in each section for the actual system you're deploying. Replace bracketed placeholders. Delete sections that don't apply (and explain why in the residual risk section). The headings are the structure regulators expect; the content under each is what makes it specific to your agent.

---

## 1. System Summary

**Agent name and purpose:** [What does this agent do? Who uses it? What outcome does it produce?]

**Operator:** [Your organisation as data controller]

**Deployment context:** [Customer-facing? Internal? Public-facing API? Embedded in a product?]

**Autonomy level:** [Choose one. Human-approved actions only. Human-in-the-loop on high-stakes. Fully autonomous within defined boundaries.]

**Decision authority:** [What can the agent decide and execute on its own? What requires human approval?]

## 2. Roles and Lawful Basis

**Controller:** [Your organisation]
**Processors:**
- LLM provider: [OpenAI, Anthropic, Google, or other. Name the specific model.]
- Tool API providers: [List every external service the agent calls]
- Hosting / infrastructure: [Cloud provider, region]
- Vector database / memory store: [Provider and location]
- Logging / observability: [Where agent traces and tool calls are stored]

**Lawful basis for each processing purpose:**
- Core service delivery: [contract / legitimate interest]
- Agent decision-making affecting individuals: [if Article 22 applies, document explicit consent or other lawful basis]
- Memory storage: [legitimate interest with retention rationale]
- Logging for audit/safety: [legitimate interest, operational necessity]

**Special category data (Article 9):** [Does the agent process or generate health data, biometric data, criminal data, or other Article 9 categories? If so, identify the Article 9(2) condition relied on.]

## 3. Personal Data Inventory

For an agent, this needs to cover *direct inputs*, *generated outputs*, *intermediate state*, and *tool-call data*.

**Direct user inputs:** [What does the user say to the agent?]
**Generated outputs:** [What does the agent produce: text, decisions, structured records?]
**Tool-call inputs:** [What personal data flows into each tool the agent uses?]
**Tool-call outputs:** [What personal data flows back from each tool?]
**Memory / state:** [What is persisted between sessions? Vector embeddings, conversation history, user profiles, derived attributes?]
**Logs and traces:** [What is captured for audit: full prompts? Tool call payloads? Decision rationales?]
**Retention period for each:** [Specific number of days. Justify why longer retention is needed if it is.]

## 4. Data Flow and Transfer Map

Visual diagram preferred. As a written sketch:

```
User input
  → Agent orchestrator (your servers)
    → LLM provider [host/region]
    → Tool API 1 [host/region/data sent]
    → Tool API 2 [host/region/data sent]
    → Memory store [host/region]
    → Decision logic
    → User-facing output
    → Logging system [host/region]
```

**Cross-border transfers:**
- For each non-UK/EEA processor: identify the Article 46 safeguard (SCCs, BCRs, adequacy decision)
- For US-based providers: document the EU-US Data Privacy Framework status if applicable

**Sub-processors:** Each tool API the agent uses is functionally a sub-processor. List them. Confirm each has a DPA.

## 5. Risk Assessment

Risks specific to agents that generic DPIAs miss:

**5.1 Decision-making errors at scale**
- Likelihood: [low/medium/high]
- Severity: [low/medium/high. Depends on whether decisions affect individual rights, finances, access to services.]
- Specific risk: agent makes wrong decision and propagates the error across multiple actions before a human notices

**5.2 Tool use exposing data to unintended processors**
- The agent may call tools the original DPIA didn't anticipate (e.g., a search tool that sends queries to a third-party search engine)
- Mitigation: tool allowlisting + per-tool DPA review

**5.3 Memory leakage across users**
- If multiple users share the same vector store, embeddings of one user's data could surface in another user's context
- Mitigation: per-user memory partitioning + retrieval boundaries

**5.4 Unbounded data collection through tool use**
- Agents that can browse the web or read files may pull in personal data the controller never intended to process
- Mitigation: tool boundary controls, output filtering

**5.5 Audit trail gaps**
- Tool calls happen in milliseconds. Logging volume is enormous. Easy to log too little (can't reconstruct decisions) or too much (creating new personal data risks)
- Mitigation: structured logging with PII redaction + defined retention

**5.6 Article 22 trigger without realisation**
- Agent makes a decision affecting an individual without human review. Even one such decision triggers Article 22 obligations
- Mitigation: explicit human-in-the-loop checkpoints for any decision with legal/significant effects

**5.7 Adversarial prompts manipulating agent behaviour**
- Users (or content the agent reads) may attempt prompt injection to make the agent perform unauthorised actions
- Mitigation: prompt isolation, output validation, action-level authorization

## 6. Controls and Mitigations

For each risk above, document the specific controls in place. Don't list generic controls. Name the specific configuration.

Examples (replace with yours):

**Tool boundary controls:**
- Agent has access only to: [explicit allowlist]
- New tools require [DPIA update / DPO sign-off]
- Tool call payloads filtered to remove [unnecessary PII categories]

**Decision boundaries:**
- Agent autonomously executes: [list of low-risk actions]
- Human approval required for: [list of significant actions, with the trigger]
- Escalation path: [who reviews, in what timeframe]

**Memory controls:**
- Per-user partitioning: [how implemented technically]
- Retention: [conversation history retained X days, embeddings retained Y days]
- Deletion on data subject request: [tested process]

**Logging controls:**
- What gets logged: [structure]
- PII handling in logs: [redaction or pseudonymisation approach]
- Log retention: [days]
- Log access controls: [who can read]

**Audit and explainability:**
- Decision audit trail: [what information is captured per decision]
- Human review process: [sample size, frequency]
- Regulator-ready reporting: [what could be produced if requested]

**Article 22 compliance:**
- Identification of decisions that fall within Article 22: [criteria]
- Human review mechanism: [process]
- Right to contest: [how communicated to data subjects, how handled operationally]

## 7. Residual Risk and Sign-Off

After controls applied:

**Residual risk level:** [low / medium / high]

**If residual risk is high after mitigation:** ICO / DPC consultation required under Article 36 before processing begins.

**Approval:**
- DPO review: [date]
- DPO sign-off: [yes/no with rationale]
- Senior management approval: [name, date]

**Review schedule:**
- Routine review: [annually]
- Triggered review: [on adding new tools / changing models / adding new data sources / on incident]

---

## What this template doesn't cover

- Sectoral regulations (financial services, healthcare, recruitment). Those layer on top of GDPR/AI Act.
- Anti-discrimination obligations for agents making decisions about individuals. Needs separate equality assessment.
- Liability allocation between operator and tool providers. Contract layer, not DPIA layer.

For agent systems with complex sectoral exposure, this template is a starting point not a complete answer. Get a real review.

---

*Template by Michael K. Onyekwere, [Janus Compliance](https://www.januscompliance.co.uk). Part of the [Compliance Engineering Toolkit](https://github.com/janus-compliance/compliance-engineering-toolkit). Subscribe to [Compliance Engineering](https://complianceengineering.substack.com) for new patterns and updates. CC BY 4.0. Attribution required when reused.*
