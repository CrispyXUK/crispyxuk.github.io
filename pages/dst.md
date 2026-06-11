---
layout: page
title: "Assessments"
permalink: /dst/
toc: true
---

NHS Decision Support Tool (MDT meeting 29 August 2025, ICB Ref BC70014) and all six Council CHC Checklists. Only DST Section 2 has been disclosed — Section 1 and MDT narrative reasoning have not been provided.
{: .lead}

<div class="strand-note"><strong>Issues evidenced here:</strong> Issues <a href="{{ '/issues/' | relative_url }}#issue-15">15</a>–<a href="{{ '/issues/' | relative_url }}#issue-17">17</a> (DST domain scoring directly contradicted by care plan and Waterlow data); Issues <a href="{{ '/issues/' | relative_url }}#issue-7">7</a>, <a href="{{ '/issues/' | relative_url }}#issue-36">36</a>–<a href="{{ '/issues/' | relative_url }}#issue-37">37</a> (incorrect age and address on all Council checklists); Issue <a href="{{ '/issues/' | relative_url }}#issue-1">1</a> (no CHC referral for two years despite nursing home placement); Issues <a href="{{ '/issues/' | relative_url }}#issue-54">54</a>–<a href="{{ '/issues/' | relative_url }}#issue-55">55</a> (EPUT's independent referral duty under NF para 6.4 unexercised; MDT composition not disclosed).</div>

<div class="cat-jump">
  <a href="#assessments">Assessments</a>
  <a href="#overview">Overview</a>
  <a href="#smoking-guns">Key Evidence Points</a>
  <a href="#assessor-pattern">Assessor Pattern</a>
  <a href="#procedural">Procedural Violations</a>
  <a href="#financial">Financial Impact</a>
  <a href="#questions">Key Questions</a>
  <a href="#status">Status</a>
</div>

---

## Assessments {#assessments}

{% assign sorted_assessments = site.assessments | sort: "date" %}
<table>
  <thead>
    <tr>
      <th>Assessment</th>
      <th>Date</th>
      <th>Assessor</th>
      <th class="tc">A*</th>
      <th class="tc">A</th>
      <th class="tc">B</th>
      <th class="tc">C</th>
      <th>Outcome</th>
      <th>Integrity</th>
    </tr>
  </thead>
  <tbody>
    {% for assessment in sorted_assessments %}
    <tr{% if assessment.integrity == 'yes' %} class="red"{% elsif assessment.integrity == 'partial' %} class="amber"{% elsif assessment.integrity == 'confirm' %} class="row-confirm"{% endif %}>
      <td><strong><a href="{{ assessment.url | relative_url }}">{{ assessment.title }}</a></strong></td>
      <td class="nowrap">{{ assessment.stated }}</td>
      <td><small>{{ assessment.assessor }}</small></td>
      <td class="tc">{{ assessment.totals.a-star }}</td>
      <td class="tc">{{ assessment.totals.a }}</td>
      <td class="tc">{{ assessment.totals.b }}</td>
      <td class="tc">{{ assessment.totals.c }}</td>
      <td>
        {% if assessment.outcome contains "MET" or assessment.outcome contains "Eligible" %}
          <span class="outcome-met">{{ assessment.outcome }}</span>
        {% elsif assessment.outcome contains "not met" or assessment.outcome contains "NOT" %}
          <span class="outcome-fail">{{ assessment.outcome }}</span>
        {% else %}
          {{ assessment.outcome }}
        {% endif %}
      </td>
      <td class="tc-bold">
        {% if assessment.integrity == 'yes' %}<span class="flag-yes">Impossible</span>
        {% elsif assessment.integrity == 'partial' %}<span class="flag-partial">Age error</span>
        {% elsif assessment.integrity == 'confirm' %}<span class="text-navy">Confirm</span>
        {% else %}<span class="flag-no">OK</span>{% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<p><small>Integrity: <strong style="color:#C00000">Impossible</strong> = address records Palmerston House before Bridget moved there. <strong style="color:#C55A11">Age error</strong> = address correct but age is 75. <strong style="color:#1F4E79">Confirm</strong> = to be verified against source document.</small></p>

---

## Overview {#overview}

Between October 2022 and May 2024, four consecutive CHC checklists — all completed by the same assessor — concluded that Mrs Bridget Walker did not meet the CHC threshold. When a different assessor evaluated the same patient in June 2025, the threshold was met on the first attempt.

The four checklists and supporting assessments contain multiple documented anomalies: impossible demographic data; domain descriptions that contradict the scores they generate; a medication record that is objectively false; and an assessment completed in 13 minutes. The checklist series culminated in an MDT on 29 August 2025 that returned a "not eligible" outcome — reversing the June 2025 finding — with no disclosed reasoning.

### CHC threshold

Eligibility is met under the National Framework where a DST shows: one A\* (Priority); or two A (Severe); or one A plus four B (Moderate); or a combination indicating a primary health need. The table below maps official outcomes against what the contemporaneous evidence supports.

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Assessor</th>
      <th>Official result</th>
      <th>Evidence-supported position</th>
    </tr>
  </thead>
  <tbody>
    <tr class="red">
      <td class="nowrap">26 Oct 2022</td>
      <td>Jacquie Deacon</td>
      <td><span class="outcome-fail">1A, 2B, 8C — NOT eligible</span></td>
      <td>1A, 4B+ arguable — impossible address; false medication claim; Behaviour understated</td>
    </tr>
    <tr class="red">
      <td class="nowrap">1 Feb 2023</td>
      <td>Jacquie Deacon</td>
      <td><span class="outcome-fail">1A, 3B, 7C — NOT eligible</span></td>
      <td>1A, 4B+ arguable — impossible address; false medication claim; Behaviour understated</td>
    </tr>
    <tr class="amber">
      <td class="nowrap">11 Sep 2023</td>
      <td>Jacquie Deacon</td>
      <td><span class="outcome-fail">1A, 3B, 7C — NOT eligible</span></td>
      <td>Identical scores to Feb 2023 despite hip fracture May 2023; Continence internal inconsistency</td>
    </tr>
    <tr class="amber">
      <td class="nowrap">22 May 2024</td>
      <td>Jacquie Deacon</td>
      <td><span class="outcome-fail">0A, 4B, 7C — NOT eligible</span></td>
      <td>Cancer unrecorded; Cognition downgraded from A without basis; 163-day completion gap</td>
    </tr>
    <tr>
      <td class="nowrap">3 Jun 2025</td>
      <td>Lynne Gardiner</td>
      <td><span class="outcome-met">1A, 5B, 5C — ELIGIBLE</span></td>
      <td>Threshold met; ICB referral triggered</td>
    </tr>
    <tr class="red">
      <td class="nowrap">29 Aug 2025</td>
      <td>ICB MDT (DST)</td>
      <td><span class="outcome-fail">NOT eligible — Sev×1 Hi×3 Mod×4</span></td>
      <td>Communication Moderate directly contradicted by MCA 31 days prior; Section 1 not disclosed</td>
    </tr>
  </tbody>
</table>

---

## Seven Key Evidence Points {#smoking-guns}

Each of the following anomalies is documented in source records. Taken individually, each might be an administrative error. Taken together, they form a consistent pattern of assessments that understated Bridget's needs.

### 1. Impossible address — Palmerston House recorded before admission

CHC Checklists #1 (26 Oct 2022) and #2 (1 Feb 2023) both record Bridget's current address as Palmerston House, Palmerston Road, Westcliff-on-Sea. Bridget was not admitted to Palmerston House until **11 April 2023** — at least 167 days after Checklist #1.

At the date of both checklists, Bridget was a resident of Westcliff Lodge, Southend-on-Sea. A document recording Palmerston House as her *current* address in October 2022 cannot be a genuine contemporaneous record of that date.

<p style="background:#FEE2E2;padding:10px 14px;border-left:4px solid #9B1C1C;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Significance:</strong> Proof of either: (a) the document was created or substantially edited after April 2023 and backdated, or (b) the Council's system populated assessment templates from shared resident data without clinical verification — and neither the assessor nor any supervisor checked basic identifying information before recording a CHC funding decision.</p>

### 2. Wrong age — 75 recorded across four checklists over 20 months

Bridget's date of birth is **8 October 1950**.

| Checklist | Date | Correct age | Recorded age |
|---|---|---|---|
| #1 | 26 Oct 2022 | 72 | **75** |
| #2 | 1 Feb 2023 | 72 | **75** |
| #3 | 11 Sep 2023 | 72 | **75** |
| #4 | 22 May 2024 | 73 | **75** |

The Council's July 2025 Care & Support Plan Review — completed by Lynne Gardiner, the same assessor who produced the correct June 2025 CHC checklist — correctly records age 74. This confirms the system held the correct date of birth; the error is specific to these four checklists.

<p style="background:#FEE2E2;padding:10px 14px;border-left:4px solid #9B1C1C;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Significance:</strong> A systematic wrong-age entry, tracking a system template rather than the real patient, persists across a 20-month span with no correction despite four separate assessments by the same assessor.</p>

### 3. "No medication" — directly contradicted by GP records

| Checklist | Date | Drug Therapies recorded |
|---|---|---|
| #1 | 26 Oct 2022 | *"No medication is taken at present."* |
| #2 | 1 Feb 2023 | *"No medication is given."* |

GP SAR records confirm Bridget was on **Donepezil 10mg** (cholinesterase inhibitor for Alzheimer's) and **Promethazine** (antipsychotic) at Westcliff Lodge at both these dates. Both medications were documented on her transfer record to Palmerston House in April 2023.

<p style="background:#FEE2E2;padding:10px 14px;border-left:4px solid #9B1C1C;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Significance:</strong> This is not an omission — it is an affirmative false statement, made twice. A dementia medication and an antipsychotic, when present, require Drug Therapies to be scored B at minimum under the National Framework. Both assessments scored C. <a href="{{ '/sar/' | relative_url }}">See GP SAR →</a></p>

### 4. Behaviour scored C — escalation documented 20 days later

Checklist #1 (26 Oct 2022), Behaviour domain: *"No evidence of challenging behaviour."* — scored **C**.

Westcliff Lodge issued a formal letter of unsuitability dated **15 November 2022** — 20 days after this assessment. The letter documents high-dependency behaviours including: faecal smearing, transferring faeces to other residents' beds, removing belongings, and touching other residents' food. These were not new behaviours: similar incidents are documented in care records from September 2020 onwards.

<p style="background:#FEE2E2;padding:10px 14px;border-left:4px solid #9B1C1C;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Significance:</strong> "No evidence of challenging behaviour" describes the same patient whom the same care home considered unsuitable within three weeks. Any assessor who reviewed care home records or spoke with care home staff would have encountered a documented behavioural history going back two years.</p>

### 5. Assessment completed in 13 minutes

Checklist #1: assigned `26 Oct 2022, 11:45` — completed `26 Oct 2022, 11:58`. Total: **13 minutes** for an 11-domain clinical assessment.

At 13 minutes, each domain received an average of 71 seconds. The National Framework requires a CHC Checklist to draw on records, carer input, and professional clinical judgment across all domains.

<p style="background:#FEE2E2;padding:10px 14px;border-left:4px solid #9B1C1C;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Significance:</strong> No genuine clinical assessment of a patient with nine-year Alzheimer's, documented behavioural incidents, and active dementia medication can be completed in 13 minutes. The duration is consistent with template-filling rather than assessment.</p>

### 6. Cognition downgraded from A to B — no clinical basis documented

Checklists #1, #2, and #3 (October 2022 – September 2023) all score Cognition as **A** (Severe). Checklist #4 (22 May 2024) scores Cognition as **B** (Moderate).

The assessor's own written description in Checklist #4 states: *"unable to make choices even with supervision… high risk of harm if without 24-hour care… removes pain patch as she does not understand why she is wearing it."* This language directly matches the A descriptor. No clinical explanation for the downgrade is recorded.

<p style="background:#FEE2E2;padding:10px 14px;border-left:4px solid #9B1C1C;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Significance:</strong> Removing the one domain that had been consistently and correctly scored moved the result further from the eligibility threshold at the same time the patient was entering palliative care. Checklist #4 is the only assessment to return zero A scores.</p>

### 7. 163-day completion gap — cancer diagnosis not reflected

Checklist #4: assigned **11 December 2023** — completed **22 May 2024**. Gap: **163 days**.

During that gap:
- **21 Dec 2023** (10 days after assignment): cancer of cells of cervix diagnosed
- **18 Jan 2024**: deep tissue injury identified on left buttock
- **c. 25 Jan 2024**: Bridget became bedbound
- **23 Feb 2024**: palliative care referral made

None of these developments are reflected in any domain of the completed assessment.

<p style="background:#FEE2E2;padding:10px 14px;border-left:4px solid #9B1C1C;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Significance:</strong> An assessment assigned, left incomplete for over five months through a cancer diagnosis and a step-change in functional status, and then completed without incorporating any of that deterioration, is not a valid assessment of the patient's needs at the time of completion.</p>

---

## Assessor Pattern Analysis {#assessor-pattern}

All four Council-initiated checklists (October 2022 – May 2024) were completed by the same assessor in the same department (Ageing Well East). All four returned "threshold not met." The checklists completed by a different assessor in a different department (Ageing Well West) returned "threshold met" on the first attempt.

### Jacquie Deacon — Ageing Well East — four checklists, four "not eligible" outcomes

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th class="tc">A</th>
      <th class="tc">B</th>
      <th class="tc">C</th>
      <th>Result</th>
      <th>Principal anomalies</th>
    </tr>
  </thead>
  <tbody>
    <tr class="red">
      <td class="nowrap"><a href="{{ '/assessments/chc-checklist-1/' | relative_url }}">26 Oct 2022</a></td>
      <td class="tc">1</td><td class="tc">2</td><td class="tc">8</td>
      <td><span class="outcome-fail">NOT eligible</span></td>
      <td><small>Impossible address; age 75 (should be 72); "no medication" (false); Behaviour C contradicted within 20 days; 13-minute completion</small></td>
    </tr>
    <tr class="red">
      <td class="nowrap"><a href="{{ '/assessments/chc-checklist-2/' | relative_url }}">1 Feb 2023</a></td>
      <td class="tc">1</td><td class="tc">3</td><td class="tc">7</td>
      <td><span class="outcome-fail">NOT eligible</span></td>
      <td><small>Impossible address; age 75 (should be 72); "no medication" (false); identical domain text to Checklist #1 in several domains</small></td>
    </tr>
    <tr class="amber">
      <td class="nowrap"><a href="{{ '/assessments/chc-checklist-3/' | relative_url }}">11 Sep 2023</a></td>
      <td class="tc">1</td><td class="tc">3</td><td class="tc">7</td>
      <td><span class="outcome-fail">NOT eligible</span></td>
      <td><small>Identical overall score to Feb 2023 despite hip fracture May 2023; Continence scored C with description recording double incontinence — internal inconsistency</small></td>
    </tr>
    <tr class="amber">
      <td class="nowrap"><a href="{{ '/assessments/chc-checklist-4/' | relative_url }}">22 May 2024</a></td>
      <td class="tc">0</td><td class="tc">4</td><td class="tc">7</td>
      <td><span class="outcome-fail">NOT eligible</span></td>
      <td><small>163-day completion gap; cancer diagnosed during gap, not reflected; Cognition downgraded from A to B; Nutrition scored C with description matching B</small></td>
    </tr>
  </tbody>
</table>

**Notable pattern:** Checklists #2 and #3 return identical overall scores (1A, 3B, 7C) six months apart, despite Bridget suffering a fractured hip and hip surgery in May 2023 between those dates. Checklist #4 is the only assessment to return zero A scores — at the same point the patient had entered palliative care.

### Lynne Gardiner — Ageing Well West — first assessment identifies eligibility

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th class="tc">A</th>
      <th class="tc">B</th>
      <th class="tc">C</th>
      <th>Result</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="nowrap"><a href="{{ '/assessments/chc-checklist-5/' | relative_url }}">3 Jun 2025</a></td>
      <td class="tc">1</td><td class="tc">5</td><td class="tc">5</td>
      <td><span class="outcome-met">ELIGIBLE</span></td>
      <td><small>First positive result. ICB referral triggered. Same assessor correctly recorded age 74 on Care & Support Plan Review, Jul 2025.</small></td>
    </tr>
    <tr class="row-confirm">
      <td class="nowrap"><a href="{{ '/assessments/chc-checklist-6/' | relative_url }}">18 Jun 2025</a></td>
      <td class="tc" colspan="3">Domain scores not yet extracted</td>
      <td><span class="outcome-fail">Threshold not met</span></td>
      <td><small>Completed 15 days after Checklist #5. Family recorded as "aware but did not wish to attend" — disputed.</small></td>
    </tr>
  </tbody>
</table>

### The August 2025 reversal

The ICB MDT on 29 August 2025 received a DST based on an ICB checklist (July 2025) and returned a "not eligible" outcome. The MDT's Section 1 reasoning has not been disclosed to the family despite formal request.

The disclosed Section 2 scores include Communication as Moderate. The MCA assessment completed on 29 July 2025 — 31 days before the MDT — records Bridget as non-verbal and unresponsive to both her GP and carer. "Moderate" is directly contradicted by this independent clinical record.

[View DST domain analysis →]({{ '/assessments/dst-aug-2025/' | relative_url }})

---

## Procedural Violations {#procedural}

### 1. CHC checklist completed before ASC foundational assessment

| Step | Timestamp |
|---|---|
| ASC assessment assigned | 26 Oct 2022, 11:22 |
| CHC Checklist assigned | 26 Oct 2022, 11:45 |
| **CHC Checklist completed** | **26 Oct 2022, 11:58** |
| ASC assessment completed | **21 November 2022** |

The CHC Checklist was completed at 11:58 on 26 October. The ASC foundational needs assessment that should underpin any CHC referral was not completed until 26 days later. A CHC assessment completed before the Council's own foundational assessment has no clinical basis to draw on.

### 2. Deferred Payment Agreement initiated before financial assessment

The family submitted the financial assessment form on **17 October 2022**. Evidence from subject access requests confirms the Council initiated Deferred Payment proceedings before this date. Under the Care Act 2014 (and associated statutory guidance), a financial assessment must precede any DPA decision. A lien established before the financial information was received is procedurally improper and challengeable.

### 3. No statutory Care Act documents provided at any stage

DoLS Standard Authorisation confirmed lack of capacity on **10 November 2020** — triggering statutory duties under the Care Act 2014. Despite this:

- No s.9 Needs Assessment has ever been provided to the family
- No s.13 Eligibility Determination has been provided
- No s.25 Care & Support Plan has been provided

Bridget's attorneys — registered with the Council as joint LPA holders for both health/welfare and property/financial domains — have been managing her affairs since 2020. There is no documented basis for the Council's failure to provide these documents to registered attorneys over a five-year period.

### 4. ASC assessments withheld for over three years

Both ASC assessments (November 2022 and February 2023) were first disclosed to the family on **11 March 2026** as attachments to the Council's second complaint response — more than three years after the earlier one was created. Both carry the same impossible demographic data as the CHC checklists. [See Document Integrity →]({{ '/document-integrity/' | relative_url }})

---

## Financial Impact {#financial}

### Property lien under Deferred Payment Agreement

A charge was registered on the family property under the Deferred Payment Agreement, established at or shortly after the October 2022 assessment process. The property value is estimated at £400,000–£450,000. The charge remains active.

If CHC eligibility is backdated to October 2022, no DPA charge should have been registered: CHC-eligible individuals are not subject to local authority means-testing for care costs, and the DPA would have had no lawful basis.

### Care charge overcharge — confirmed

The Council contracted **£750/week** with Palmerston House but invoiced the family at **£877.59/week**. The Council contracted **£738.46/week** with Westcliff Lodge but invoiced at **£800/week**. Both overcharges are documented in the Council's own invoices. [See Invoices →]({{ '/invoices/' | relative_url }})

### Potential restitution if CHC eligibility backdated

| Backdating to | Approximate overcharged period | Indicative figure |
|---|---|---|
| October 2022 | ~36 months | Subject to audit of actual invoices |
| February 2023 | ~30 months | Subject to audit of actual invoices |
| May 2024 | ~12 months | Subject to audit of actual invoices |

Figures are indicative; the precise quantum depends on the confirmed start date, actual invoiced amounts, and whether FNC is also payable for any period. These are in addition to the confirmed weekly overcharge referenced above.

### September 2020 emergency 1:1 care

Following absconding incidents at Sweyne Court (5–6 September 2020), emergency 24-hour 1:1 observation was imposed at a cost of **£4,460.65/month**, paid entirely by the family. The Council's stated position at the time was that it had no obligation to assist as Bridget was privately funded. Whether safeguarding duties under s.42 Care Act 2014 applied at that point is a matter for the investigation.

---

## Key Questions for the Ombudsman {#questions}

The following questions are unresolved on the current evidence and are material to the LGSCO investigation.

**On document integrity:**
1. Why do Checklists #1 and #2 record Palmerston House as Bridget's current address in October 2022 and February 2023, when she was not admitted there until April 2023?
2. Why does age 75 appear on four consecutive checklists spanning 20 months, when the correct age was 72–73 throughout?
3. Why does the June 2025 checklist PDF carry a file creation date of 5 March 2026 — six days before it was disclosed to the family as an attachment to the complaint response?

**On assessment quality:**
4. How was CHC Checklist #1 completed in 13 minutes across 11 domains for a patient with nine-year Alzheimer's?
5. Why do Checklists #1 and #2 record "no medication" when GP records confirm Donepezil and Promethazine were prescribed and active at both dates?
6. Why was Cognition downgraded from A to B in Checklist #4 when the assessor's own written description matched the A descriptor?
7. Why did Checklists #2 and #3 return identical overall scores six months apart, despite a hip fracture and surgery occurring between those dates?
8. Why was the cancer diagnosis (21 December 2023) and subsequent palliative care referral (February 2024) not reflected in Checklist #4, which was completed in May 2024?

**On procedural compliance:**
9. Why was the CHC Checklist completed at 11:58 on 26 October 2022 when the ASC foundational assessment was not completed until 21 November 2022?
10. Why was the Deferred Payment Agreement initiated before the financial assessment form was received?
11. Why have no statutory Care Act documents (s.9, s.13, s.25) ever been provided to the attorneys, despite DoLS authorisation confirming lack of capacity in November 2020?

**On the August 2025 DST reversal:**
12. Why was CHC eligibility reversed at the August 2025 MDT when the clinical record showed continued deterioration since June 2025?
13. What is the MDT's reasoning? Why has DST Section 1 not been disclosed to the family despite formal request?
14. Why does the DST record Communication as Moderate when the MCA assessment completed 31 days earlier records Bridget as non-verbal and unresponsive?

---

## Status {#status}

| Reference | Detail |
|---|---|
| **LGSCO ref** | 25 019 572 |
| **Investigator** | Paul Gyan-Apenteng |
| **Accepted** | 18 May 2026 |
| **Last updated** | 9 June 2026 |
| **Council ref** | 30000912 |
| **ICB ref** | BC70014 |

**Outstanding disclosures:**
- DST Section 1 and MDT narrative reasoning — requested, not yet received
- CHC Checklist #6 (18 Jun 2025) — domain scores not yet fully extracted from source document
- ICB CHC Checklist (23 Jul 2025) — domain scores not yet fully extracted
- ASC assessment crosscheck — integrity analysis pending full document review

**Ongoing matters:**
- Property lien remains active pending CHC eligibility determination
- Deferred Payment charges accumulating pending investigation outcome

---

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/issues/' | relative_url }}#chc-fnc">CHC / FNC Issues</a>
  <a href="{{ '/issues/' | relative_url }}#dst-challenge">DST Issues</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Clinical</a>
  <a href="{{ '/invoices/' | relative_url }}">Invoices</a>
  <a href="{{ '/sar/' | relative_url }}">GP SAR</a>
</div>
