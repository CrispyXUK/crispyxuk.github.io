---
layout: page
title: "Medication Summary"
permalink: /medications/
---

<p class="lead">Complete medication record for Bridget Walker — extracted from GP Subject Access Request (January 2020 – September 2025, 242 pages, Pall Mall Surgery).</p>

<div class="strand-note"><strong>Issues evidenced here:</strong> Issue <a href="{{ '/issues/' | relative_url }}#issue-26">26</a> — covert medication administered from May 2023 without MCA Best Interest process; formal MCA not completed until July 2024 (gap of over 13 months). Issue <a href="{{ '/issues/' | relative_url }}#issue-5">5</a> — medication regime consistent with nursing-level need at a home prohibited from providing nursing care.</div>

<div class="cat-jump">
  <a href="#allergy">Allergy</a>
  <a href="#current">Current Medications</a>
  <a href="#mca-gap">MCA Compliance Gap</a>
  <a href="#history">Medication History</a>
</div>

<hr>
<h2 id="allergy">Known Allergy</h2>

<table>
  <thead>
    <tr><th>Drug</th><th>Reaction</th></tr>
  </thead>
  <tbody>
    <tr class="red">
      <td><strong>{{ site.data.clinical.medications.allergy.drug }}</strong></td>
      <td>{{ site.data.clinical.medications.allergy.reaction }}</td>
    </tr>
  </tbody>
</table>

<hr>
<h2 id="current">Current Medications ({{ site.data.clinical.medications.final-list.date }})</h2>

<p><small>{{ site.data.clinical.medications.final-list.note }}</small></p>

<table>
  <thead>
    <tr>
      <th>Drug</th>
      <th>Dose</th>
      <th>Route</th>
      <th>Indication</th>
    </tr>
  </thead>
  <tbody>
    {% for item in site.data.clinical.medications.final-list.items %}
    <tr{% if item.route contains "covert" %} class="amber"{% endif %}>
      <td><strong>{{ item.drug }}</strong></td>
      <td>{{ item.dose }}</td>
      <td>{{ item.route }}</td>
      <td>{{ item.indication }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
<p><small>Rows in <strong style="background:#FFF2CC;padding:0 4px;">amber</strong> indicate covert administration.</small></p>

<hr>
<h2 id="mca-gap">MCA Compliance Gap</h2>

<div style="background:#FCE4D6;border-left:4px solid #C00000;padding:12px 16px;border-radius:0 6px 6px 0;margin-bottom:1.5em">
  <strong>Key finding:</strong> {{ site.data.clinical.mca-significance }}
</div>

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Event</th>
      <th>Significance</th>
    </tr>
  </thead>
  <tbody>
    {% for entry in site.data.clinical.mca-history %}
    {% if entry.date %}
    <tr{% if entry.significance != "" %} class="amber"{% endif %}>
      <td class="nowrap"><strong>{{ entry.date }}</strong></td>
      <td>{{ entry.event }}<br><small>{{ entry.detail }}</small></td>
      <td><small style="color:#C00000">{{ entry.significance }}</small></td>
    </tr>
    {% endif %}
    {% endfor %}
  </tbody>
</table>

<hr>
<h2 id="history">Medication History — Chronological</h2>

<ul class="timeline">
  {% for entry in site.data.clinical.medications.history %}
  <li{% if entry.significance != "" %} class="key"{% endif %}>
    <span class="date">{{ entry.date }}</span>
    <span class="event">
      <strong>{{ entry.event }}</strong><br>
      <small>{{ entry.detail }}</small>
      {% if entry.significance != "" %}
      <br><span style="color:#C00000;font-size:.85rem;font-weight:600">&#9654; {{ entry.significance }}</span>
      {% endif %}
    </span>
  </li>
  {% endfor %}
</ul>

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/clinical/' | relative_url }}">Clinical</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}#dols-mca">DoLS / MCA Issues</a>
  <a href="{{ '/issues/' | relative_url }}#chc-fnc">CHC / FNC Issues</a>
</div>
