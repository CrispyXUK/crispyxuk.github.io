---
layout: default
title: "Emails"
permalink: /emails/
---

<p class="lead">Contemporaneous email evidence, annotated with significance and cross-referenced to the issue register and timeline. Oldest first.</p>

{% assign posts_sorted = site.posts | sort: 'date' %}

<table>
  <thead>
    <tr>
      <th style="width:120px">Date</th>
      <th>Subject</th>
      <th>From</th>
      <th>Category</th>
      <th>Issues</th>
    </tr>
  </thead>
  <tbody>
    {% for post in posts_sorted %}
    <tr>
      <td style="white-space:nowrap">{{ post.email-date }}</td>
      <td><a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a></td>
      <td>{{ post.from }}</td>
      <td>{{ post.category }}</td>
      <td>
        {% for issue_num in post.related-issues %}
          <a href="{{ '/issues/' | relative_url }}#issue-{{ issue_num }}" class="issue-badge">#{{ issue_num }}</a>
        {% endfor %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<div class="cat-jump">
  <a href="{{ '/' | relative_url }}">Summary</a>
  <a href="{{ '/timeline/' | relative_url }}">Timeline</a>
  <a href="{{ '/issues/' | relative_url }}">Issue Register</a>
  <a href="{{ '/document-integrity/' | relative_url }}">Document Integrity</a>
  <a href="{{ '/dst/' | relative_url }}">DST Analysis</a>
  <a href="{{ '/parties/' | relative_url }}">Key Parties</a>
  <a href="{{ '/evidence/' | relative_url }}">Evidence</a>
  <a href="{{ '/clinical/' | relative_url }}#status">Status</a>
</div>