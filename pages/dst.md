---
layout: page
title: "Assesements"
permalink: /dst/
---

<p class="lead">NHS Decision Support Tool (MDT meeting 29 August 2025, ICB Ref BC70014) and all six Council CHC Checklists. Only DST Section 2 has been disclosed — Section 1 and MDT narrative reasoning have not been provided.</p>

<div class="strand-note"><strong>Issues evidenced here:</strong> Issues <a href="{{ '/issues/' | relative_url }}#issue-15">15</a>–<a href="{{ '/issues/' | relative_url }}#issue-17">17</a> (DST domain scoring directly contradicted by care plan and Waterlow data); Issues <a href="{{ '/issues/' | relative_url }}#issue-7">7</a>, <a href="{{ '/issues/' | relative_url }}#issue-36">36</a>–<a href="{{ '/issues/' | relative_url }}#issue-37">37</a> (incorrect age and address on all Council checklists); Issue <a href="{{ '/issues/' | relative_url }}#issue-1">1</a> (no CHC referral for two years despite nursing home placement).</div>

<div class="cat-jump">
  <a href="#dst">DST Domain Scores</a>
  <a href="#checklists">CHC Checklists</a>
  <a href="#summary">Checklist Summary</a>
</div>

<hr>
<h2 id="dst">DST Domain Scores — 29 August 2025</h2>

<p>Rows in <strong style="background:#FFF2CC;padding:2px 5px;">amber</strong> may be understated. Rows in <strong style="background:#FCE4D6;padding:2px 5px;">red</strong> are directly contradicted by contemporaneous evidence.</p>

<table>
  <thead>
    <tr>
      <th>Domain</th>
      <th>Awarded</th>
      <th>Correct?</th>
      <th>Challenge basis</th>
    </tr>
  </thead>
  <tbody>
    {% for d in site.data.dst %}
    <tr{% if d.flag == 'red' %} class="red"{% elsif d.flag == 'amber' %} class="amber"{% endif %}>
      <td><strong>{{ d.domain }}</strong></td>
      <td>{{ d.awarded }}</td>
      <td>{{ d.correct }}</td>
      <td><em>{{ d.challenge }}</em></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<p>With Communication corrected to High: Severe&nbsp;&times;1, High&nbsp;&times;4, Moderate&nbsp;&times;3. With Skin also corrected: Severe&nbsp;&times;1, High&nbsp;&times;5, Moderate&nbsp;&times;2. No MDT reasoning has been disclosed to rebut this profile.</p>

<hr>
<h2 id="checklists">CHC Checklists — Domain Scores</h2>

<p>All six Council checklists were first disclosed to the family on 11 March 2026 as attachments to the Council's second complaint response. The June 2025 checklist PDF carries creation metadata of 5 March 2026 — six days before disclosure. See <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a> for the full analysis.</p>

<p>Score key: <strong>A*</strong> = Priority &nbsp;|&nbsp; <strong>A</strong> = Severe &nbsp;|&nbsp; <strong>B</strong> = Moderate &nbsp;|&nbsp; <strong>C</strong> = Low/No needs<br>
<small>The <strong>Should be</strong> column shows what the score should have been based on the assessor's own recorded description. Rows highlighted in <strong style="background:#FCE4D6;padding:0 3px;">red</strong> indicate a mismatch between the recorded description and the selected score.</small></p>

{% assign checklists = site.data.integrity | where_exp: "d", "d.document contains 'Checklist'" %}
{% for doc in checklists %}

<h3 style="margin-top:2em;color:#1F4E79;border-bottom:2px solid #D6E4F0;padding-bottom:6px">
  {{ doc.document }}
  <span style="font-size:.85rem;font-weight:400;color:#666;margin-left:12px">{{ doc.stated }} &mdash; {{ doc.assessor }}, {{ doc.department }}</span>
</h3>

<div style="display:flex;gap:12px;flex-wrap:wrap;margin-bottom:12px">
  <span style="background:#F2F2F2;padding:4px 10px;border-radius:4px;font-size:.85rem"><strong>A* (Priority):</strong> {{ doc.totals.a-star }}</span>
  <span style="background:#F2F2F2;padding:4px 10px;border-radius:4px;font-size:.85rem"><strong>A (Severe):</strong> {{ doc.totals.a }}</span>
  <span style="background:#F2F2F2;padding:4px 10px;border-radius:4px;font-size:.85rem"><strong>B (Moderate):</strong> {{ doc.totals.b }}</span>
  <span style="background:#F2F2F2;padding:4px 10px;border-radius:4px;font-size:.85rem"><strong>C (Low):</strong> {{ doc.totals.c }}</span>
  <span style="padding:4px 10px;border-radius:4px;font-size:.85rem;font-weight:700;{% if doc.outcome contains 'MET' %}background:#d4edda;color:#155724{% else %}background:#FCE4D6;color:#C00000{% endif %}">{{ doc.outcome }}</span>
