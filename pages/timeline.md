---
layout: default
title: "Timeline"
permalink: /timeline/
---

<p class="lead">Private evidential record supporting the LGSCO investigation into Southend-on-Sea City Council's Adult Social Care handling of Mrs Bridget Penelope Walker's care, funding, and assessment.</p>

<div class="summary-grid">
  <div class="card"><span class="n">{{ site.data.issues | size }}</span><span class="l">issues catalogued across seven categories</span></div>
  <div class="card"><span class="n">{{ site.data.timeline | size }}</span><span class="l">timeline events (Apr 2020 – May 2026)</span></div>
  <div class="card"><span class="n">11</span><span class="l">DST domains analysed</span></div>
</div>

<h2>Timeline</h2>

<ul>
{% for date in site.data.timeline %}
  <li>
    <a href="https://github.com/{{ member.github }}">
      {{ member.name }}
    </a>
  </li>
{% endfor %}
</ul>

<ul class="list-group list-group-horizontal">
{% for date in site.data.timeline %}
  <li class="list-group-item">{{ timeline.date }}</li>
  <li class="list-group-item">{{ timeline.event }}</li>
  <li class="list-group-item">A third item</li>
</ul>

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