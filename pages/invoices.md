---
layout: page
title: "Council Invoices"
permalink: /invoices/
---

<p class="lead">Income-contribution invoices issued by Southend-on-Sea City Council to Mrs Bridget Walker (Customer C42983, Adult Res Finance). These are <strong>contribution invoices</strong> — the resident's assessed income contribution billed directly to the family. They do not represent the total care home fee; the balance between the care home's weekly rate and this contribution is deferred under the DPA and accrues against 84 Bellhouse Road.</p>

<div class="strand-note"><strong>Issues evidenced here:</strong> Issue <a href="{{ '/issues/' | relative_url }}#issue-19">19</a> (overcharge vs Council's own contractual rate); Issue <a href="{{ '/issues/' | relative_url }}#issue-27">27</a> (combined contributions and deferred charges exceeded actual fee); Issue <a href="{{ '/issues/' | relative_url }}#issue-28">28</a> (double-payment); Issue <a href="{{ '/issues/' | relative_url }}#issue-25">25</a> (charges at Palmerston lack contractual authority — DPA names Westcliff Lodge). Scans provided are incomplete — at least one invoice period is unaccounted for.</div>

<div class="cat-jump">
  <a href="#rates">Contribution Rate History</a>
  <a href="#register">Invoice Register</a>
</div>

---

## Contribution Rate History {#rates}

<p>The income contribution (the amount billed directly from income) changed five times across the placement period. Each change reflects a financial reassessment. No FA letter or assessment document has been disclosed to the family for any of these changes.</p>

<table>
  <thead>
    <tr>
      <th>Period</th>
      <th>Location</th>
      <th class="tc">Rate (£/wk)</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>27/09/2022 – 24/10/2022</td>
      <td>Westcliff Lodge</td>
      <td class="tc">£379.68</td>
      <td>12-week disregard period</td>
    </tr>
    <tr class="amber">
      <td>25/10/2022 – 19/12/2022</td>
      <td>Westcliff Lodge</td>
      <td class="tc">£317.83</td>
      <td>Basis for this rate unclear — no FA letter disclosed</td>
    </tr>
    <tr>
      <td>20/12/2022 – 09/04/2023</td>
      <td>Westcliff Lodge</td>
      <td class="tc">£800.00</td>
      <td>DPA purportedly commences 19 Dec 2022 — rate rises to full billed amount</td>
    </tr>
    <tr class="red">
      <td>10/04/2023</td>
      <td>Westcliff Lodge</td>
      <td class="tc">£877.59</td>
      <td><strong>ANOMALY</strong> — last day at Westcliff Lodge billed at Palmerston rate. Palmerston rate applied one day early.</td>
    </tr>
    <tr class="amber">
      <td>11/04/2023 – 30/04/2023</td>
      <td>Palmerston</td>
      <td class="tc">£750.00</td>
      <td>First period at Palmerston — billed at full IPC rate, no FA completed at transfer</td>
    </tr>
    <tr>
      <td>01/05/2023 – 04/02/2024</td>
      <td>Palmerston</td>
      <td class="tc">£416.38</td>
      <td>FA completed post-transfer — income contribution assessed</td>
    </tr>
    <tr class="amber">
      <td>05/02/2024 – 07/04/2024</td>
      <td>Palmerston</td>
      <td class="tc">£363.70</td>
      <td>Reassessment — rate reduced. No FA letter disclosed.</td>
    </tr>
    <tr class="amber">
      <td>08/04/2024 – 06/04/2025</td>
      <td>Palmerston</td>
      <td class="tc">£384.13</td>
      <td>Reassessment — rate increased. No FA letter disclosed.</td>
    </tr>
    <tr class="amber">
      <td>07/04/2025 onwards</td>
      <td>Palmerston</td>
      <td class="tc">£395.56</td>
      <td>Reassessment — rate increased. No FA letter disclosed.</td>
    </tr>
  </tbody>
</table>

---

## Invoice Register {#register}

<p>Rows in <strong style="background:#FCE4D6;padding:0 4px;">red</strong> contain anomalies requiring explanation. Rows in <strong style="background:#FFF2CC;padding:0 4px;">amber</strong> show rate changes or unexplained billing. A missing invoice period is flagged in red.</p>

<table>
  <thead>
    <tr>
      <th>Invoice</th>
      <th>Invoice date</th>
      <th>Period from</th>
      <th>Period to</th>
      <th>Location</th>
      <th class="tc">Rate (£/wk)</th>
      <th class="tc">Amount (£)</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    {% assign all_invoices = site.invoices | sort: "date" %}
    {% for inv in all_invoices %}
    {% for line in inv.lines %}
    <tr{% if inv.flag == 'red' %} class="red"{% elsif inv.flag == 'amber' %} class="amber"{% endif %}>
      {% if forloop.first %}
      <td rowspan="{{ inv.lines.size }}">
        <strong><a href="{{ inv.url | relative_url }}">{{ inv.invoice-number }}</a></strong>
      </td>
      <td rowspan="{{ inv.lines.size }}" class="nowrap">{{ inv.invoice-date }}</td>
      {% endif %}
      <td class="nowrap">{{ line.from }}</td>
      <td class="nowrap">{{ line.to }}</td>
      <td>{{ line.location }}</td>
      <td class="tc">{% if line.rate > 0 %}£{{ line.rate }}{% endif %}</td>
      <td class="tc">{% if line.amount > 0 %}£{{ line.amount }}{% endif %}</td>
      {% if forloop.first %}
      <td rowspan="{{ inv.lines.size }}">
        <small>
          {% if inv.flag == 'red' or inv.flag == 'amber' %}
            <a href="{{ inv.url | relative_url }}">
              {% if inv.flag == 'red' %}<span class="flag-yes">Anomaly</span>{% else %}<span class="flag-partial">Note</span>{% endif %}
            </a>
          {% endif %}
          {% if inv.related-issues %}
            {% for issue_num in inv.related-issues %}
              <a href="{{ '/issues/' | relative_url }}#issue-{{ issue_num }}" class="issue-badge">#{{ issue_num }}</a>
            {% endfor %}
          {% endif %}
        </small>
      </td>
      {% endif %}
    </tr>
    {% endfor %}
    {% if inv.lines.size > 1 or inv.total > 0 %}
    <tr style="background:#f5f5f5;font-weight:600">
      <td colspan="6" style="text-align:right">Invoice total</td>
      <td class="tc">{% if inv.total > 0 %}£{{ inv.total }}{% endif %}</td>
      <td></td>
    </tr>
    {% endif %}
    {% endfor %}
  </tbody>
</table>

<div class="cat-jump" style="margin-top:2em">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/issues/' | relative_url }}#financial-dpa">Financial / DPA Issues</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
</div>
