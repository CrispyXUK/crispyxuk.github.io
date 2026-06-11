---
layout: page
title: "Issue Register"
permalink: /issues/
---

{% assign high_count = site.data.issues | where: "severity", "high"   | size %}
{% assign med_count  = site.data.issues | where: "severity", "medium" | size %}
{% assign low_count  = site.data.issues | where: "severity", "low"    | size %}

<div class="strand-note"><strong>Key cross-references:</strong> Issues <a href="#doc-integrity">36–38</a>, <a href="#issue-46">46</a> (document backdating and withheld disclosure); Issues <a href="#issue-1">1</a>–<a href="#issue-2">2</a> (no CHC / FNC referral at nursing home); Issue <a href="#issue-23">23</a> (DPA names wrong care home); Issue <a href="#issue-6">6</a> (undisclosed meeting); Issues <a href="#issue-54">54</a>–<a href="#issue-55">55</a> (EPUT governance — independent referral duty unexercised; MDT composition not disclosed).</div>

---

## Summary {#summary}

<p>{{ site.data.issues.size }} registered issues across {{ site.data.categories.size }} categories arising from the Council's handling of Bridget Walker's care from 2020 to the present.</p>

<div class="tl-summary-grid">
  <div class="tl-summary-card">
    <span class="n">{{ site.data.issues.size }}</span>
    <span class="lbl">Total registered issues</span>
  </div>
  <div class="tl-summary-card" style="border-left-color:#C00000">
    <span class="n" style="color:#C00000">{{ high_count }}</span>
    <span class="lbl">High severity</span>
  </div>
  <div class="tl-summary-card" style="border-left-color:#C55A11">
    <span class="n" style="color:#C55A11">{{ med_count }}</span>
    <span class="lbl">Medium severity</span>
  </div>
  <div class="tl-summary-card">
    <span class="n">{{ low_count }}</span>
    <span class="lbl">Lower priority</span>
  </div>
  <div class="tl-summary-card">
    <span class="n">{{ site.data.categories.size }}</span>
    <span class="lbl">Categories</span>
  </div>
</div>

### Category breakdown

<table>
  <thead>
    <tr>
      <th>Category</th>
      <th class="tc">Total</th>
      <th class="tc"><span class="sev-high">●</span> High</th>
      <th class="tc"><span class="sev-medium">●</span> Medium</th>
      <th class="tc"><span class="sev-low">●</span> Lower</th>
    </tr>
  </thead>
  <tbody>
    {% for cat in site.data.categories %}
    {% assign cat_issues = site.data.issues | where: "category", cat.slug %}
    {% assign cat_high   = cat_issues | where: "severity", "high"   | size %}
    {% assign cat_med    = cat_issues | where: "severity", "medium" | size %}
    {% assign cat_low    = cat_issues | where: "severity", "low"    | size %}
    <tr>
      <td><a href="#{{ cat.slug }}">{{ cat.label }}</a></td>
      <td class="tc"><strong>{{ cat_issues.size }}</strong></td>
      <td class="tc {% if cat_high > 0 %}sev-high{% endif %}">{{ cat_high }}</td>
      <td class="tc {% if cat_med > 0 %}sev-medium{% endif %}">{{ cat_med }}</td>
      <td class="tc">{{ cat_low }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

---

## Navigate {#navigate}

<div class="cat-jump">
  {% for cat in site.data.categories %}
  <a href="#{{ cat.slug }}">{{ cat.label }}</a>
  {% endfor %}
</div>

---


<ul class="timeline">
{% for cat in site.data.categories %}
  {% assign cat_issues = site.data.issues | where: "category", cat.slug %}

  <li class="tl-year-header" id="{{ cat.slug }}">
    <div class="tl-year-header-inner">
      <span class="tl-year-label">{{ cat.label }}
        <span style="font-weight:400;font-size:.85rem;margin-left:8px;opacity:.75">{{ cat_issues.size }} issue{% if cat_issues.size != 1 %}s{% endif %}</span>
      </span>
      <span class="tl-year-desc">{{ cat.description }}</span>
    </div>
  </li>

  {% for issue in cat_issues %}
  <li class="issue-li{% if issue.severity == 'high' %} key{% endif %}" id="issue-{{ issue.num }}">
    <span class="date">
      <span class="issue-num">#{{ issue.num }}</span>
      <span class="issue-sev sev-{{ issue.severity }}">● {{ issue.severity }}</span>
    </span>
    <span class="event">
      {{ issue.issue }}
      {% if issue.evidence %}
      <small class="issue-evidence"><strong>Evidence:</strong> {{ issue.evidence }}</small>
      {% endif %}
      {% if issue.timeline-refs %}
      <span class="tl-issue-refs">
        {% for ref in issue.timeline-refs %}
          <a class="tl-ref" href="{{ '/timeline/' | relative_url }}#tl-{{ ref }}" title="Timeline: {{ ref }}">&#8599;&nbsp;{{ ref }}</a>
        {% endfor %}
      </span>
      {% endif %}
    </span>
  </li>
  {% endfor %}

{% endfor %}
</ul>

<div class="cat-jump" style="margin-top:2em">
  <a href="#summary">Summary</a>
  <a href="#navigate">Navigate</a>
  <a href="{{ '/' | relative_url }}">Case Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Clinical Record</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
</div>
