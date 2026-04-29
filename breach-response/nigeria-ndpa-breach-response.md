# Breach Response Template — Nigeria (NDPA 2023)

A response framework for personal data breaches under the Nigeria Data Protection Act 2023, Section 40. Built for fintechs, SaaS companies, and any controller processing Nigerian residents' personal data.

This isn't legal advice. It's the structure I use when delivering breach response work for clients — adapt it to your specific business.

## How to use

Build this into your incident response process before you need it. Print it. Pin it. The 72-hour clock under NDPA Section 40(2) does not wait for you to figure out what to do.

---

## The trigger — when the clock starts

The NDPA Section 40(2) clock starts when a controller becomes **aware** of a breach likely to result in a risk to the rights and freedoms of individuals.

"Aware" is not "happened." Document the moment of awareness — who knew first, when, in what form.

If a processor (e.g. CRM vendor, hosting provider) discovered the breach first, Section 40(1) obliges them to notify you. Your clock starts when their notification reaches someone with authority to act, not when they hit send.

---

## Phase 1: First 4 hours — containment and scope

| Action | Owner | Status |
|--------|-------|--------|
| Confirm the incident is a personal data breach (not just a security incident) | DPO + Security Lead | |
| Contain the breach — stop further data exposure | Security Lead | |
| Identify what personal data is affected (categories) | DPO | |
| Identify approximately how many data subjects affected | DPO | |
| Identify whether special category data is involved (health, biometric, children) | DPO | |
| Open the incident log — timestamped record of every action | DPO | |
| Notify your DPO formally if not already aware | Whoever discovered | |

Containment first. Notification second. The NDPC will look at containment evidence in any subsequent investigation.

---

## Phase 2: Hours 4-24 — assessment

| Action | Owner | Status |
|--------|-------|--------|
| Assess whether the breach is "likely to result in a risk to the rights and freedoms of individuals" — Section 40(2) threshold | DPO | |
| If yes: NDPC notification is required | DPO | |
| Assess whether the breach is "likely to result in a high risk" — Section 40(3) threshold | DPO | |
| If yes: data subject notification is also required | DPO | |
| Identify all affected processors and sub-processors | DPO | |
| Document the cross-border transfer position (if data left Nigeria) | DPO | |
| Begin drafting NDPC notification using the template below | DPO | |
| Begin drafting data subject notification (if applicable) | DPO + Communications | |

---

## Phase 3: Hours 24-72 — notification

### NDPC notification (Section 40(2)) — required within 72 hours of awareness

The notification must include:

- **Nature of the personal data breach** — what happened, plainly
- **Categories of data subjects affected** — customers, employees, beneficiaries, etc.
- **Approximate number of data subjects affected**
- **Categories of personal data records affected** — names, contact details, financial, health, identity documents
- **Approximate number of personal data records affected** (different from data subjects — one subject can have many records)
- **Likely consequences of the breach** — identity theft, financial fraud, reputational harm
- **Measures taken or proposed to address the breach** — containment, mitigation, prevention going forward
- **Contact details of the DPO** — or person handling response

If you cannot provide all of the above within 72 hours, send what you have and update the NDPC as you learn more. NDPA Section 40(2) does not penalise partial reporting; it penalises silence.

