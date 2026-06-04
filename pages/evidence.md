---
layout: default
title: "Evidence Overview"
permalink: /evidence/
---

<p class="lead">{{ site.data.evidence | where: "obtained", true | size }} items in hand across four categories. {{ site.data.evidence | where: "obtained", false | size }} items outstanding.</p>

<div class="cat-jump">
  <a href="#documentary">Documentary</a>
  <a href="#public">Public Records</a>
  <a href="#contemporaneous">Contemporaneous</a>
  <a href="#forensic">Forensic / Technical</a>
  <a href="#outstanding">Outstanding</a>
</div>

{% assign type_order = "documentary,public,contemporaneous,forensic" | split: "," %}
{% assign type_labels = "documentary:Documentary & Email Evidence,public:Public Records,contemporaneous:Contemporaneous Evidence,forensic:Forensic / Technical Evidence" | split: "," %}

{% for type_slug in type_order %}
  {% assign obtained_items = site.data.evidence | where: "type", type_slug | where: "obtained", true %}
  {% if obtained_items.size > 0 %}

  {% assign label = type_slug %}
  {% for pair in type_labels %}
    {% assign parts = pair | split: ":" %}
    {% if parts[0] == type_slug %}{% assign label = parts[1] %}{% endif %}
  {% endfor %}

<hr>
<h2 id="{{ type_slug }}">{{ label }}</h2>

<table>
  <thead>
    <tr>
      <th>Item</th>
      <th style="width:140px">Date</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    {% for e in obtained_items %}
    <tr>
      <td>{{ e.item }}</td>
      <td style="white-space:nowrap"><small>{{ e.date }}</small></td>
      <td><small>{{ e.note }}</small></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

  {% endif %}
{% endfor %}

<hr>
<h2 id="outstanding">Documents Still to Obtain</h2>

<table>
  <thead>
    <tr>
      <th>Item</th>
      <th style="width:140px">Date / period</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    {% assign outstanding = site.data.evidence | where: "obtained", false %}
    {% for e in outstanding %}
    <tr style="background:#FCE4D6">
      <td>{{ e.item }}</td>
      <td style="white-space:nowrap"><small>{{ e.date }}</small></td>
      <td><small>{{ e.note }}</small></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>
