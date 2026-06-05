---
layout: page
title: "Timeline"
permalink: /timeline/
---

<div class="strand-note"><strong>Issues evidenced here:</strong> Issues <a href="{{ '/issues/' | relative_url }}#issue-36">36</a>–<a href="{{ '/issues/' | relative_url }}#issue-38">38</a>, <a href="{{ '/issues/' | relative_url }}#issue-46">46</a> (document backdating — addresses and metadata); Issues <a href="{{ '/issues/' | relative_url }}#issue-1">1</a>–<a href="{{ '/issues/' | relative_url }}#issue-2">2</a> (no CHC/FNC referral for two years); Issue <a href="{{ '/issues/' | relative_url }}#issue-23">23</a> (DPA names wrong care home); Issue <a href="{{ '/issues/' | relative_url }}#issue-6">6</a> (undisclosed 'Mercy' meeting).</div>

<ul class="timeline">
  {% for entry in site.data.timeline %}

  {% if entry.type == 'placement' %}
    {% assign p = site.data.placement | where: "home", entry.placement-name | first %}
    {% if p %}
    <li class="placement-block">
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
        {% if related.size > 0 or entry.email-refs or entry.evidence-refs %}
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
        </span>
        {% endif %}
      </span>
    </li>

  {% endif %}
  {% endfor %}
</ul>

<div class="cat-jump">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>