</div>

{% if doc.domains and doc.domains.size > 0 %}
<table>
  <thead>
    <tr>
      <th class="col-domain">Domain</th>
      <th class="col-score tc">Scored</th>
      <th class="col-score tc">Should be</th>
      <th>Assessor's recorded description</th>
      <th>Challenge / significance</th>
    </tr>
  </thead>
  <tbody>
    {% for domain in doc.domains %}
    {% assign mismatch = false %}
    {% if domain.score-based-on-description != domain.score and domain.score-based-on-description != "" %}
      {% assign mismatch = true %}
    {% endif %}
    <tr{% if mismatch %} class="red"{% elsif domain.challenge != "" %} class="row-note"{% endif %}>
      <td><strong>{{ domain.name }}</strong></td>
      <td class="score-cell {% if domain.score == 'A*' %}score-Priority{% elsif domain.score == 'A' %}score-Severe{% elsif domain.score == 'B' %}score-Moderate{% else %}score-Low{% endif %}">{{ domain.score }}</td>
      <td class="score-cell{% if domain.score-based-on-description != domain.score and domain.score-based-on-description != '' %} {% if domain.score-based-on-description == 'A*' %}score-Priority{% elsif domain.score-based-on-description == 'A' %}score-Severe{% elsif domain.score-based-on-description == 'B' %}score-Moderate{% else %}score-Low{% endif %}{% endif %}">
        {% if domain.score-based-on-description != domain.score %}{{ domain.score-based-on-description }}{% else %}&mdash;{% endif %}
      </td>
      <td><small>{{ domain.recorded }}</small></td>
      <td><small class="sev-high">{{ domain.challenge }}</small></td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% endif %}

{% if doc.notes != "" %}
<p style="background:#F2F2F2;padding:10px 14px;border-left:4px solid #2E75B6;border-radius:0 4px 4px 0;font-size:.88rem;margin-top:8px"><strong>Notes:</strong> {{ doc.notes }}</p>
{% endif %}

{% endfor %}

<hr>
<h2 id="summary">Checklist Score Summary</h2>

<table>
  <thead>
    <tr>
      <th>Checklist</th>
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
    {% for doc in site.data.integrity %}
    {% unless doc.document contains "Review" or doc.document contains "ICB" %}
    <tr{% if doc.impossible == 'yes' %} class="red"{% elsif doc.impossible == 'partial' %} class="amber"{% elsif doc.impossible == 'confirm' %} class="row-confirm"{% endif %}>
      <td><strong>{{ doc.document }}</strong></td>
      <td class="nowrap">{{ doc.stated }}</td>
      <td><small>{{ doc.assessor }}</small></td>
      <td class="tc">{{ doc.totals.a-star }}</td>
      <td class="tc">{{ doc.totals.a }}</td>
      <td class="tc">{{ doc.totals.b }}</td>
      <td class="tc">{{ doc.totals.c }}</td>
      <td>{% if doc.outcome contains "MET" %}<span class="outcome-met">{{ doc.outcome }}</span>{% else %}<span class="outcome-fail">{{ doc.outcome }}</span>{% endif %}</td>
      <td class="tc-bold">{% if doc.impossible == 'yes' %}<span class="flag-yes">Impossible</span>{% elsif doc.impossible == 'partial' %}<span class="flag-partial">Age error</span>{% elsif doc.impossible == 'confirm' %}<span class="text-navy">Confirm</span>{% else %}<span class="flag-no">OK</span>{% endif %}</td>
    </tr>
    {% endunless %}
    {% endfor %}
  </tbody>
</table>

<p><small>Integrity: <strong style="color:#C00000">Impossible</strong> = address records Palmerston House before Bridget moved there. <strong style="color:#C55A11">Age error</strong> = address correct but age is 75. <strong style="color:#1F4E79">Confirm</strong> = to be verified against source document.</small></p>

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/issues/' | relative_url }}#chc-fnc">CHC / FNC Issues</a>
  <a href="{{ '/issues/' | relative_url }}#dst-challenge">DST Issues</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>