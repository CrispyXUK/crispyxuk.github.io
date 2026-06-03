---
layout: default
title: "Timeline"
permalink: /timeline/
---

<h2>Placement Timeline</h2>

<ol class="list-group list-group-horizontal">
{% for home in site.data.placement %}
<li class="list-group-item d-flex justify-content-between align-items-start">
    <div class="ms-2 me-auto">
      <div class="fw-bold">{{ home.home }} {{ home.date-start }} {{ home.date-end }}</div>
      <div>{{ home.about }}</div>
    </div>
  </li>
  {% endfor %}
</ol>

<hr>
<h2>General Timeline</h2>

<p class="lead">Private evidential record supporting the LGSCO investigation into Southend-on-Sea City Council's Adult Social Care handling of Mrs Bridget Penelope Walker's care, funding, and assessment.</p>

<ol class="list-group list-group-horizontal">
{% for date in site.data.timeline %}
<li class="list-group-item d-flex justify-content-between align-items-start">
    <div class="ms-2 me-auto">
      <div class="fw-bold">{{ date.date }}</div>
      {{ date.event }}
    </div>
  </li>
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