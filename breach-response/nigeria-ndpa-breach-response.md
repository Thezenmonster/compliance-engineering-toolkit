# Breach Response Template: Nigeria (NDPA 2023)

A framework for responding to personal data breaches under section 40 of the Nigeria Data Protection Act 2023, for fintechs, software companies and any other controller processing the personal data of people in Nigeria. It is a starting point rather than legal advice, and it should be adapted to your organisation and checked against any directives the Nigeria Data Protection Commission (NDPC) has issued since the date below.

## How to use

Build this into your incident response process before a breach occurs, because the 72-hour period under section 40(2) leaves little time to design a process once one has started.

---

## When the 72-hour period starts

Under section 40(2), a controller must notify the NDPC within 72 hours of becoming aware of a breach that is likely to result in a risk to the rights and freedoms of individuals. Because the period runs from awareness rather than from the breach itself, record when each person first learned of the breach, and in what form.

Where a processor, such as a hosting or CRM provider, discovers a breach first, section 40(1) requires it, on becoming aware of the breach, to notify the controller that engaged it, describing the breach and, where possible, the categories and approximate numbers of data subjects and records affected, and to respond to the controller's requests for information. Record the time the processor's notification was received and who received it, since that is likely to be treated as the point at which the controller became aware.

---

## Phase 1: containment and scope (first hours)

| Action | Owner | Status |
|--------|-------|--------|
| Confirm whether the incident is a personal data breach rather than a security incident only | DPO and security lead | |
| Contain the breach and stop further exposure | Security lead | |
| Identify the categories of personal data affected | DPO | |
| Estimate how many data subjects and records are affected | DPO | |
| Identify whether sensitive personal data or children's data is involved | DPO | |
| Open an incident log recording every action with a timestamp | DPO | |
| Notify the DPO formally if they are not already aware | Whoever discovered the breach | |

Containment comes first, and the record of what was done and when will be important evidence if the NDPC later investigates.

---

## Phase 2: assessment

| Action | Owner | Status |
|--------|-------|--------|
| Assess whether the breach is likely to result in a risk to individuals' rights and freedoms (the section 40(2) test) | DPO | |
| If so, prepare to notify the NDPC | DPO | |
| Assess whether the breach is likely to result in a high risk (the section 40(3) test) | DPO | |
| If so, prepare to notify the affected data subjects as well | DPO | |
| Identify all processors and sub-processors involved | DPO | |
| Record the cross-border transfer position if the data left Nigeria | DPO | |
| Begin drafting the NDPC notification using the template below | DPO | |
| Begin drafting the data subject notification, if required | DPO and communications | |

In assessing risk, section 40(7) allows the controller to take into account the effectiveness of technical and organisational measures already in place, such as encryption or de-identification, any later measures that reduce the risk, and the nature, scope and sensitivity of the data.

---

## Phase 3: notification (within 72 hours of awareness)

### Notifying the NDPC (section 40(2))

The controller must notify the NDPC within 72 hours of becoming aware of the breach and, where feasible, describe the nature of the breach, including the categories and approximate numbers of data subjects and records concerned. Under section 40(4), the notification must also give the name and contact details of a point of contact from whom more information can be obtained, describe the likely consequences of the breach, and describe the measures taken or proposed to address it, including measures to mitigate its possible adverse effects.

In practice, the notification should cover:

- the nature of the breach, described plainly;
- the categories and approximate number of data subjects affected;
- the categories and approximate number of records affected, which can differ from the number of data subjects;
- the likely consequences, such as identity theft, financial fraud or reputational harm;
- the measures taken or proposed, covering containment, mitigation and prevention;
- the contact details of the DPO or other point of contact.

Where it is not possible to provide all of this information at the same time, section 40(9) allows it to be provided in phases without undue delay, so an initial notification should not be delayed while the investigation continues.

