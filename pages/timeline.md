---
layout: page
title: "Timeline"
permalink: /timeline/
---

<div class="strand-note"><strong>Issues evidenced here:</strong> Issues <a href="{{ '/issues/' | relative_url }}#issue-36">36</a>–<a href="{{ '/issues/' | relative_url }}#issue-38">38</a>, <a href="{{ '/issues/' | relative_url }}#issue-46">46</a> (document backdating — addresses and metadata); Issues <a href="{{ '/issues/' | relative_url }}#issue-1">1</a>–<a href="{{ '/issues/' | relative_url }}#issue-2">2</a> (no CHC/FNC referral for two years); Issue <a href="{{ '/issues/' | relative_url }}#issue-23">23</a> (DPA names wrong care home); Issue <a href="{{ '/issues/' | relative_url }}#issue-6">6</a> (undisclosed 'Mercy' meeting).</div>

---

## Summary {#summary}

<p>Chronological record from Bridget's dementia diagnosis in May 2015 to the active LGSCO investigation. The first care home placement was entirely self-funded; Council involvement began formally in September 2022 — two years after the Care Act s.13 triggering event. The timeline spans four placements, six CHC checklists, and a 45-month period in which the Council had no documented involvement.</p>

<div class="tl-summary-grid">
  <div class="tl-summary-card">
    <span class="n">{{ site.data.placement.size }}</span>
    <span class="lbl">Care home placements</span>
  </div>
  <div class="tl-summary-card">
    <span class="n">6</span>
    <span class="lbl">CHC checklists</span>
  </div>
  <div class="tl-summary-card">
    <span class="n">{{ site.data.issues.size }}</span>
    <span class="lbl">Registered issues</span>
  </div>
  <div class="tl-summary-card">
    <span class="n">45+</span>
    <span class="lbl">Months without Council care plan</span>
  </div>
  <div class="tl-summary-card">
    <span class="n">13+</span>
    <span class="lbl">Months covert medication without MCA</span>
  </div>
  <div class="tl-summary-card">
    <span class="n">2019</span>
    <span class="lbl">SMI exemption granted — no follow-up</span>
  </div>
</div>

### Placement overview

<table>
  <thead>
    <tr>
      <th>Period</th>
      <th>Home</th>
      <th>Registration</th>
      <th>Council rate</th>
      <th>Billed to family</th>
      <th>Funding basis</th>
    </tr>
  </thead>
  <tbody>
    {% for p in site.data.placement %}
    <tr>
      <td class="nowrap">{{ p.date-start }} &rarr; {{ p.date-end }}</td>
      <td><a href="#placement-{{ p.home | slugify }}"><strong>{{ p.home }}</strong></a></td>
      <td><small>{{ p.type }}</small></td>
      <td class="nowrap">{{ p.weekly-fee-council }}</td>
      <td class="nowrap">{{ p.weekly-fee-billed }}</td>
      <td><small>{{ p.funding | split: "." | first }}</small></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

---

## Navigate {#navigate}

<p style="margin-bottom:4px"><strong>By year</strong></p>
<div class="cat-jump" style="margin-bottom:1em">
  <a href="#year-pre2020">Pre-2020</a>
  <a href="#year-2020">2020</a>
  <a href="#year-2021">2021</a>
  <a href="#year-2022">2022</a>
  <a href="#year-2023">2023</a>
  <a href="#year-2024">2024</a>
  <a href="#year-2025">2025</a>
  <a href="#year-2026">2026</a>
</div>

<p style="margin-bottom:4px"><strong>By placement</strong></p>
<div class="cat-jump" style="margin-bottom:1.5em">
  {% for p in site.data.placement %}
  <a href="#placement-{{ p.home | slugify }}">{{ p.home }}</a>
  {% endfor %}
</div>

---


<ul class="timeline">
  {% for entry in site.data.timeline %}

  {% if entry.type == 'year-header' %}
    <li class="tl-year-header" id="{{ entry.anchor }}">
      <div class="tl-year-header-inner">
        <span class="tl-year-label">{{ entry.label }}</span>
        {% if entry.description %}<span class="tl-year-desc">{{ entry.description }}</span>{% endif %}
      </div>
    </li>

  {% elsif entry.type == 'placement' %}
    {% assign p = site.data.placement | where: "home", entry.placement-name | first %}
    {% if p %}
    <li class="placement-block" id="placement-{{ entry.placement-name | slugify }}">
      <div class="placement-block-inner">
        <div class="placement-name">{{ p.home }}</div>
        <div class="placement-meta">
          <span>{{ p.date-start }} &rarr; {{ p.date-end }}</span>
          <span class="placement-pipe">|</span>
          <span>{{ p.type }}</span>
          <span class="placement-pipe">|</span>
          <span>{{ p.funding | split: "." | first }}</span>
        </div>
        <div class="placement-rates">
          <span><strong>Council rate:</strong> {{ p.weekly-fee-council }}</span>
          <span class="placement-pipe">|</span>
          <span><strong>Billed to family:</strong> {{ p.weekly-fee-billed }}</span>
        </div>
        <div class="placement-about"><small>{{ p.about }}</small></div>
      </div>
    </li>
    {% endif %}

  {% else %}

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
        {% if related.size > 0 or entry.email-refs or entry.evidence-refs or entry.year-refs %}
        <span class="tl-issue-refs">
          {% for issue in related %}<a class="issue-badge {% if issue.severity == 'high' %}issue-badge-high{% elsif issue.severity == 'medium' %}issue-badge-med{% endif %}" href="{{ '/issues/' | relative_url }}#issue-{{ issue.num }}" title="{{ issue.issue | truncate: 80 }}">#{{ issue.num }}</a>{% endfor %}
          {% for slug in entry.email-refs %}
            {% assign epost = site.posts | where_exp: "p", "p.url contains slug" | first %}
            {% if epost %}<a class="tl-email-badge" href="{{ epost.url | relative_url }}" title="{{ epost.title }}">&#9993; {{ epost.from | split: " (" | first }}</a>{% endif %}
          {% endfor %}
          {% for evid in entry.evidence-refs %}
            {% assign evitem = site.data.evidence | where: "id", evid | first %}
            {% if evitem %}<a class="tl-doc-badge" href="{{ '/evidence/' | relative_url }}#ev-{{ evid }}" title="{{ evitem.item }}">&#128196; {{ evitem.item | truncate: 35 }}</a>{% endif %}
          {% endfor %}
          {% for yr in entry.year-refs %}
            <a class="tl-year-badge" href="{{ yr.url | relative_url }}">&#128205; {{ yr.label }}</a>
          {% endfor %}
        </span>
        {% endif %}
      </span>
    </li>

  {% endif %}
  {% endfor %}
</ul>

<div class="cat-jump" style="margin-top:2em">
  <a href="#summary">Summary</a>
  <a href="#navigate">Navigate</a>
  <a href="{{ '/' | relative_url }}">Case Summary</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Clinical Record</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
</div>
