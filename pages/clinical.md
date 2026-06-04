---
layout: default
title: "Clinical Record & Status"
permalink: /clinical/
---

<p class="lead">Current case status and clinical record extracted from the GP Subject Access Request (January 2020 – September 2025, 242 pages, Pall Mall Surgery).</p>

<div class="strand-note"><strong>Issues evidenced here:</strong> Issue <a href="{{ '/issues/' | relative_url }}#issue-5">5</a> (nursing-level needs at a residential home); Issues <a href="{{ '/issues/' | relative_url }}#issue-15">15</a>–<a href="{{ '/issues/' | relative_url }}#issue-16">16</a> (DST Communication and Skin scores contradicted by GP records); Issue <a href="{{ '/issues/' | relative_url }}#issue-26">26</a> (DPA signed without MCA compliance — covert medication began May 2023, formal MCA not until July 2024).</div>

<div class="cat-jump">
  <a href="#status">Current Status</a>
  <a href="#medications">Medications</a>
  <a href="#mca">MCA History</a>
  <a href="#waterlow">Waterlow Scores</a>
  <a href="#weight">Weight</a>
  <a href="#gsf">GSF Staging</a>
  <a href="#acb">Anticholinergic Burden</a>
</div>

<hr>
<h2 id="status">Current Status</h2>

<table>
  <thead>
    <tr><th>Item</th><th>Status</th></tr>
  </thead>
  <tbody>
    <tr><td class="cat">Council complaint</td><td>Exhausted — two final responses (Oct 2025, Mar 2026).</td></tr>
    <tr><td class="cat">LGSCO investigation</td><td>Active. Ref {{ site.case_ref_lgsco }}. Investigator {{ site.investigator }}. Accepted 18 May 2026.</td></tr>
    <tr><td class="cat">Recovery action</td><td>Temporarily suspended pending LGSCO outcome (ref provided 10 Apr 2026).</td></tr>
    <tr><td class="cat">Supplementary LGSCO submission</td><td>In preparation.</td></tr>
    <tr><td class="cat">FNC (Admiral Court)</td><td>To be raised with ICB and LGSCO as a separate strand.</td></tr>
    <tr><td class="cat">Placement appropriateness</td><td>To be raised: nursing-level needs at a home prohibited from providing nursing care.</td></tr>
    <tr><td class="cat">DST challenge</td><td>Communication and Skin scores to be challenged; full DST and MDT reasoning to be obtained.</td></tr>
    <tr><td class="cat">'Mercy' meeting records</td><td>To be requested from Council and ICB.</td></tr>
    <tr><td class="cat">LiquidLogic audit logs</td><td>Pending — session token identified.</td></tr>
    <tr><td class="cat">Property disregard</td><td>DPA application form (Feb 2023) rebuts Council's move-in date claim; to be put to LGSCO.</td></tr>
  </tbody>
</table>

<hr>
<h2 id="medications">Medication History</h2>

<h3>Known allergy</h3>
<p><strong style="color:#C00000">{{ site.data.clinical.medications.allergy.drug }}</strong> — {{ site.data.clinical.medications.allergy.reaction }}</p>

<h3>Final medication list ({{ site.data.clinical.medications.final-list.date }})</h3>
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
    <tr{% if item.route contains "covert" %} style="background:#FFF2CC"{% endif %}>
      <td><strong>{{ item.drug }}</strong></td>
      <td>{{ item.dose }}</td>
      <td>{{ item.route }}</td>
      <td>{{ item.indication }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
<p><small>Rows in <strong style="background:#FFF2CC;padding:0 4px;">amber</strong> indicate covert administration.</small></p>

<h3>Medication history — chronological</h3>

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

<hr>
<h2 id="mca">Mental Capacity Act Assessment History</h2>

<div style="background:#FCE4D6;border-left:4px solid #C00000;padding:12px 16px;border-radius:0 6px 6px 0;margin-bottom:1.5em">
  <strong>Key finding:</strong> {{ site.data.clinical.mca-significance }}
</div>

<ul class="timeline">
  {% for entry in site.data.clinical.mca-history %}
  {% if entry.date %}
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
  {% endif %}
  {% endfor %}
</ul>

<hr>
<h2 id="waterlow">Waterlow Pressure Sore Risk Scores</h2>

<p>Waterlow scores show a consistent upward trajectory from borderline "at risk" in 2020 to "very high risk" (27) by 2025. The May 2024 CHC Checklist scored Skin Integrity as C ("no risk") while the Waterlow score was already at high-risk levels. The June 2025 checklist correctly scored Skin as B.</p>

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th style="text-align:center">Score</th>
      <th>Risk category</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    {% for w in site.data.clinical.waterlow %}
    <tr{% if w.score >= 20 %} style="background:#FCE4D6"{% elsif w.score >= 15 %} style="background:#FFF2CC"{% endif %}>
      <td>{{ w.date }}</td>
      <td style="text-align:center;font-weight:700;font-size:1.1rem;
        {% if w.score >= 20 %}color:#C00000{% elsif w.score >= 15 %}color:#C55A11{% else %}color:#2e7d32{% endif %}">
        {{ w.score }}
      </td>
      <td>{{ w.category }}</td>
      <td><small>{{ w.notes }}</small></td>
    </tr>
    {% endfor %}
  </tbody>
</table>
<p><small>Waterlow thresholds: 10–14 = At risk &nbsp;|&nbsp; 15–19 = High risk &nbsp;|&nbsp; 20+ = Very high risk</small></p>

<hr>
<h2 id="weight">Weight</h2>

<p>Weight declined from approximately 47kg in 2020 to 44.9kg by mid-2024, with a slight recorded increase to 48.3kg in August 2025 (possibly fluid retention). The January 2024 reading of 65kg is almost certainly a recording error.</p>

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th style="text-align:center">Weight (kg)</th>
      <th style="text-align:center">BMI</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    {% for w in site.data.clinical.weight %}
    <tr{% if w.notes contains "error" %} style="background:#FFF2CC"{% endif %}>
      <td>{{ w.date }}</td>
      <td style="text-align:center;font-weight:600">{{ w.kg }}</td>
      <td style="text-align:center">{{ w.bmi }}</td>
      <td><small>{{ w.notes }}</small></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<hr>
<h2 id="gsf">GSF Prognostic Staging</h2>

<p>Gold Standards Framework staging recorded by the palliative care team.</p>

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Stage</th>
      <th>Description</th>
      <th>Recorded by</th>
    </tr>
  </thead>
  <tbody>
    {% for g in site.data.clinical.gsf-staging %}
    <tr>
      <td>{{ g.date }}</td>
      <td><strong>{{ g.stage }}</strong></td>
      <td>{{ g.description }}</td>
      <td><small>{{ g.recorded-by }}</small></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<hr>
<h2 id="acb">Anticholinergic Cognitive Burden</h2>

<p>{{ site.data.clinical.anticholinergic-burden.significance }}</p>

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th style="text-align:center">Score</th>
      <th>Category</th>
    </tr>
  </thead>
  <tbody>
    {% for a in site.data.clinical.anticholinergic-burden.scores %}
    <tr style="background:#FFF2CC">
      <td>{{ a.date }}</td>
      <td style="text-align:center;font-weight:700;font-size:1.1rem;color:#C55A11">{{ a.score }}</td>
      <td>{{ a.category }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/dst/' | relative_url }}">DST &amp; Checklists</a>
  <a href="{{ '/issues/' | relative_url }}#chc-fnc">CHC / FNC Issues</a>
  <a href="{{ '/issues/' | relative_url }}#dols-mca">DoLS / MCA Issues</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
</div>