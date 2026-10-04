# AI API Compliance Checklist

**Setting up the OpenAI and Anthropic APIs for GDPR compliance: data processing agreements, retention, zero data retention, documentation and the EU AI Act transparency duties**

*Version 1.4.1: October 2026. Provider terms checked 2 to 4 October 2026 unless stated otherwise.*

*By Michael K. Onyekwere · CIPP/E · Common Law Qualified Lawyer (LLB, LLM) · januscompliance.co.uk*

*Licensed CC BY 4.0. Attribution required on reuse.*

---

## Who this is for

This checklist is for organisations building or operating a product that calls the OpenAI API, the Anthropic API or both, on behalf of a controller subject to the EU GDPR, the UK GDPR or an equivalent regime. It assumes the decision to use the API has been made, and it covers the work needed to show that the processor relationship is set up correctly, that retention is limited, and that a procurement reviewer or DPIA panel has the evidence it needs.

---

## How to use this checklist

Each section contains a small number of tasks. For each one, confirm the action is complete, capture the evidence, and file it in the documentation pack described in Part 4. The worked example at the end shows a completed setup for a fictional UK fintech using the OpenAI API to summarise customer support conversations.

---

## Part 1: Data processing agreements

### 1.1 Identify the controller

The controller is the legal person that determines the purposes and means of the processing. For most products this is the customer-facing company, but in a group of companies the controlling entity should be confirmed before any terms are accepted.

- [ ] Controller's legal name confirmed (not a trading name)
- [ ] Controller's registration number recorded
- [ ] Controller's registered office recorded

### 1.2 OpenAI Data Processing Addendum

OpenAI's Data Processing Addendum, published at `openai.com/policies/data-processing-addendum`, was updated on 1 December 2025 and took effect on 1 January 2026. It is incorporated into the OpenAI Services Agreement, which a business customer accepts by agreeing to it, by accepting an order form or by using the services. Customers based in the EEA or Switzerland contract with OpenAI Ireland Ltd and other customers with OpenAI OpCo, LLC. The DPA page also provides a link to execute the DPA, which is worth using so that you hold a signed record.

- [ ] Business account confirmed (there is no DPA for consumer ChatGPT)
- [ ] Contracting OpenAI entity recorded
- [ ] DPA executed through the DPA page, and the signed copy saved with the date
- [ ] Signatory name and role recorded

### 1.3 Anthropic Commercial Terms and DPA

Anthropic's Data Processing Addendum is incorporated into its Commercial Terms of Service (`anthropic.com/legal/commercial-terms`), so accepting the Commercial Terms also accepts the DPA. In the version checked, dated 24 February 2025, the contracting entity for customers in the EEA, Switzerland or the UK is Anthropic Ireland, Limited, the governing law is Irish law, and the DPA incorporates the Standard Contractual Clauses with the UK and Swiss addenda.

- [ ] Account opened under the controller's legal name
- [ ] Commercial Terms accepted by an authorised person
- [ ] Record of acceptance saved (confirmation email or screenshot)
- [ ] Effective date recorded

### 1.4 Sub-processor lists

Both providers publish sub-processor lists that change over time. OpenAI's DPA requires it to notify changes and gives customers 30 days from notice to object. Anthropic's DPA requires reasonable notice of a new sub-processor and gives customers 15 days from that notice to object on reasonable data privacy or security grounds.

- [ ] OpenAI list recorded: `platform.openai.com/subprocessors`
- [ ] Anthropic list recorded: `anthropic.com/subprocessors`
- [ ] Notifications of changes subscribed to, where the provider offers them
- [ ] Review scheduled at least quarterly
- [ ] Process for escalating new sub-processors to the DPO recorded

---

## Part 2: Retention, training and data residency

### 2.1 OpenAI retention and zero data retention

By default, OpenAI generates abuse monitoring logs for API usage and retains them for up to 30 days, unless longer retention is required by law or is reasonably necessary to protect its services or third parties. Zero Data Retention and Modified Abuse Monitoring, which exclude customer content from those logs, are available to eligible customers only with OpenAI's prior approval and acceptance of additional requirements.

- [ ] Eligibility for Zero Data Retention or Modified Abuse Monitoring checked
- [ ] Request submitted, and approval received in writing and saved
- [ ] Effective date recorded
- [ ] Where neither is available: the 30-day default recorded and assessed against the controller's retention schedule

