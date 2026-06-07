---
layout: page
title: "Executive Summary"
permalink: /
---

Private evidential record supporting LGSCO investigation **{{ site.case_ref_lgsco }}** into Southend-on-Sea City Council Adult Social Care's handling of Mrs Bridget Penelope Walker's care, funding, and assessment. Investigator: {{ site.investigator }}. Case accepted 18 May 2026.

<div class="row row-cols-1 row-cols-md-3 g-2 mb-4">
  <div class="col">
    <article class="card-wrapper card h-100">
      <a href="{{ '/issues/' | relative_url }}" class="post-preview row g-0">
        <div class="col-12">
          <div class="card-body d-flex flex-column">
            <h1 class="card-title my-2 mt-md-0">{{ site.data.issues | size }}</h1>
            <div class="card-text content mt-0 mb-3">
              <p>issues across eight categories</p>
            </div>
            <div class="post-meta flex-grow-1 d-flex align-items-end">
              <div class="me-auto"><i class="fas fa-list-ul fa-fw me-1"></i>Issue Register</div>
            </div>
          </div>
        </div>
      </a>
    </article>
  </div>
  <div class="col">
    <article class="card-wrapper card h-100">
      <a href="{{ '/timeline/' | relative_url }}" class="post-preview row g-0">
        <div class="col-12">
          <div class="card-body d-flex flex-column">
            <h1 class="card-title my-2 mt-md-0">{{ site.data.timeline | size }}</h1>
            <div class="card-text content mt-0 mb-3">
              <p>timeline events (Apr 2020 – Jun 2026)</p>
            </div>
            <div class="post-meta flex-grow-1 d-flex align-items-end">
              <div class="me-auto"><i class="fas fa-clock fa-fw me-1"></i>Timeline</div>
            </div>
          </div>
        </div>
      </a>
    </article>
  </div>
  <div class="col">
    <article class="card-wrapper card h-100">
      <a href="{{ '/timeline/' | relative_url }}" class="post-preview row g-0">
        <div class="col-12">
          <div class="card-body d-flex flex-column">
            <h1 class="card-title my-2 mt-md-0">{{ site.data.placement | size }}</h1>
            <div class="card-text content mt-0 mb-3">
              <p>care placements documented</p>
            </div>
            <div class="post-meta flex-grow-1 d-flex align-items-end">
              <div class="me-auto"><i class="fas fa-home fa-fw me-1"></i>Placements</div>
            </div>
          </div>
        </div>
      </a>
    </article>
  </div>
</div>

---

## Mrs {{ site.data.resident.name.full }}

| | |
|---|---|
| **Date of birth** | {{ site.data.resident.dob }} |
| **NHS number** | {{ site.data.resident.nhs-number }} |
| **Person ID** | {{ site.data.resident.person-id }} |
| **Current address** | {{ site.data.resident.address.home }}, {{ site.data.resident.address.road }}, {{ site.data.resident.address.town }}, {{ site.data.resident.address.postcode }} |
| **Diagnosis** | {{ site.data.resident.diagnosis.primary }}; {{ site.data.resident.diagnosis.secondary }} |
| **Capacity** | {{ site.data.resident.capacity }} |
| **DoLS status** | {{ site.data.resident.dols.status }} |

## Attorneys — joint LPA, both domains

| Name | Relationship | Role |
|---|---|---|
{% for attorney in site.data.resident.attorneys %}| **{{ attorney.name }}** | {{ attorney.relationship }} | {{ attorney.role }} |
{% endfor %}

## Current condition

| | |
|---|---|
| **Mobility** | {{ site.data.resident.current-condition.mobility }} |
| **Communication** | {{ site.data.resident.current-condition.communication }} |
| **Continence** | {{ site.data.resident.current-condition.continence }} |
| **Nutrition** | {{ site.data.resident.current-condition.nutrition }} |
| **Skin** | {{ site.data.resident.current-condition.skin }} |
| **Medication** | {{ site.data.resident.current-condition.medication }} |
| **Resuscitation** | {{ site.data.resident.current-condition.resuscitation }} |

## Case references

| | |
|---|---|
| **Council ref** | {{ site.data.resident.case-references.council }} |
| **LGSCO ref** | {{ site.data.resident.case-references.lgsco }} |
| **ICB ref** | {{ site.data.resident.case-references.icb }} |
| **LGSCO investigator** | {{ site.data.resident.case-references.lgsco-investigator }} |
| **LGSCO accepted** | {{ site.data.resident.case-references.lgsco-accepted }} |

## Council Tax exemption

Class U (Severe Mental Impairment) exemption granted by Southend-on-Sea City Council on **{{ site.data.resident.council-tax.granted }}**. {{ site.data.resident.council-tax.significance }}

## Key parties

| Name | Details |
|---|---|
{% for p in site.data.parties %}| **{{ p.name }}** | {{ p.detail }} |
{% endfor %}

---

## Major incidents and events

