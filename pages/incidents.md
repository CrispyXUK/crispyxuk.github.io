---
layout: page
title: "Incidents"
permalink: /incidents/
---

<p class="lead">Significant safety incidents during Bridget Walker's care, drawn from clinical records. Incidents marked <strong style="background:#FCE4D6;padding:2px 5px;">not notified</strong> were not reported to attorneys (Mark Walker / Kira Walker, joint LPA holders) at the time.</p>

<div class="strand-note"><strong>Issues evidenced here:</strong> Issue <a href="{{ '/issues/' | relative_url }}#issue-56">56</a> (fall requiring ambulance attendance post-NOF-fracture not notified to attorneys — CQC Reg 16 / Duty of Candour); Issue <a href="{{ '/issues/' | relative_url }}#issue-52">52</a> (DATIX E259548 — DTI Jan 2024 — not disclosed).</div>

---

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Location</th>
      <th>Incident</th>
      <th>Type</th>
      <th>Notified to attorneys</th>
      <th>Detail</th>
    </tr>
  </thead>
  <tbody>
    {% assign incidents = site.posts | where: "category", "incident" | sort: "date" %}
    {% for incident in incidents %}
    <tr{% if incident.highlight %} class="red"{% endif %}>
      <td class="nowrap">{{ incident.incident-date }}</td>
      <td>{{ incident.location }}</td>
      <td>{{ incident.summary }}</td>
      <td>{{ incident.incident-type }}</td>
      <td>
        {% if incident.notified == "yes" %}
          <span class="flag-no">Yes</span>
        {% elsif incident.notified == "not-notified" %}
          <span class="flag-yes">Not notified</span>
        {% else %}
          <span class="flag-partial">Unknown</span>
        {% endif %}
      </td>
      <td>
        <a href="{{ incident.url | relative_url }}">&#8594;</a>
        {% if incident.related-timeline %}
          <a href="{{ '/timeline/' | relative_url }}#{{ incident.related-timeline }}">&#8599;</a>
        {% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>

## Notification obligations

<p>Palmerston House is CQC-registered and subject to the <strong>Duty of Candour (Regulation 20)</strong> and <strong>CQC Regulation 16</strong> (receiving and acting on complaints). For a resident who lacks capacity, the duty to notify extends to legal representatives — here Mark Walker and Kira Walker as joint LPA attorneys for both health/welfare and property/financial affairs.</p>

<p>Incidents marked <em>Not notified</em> above were identified from clinical records (GP SAR, PCN notes, EPUT records) rather than from any communication by the care home. Failure to notify attorneys of significant safety incidents — including a fall requiring ambulance attendance 10 days after hip surgery, and a reportable pressure injury triggering a DATIX — is a governance failure under both regulatory frameworks.</p>

<p>See <a href="{{ '/issues/' | relative_url }}#issue-56">Issue 56</a> (fall notification failure) and <a href="{{ '/issues/' | relative_url }}#issue-52">Issue 52</a> (DATIX non-disclosure).</p>

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/clinical/' | relative_url }}">Clinical Record</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
</div>
