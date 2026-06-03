---
layout: default
title: "Key Parties"
permalink: /parties/
---

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