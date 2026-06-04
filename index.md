---
layout: default
title: "Executive Summary"
permalink: /
---

<p class="lead">Private evidential record supporting the LGSCO investigation into Southend-on-Sea City Council's Adult Social Care handling of {{ site.data.resident.name.full }}'s care, funding, and assessment.</p>

<div class="summary-grid">
  <div class="card"><span class="n">{{ site.data.issues | size }}</span><span class="l">issues catalogued across seven categories</span></div>
  <div class="card"><span class="n">{{ site.data.timeline | size }}</span><span class="l">timeline events (Apr 2020 – May 2026)</span></div>
  <div class="card"><span class="n">{{ site.data.placement | size }}</span><span class="l">placements recorded</span></div>
  <div class="card"><span class="n">11</span><span class="l">DST domains analysed</span></div>
</div>

<h2>Resident</h2>

<table>
  <tbody>
    <tr>
      <td><strong>Full name</strong></td>
      <td>{{ site.data.resident.name.title }} {{ site.data.resident.name.full }}</td>
    </tr>
    <tr>
      <td><strong>Date of birth</strong></td>
      <td>{{ site.data.resident.dob }}</td>
    </tr>
    <tr>
      <td><strong>NHS number</strong></td>
      <td>{{ site.data.resident.nhs-number }}</td>
    </tr>
    <tr>
      <td><strong>Person ID</strong></td>
      <td>{{ site.data.resident.person-id }}</td>
    </tr>
    <tr>
      <td><strong>Current address</strong></td>
      <td>{{ site.data.resident.address.home }}, {{ site.data.resident.address.road }}, {{ site.data.resident.address.town }}, {{ site.data.resident.address.postcode }}</td>
    </tr>
    <tr>
      <td><strong>Diagnosis</strong></td>
      <td>{{ site.data.resident.diagnosis.primary }}<br>{{ site.data.resident.diagnosis.secondary }}</td>
    </tr>
    <tr>
      <td><strong>Capacity</strong></td>
      <td>{{ site.data.resident.capacity }}</td>
    </tr>
    <tr>
      <td><strong>DoLS status</strong></td>
      <td>{{ site.data.resident.dols.status }}</td>
    </tr>
  </tbody>
</table>

<h2>Current condition</h2>

<table>
  <tbody>
    <tr><td><strong>Mobility</strong></td><td>{{ site.data.resident.current-condition.mobility }}</td></tr>
    <tr><td><strong>Communication</strong></td><td>{{ site.data.resident.current-condition.communication }}</td></tr>
    <tr><td><strong>Continence</strong></td><td>{{ site.data.resident.current-condition.continence }}</td></tr>
    <tr><td><strong>Nutrition</strong></td><td>{{ site.data.resident.current-condition.nutrition }}</td></tr>
    <tr><td><strong>Skin</strong></td><td>{{ site.data.resident.current-condition.skin }}</td></tr>
    <tr><td><strong>Medication</strong></td><td>{{ site.data.resident.current-condition.medication }}</td></tr>
    <tr><td><strong>Resuscitation</strong></td><td>{{ site.data.resident.current-condition.resuscitation }}</td></tr>
  </tbody>
</table>

<h2>Case references</h2>

<table>
  <tbody>
    <tr><td><strong>Council ref</strong></td><td>{{ site.data.resident.case-references.council }}</td></tr>
    <tr><td><strong>LGSCO ref</strong></td><td>{{ site.data.resident.case-references.lgsco }}</td></tr>
    <tr><td><strong>ICB ref</strong></td><td>{{ site.data.resident.case-references.icb }}</td></tr>
    <tr><td><strong>LGSCO investigator</strong></td><td>{{ site.data.resident.case-references.lgsco-investigator }}</td></tr>
    <tr><td><strong>LGSCO accepted</strong></td><td>{{ site.data.resident.case-references.lgsco-accepted }}</td></tr>
  </tbody>
</table>

<h2>Attorneys (joint LPA — both domains)</h2>

<table>
  <thead>
    <tr><th>Name</th><th>Relationship</th><th>LPA</th><th>Role</th></tr>
  </thead>
  <tbody>
    {% for attorney in site.data.resident.attorneys %}
    <tr>
      <td><strong style="color:#1F4E79">{{ attorney.name }}</strong></td>
      <td>{{ attorney.relationship }}</td>
      <td>{{ attorney.lpa }}</td>
      <td>{{ attorney.role }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<h2>Council Tax exemption</h2>

<p>Class U (Severe Mental Impairment) exemption granted by Southend-on-Sea City Council on <strong>{{ site.data.resident.council-tax.granted }}</strong>. {{ site.data.resident.council-tax.significance }}</p>

<h2>Strongest evidential strands</h2>
<ul>
  <li><strong>Document integrity</strong> — CHC checklists and assessments record a future care home address as current; logically impossible unless created later and backdated. <a href="{{ '/document-integrity/' | relative_url }}">See analysis →</a></li>
  <li><strong>Proven overcharge</strong> — Council contracted £750/week with Palmerston House but invoiced the family £877.59/week; contracted £738.46/week with Westcliff Lodge but invoiced £800/week.</li>
  <li><strong>Property disregard</strong> — DPA application form (Feb 2023) declares dependent occupants, rebutting the Council's later refusal.</li>
  <li><strong>FNC failure</strong> — no NHS-Funded Nursing Care assessment during two years at Admiral Court (registered nursing home).</li>
  <li><strong>Placement appropriateness</strong> — nursing-level needs at a residential home CQC-prohibited from providing nursing care.</li>
</ul>

<h2>Navigate</h2>
<div class="cat-jump">
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>