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

## The proof

<p><strong>Address:</strong> Bridget moved to Palmerston House on 11 April 2023, confirmed by the Council's own Individual Placement Contract (created 13 April 2023). Every document above dated before that date records Palmerston House as her current address — which is logically impossible for a contemporaneous record.</p>

<p><strong>Age:</strong> Bridget's correct age was 71 in late 2022, 72 in 2023, and 73 in 2024. All checklists record age 75, which corresponds to late 2025 or 2026 — the period when the documents were reviewed and disputed. The July 2025 Care &amp; Support Plan Review by the same assessor correctly records age 74, proving the system held the correct age.</p>

<p><strong>Metadata:</strong> The June 2025 checklist PDF carries creation metadata of 5 March 2026 — six days before the documents were first disclosed to the family on 11 March 2026. The DPA was scanned 17 May 2023, two days before its stated execution date of 19 May 2023.</p>

<h2>Individual Placement Contract — <code>Contract_-_Palmerston_2023.doc</code></h2>

<p>The IPC formalising Bridget's placement at Palmerston House was generated on <strong>13 April 2023</strong>, two days after the stated placement date of 11 April 2023. Metadata extracted from the OLE2 compound document reveals automated creation and two distinct council staff accounts.</p>

### Document metadata

<table>
  <thead>
    <tr><th>Property</th><th>Value</th><th>Source</th></tr>
  </thead>
  <tbody>
    <tr><td>Author (creator account)</td><td><strong>Jade Spong</strong></td><td>OLE SummaryInformation stream</td></tr>
    <tr><td>Last Saved By</td><td><strong>vicky raven</strong></td><td>OLE SummaryInformation stream</td></tr>
    <tr><td>Template</td><td><code>res_ind_place.dot</code></td><td>OLE DocumentSummaryInformation</td></tr>
    <tr><td>Create time</td><td>2023-04-13 11:47:00 UTC</td><td>OLE FILETIME</td></tr>
    <tr><td>Last saved time</td><td>2023-04-13 11:47:00 UTC (identical)</td><td>OLE FILETIME</td></tr>
    <tr><td>Total edit time</td><td><strong>0 minutes</strong></td><td>OLE SummaryInformation</td></tr>
    <tr><td>Revision count</td><td>2</td><td>OLE SummaryInformation</td></tr>
    <tr><td>Security flag</td><td>0 (no protection)</td><td>OLE SummaryInformation</td></tr>
    <tr><td>Contact in body</td><td>EmilyEllul@southend.gov.uk</td><td>Document body</td></tr>
    <tr><td>Care Manager in body</td><td>Jacquie Deacon</td><td>Document body</td></tr>
  </tbody>
</table>

### Document content

<table>
  <thead>
    <tr><th>Field</th><th>Value</th></tr>
  </thead>
  <tbody>
    <tr><td>IPC date (stated, appears four times)</td><td>11 April 2023</td></tr>
    <tr><td>Service Provider address</td><td>Palmerston House, <strong>23–25 Palmerston Road</strong>, Westcliff-on-Sea SS0 7TA</td></tr>
    <tr><td>Resident</td><td>Bridget Walker, DOB 08 October 1950</td></tr>
    <tr><td>Person ID</td><td>30000912</td></tr>
    <tr><td>Placement type ticked</td><td><strong>Permanent</strong> (not Temporary / Respite)</td></tr>
    <tr><td>Weekly charge</td><td>£750.00</td></tr>
    <tr><td>Council contribution</td><td>£750.00</td></tr>
    <tr><td>Resident contribution</td><td><strong>TBC</strong></td></tr>
    <tr><td>Signature block</td><td><strong>Unsigned</strong> (three blank signature lines)</td></tr>
  </tbody>
</table>

### Forensic findings

<p><strong>Automated generation, zero edit time.</strong> Create time and Last Saved time are identical to the second. With a revision count of 2 and 0 minutes total edit time, both saves occurred within a single automated operation — consistent with the council's template-population system (<code>res_ind_place.dot</code>) rather than manual drafting. There is no recorded human revision after generation.</p>

<p><strong>Two distinct council accounts.</strong> The document was created under <strong>Jade Spong</strong>'s account and last saved by <strong>vicky raven</strong> — two separate individuals. Neither name currently appears in the key parties list. A SAR should specifically request their job titles and whether either is recorded in Bridget's LiquidLogic case record.</p>

