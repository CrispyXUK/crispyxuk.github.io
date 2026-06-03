---
layout: default
title: "Timeline"
permalink: /timeline/
---

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
  <li{% if entry.key %} class="key"{% endif %}>
    <span class="date">{{ entry.date }}</span>
    <span class="event">{{ entry.event }}</span>
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
  <a href="{{ '/status/' | relative_url }}">Status</a>
</div>