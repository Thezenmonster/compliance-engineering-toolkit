# Compliance Engineering Toolkit

Open-source DPIA templates, a breach response framework and an AI API compliance checklist for organisations building or deploying AI systems.

By **Michael K. Onyekwere**, CIPP/E certified data protection professional and Principal at [Janus Compliance](https://www.januscompliance.co.uk), who writes [Compliance Engineering](https://complianceengineering.substack.com), a newsletter on practical AI compliance for engineering and compliance teams.

## What this is

A set of working compliance documents that you can use, adapt or fork when building AI systems. They are starting points rather than legal advice, and each one needs to be completed for the system you are actually deploying.

## What's here

### `dpia-templates/`
Data protection impact assessment templates for common AI patterns:
- `chatbot.md`: customer-facing chatbots built on large language model APIs
- `agent.md`: AI agents that use tools, call APIs and take actions across systems

### `checklists/`
- `ai-api-compliance-checklist.md`: setting up the OpenAI or Anthropic API for GDPR compliance, covering the data processing agreement, retention and zero data retention, logging, lawful basis, automated decision-making, transfers, the EU AI Act Article 50 transparency duties, and the documentation a procurement or DPIA reviewer will ask for, with a worked example.

### `breach-response/`
- `nigeria-ndpa-breach-response.md`: responding to a personal data breach under section 40 of the Nigeria Data Protection Act 2023, with notification templates for the Nigeria Data Protection Commission and for data subjects.

## Licence

[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).

You can use, adapt and redistribute these templates, including commercially, provided you give attribution in this form:

> Adapted from the Compliance Engineering Toolkit by Michael K. Onyekwere (Janus Compliance). https://github.com/Thezenmonster/compliance-engineering-toolkit

New templates and updates are announced in [Compliance Engineering](https://complianceengineering.substack.com).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to suggest corrections or new templates.

## Limits

**These templates are not legal advice.** They reflect structures that suit a typical AI system, and your system may need different decisions. A DPIA for a deployed system needs a risk assessment specific to its architecture and data flows; if you would like that done for you, start with a [£500 scoping review](https://www.januscompliance.co.uk/contact?intent=scoping-review&source=toolkit).

**They are not exhaustive, and the law changes.** New AI patterns and new rules, such as amendments to the EU AI Act, can change what a template needs to cover. Each document records the date its facts were last checked, and changes are announced in the newsletter.

## About Michael K. Onyekwere

CIPP/E certified data protection professional with more than ten years in compliance and data protection at Royal Bank of Scotland, Fidelity International, UnitedHealth and TMF Group, and a common law qualified lawyer (LLB, LLM). He also leads product development using AI coding tools, which informs the practical focus of these templates.

For help with a specific system:
- a one-off review: [£500 scoping review](https://www.januscompliance.co.uk/contact?intent=scoping-review&source=toolkit-readme)
- ongoing support: [DPO as a service](https://www.januscompliance.co.uk/services/dpo-as-a-service)
- AI agents: [AI agent compliance](https://www.januscompliance.co.uk/ai-agent-compliance)