### 2.2 OpenAI training

OpenAI states that, since 1 March 2023, data sent to the API has not been used to train or improve its models unless the customer explicitly opts in to share it.

- [ ] Confirmed that no data-sharing opt-in is enabled for the organisation
- [ ] OpenAI's statement saved with the date, for the documentation pack

### 2.3 Anthropic retention, zero data retention and training

Anthropic's Commercial Terms state that it may not train models on customer content. Anthropic describes its retention in two places, which should be recorded separately: its Privacy Center states that API inputs and outputs are deleted within 30 days of receipt or generation, subject to exceptions, while its developer documentation states that conversation content is not retained by default, except for covered models. Content flagged by its trust and safety systems may be kept for up to two years, even under zero data retention. Zero data retention is available with Anthropic's approval and does not cover several features, including batch processing, the Files API, code execution and the MCP connector. Claude Fable 5.1, Mythos 5.1, Fable 5 and Mythos 5 are covered models, retained for at least 30 days, and Anthropic's Service Specific Terms state that its right to retain and review covered-model data supersedes zero data retention commitments (checked 4 October 2026).

- [ ] Anthropic's retention and training position saved with the date
- [ ] Models in use checked against the covered-model list
- [ ] Zero data retention requested where the data warrants it, and confirmation saved

### 2.4 Data residency and transfers

Neither OpenAI nor Anthropic has an entry on the EU-US Data Privacy Framework register (checked 4 October 2026). Anthropic's DPA incorporates the Standard Contractual Clauses with the UK and Swiss addenda. OpenAI's DPA treats UK data, processed by OpenAI OpCo, LLC under the Standard Contractual Clauses as amended by the UK Addendum, differently from EEA and Swiss data, which OpenAI Ireland Limited transfers onward under agreements containing the Standard Contractual Clauses or an adequacy decision.

On processing location, Anthropic's own API runs inference in any available geography by default, or only in the US on request, stores data at rest in the US and offers no EU option. OpenAI offers EU data residency to eligible customers through `eu.api.openai.com`, subject to approval, abuse-monitoring controls and a Modified Retention amendment. Where Claude processing needs to stay in Europe, the route is a cloud platform, and on Amazon Bedrock it depends on the model: Claude Opus 5 and Sonnet 5 run in-Region in Ireland and Stockholm, and Sonnet 5 also in London, while Claude Fable 5, Fable 5.1 and Mythos 5.1 are available in the EU Regions only through global routing (checked 4 October 2026). On a cloud platform the cloud provider is generally the processor, but Anthropic's Service Specific Terms provide that it processes covered-model data under its own DPA.

