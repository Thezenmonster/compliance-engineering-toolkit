# Compliance Engineering Toolkit

Open-source DPIA templates, privacy notice patterns, conformity assessment frameworks, and vendor due diligence checklists for AI systems.

By **Michael K. Onyekwere**, CIPP/E certified data protection professional. Founder of [Janus Compliance](https://www.januscompliance.co.uk). Writes [Compliance Engineering](https://complianceengineering.substack.com), practical AI compliance for engineers and founders.

## What this is

A collection of working compliance documents you can use, adapt, or fork when building AI systems. Each template is the structure I actually use when delivering consulting work, redacted of client specifics, kept current with regulatory changes.

These aren't legal advice. They're starting points. Use them, adapt them, ship faster.

## What's here

### `dpia-templates/`
Data Protection Impact Assessment templates for common AI patterns:
- `chatbot.md`: customer-facing chatbots using LLM APIs
- `rag-system.md`: retrieval-augmented generation over private documents *(coming)*
- `agent.md`: autonomous AI agents using tools (MCP, function calling)
- `document-processor.md`: automated document processing and extraction *(coming)*

### `breach-response/`
Breach response templates and notification frameworks:
- `nigeria-ndpa-breach-response.md`: Nigeria Data Protection Act 2023 (Section 40) breach response, notification templates, and process patterns

### `privacy-notice-updates/`
Before/after examples of how privacy notices change when AI is added to a system:
- `ai-chatbot-update.md`: updating a privacy notice for a customer-facing chatbot
- `agent-system-update.md`: updating for an autonomous agent (more complex)
- `rag-private-data.md`: when AI processes documents containing personal data

### `conformity-assessment/`
EU AI Act conformity assessment templates:
- `high-risk-conformity-assessment.md`: full Annex IV documentation structure
- `risk-management-system.md`: Article 9 risk management system template
- `human-oversight.md`: Article 14 human oversight design template

### `vendor-due-diligence/`
Vendor evaluation frameworks:
- `ai-vendor-checklist.md`: comprehensive AI provider due diligence
- `mcp-tool-evaluation.md`: evaluating MCP tools an agent might use
- `data-processor-questionnaire.md`: Article 28 questionnaire for AI vendors

## License

[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).

You can use, adapt, and redistribute these templates, including commercially, provided you give attribution. The required attribution is:

> Adapted from the Compliance Engineering Toolkit by Michael K. Onyekwere (Janus Compliance). https://github.com/janus-compliance/compliance-engineering-toolkit

If you find this useful, the best thanks is to subscribe to [Compliance Engineering](https://complianceengineering.substack.com), the weekly newsletter where I publish new patterns and update existing ones.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to suggest improvements or add new templates.

## A note on what these are not

**Not legal advice.** These templates reflect compliance patterns that work for the typical AI system. Your specific situation may need different decisions. If you need a DPIA written for your actual deployed system, with a real risk assessment specific to your architecture and data flows, that's a paid engagement. Start with a [£500 scoping review](https://www.januscompliance.co.uk/contact?intent=scoping-review&source=toolkit).

**Not exhaustive.** The AI compliance field is moving fast. New patterns appear (agents, multimodal models, on-device LLMs) and new regulations land (EU AI Act amendments, sectoral rules). I update these when the underlying landscape changes. Watch the repo or subscribe to the newsletter for change notifications.

## About Michael K. Onyekwere

CIPP/E certified data protection professional. 10+ years across Royal Bank of Scotland, Fidelity, TMF Group, and UnitedHealth, doing financial services and corporate compliance at enterprise scale. Common law qualified lawyer (LLB, LLM).

Now building AI systems and writing the compliance documentation alongside them. Founder of [Janus Compliance](https://www.januscompliance.co.uk). Author of [Compliance Engineering](https://complianceengineering.substack.com), the weekly newsletter on practical AI compliance for engineers and founders.

If you need direct help with an AI compliance question:
- For one-off systems: [book a £500 scoping review](https://www.januscompliance.co.uk/contact?intent=scoping-review&source=toolkit-readme)
- For ongoing support: [DPO-as-a-Service](https://www.januscompliance.co.uk/services/dpo-as-a-service) on a monthly retainer
- For agent-specific questions: see [AI Agent Compliance](https://www.januscompliance.co.uk/ai-agent-compliance)