**How to file.** Use the channel the NDPC currently specifies on [ndpc.gov.ng](https://ndpc.gov.ng), whether by email or through an online portal, and confirm it is current at the time of filing.

### Notifying data subjects (section 40(3))

Where a breach is likely to result in a high risk to the rights and freedoms of data subjects, the controller must communicate the breach to them immediately, in plain and clear language, including advice on the measures they could take to mitigate its possible adverse effects. Where direct communication would involve disproportionate effort, or is otherwise not feasible, the controller may instead make a public communication through widely used media that the data subjects are likely to see. The communication must also include the information required by section 40(4) set out above.

---

## Notification template: NDPC

An email body to adapt. Replace the bracketed placeholders, and send it from the DPO's address with a copy to your senior compliance contact.

```
Subject: Personal data breach notification under section 40(2) of the NDPA 2023, [Organisation name]

To: The National Commissioner, Nigeria Data Protection Commission

Dear National Commissioner,

Pursuant to section 40(2) of the Nigeria Data Protection Act 2023,
[Organisation name] notifies the Commission of a personal data breach.

1. ORGANISATION
   Name: [Full registered name]
   Registered address: [Address]
   Point of contact: [DPO name, email, phone]

2. AWARENESS
   We became aware of the breach on [date and time].
   This notification is submitted within 72 hours of that time.

3. NATURE OF THE BREACH
   [Plain description of what happened, when it happened and how it
   was discovered.]

4. PERSONAL DATA AFFECTED
   Categories of data: [for example name, email, phone, ID number,
   financial data, health data]
   Approximate number of data subjects: [number]
   Approximate number of records: [number]
   Sensitive personal data involved: [Yes (specify) or No]

5. LIKELY CONSEQUENCES
   [The harm that could result for the individuals affected, for
   example identity theft, financial fraud or discrimination.]

6. MEASURES TAKEN OR PROPOSED
   - Containment: [steps taken to stop further exposure]
   - Mitigation: [steps taken to reduce harm to the individuals]
   - Investigation: [scope and current status]
   - Prevention: [planned steps to prevent recurrence]

7. DATA SUBJECT NOTIFICATION
   We have assessed the breach against the high-risk test in
   section 40(3) and concluded that communication to data subjects is:
   [Required, and being made as of (date), OR not required, because
   (reasons)]

8. FURTHER INFORMATION
   This notification contains the information available at this time.
   In accordance with section 40(9), we will provide further information
   in phases as our investigation proceeds.

   Cross-border transfer position: [If data left Nigeria, the transfer
   mechanism and safeguards.]

We remain available to assist the Commission.

Yours faithfully,

[DPO name]
Data Protection Officer
[Organisation name]
[Email] / [Phone]
```

---

## Notification template: data subjects (high-risk breaches)

```
Subject: Important information about the security of your [Service name] account

Dear [First name or "Customer"],

We are writing to tell you about a security incident that has
affected some of our customers' personal data, including yours.

WHAT HAPPENED
[Two or three sentences in plain language.]

WHAT INFORMATION WAS INVOLVED
[The specific categories of data.]

WHAT WE ARE DOING
- [Containment step]
- [Containment step]
- [What we have done to protect you specifically]

WHAT YOU CAN DO
- [A specific protective step, for example changing your password]
- [A specific protective step, for example checking your statements]
- [Where to get help if you think you have been affected]

WHO TO CONTACT
If you have any questions, please contact our Data Protection Officer:
[DPO name]
[Email]
[Phone]

You can also contact the Nigeria Data Protection Commission at
https://ndpc.gov.ng if you have concerns about how your personal
data has been handled.

We are sorry that this has happened.

[Name and title of a senior authorised person]
[Organisation name]
```

---

## Records to keep

Section 40(8) requires controllers and processors to keep a record of all personal data breaches, setting out the facts, the effects and the remedial action taken, in a way that allows the NDPC to verify compliance with section 40. The record should include:

- when each named person became aware of the breach;
- the containment steps taken, with timestamps;
- each threshold decision (whether the breach was notifiable, and whether it was high risk), who took it and on what evidence;
- drafts, approvals, sent versions and confirmations of every notification;
- how the breach was escalated internally;
- the post-incident review and any process changes that followed.

The Act does not set a retention period for these records, so retain them in line with your retention policy and any longer period required by a sector regulator, such as the Central Bank of Nigeria for financial services.

---

## Common difficulties

**Approval when time is short.** If internal policy requires a senior executive to approve a regulatory notification, the 72-hour period can be lost while that person is unavailable. Authorising the DPO in advance to file statutory notifications within their deadline avoids this.

**Waiting for certainty.** Because section 40(9) allows information to be provided in phases, waiting for the full picture before notifying is not necessary, and it puts the 72-hour deadline at risk. Notify what is known and update the NDPC as the investigation develops.

**A growing scope.** The number of people affected often rises as an investigation continues, and the NDPC should be updated when it does rather than left with the original estimate.

**Breaches at a processor.** Where a processor causes the breach, the controller remains responsible for notifying the NDPC under section 40(2). The written agreement with the processor, which section 29(2) requires, should require prompt notification and cooperation so that the controller can meet its own deadline.

**Tone of the data subject notice.** Section 40(3) requires plain and clear language and advice on what people can do to protect themselves, so the notice should explain the impact and the protective steps directly rather than in general reassurances.

---

## When to seek external advice

Many breaches can be handled in-house by an organisation that has prepared. External advice is advisable where:

- the breach raises cross-border transfer questions you have not planned for;
- children's data is involved;
- a large number of people is affected;
- the organisation is already the subject of NDPC scrutiny for another matter;
- a sector regulator also requires notification, since its deadline may be shorter than the NDPA's. For example, the Nigerian Communications Commission's Internet Code of Practice 2026 is reported to require internet access service providers to notify it and affected consumers within 48 hours, so check the current text of any sector rules that apply to you.

---

*Template by Michael K. Onyekwere, [Janus Compliance](https://www.januscompliance.co.uk). Part of the [Compliance Engineering Toolkit](https://github.com/Thezenmonster/compliance-engineering-toolkit). New templates and updates are announced in [Compliance Engineering](https://complianceengineering.substack.com). Licensed CC BY 4.0; attribution required on reuse.*

*Sources: Nigeria Data Protection Act 2023, sections 29(2) and 40 (official gazette text, checked 4 October 2026). The NCC Internet Code of Practice 2026 reference is from secondary reporting (Mondaq, 1 July 2026) and should be checked against the Code itself.*
