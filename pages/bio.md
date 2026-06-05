---
layout: page
title: "About Bridget"
permalink: /bio/
---

<div class="row g-4">

<!-- ── LEFT: biography ───────────────────────────────── -->
<div class="col-md-5">

{% include bio-content.html %}

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/clinical/' | relative_url }}">Clinical Record</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
</div>

</div>

<!-- ── RIGHT: issue register ─────────────────────────── -->
<div class="col-md-7 issues-col col-bordered">

{% assign category_labels = "chc-fnc:CHC / FNC|dst-challenge:DST Challenge|financial-dpa:Financial / DPA|care-act:Care Act|dols-mca:DoLS / MCA|doc-integrity:Document Integrity|complaint-handling:Complaint Handling|regulatory:Regulatory" | split: "|" %}

{% assign high_count = site.data.issues | where: "severity", "high" | size %}
{% assign med_count  = site.data.issues | where: "severity", "medium" | size %}
{% assign low_count  = site.data.issues | where: "severity", "low" | size %}

<h2>Issue Register</h2>
<p><span class="sev-high">&#9679;</span> {{ high_count }} high &nbsp;<span class="sev-medium">&#9679;</span> {{ med_count }} medium &nbsp;<span class="sev-low">&#9679;</span> {{ low_count }} lower priority</p>

<div class="cat-jump">
  <a href="#i-chc-fnc">CHC / FNC</a>
  <a href="#i-dst-challenge">DST</a>
  <a href="#i-financial-dpa">Financial</a>
  <a href="#i-care-act">Care Act</a>
  <a href="#i-dols-mca">DoLS / MCA</a>
  <a href="#i-doc-integrity">Doc Integrity</a>
  <a href="#i-complaint-handling">Complaints</a>
  <a href="#i-regulatory">Regulatory</a>
</div>

{% assign grouped = site.data.issues | group_by: "category" %}
{% assign category_order = "chc-fnc,dst-challenge,financial-dpa,care-act,dols-mca,doc-integrity,complaint-handling,regulatory" | split: "," %}

{% for cat_slug in category_order %}
  {% assign group = grouped | where: "name", cat_slug | first %}
  {% if group %}

  {% assign label = "" %}
  {% for pair in category_labels %}
    {% assign parts = pair | split: ":" %}
    {% if parts[0] == cat_slug %}{% assign label = parts[1] %}{% endif %}
  {% endfor %}

<h3 id="i-{{ cat_slug }}" style="margin-top:1.5em;border-bottom:2px solid var(--light-blue);padding-bottom:4px">{{ label }}</h3>

<table>
  <thead>
    <tr>
      <th style="width:30px">#</th>
      <th style="width:20px"></th>
      <th>Issue</th>
      <th style="width:90px">Timeline</th>
    </tr>
  </thead>
  <tbody>
    {% for issue in group.items %}
    <tr id="issue-{{ issue.num }}"{% if issue.severity == "high" %} class="sev-high-row"{% endif %}>
      <td class="num" style="font-size:.8rem">{{ issue.num }}</td>
      <td style="text-align:center"><span class="sev-dot sev-{{ issue.severity }}" title="{{ issue.severity }}">&#9679;</span></td>
      <td style="font-size:.82rem">{{ issue.issue }}</td>
      <td>
        {% if issue.timeline-refs %}
          {% for ref in issue.timeline-refs %}
            <a class="tl-ref" href="{{ '/timeline/' | relative_url }}#tl-{{ ref }}">{{ ref }}</a>
          {% endfor %}
        {% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>

  {% endif %}
{% endfor %}

</div>

</div>
