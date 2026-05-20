# AI API Compliance Checklist

**OpenAI / Anthropic DPA Setup, Zero-Retention Configuration, and Documentation Pack for GDPR Reviews**

*Version 1.0 — May 2026*

*By Michael K. Onyekwere · CIPP/E · Common Law Qualified Lawyer (LLB, LLM) · januscompliance.co.uk*

*Licensed CC BY 4.0. Attribution required when reused.*

---

## Who this is for

You are building or operating a product that calls the OpenAI API, the Anthropic API, or both, on behalf of a controller subject to GDPR, UK DPA 2018, or an equivalent regime. You need to evidence that the controller-to-processor relationship is configured correctly, that retention is bounded, and that a procurement reviewer or DPIA panel can sign off without coming back with a list of follow-ups.

This is not a discovery document. It is a setup checklist. The expected reader has already decided to use the API and needs the compliance work shipped to production.

---

## How to use this checklist

Each section has a small number of tasks. For each task: confirm the action is complete, capture the evidence, and file the evidence in the documentation pack at the back of this PDF.

The worked example at the end shows what a completed setup looks like for a hypothetical UK fintech using the OpenAI API for customer support summarisation.

---

## Part 1 — DPA scoping and execution

### 1.1 Identify the legal entity acting as controller

The controller is the legal person that determines purposes and means of processing. For most SaaS or fintech products, this is the customer-facing company entity. For multi-entity groups, confirm which entity is the controller before signing.

- [ ] Controller entity name confirmed (legal name, not trading name)
- [ ] Controller registration number captured
- [ ] Controller's registered office address captured

### 1.2 Sign the OpenAI Data Processing Addendum

OpenAI's DPA is a click-through agreement available through the OpenAI platform account at `platform.openai.com/account/data-processing-addendum`. It activates on signature and applies retroactively to API usage under the account.

- [ ] OpenAI account access confirmed (admin-level access required to sign)
- [ ] DPA signed under the correct controller legal name
- [ ] Signed DPA PDF saved to documentation pack with timestamp
- [ ] Signatory name and role recorded
- [ ] Effective date recorded

### 1.3 Sign the Anthropic Commercial Terms and DPA

Anthropic's terms are at `console.anthropic.com/legal/commercial-terms`. The DPA is incorporated by reference. The Anthropic console requires an authorised signatory to accept the terms before API keys are issued under the controller account.

- [ ] Anthropic account created under the correct controller legal name
- [ ] Commercial Terms accepted by an authorised signatory
- [ ] DPA acknowledgement screenshot or confirmation email saved
- [ ] Effective date recorded

### 1.4 Track sub-processor lists

Both OpenAI and Anthropic publish sub-processor lists that change. The DPA obliges you to monitor for changes and surface material changes to the controller's compliance function.

- [ ] OpenAI sub-processor list URL added to register: `openai.com/policies/sub-processor-list`
- [ ] Anthropic sub-processor list URL added to register: `anthropic.com/legal/subprocessors`
- [ ] Quarterly review cadence scheduled (recommend the first Monday of each quarter)
- [ ] Process for escalating new sub-processors to the DPO documented

---

## Part 2 — Zero-retention and data residency configuration

### 2.1 OpenAI zero-retention enablement

OpenAI offers Zero Data Retention (ZDR) for API customers meeting eligibility criteria. ZDR ensures prompts and completions are not stored beyond the duration of the API call. ZDR must be requested through OpenAI; it is not enabled by default.

- [ ] ZDR eligibility verified for your account tier
- [ ] ZDR request submitted via OpenAI support
- [ ] ZDR confirmation received in writing and saved to documentation pack
- [ ] ZDR effective date recorded
- [ ] If ZDR not available: 30-day default retention documented and risk-assessed against the controller's retention schedule

### 2.2 OpenAI training-data exclusion

API usage is excluded from training by default for paid accounts, but verify:

- [ ] OpenAI account settings show "Allow training" disabled (or N/A for ZDR)
- [ ] Screenshot of training-exclusion setting saved
- [ ] Internal policy document references this default

### 2.3 Anthropic data handling

Anthropic does not train its production models on customer API data per its current Commercial Terms. Confirm in writing where this is required for the documentation pack.

- [ ] Anthropic data-handling page reviewed and current version saved
- [ ] Anthropic retention default (30 days, per current terms) documented
- [ ] Where the controller requires shorter retention, raise with Anthropic enterprise support before launch

### 2.4 Data residency

Both providers expose region selection that affects where inference happens. Choose region(s) that match the controller's data residency requirements.

- [ ] OpenAI Azure deployment used where EU residency is required (Azure OpenAI Service in the EU regions)
- [ ] Anthropic region selection documented (AWS Bedrock or Anthropic API)
- [ ] Standard Contractual Clauses incorporated where data leaves the EEA / UK
- [ ] Transfer Impact Assessment (TIA) completed for any onward transfer

---

## Part 3 — Operational controls

### 3.1 Logging discipline

What you log matters as much as what the API stores. The controller's logging system can become a privacy hotspot if prompts containing personal data are persisted to log files indefinitely.

- [ ] Application logs sanitised before storage (PII redaction at write time)
- [ ] Log retention schedule documented (recommend 30 days for production traffic)
- [ ] Log access controls documented (who can read prompts, under what circumstances)
- [ ] Audit log for log access kept

### 3.2 Prompt and completion handling

Prompts may contain personal data even when you are not asking for it (free-text fields, customer support transcripts, etc.). Treat user input as personal data by default.