**Filing channel.** Email to the NDPC at the address listed on [ndpc.gov.ng](https://ndpc.gov.ng) plus, where applicable, any portal the NDPC has activated. Confirm the receiving address is current at time of filing — NDPC channels evolve.

### Data subject notification (Section 40(3)) — if high risk

Required when the breach is likely to result in a **high risk** to the rights and freedoms of data subjects. Must include:

- A description of the nature of the breach
- The DPO's contact details
- The likely consequences
- The measures being taken in response

The notification must be communicated to data subjects "immediately." Direct, written-tone, in plain language. Avoid corporate hedging — the NDPC has been explicit that data subject communication should serve the subject, not the controller's brand.

---

## Notification template — NDPC

A pre-drafted email body. Replace bracketed placeholders. Send from your DPO's address with cc to your senior compliance contact.

```
Subject: NDPA Section 40(2) Breach Notification — [Your Organisation Name]

To: The Commissioner, Nigeria Data Protection Commission

Dear Commissioner,

Pursuant to Section 40(2) of the Nigeria Data Protection Act 2023,
[Your Organisation Name] hereby notifies the Commission of a
personal data breach.

1. ORGANISATION
   Name: [Full registered name]
   Registered address: [Address]
   DPO contact: [DPO name, email, phone]

2. AWARENESS TIMESTAMP
   The breach came to our attention on [date and time].
   This notification is being submitted within 72 hours of awareness.

3. NATURE OF THE BREACH
   [Plain language description: what happened, when it happened,
   how it was discovered.]

4. PERSONAL DATA AFFECTED
   Categories of data: [name, email, phone, ID number, financial data,
   health data, etc.]
   Approximate number of data subjects: [number]
   Approximate number of records: [number]
   Special category data involved: [Yes — specify / No]

5. LIKELY CONSEQUENCES
   [What harm could result for affected individuals — identity theft,
   financial fraud, discrimination risk, physical safety, etc.]

6. MEASURES TAKEN OR PROPOSED
   - Containment: [steps taken to stop further exposure]
   - Mitigation: [steps taken to reduce harm to affected individuals]
   - Investigation: [scope and current status]
   - Prevention: [planned steps to prevent recurrence]

7. DATA SUBJECT NOTIFICATION
   We have assessed the breach against the Section 40(3) high-risk
   threshold and determined that direct notification of data subjects is:
   [Required — being communicated as of (date) / Not required — reasoning]

8. ADDITIONAL INFORMATION
   This notification is being submitted with the information available
   at this time. We undertake to provide the Commission with further
   information as the investigation proceeds.

   Cross-border transfer position: [If data left Nigeria, describe the
   transfer mechanism and any safeguards.]

We remain available to assist the Commission's review.

Yours faithfully,

[DPO Name]
Data Protection Officer
[Your Organisation Name]
[Email] | [Phone]
```

---

## Notification template — data subjects (high-risk breaches)

```
Subject: Important security update about your [Service Name] account

Dear [First Name or "Customer"],

We are writing to let you know about a security incident affecting
some of our customer data, including yours.

WHAT HAPPENED
[2-3 sentences. Plain English. No jargon.]

WHAT INFORMATION WAS INVOLVED
[Specific list of data categories.]

WHAT WE ARE DOING
- [Containment action 1]
- [Containment action 2]
- [What we have done to protect you specifically]

WHAT YOU CAN DO
- [Specific protective action 1, e.g. change password]
- [Specific protective action 2, e.g. monitor statements]
- [Where to get help if you believe you've been affected]

WHO TO CONTACT
For any questions, please contact our Data Protection Officer:
[DPO Name]
[Email]
[Phone]

You also have the right to contact the Nigeria Data Protection
Commission at https://ndpc.gov.ng if you have concerns about how
your personal data has been handled.

We take this seriously. We are sorry this has happened.

[Senior Authorised Person, not just DPO]
[Your Organisation Name]
```

---

## What to document throughout

The NDPC may investigate even after notification. The records they will look at:

- Awareness log — when each named individual learned of the breach
- Containment evidence — technical actions taken, with timestamps
- Decision log — every threshold decision (notifiable yes/no, high-risk yes/no), who made it, on what evidence
- Communications log — drafts, sign-offs, sent versions, recipient confirmations
- Internal escalation evidence — that the breach was raised through proper channels in the right timeframe
- Post-incident review — what was learned, what process changes followed

Keep these records for at least 3 years after the incident. Some sectoral regulators (CBN for fintechs) may require longer retention.

---

## Things that go wrong in real responses

These are patterns from real client work. Build your process to avoid them.

**The procurement delay.** Breach is contained, DPO is ready to file, NDPC notification needs to go in 4 hours. The CEO has to sign off because that's the policy. The CEO is on a flight. Pre-authorise your DPO to file without escalation for time-bounded statutory notifications.

**The investigation paralysis.** "We need certainty before we report." The NDPC explicitly accepts partial reporting under Section 40(2). File what you know, update as you learn. Waiting for certainty is how you miss the 72-hour window.

**The wrong scope.** Initial assessment said 4,500 affected. Actual count grows to 40,000 over the following week. The NDPC accepts revised numbers; what they don't accept is silence after you knew the number had grown.

**The processor blame game.** Your CRM provider lost the data, but you're the controller — the NDPC notifies and fines the controller, then leaves you to recover from your processor under contract. Build your DPAs (Section 27 NDPA) to make recovery actually possible.

**The "we regret to inform you" data subject email.** Customers see straight through corporate hedging. The NDPC has signalled in subsequent guidance that data subject notification should be clear about impact, not soft about brand. Match the tone of a clear public service notice, not a marketing email.

---

## When to bring in external help

Self-build this template into your existing incident response. For most breaches, you can run the response in-house if you've prepared.

You probably need external counsel if:
- The breach involves cross-border transfer issues you haven't planned for
- The breach involves children's data
- The numbers are large (10,000+ data subjects)
- You're already under NDPC scrutiny for unrelated reasons
- Your sector regulator (CBN, NCC) overlaps and you need to coordinate filings

---

*Template by Michael K. Onyekwere — [Janus Compliance](https://www.januscompliance.co.uk). Part of the [Compliance Engineering Toolkit](https://github.com/Thezenmonster/compliance-engineering-toolkit). Subscribe to [Compliance Engineering](https://complianceengineering.substack.com) for new patterns and updates. CC BY 4.0 — attribution required when reused.*

*Sources: Nigeria Data Protection Act 2023, Section 40. NDPC published enforcement actions and guidance.*