- [ ] Processing location recorded for each provider and model
- [ ] Transfer mechanism recorded (Standard Contractual Clauses with the UK Addendum, or the cloud provider's terms)
- [ ] Transfer impact assessment completed
- [ ] Onward transfers to sub-processors recorded

---

## Part 3: Operational controls

### 3.1 Logging

The controller's own logs can become the largest privacy risk if prompts containing personal data are kept indefinitely.

- [ ] Personal data removed or redacted from application logs before storage
- [ ] Log retention period set and recorded
- [ ] Access to logs restricted, with the access rules recorded
- [ ] Access to logs itself logged

### 3.2 Prompts and outputs

Prompts can contain personal data even when it is not requested, for example in free-text fields or support transcripts, so user input should be treated as personal data by default.

- [ ] Free-text input recorded as personal data in the data map
- [ ] Filtering or minimisation applied where the use case allows
- [ ] Privacy notice explains that AI is used in the processing (Articles 13 and 14)
- [ ] Right to object addressed where the processing relies on legitimate interests

### 3.3 Lawful basis

The controller chooses the lawful basis under Article 6 for each purpose, usually performance of a contract, legitimate interests or consent, and records the analysis.

- [ ] Lawful basis recorded for each purpose
- [ ] Legitimate interests assessment on file where Article 6(1)(f) is relied on
- [ ] Consent process recorded where Article 6(1)(a) is relied on
- [ ] Special category data identified, with an Article 9 condition recorded where it is in scope

### 3.4 Automated decision-making (EU Article 22 and UK Articles 22A to 22D)

Where an AI output is used to make a decision about a person based solely on automated processing, with legal or similarly significant effects, such as on credit, employment, insurance or access to a service, the automated decision-making rules apply. Under the EU GDPR this is Article 22. Under the UK GDPR, the Data (Use and Access) Act 2025 replaced Article 22 with Articles 22A to 22D from 5 February 2026, which permit such decisions subject to safeguards: the person must be given information about the decision, be able to make representations, be able to obtain human intervention and be able to contest the decision. Stricter limits continue to apply where the decision is based on special category data.

- [ ] Applicability assessed under EU Article 22 and UK Articles 22A to 22D
- [ ] For UK solely automated significant decisions: the four safeguards in place
- [ ] Review by a person, with authority to change the outcome, recorded where it is relied on
- [ ] Right to obtain human intervention explained in the privacy notice
- [ ] Decisions based on special category data checked against the stricter conditions

---

## Part 4: Documentation pack for procurement or DPIA review

A procurement reviewer or DPIA panel will usually ask for the following, so have it ready before submitting the system for review.

### 4.1 Provider documents

- [ ] Signed OpenAI DPA, or record of acceptance of the Services Agreement
- [ ] Record of acceptance of Anthropic's Commercial Terms
- [ ] Current sub-processor lists for each provider, dated
- [ ] Zero data retention approvals, where applicable
- [ ] Evidence of processing region (account or platform settings)

### 4.2 Controller documents

- [ ] DPIA, where the processing is likely to result in a high risk
- [ ] Entry in the records of processing activities
- [ ] Legitimate interests assessment, where relevant
- [ ] Updated privacy notice
- [ ] Internal policy on the use of AI

### 4.3 Operational evidence

- [ ] Log redaction policy and evidence from sample checks
- [ ] Retention schedule for prompts, outputs and derived data
- [ ] Access controls for API keys and logs
- [ ] Incident response plan covering AI-specific failures, such as prompt injection and disclosure of data in outputs

### 4.4 Transfer documents

- [ ] Standard Contractual Clauses (Module Two, controller to processor) where the processor is outside the UK or EEA
- [ ] UK International Data Transfer Agreement or UK Addendum where required
- [ ] Transfer impact assessment
- [ ] Onward transfers to sub-processors and their locations

---

## Part 5: EU AI Act Article 50 transparency duties (applying since 2 August 2026)

Where the API powers a chatbot that interacts with people or generates content, the EU AI Act's transparency duties have applied since 2 August 2026 alongside the GDPR, wherever Article 2 brings the system or its output within scope. Which duties apply depends on your role for each system. The provider is the party that develops the system, or has it developed, and places it on the market or puts it into service under its own name or trademark; the deployer is the party that uses it in a professional context. Branding a supplier's tool does not by itself make you the provider, although having a system developed for you and running it under your own name does. The free [Article 50 Duty Mapper](https://www.januscompliance.co.uk/tools/article-50-duty-mapper) maps the role, duties and dates for each system.

### 5.1 Role classification

- [ ] Each AI system classified as provider or deployer, with the reasoning recorded
- [ ] White-labelling and substantial modification checked, since either can make you a provider
- [ ] EU reach confirmed: the Act applies to non-EU businesses whose systems or outputs are used in the EU

### 5.2 Disclosure for systems that interact with people (Article 50(1), a provider duty)

- [ ] System designed so that people are told they are interacting with AI, at the latest at their first interaction
- [ ] The exemption for cases obvious to a reasonably well-informed, observant and circumspect person relied on only with recorded reasoning
- [ ] Deployers of a supplier's chatbot: disclosure checked in your own deployment, and the provider's Article 50 position obtained in writing

### 5.3 Machine-readable marking of generated content (Article 50(2), a provider duty)

- [ ] Outputs marked in a machine-readable format and detectable as artificially generated, so far as technically feasible
- [ ] Systems placed on the market before 2 August 2026: marking in place by 2 December 2026, under the transitional period introduced by the Digital Omnibus, which covers the marking duty only
- [ ] Systems placed on the market from 2 August 2026: marking from the start

### 5.4 Labelling of content (Article 50(4), deployer duties)

- [ ] Deepfakes, meaning realistic AI-generated or manipulated images, audio or video, labelled as artificially generated or manipulated
- [ ] AI-generated text published to inform the public on matters of public interest labelled, unless it has undergone human review and a person holds editorial responsibility for its publication
- [ ] Any labelling icon used treated as presentation only, since using an icon does not by itself discharge the duty

### 5.5 Emotion recognition

- [ ] No emotion recognition used on staff or students, which Article 5(1)(f) has prohibited since 2 February 2025; the Commission's guidelines read "workplace" broadly enough to include recruitment, so job candidates are covered
- [ ] Emotion recognition used on customers, such as sentiment analysis in a call centre, assessed before deployment against the disclosure duty in Article 50(3)

Fines for breaches of the transparency duties can reach €15 million or 3% of worldwide annual turnover, and for prohibited practices €35 million or 7%. The Digital Omnibus amending the AI Act's timetable was published in the Official Journal as Regulation (EU) 2026/1744 on 24 July 2026 and entered into force on 27 July 2026.

---

## Worked example: a UK fintech using OpenAI to summarise support conversations

**Controller:** ExampleFintech Ltd, a fictional company registered in England.

**Use case:** live chat transcripts are summarised through the OpenAI API to populate a CRM record once the support agent closes the case.

**Personal data in scope:** the customer's name where mentioned, account reference, transaction details and the free-text content of the customer's messages.

**Lawful basis:** legitimate interests (Article 6(1)(f)), namely efficient and consistent customer service. The legitimate interests assessment records the necessity test, the balancing test against customers' expectations, and the safeguards applied, including filtering and limited retention.

**Provider configuration:**
- OpenAI Services Agreement accepted, and the DPA executed through the DPA page by the company's CFO on 12 March 2026
- Zero Data Retention approved for the organisation on 18 March 2026, with the approval saved
- confirmed that no data-sharing opt-in is enabled
- transfer recorded as relying on the Standard Contractual Clauses with the UK Addendum, with a transfer impact assessment on file

**Operational controls:**
- card numbers and authentication tokens removed before any API call
- application logs keep prompts for 30 days and then delete them automatically
- the summary written to the CRM is the only stored output of the API call
- privacy notice updated to explain that AI is used in the support process

**Automated decision-making:** the summary is used by a person for record-keeping and no decision about the customer is made from it automatically, so neither UK Articles 22A to 22D nor EU Article 22 applies.

**DPIA:** the company screened the processing against the ICO's criteria and recorded its reasons for concluding that a full DPIA was not required, with a risk assessment signed off by the DPO. A controller reaching a different conclusion on its own facts would complete a full DPIA.

**Sub-processors:** the privacy team reviews OpenAI's sub-processor list quarterly and assesses any new sub-processor within the 30-day objection period.

---

## Outside the scope of this checklist

- Fine-tuning, batch processing and assistant features, which raise separate considerations
- Self-hosted models, which need different controls
- Image, audio and video endpoints, where sector rules may also apply
- High-risk systems under the EU AI Act, which need a fuller conformity assessment; under the Digital Omnibus, the obligations for Annex III high-risk systems apply from 2 December 2027, and for high-risk AI in products covered by Annex I from 2 August 2028

---

## More from Janus Compliance

**The Article 50 Duty Mapper (free).** Answer a few questions about your AI systems to see your role, duties and dates, including the 2 December 2026 marking deadline. `januscompliance.co.uk/tools/article-50-duty-mapper`

**The Compliance Engineering newsletter.** Analysis of AI regulation for engineering and compliance teams, checked against primary sources. `complianceengineering.substack.com`

**The Article 50 compliance check.** A fixed-fee (£250) written review of your AI systems against each Article 50 duty, covering your role for each system, the exemptions available and what to address first, delivered within 72 hours. `januscompliance.co.uk/services/eu-ai-act-compliance`

---

## About this checklist

This checklist is part of the Compliance Engineering Toolkit at `github.com/Thezenmonster/compliance-engineering-toolkit`, licensed CC BY 4.0 for reuse with attribution. For advice on a specific system, see `januscompliance.co.uk/services` or write to `michaelo@januscompliance.co.uk`.

---

*Michael K. Onyekwere · Janus Compliance · October 2026*