- [ ] Free-text user input flagged as personal data in the data map
- [ ] Sanitisation or filtering applied where the use case permits
- [ ] User-facing notice that AI is involved in processing (Article 13 / 14 obligation)
- [ ] Right to object documented where the AI processing is necessary for performance of a contract or based on legitimate interest

### 3.3 Lawful basis documented

The controller selects the lawful basis under Article 6. For most product features the basis will be contract performance, legitimate interest, or consent. Document the choice and the analysis.

- [ ] Lawful basis selected per processing purpose
- [ ] Legitimate Interest Assessment (LIA) on file if Article 6(1)(f) is the basis
- [ ] Consent capture flow documented if Article 6(1)(a) is the basis
- [ ] Special category data exclusion confirmed (Article 9) — if special category data is in scope, separate Article 9 condition required

### 3.4 Article 22 — automated decision-making

If the AI output affects the data subject's legal status or has similarly significant effects (credit, employment, insurance, denial of service), Article 22 protections apply.

- [ ] Article 22 applicability assessed
- [ ] Human-in-the-loop documented where Article 22 applies
- [ ] Right to obtain human intervention surfaced in the user-facing notice

---

## Part 4 — Documentation pack for procurement / DPIA review

A procurement reviewer or DPIA panel will typically ask for the following. Have them ready before you submit for review.

### 4.1 Vendor documentation

- [ ] Signed OpenAI DPA (PDF)
- [ ] Signed Anthropic Commercial Terms acceptance (confirmation email or screenshot)
- [ ] OpenAI sub-processor list (latest version, dated)
- [ ] Anthropic sub-processor list (latest version, dated)
- [ ] ZDR confirmation (where applicable)
- [ ] Region selection evidence (account settings screenshot)

### 4.2 Controller documentation

- [ ] DPIA (if the processing is likely to result in high risk to data subjects)
- [ ] Records of Processing Activities (RoPA) entry for this processing operation
- [ ] LIA where legitimate interest is the lawful basis
- [ ] User-facing privacy notice updated to reflect AI processing
- [ ] Internal AI usage policy

### 4.3 Operational evidence

- [ ] Log sanitisation policy and sampling evidence
- [ ] Retention schedule for prompts, completions, and derived data
- [ ] Access controls policy for the API keys and the logs
- [ ] Incident response plan covering AI-specific failure modes (prompt injection, jailbreak, output leakage)

### 4.4 Transfer documentation

- [ ] Standard Contractual Clauses (Module Two: controller to processor) — where the processor is outside the UK / EEA
- [ ] UK International Data Transfer Agreement or Addendum where required
- [ ] Transfer Impact Assessment (TIA)
- [ ] Documented onward transfers (sub-processors and their locations)

---

## Worked example: UK fintech using OpenAI for customer support summarisation

**Controller:** ExampleFintech Ltd, registered in England, registered office London EC2.

**Use case:** Live chat transcripts summarised by the OpenAI Chat Completions API to populate a CRM record after the customer support agent closes the case.

**Personal data in scope:** Customer name (where mentioned in the chat), account reference, transaction details, free-text content of the customer's message.

**Lawful basis:** Article 6(1)(f) legitimate interest. The legitimate interest is operational efficiency and quality of customer service. The LIA records the necessity test, the balancing test against data subject expectations, and the safeguards applied (sanitisation, retention limit).

**Vendor configuration:**
- OpenAI DPA signed by the ExampleFintech CFO on 12 March 2026
- ZDR enabled on the account effective 18 March 2026 (confirmation email saved)
- Azure OpenAI Service used for inference, deployed in the West Europe region
- Training opt-out confirmed (account setting)

**Operational controls:**
- Application sanitises card numbers and authentication tokens before any API call
- Application logs retain prompts for 30 days, then auto-purge
- The summary written to the CRM is the only persisted output of the API call
- User-facing notice updated to state that AI is used in support workflow

**Article 22 assessment:** the summary is used by a human agent for record-keeping, not for automated decisioning about the customer. Article 22 does not apply.

**DPIA:** not formally required (low risk profile) but a lightweight risk assessment is documented and signed off by the DPO.

**Sub-processor monitoring:** the OpenAI sub-processor list is reviewed quarterly by the privacy team. The list is appended to the DPIA file. Any new sub-processor flagged for assessment within 30 days of publication.

The above pack passes a typical financial services procurement review without follow-up questions.

---

## What this checklist does not cover

- Fine-tuning, batch inference, or assistants API usage (separate compliance considerations apply)
- Internal LLM deployments (self-hosted models have different controls)
- Image, audio, or video API endpoints (sectoral rules may apply)
- High-risk AI Act applicability (Annex III): if your use case is high-risk, a fuller AI Act conformity assessment is required
- The detailed Records of Processing Activities (RoPA) entry — see the separate RoPA template in the Compliance Engineering Toolkit

---

## About this checklist

This checklist is part of the Compliance Engineering Toolkit at `github.com/Thezenmonster/compliance-engineering-toolkit`. The toolkit is licensed CC BY 4.0 and may be reused with attribution.

For consulting on AI compliance for your specific system, see `januscompliance.co.uk/services` or write to `michael@januscompliance.co.uk`.

For the Compliance Engineering newsletter — weekly practitioner-grade AI compliance writing — see `januscompliance.co.uk/newsletter`.

---

*Michael K. Onyekwere · Janus Compliance · May 2026*
