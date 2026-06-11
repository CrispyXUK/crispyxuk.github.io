---
layout: page
title: "Key Parties"
permalink: /parties/
---

{% include bio-content.html %}

---

## Key parties in the investigation

<table>
  <thead>
    <tr><th>Name / Role</th><th>Details</th></tr>
  </thead>
  <tbody>
    {% for p in site.data.parties %}
    <tr><td class="cat">{{ p.name }}</td><td>{{ p.detail }}</td></tr>
    {% endfor %}
  </tbody>
</table>

<div class="cat-jump">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/bio/' | relative_url }}">About Bridget</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>
