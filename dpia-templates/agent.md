# DPIA Template: AI Agent

A data protection impact assessment structure for AI agents, meaning systems that use tools, call APIs and take actions across several systems with some degree of autonomy.

Generic DPIA templates were not designed for agents, so this one adds the areas they tend to miss: tool use, decision boundaries, memory, escalation and the chain of processors that an agent creates.

## How to use

Complete each section for the system you are actually deploying, replacing the bracketed placeholders. Where a section does not apply, say so and explain why in the residual risk section.

---

## 1. System summary

**Agent name and purpose:** [What the agent does, who uses it and what it produces]

**Operator:** [Your organisation, as controller]

**Deployment context:** [Customer-facing, internal, a public API, or embedded in a product]

**Level of autonomy:** [Choose one: every action approved by a person; a person approves high-impact actions; or fully autonomous within defined boundaries]

**Decision authority:** [What the agent can decide and do by itself, and what requires approval by a person]

## 2. Roles and lawful basis

**Controller:** [Your organisation]
**Processors:**
- Model provider: [Provider and the specific model]
- Tool and API providers: [Every external service the agent calls]
- Hosting and infrastructure: [Cloud provider and region]
- Vector database or memory store: [Provider and location]
- Logging and monitoring: [Where agent traces and tool calls are stored]

**Lawful basis, for each purpose:**
- Delivering the service: [contract or legitimate interests]
- Decisions about individuals: [if a decision is based solely on automated processing and has legal or similarly significant effects, record the condition relied on under Article 22(2) of the EU GDPR, or the safeguards required by Articles 22A to 22D of the UK GDPR]
- Memory storage: [legitimate interests, with the reason for the retention period]
- Logging for audit and safety: [legitimate interests]

**Special category data (Article 9):** [Whether the agent processes or infers health, biometric, criminal offence or other special category data, and if so the Article 9(2) condition relied on]

## 3. Personal data inventory

For an agent this needs to cover what users provide, what the agent produces, what it stores between steps and what passes to and from each tool.

**Data provided by users:** [What users tell the agent]
**Outputs:** [What the agent produces: text, decisions or structured records]
**Data sent to tools:** [What personal data goes to each tool]
**Data returned by tools:** [What personal data comes back from each tool]
**Memory and state:** [What persists between sessions, such as conversation history, embeddings, user profiles or inferred attributes]
**Logs and traces:** [What is captured for audit, such as full prompts, tool call contents or decision reasons]
**Retention for each:** [A specific period, with the reason for any longer retention]

## 4. Data flow and transfers

A diagram is the clearest way to show the flow; in outline:

```
User input
  → agent orchestration (your servers)
    → model provider [host/region]
    → tool API 1 [host/region/data sent]
    → tool API 2 [host/region/data sent]
    → memory store [host/region]
    → decision logic
    → output to the user
    → logging [host/region]
```

**International transfers:**
- For each processor outside the UK or EEA, identify the transfer mechanism, such as the Standard Contractual Clauses, binding corporate rules or an adequacy decision.
- For US providers, check the EU-US Data Privacy Framework register by legal entity name rather than assuming certification.

**Sub-processors:** each tool provider that processes personal data on your behalf is a processor or sub-processor, so list them and confirm a data processing agreement is in place with each.

## 5. Risk assessment

The following risks are specific to agents.

**5.1 Errors repeated at scale**
- Likelihood: [low, medium or high]
- Severity: [low, medium or high, depending on whether decisions affect people's rights, finances or access to services]
- Risk: the agent makes a wrong decision and repeats it across several actions before anyone notices

**5.2 Tools sending data to processors that were not assessed**
- The agent may call a tool the DPIA did not anticipate, such as a search tool that sends queries to a third-party search provider.
- Mitigation: an allowlist of permitted tools, with a data protection review of each

**5.3 Memory shared across users**
- Where several users share one vector store, information from one user's data could appear in another user's context.
- Mitigation: memory partitioned by user, with retrieval limited to each user's own data

**5.4 Collecting more data than intended through tools**
- Agents that can browse the web or read files may bring in personal data the controller never intended to process.
- Mitigation: limits on tool access, and filtering of tool outputs

**5.5 Gaps in the audit trail**
- Because tool calls are frequent and fast, logging too little makes decisions impossible to reconstruct, while logging too much creates new personal data risks.
- Mitigation: structured logging with personal data removed or pseudonymised, and a defined retention period

**5.6 Automated decisions made without anyone noticing**
- Where the agent takes a decision about a person based solely on automated processing, with legal or similarly significant effects, the automated decision-making rules apply: Article 22 of the EU GDPR, or Articles 22A to 22D of the UK GDPR.
- Mitigation: review by a person, with real authority to change the outcome, before any decision with legal or similarly significant effects

**5.7 Prompt injection**
- Users, or content the agent reads, may contain instructions designed to make the agent take actions it should not.
- Mitigation: separation of instructions from untrusted content, validation of outputs, and authorisation checks for each action

## 6. Controls

For each risk, record the specific controls in place and how they are configured. The following are examples to replace with your own.

**Tool controls:**
- tools the agent can use: [explicit allowlist]
- process for adding a tool: [DPIA update and DPO advice]
- data removed from tool calls: [categories of personal data that are filtered]

**Decision boundaries:**
- actions the agent takes by itself: [list of low-risk actions]
- actions requiring approval by a person: [list of significant actions and the trigger]
- escalation: [who reviews and how quickly]

**Memory controls:**
- partitioning by user: [how it is implemented]
- retention: [conversation history kept X days, embeddings Y days]
- deletion on request: [the tested process]

**Logging controls:**
- what is logged: [structure]
- personal data in logs: [removal or pseudonymisation approach]
- retention: [days]
- access: [who can read the logs]

**Audit and explainability:**
- information captured for each decision: [fields]
- review by a person: [sample size and frequency]
- reporting a regulator could request: [what can be produced]

**Automated decision-making:**
- how decisions within the rules are identified: [criteria]
- review by a person: [process]
- how people can contest a decision: [how they are told, and how challenges are handled]

## 7. Residual risk and sign-off

**Residual risk after controls:** [low, medium or high]

If the residual risk remains high after mitigation, consult the supervisory authority, such as the ICO or the Irish Data Protection Commission, before processing begins (Article 36).

**Approval:**
- DPO advice: [date and summary]
- Senior management approval: [name and date]

**Review:**
- routine review: [annually]
- triggered review: [when tools, models or data sources change, and after any incident]

---

## Outside the scope of this template

- Sector rules, for example in financial services, healthcare or recruitment, which apply alongside the GDPR and the EU AI Act.
- Equality obligations where an agent makes decisions about people, which need a separate equality assessment.
- How liability is allocated between the operator and tool providers, which is a matter for the contracts.

Agents with significant sector-specific exposure will need a fuller review than this template provides.

---

*Template by Michael K. Onyekwere, [Janus Compliance](https://www.januscompliance.co.uk). Part of the [Compliance Engineering Toolkit](https://github.com/Thezenmonster/compliance-engineering-toolkit). Legal references checked on 4 October 2026. New templates and updates are announced in [Compliance Engineering](https://complianceengineering.substack.com). Licensed CC BY 4.0; attribution required on reuse.*
