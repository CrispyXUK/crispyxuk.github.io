---
layout: default
title: "DST Domain Analysis"
permalink: /dst/
---

<p class="lead">NHS Decision Support Tool, multi-disciplinary team meeting of 29 August 2025 (ICB Ref {{ site.case_ref_icb }}).</p>

<p>The disclosed DST is <strong>Section 2 only</strong> (domain scoring). Section 1 and the MDT narrative reasoning have not been provided and must be obtained. In the table below, <span class="amber">amber</span> marks a score that may be understated; <span class="red">red</span> marks a score directly contradicted by contemporaneous evidence.</p>

<table>
  <thead>
    <tr><th>Domain</th><th>Awarded</th><th>Correct?</th><th>Challenge basis</th></tr>
  </thead>
  <tbody>
    {% for d in site.data.dst %}
    <tr{% if d.flag == 'amber' %} class="amber"{% elsif d.flag == 'red' %} class="red"{% endif %}>
      <td>{{ d.domain }}</td>
      <td class="score-{{ d.awarded }}">{{ d.awarded }}</td>
      <td class="score-{{ d.correct }}">{{ d.correct }}</td>
      <td>{{ d.challenge }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<p>Under the National Framework (paras 35–37), a profile of Severe&nbsp;×1 alongside multiple Highs is a strong indicator for CHC that requires clear, documented reasoning to rebut. No such reasoning has been disclosed. With the Communication domain corrected from Moderate to High, the profile becomes Severe&nbsp;×1, High&nbsp;×4, Moderate&nbsp;×3 — strengthening the indicator further.</p>