| Date | Incident |
|---|---|
| **5 Sep 2020** | Day 3 at Sweyne Court: acute behavioural crisis — found on top of a bedridden resident; attempting to escape through a window. Cellulitis of left leg. Paramedic called. |
| **6 Sep 2020** | Absconds from Sweyne Court; walks barefoot to Rayleigh High Street. CQC and safeguarding lead Jo Allen notified. 24-hour 1:1 care imposed at family's cost (£4,460.65). Council's position: not obliged to assist as Bridget is privately funded. |
| **9 Sep 2020** | CMHT crisis briefing: absconded twice; absconding risk assessed as **high**. 1:1 observation. ABC behaviour chart recommended — subsequently absent from all records. |
| **10 Nov 2020** | DoLS Standard Authorisation granted at Admiral Court. Lack of capacity formally confirmed; continuous supervision; not free to leave. |
| **Dec 2020** | COVID-19 positive. Waterlow score rises from 11 to 14 in five weeks; cracked and broken skin on feet not treated until GP home visit 11 Dec 2020. |
| **4 Dec 2020** | Continence assessment: doubly incontinent; faecal smearing; wet bedding nightly; removing pads. Waterlow +27% in 5 weeks. No Council involvement throughout this period. |
| **11 May 2023** | Unwitnessed fall at Palmerston House — right hip and knee bruising; vomited twice. X-rays requested. DNAR signed. |
| **15 May 2023** | Admitted to Shopland Ward, Southend Hospital. X-ray: displaced subcapital fracture of right neck of femur. Emergency hemiarthroplasty (cemented Zimmer/Mueller). |
| **26 May 2023** | Discovered hospital did not administer Memantine during 10-day admission — titration pack brought in but not given, citing unclear dosing. Medication restarts from zero. |
| **27 May 2023** | Second fall at Palmerston House — skin tear right wrist. East of England Ambulance called. Falls notification records "recent NOF surgery" and two or more falls in the past six months. |
| **21 Dec 2023** | Cancer of cells of cervix diagnosed (confirmed via hysteroscopy biopsy 9 Nov 2023). EPUT bladder and bowel nurse records Bridget as chairbound, needing prompting for diet and fluids, Waterlow 19. CHC Checklist #4 was already overdue at this point, assigned 10 days earlier. |
| **18 Jan 2024** | Deep Tissue Injury identified on left buttock by District Nurse (DATIX ref E259548). Previously on a static mattress; dynamic mattress ordered same day. |
| **Jan–Feb 2024** | Rapid mobility collapse: chairbound (21 Dec 2023) → wheelchair with rotundar (c. 9 Jan 2024) → bedbound (c. 25 Jan 2024). CRP raised, hypernatraemia. Palliative care referral made 23 Feb 2024. Weekly PCN ward rounds recorded "no concerns" throughout. |
| **Mar 2025** | Scabies outbreak at Palmerston House. Permethrin 5% cream prescribed — whole-body application including face, scalp and ears, repeated after 7 days. Relevant to CQC Regulation 12. |
| **18 Dec 2025** | CQC serves two warning notices on E&F Enterprises Ltd (Palmerston House operator): breach of Regulation 12 (Safe Care and Treatment) and Regulation 17 (Good Governance). Home rated Requires Improvement. |

---

## Strongest evidential strands

- **Document integrity** — CHC checklists and ASC assessments record a future care home address as current; logically impossible unless created later and backdated. [See analysis →]({{ '/document-integrity/' | relative_url }})
- **Assessment non-disclosure** — both ASC assessments (Nov 2022, Feb 2023) were withheld from the family and first seen by Mark Walker on 11 Mar 2026 — over three years after the earlier one was created — as attachments to the Council's second complaint response. Both carry the same integrity errors as the CHC checklists.
- **No Care Act framework** — no s.9 Needs Assessment, s.13 Eligibility Determination, or s.25 Care & Support Plan has ever been provided at any stage, despite DoLS authorisation confirming lack of capacity from November 2020.
- **Proven overcharge** — Council contracted £750/week with Palmerston House but invoiced £877.59/week; contracted £738.46/week with Westcliff Lodge but invoiced £800/week.
- **Property disregard** — DPA application form (Feb 2023) declares dependent occupants, directly rebutting the Council's later refusal of the disregard.
- **FNC failure** — no NHS-Funded Nursing Care assessment during two years at Admiral Court (a registered nursing home, CQC Outstanding).
- **Placement appropriateness** — nursing-level needs managed at a residential home CQC-prohibited from providing nursing care.
- **Covert medication without MCA** — covert administration began May 2023; first MCA not completed until July 2024 — a gap of over 13 months. [See GP SAR →]({{ '/sar/' | relative_url }})
- **Ethnicity misclassification** — EGFR results from Apr 2023, Feb 2024 and Aug 2025 all carry an African-Caribbean correction flag. Mrs Walker is White British. No correction confirmed. [See GP SAR →]({{ '/sar/' | relative_url }})

---

{% include bio-content.html %}

---

[Timeline]({{ '/timeline/' | relative_url }}) · [Issue Register]({{ '/issues/' | relative_url }}) · [Document Integrity]({{ '/document-integrity/' | relative_url }}) · [DST Analysis]({{ '/dst/' | relative_url }}) · [Evidence]({{ '/evidence/' | relative_url }}) · [Clinical]({{ '/clinical/' | relative_url }}#status) · [GP SAR]({{ '/sar/' | relative_url }})
