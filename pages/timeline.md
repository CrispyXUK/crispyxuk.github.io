---
layout: default
title: "Timeline"
permalink: /timeline/
---

<div class="strand-note"><strong>Issues evidenced here:</strong> Issues <a href="{{ '/issues/' | relative_url }}#issue-36">36</a>–<a href="{{ '/issues/' | relative_url }}#issue-38">38</a>, <a href="{{ '/issues/' | relative_url }}#issue-46">46</a> (document backdating — addresses and metadata); Issues <a href="{{ '/issues/' | relative_url }}#issue-1">1</a>–<a href="{{ '/issues/' | relative_url }}#issue-2">2</a> (no CHC/FNC referral for two years); Issue <a href="{{ '/issues/' | relative_url }}#issue-23">23</a> (DPA names wrong care home); Issue <a href="{{ '/issues/' | relative_url }}#issue-6">6</a> (undisclosed 'Mercy' meeting).</div>

<h2>Placement Timeline</h2>

<table>
  <thead>
    <tr>
      <th>Placement</th>
      <th>Dates</th>
      <th>Type</th>
      <th>Funding</th>
      <th>Council rate</th>
      <th>Billed to family</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    {% for home in site.data.placement %}
    <tr>
      <td><strong style="color:#1F4E79">{{ home.home }}</strong></td>
      <td style="white-space:nowrap">{{ home.date-start }}<br>to {{ home.date-end }}</td>
      <td>{{ home.type }}</td>
      <td>{{ home.funding }}</td>
      <td>{{ home.weekly-fee-council }}</td>
      <td>{{ home.weekly-fee-billed }}</td>
      <td>{{ home.about }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<hr>
<h2>General Timeline</h2>

<ul class="timeline">
  {% for entry in site.data.timeline %}
  {% if entry.id %}
    {% assign related = "" | split: "" %}
    {% for issue in site.data.issues %}
      {% if issue.timeline-refs contains entry.id %}
        {% assign related = related | push: issue %}
      {% endif %}
    {% endfor %}
  {% else %}
    {% assign related = "" | split: "" %}
  {% endif %}
  <li{% if entry.key %} class="key"{% endif %}{% if entry.id %} id="tl-{{ entry.id }}"{% endif %}>
    <span class="date">{{ entry.date }}</span>
    <span class="event">
      {{ entry.event }}
      {% if related.size > 0 %}
      <span class="tl-issue-refs">
        {% for issue in related %}<a class="issue-badge {% if issue.severity == 'high' %}issue-badge-high{% elsif issue.severity == 'medium' %}issue-badge-med{% endif %}" href="{{ '/issues/' | relative_url }}#issue-{{ issue.num }}" title="{{ issue.issue | truncate: 80 }}">#{{ issue.num }}</a>{% endfor %}
      </span>
      {% endif %}
    </span>
  </li>
  {% endfor %}
</ul>

<div class="cat-jump">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>