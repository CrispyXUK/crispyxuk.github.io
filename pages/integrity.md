---
layout: default
title: "Document Integrity"
permalink: /document-integrity/
---

<ol class="list-group list-group-horizontal">
{% for document in site.data.integrity %}
<li class="list-group-item d-flex justify-content-between align-items-start">
    <div class="ms-2 me-auto"></div>
      <div><b>Document Name: </b>{{ document.document }} (Dated) - {{ document.stated }}</div>
      <div><b>Listed Age</b> {{ document.age }}</div>
      <div><b>Placement listed</b> {{ document.address }}</div>
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