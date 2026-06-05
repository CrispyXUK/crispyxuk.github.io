---
layout: page
title: "Issue Register"
permalink: /issues/
---

{% assign category_labels = "chc-fnc:CHC / FNC|dst-challenge:DST Challenge|financial-dpa:Financial / DPA|care-act:Care Act|dols-mca:DoLS / MCA|doc-integrity:Document Integrity|complaint-handling:Complaint Handling|regulatory:Regulatory" | split: "|" %}

{% assign high_count = site.data.issues | where: "severity", "high" | size %}
{% assign med_count  = site.data.issues | where: "severity", "medium" | size %}
{% assign low_count  = site.data.issues | where: "severity", "low" | size %}

<p class="lead">{{ site.data.issues | size }} issues across eight categories. <span class="sev-high">&#9679;</span> {{ high_count }} high &nbsp;<span class="sev-medium">&#9679;</span> {{ med_count }} medium &nbsp;<span class="sev-low">&#9679;</span> {{ low_count }} lower priority.</p>

<div class="cat-jump">
  <a href="#chc-fnc">CHC / FNC</a>
  <a href="#dst-challenge">DST Challenge</a>
  <a href="#financial-dpa">Financial / DPA</a>
  <a href="#care-act">Care Act</a>
  <a href="#dols-mca">DoLS / MCA</a>
  <a href="#doc-integrity">Document Integrity</a>
  <a href="#complaint-handling">Complaint Handling</a>
  <a href="#regulatory">Regulatory</a>
</div>

{% assign grouped = site.data.issues | group_by: "category" %}
{% assign category_order = "chc-fnc,dst-challenge,financial-dpa,care-act,dols-mca,doc-integrity,complaint-handling,regulatory" | split: "," %}

{% for cat_slug in category_order %}
  {% assign group = grouped | where: "name", cat_slug | first %}
  {% if group %}

  {% assign label = "" %}
  {% for pair in category_labels %}
    {% assign parts = pair | split: ":" %}
    {% if parts[0] == cat_slug %}
      {% assign label = parts[1] %}
    {% endif %}
  {% endfor %}

<h2 id="{{ cat_slug }}">{{ label }}</h2>

<table>
  <thead>
    <tr>
      <th class="col-num">#</th>
      <th class="col-sev"></th>
      <th>Issue</th>
      <th class="col-evidence">Key evidence</th>
      <th class="col-timeline">Timeline</th>
    </tr>
  </thead>
  <tbody>
    {% for issue in group.items %}
    <tr id="issue-{{ issue.num }}"{% if issue.severity == "high" %} class="sev-high-row"{% endif %}>
      <td class="num">{{ issue.num }}</td>
      <td class="tc"><span class="sev-dot sev-{{ issue.severity }}" title="{{ issue.severity }} priority">&#9679;</span></td>
      <td>{{ issue.issue }}</td>
      <td><small>{{ issue.evidence }}</small></td>
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

<div class="cat-jump">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/emails/' | relative_url }}">Emails</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>
