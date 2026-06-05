---
layout: page
title: "Document Integrity"
permalink: /document-integrity/
---

<p class="lead">Each document below records Palmerston House as Bridget's current address. The placement data confirms when she actually moved there. A current-address field cannot contain a future address — each document marked <strong style="background:#FCE4D6;padding:2px 5px;">impossible</strong> was either created after the move and backdated, or populated from a future-dated system entry.</p>

<div class="strand-note"><strong>Issues evidenced here:</strong> Issues <a href="{{ '/issues/' | relative_url }}#issue-36">36</a>–<a href="{{ '/issues/' | relative_url }}#issue-39">39</a>, <a href="{{ '/issues/' | relative_url }}#issue-46">46</a> — the strongest single evidential strand. Future addresses on past documents, PDF creation dates post-dating stated execution, and documents withheld until after the LGSCO referral. Directly supports a finding of deliberate backdating.</div>

<table>
  <thead>
    <tr>
      <th>Document</th>
      <th>Stated date</th>
      <th>Age shown / correct</th>
      <th>Address recorded</th>
      <th>Actual placement on stated date</th>
      <th>Impossible?</th>
    </tr>
  </thead>
  <tbody>
    {% for document in site.data.integrity %}
    <tr{% if document.impossible == 'yes' %} class="red"{% elsif document.impossible == 'partial' %} class="amber"{% endif %}>
      <td><strong>{{ document.document }}</strong></td>
      <td class="nowrap">{{ document.stated }}</td>
      <td>{{ document.age }}</td>
      <td>{{ document.address }}</td>
      <td>
        {% assign doc_date = document.stated %}
        {% for home in site.data.placement %}
          {% if doc_date contains "2022" and home.home == "Westcliff Lodge" %}
            <strong class="text-navy">{{ home.home }}</strong><br>
            <small>{{ home.date-start }} to {{ home.date-end }}</small>
          {% elsif doc_date contains "Feb 2023" or doc_date contains "22 Feb" or doc_date contains "01 Feb" or doc_date contains "1 Feb" %}
            {% if home.home == "Westcliff Lodge" %}
            <strong class="text-navy">{{ home.home }}</strong><br>
            <small>{{ home.date-start }} to {{ home.date-end }}</small>
            {% endif %}
          {% elsif doc_date contains "2024" and home.home == "Palmerston House" %}
            <strong class="text-navy">{{ home.home }}</strong><br>
            <small>{{ home.date-start }} to {{ home.date-end }}</small>
          {% elsif doc_date contains "2025" and home.home == "Palmerston House" %}
            <strong class="text-navy">{{ home.home }}</strong><br>
            <small>{{ home.date-start }} to {{ home.date-end }}</small>
          {% endif %}
        {% endfor %}
      </td>
      <td class="tc-bold">
        {% if document.impossible == 'yes' %}
          <span class="flag-yes">YES</span>
        {% elsif document.impossible == 'partial' %}
          <span class="flag-partial">AGE ONLY</span>
        {% else %}
          <span class="flag-no">No</span>
        {% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<h2>The proof</h2>

<p><strong>Address:</strong> Bridget moved to Palmerston House on 11 April 2023, confirmed by the Council's own Individual Placement Contract (created 13 April 2023). Every document above dated before that date records Palmerston House as her current address — which is logically impossible for a contemporaneous record.</p>

<p><strong>Age:</strong> Bridget's correct age was 71 in late 2022, 72 in 2023, and 73 in 2024. All checklists record age 75, which corresponds to late 2025 or 2026 — the period when the documents were reviewed and disputed. The July 2025 Care &amp; Support Plan Review by the same assessor correctly records age 74, proving the system held the correct age.</p>

<p><strong>Metadata:</strong> The June 2025 checklist PDF carries creation metadata of 5 March 2026 — six days before the documents were first disclosed to the family on 11 March 2026. The DPA was scanned 17 May 2023, two days before its stated execution date of 19 May 2023.</p>

<div class="cat-jump">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>