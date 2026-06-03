---
layout: default
title: "List of Issues"
permalink: /issues/
---

<div class="summary-grid">
  <div class="card"><span class="n">{{ site.data.issues | size }}</span><span class="l">issues catalogued across seven categories</span></div>
  <div class="card"><span class="n">{{ site.data.timeline | size }}</span><span class="l">timeline events (Apr 2020 – May 2026)</span></div>
  <div class="card"><span class="n">11</span><span class="l">DST domains analysed</span></div>
</div>

<ol class="list-group list-group-horizontal">
{% for num in site.data.issues %}
<li class="list-group-item d-flex justify-content-between align-items-start">
    <div class="ms-2 me-auto"></div>
      <div class="fw-bold">{{ num.category }}</div>
      <div>{{ num.issue }}</div>
      <div><b>Evidence</b> {{ num.evidence }}</div>
  </li>
  <hr>
  {% endfor %}
</ol>


<h2>Navigate</h2>
<div class="cat-jump">
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/status/' | relative_url }}">Status</a>
</div>