<p><strong>Resident contribution recorded as TBC.</strong> The IPC was issued on 11 April 2023 with the resident's financial contribution unresolved. The Deferred Payment Agreement was not signed until 19 May 2023 — 38 days later. The IPC therefore formalised a <em>permanent</em> placement without a settled financial contribution from the resident. The DPA was presented after the placement had already commenced, undermining any claim that it was freely negotiated in advance.</p>

<p><strong>Address discrepancy — wrong legal entity (<a href="{{ '/issues/' | relative_url }}#issue-41">Issue 41</a>).</strong> The IPC records the service provider as <strong>Palmerston House, 23–25 Palmerston Road</strong>. CQC registration 1-156343233 is at <strong>21 Palmerston Road</strong>, recorded as <em>Interchurch Care Centre</em>. Land Registry confirms these are separately-owned freeholds: 23–25 is owned by Higgins Property Investments Limited (since 2011); No. 21 by Aysen Tekin &amp; Erbil Gulhan (from September 2023, with Lloyds Bank charge). The IPC therefore names the address of a different legal entity from the CQC-registered provider. No explanation has been given. If the contract binds only the owner of 23–25, the registered care home operator at No. 21 may not be party to the placement agreement at all.</p>

### Cross-references

<table>
  <thead>
    <tr><th>Issue</th><th>Detail</th></tr>
  </thead>
  <tbody>
    <tr><td>DPA naming wrong home</td><td>The DPA signed 19 May 2023 names <strong>Westcliff Lodge</strong>, which Bridget had left 38 days before. This IPC confirms Palmerston was already the operative placement when the DPA was executed — the DPA was contractually misaligned from day one.</td></tr>
    <tr><td>IPC designates placement as Permanent</td><td>Undermines any suggestion that the DPA terms were negotiated in advance of a settled arrangement, or that the placement was initially treated as temporary.</td></tr>
    <tr><td>Jacquie Deacon as Care Manager at placement</td><td>Her role at commencement is now formally documented in the IPC metadata and body.</td></tr>
    <tr><td>Executed copy outstanding</td><td>This electronic copy is unsigned. A SAR should specifically request the wet-signed executed IPC and any distribution correspondence.</td></tr>
    <tr><td>EmilyEllul@southend.gov.uk</td><td>Contact named in IPC header — does not currently appear in key parties. Request all correspondence from this address relating to Person ID 30000912, April–June 2023.</td></tr>
  </tbody>
</table>

## Property title: Palmerston Road

<p>HM Land Registry searches on the freehold titles covering the care home site establish the legal ownership position and flag a name discrepancy: Land Registry records the building at No. 21 as <em>Interchurch Care Centre</em>, not "Palmerston House" — the name used in every Council and ICB document.</p>

<table>
  <thead>
    <tr>
      <th>Title</th>
      <th>Address</th>
      <th>Registered name</th>
      <th>Registered owner</th>
      <th>Ownership from</th>
      <th>Charges</th>
      <th>HMLR search date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="nowrap">EX240310</td>
      <td class="nowrap">21 Palmerston Road,<br>Westcliff-on-Sea SS0 7TA</td>
      <td>Interchurch Care Centre</td>
      <td>Aysen Tekin &amp; Erbil Gulhan</td>
      <td class="nowrap">18 Sep 2023</td>
      <td>Lloyds Bank PLC charge registered 18 Sep 2023 (dated 6 Sep 2023)</td>
      <td class="nowrap">18 Feb 2026</td>
    </tr>
    <tr>
      <td class="nowrap">EX298329</td>
      <td class="nowrap">23–25 Palmerston Road,<br>Westcliff-on-Sea SS0 7TA</td>
      <td>—</td>
      <td>Higgins Property Investments Limited<br><small>Co. 07537873, 117 Vicarage Hill, Benfleet SS7 1PD</small></td>
      <td class="nowrap">13 Apr 2011</td>
      <td>None recorded</td>
      <td class="nowrap">3 Apr 2026</td>
    </tr>
  </tbody>
</table>

<p><strong>Significant:</strong> The current owners of No. 21 were registered on 18 September 2023 — five months <em>after</em> Bridget moved in on 11 April 2023. The Lloyds Bank charge was secured at the same time (6 September 2023), indicating a mortgage or lending facility taken out at the point of transfer. No. 21 last sold for £546,000 on 19 July 2010. The Council's placement documentation consistently refers to the facility as "Palmerston House"; the Land Registry title describes it as "Interchurch Care Centre" — a name discrepancy that has not been explained in correspondence.</p>

<div class="cat-jump">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>