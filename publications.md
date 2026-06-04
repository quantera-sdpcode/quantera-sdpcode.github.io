---
layout: page
title: Publications
description: Selected publications from consortium members.
image: pics/background/kateryna-melnyk-6XZZns74XGc-unsplash.jpg
nav-menu: true
show_tile: true
---

<div class="row">
  <div class="12u">
    <p>
      Publications by Quantera SDPCode consortium members, listed in reverse chronological order.
      Preprints are available on <a href="https://arxiv.org">arXiv</a>; click the links below.
    </p>
  </div>
</div>

---

{% if site.data.publications %}
{% assign pubs_by_year = site.data.publications | group_by: "year" | sort: "name" | reverse %}
{% else %}
{% assign pubs_by_year = "" | split: "" %}
{% endif %}
{% if pubs_by_year.size == 0 %}
<p><em>No publications listed yet.</em></p>
{% endif %}
{% for year_group in pubs_by_year %}
<h2>{{ year_group.name }}</h2>
<div class="table-wrapper">
  <table>
    <tbody>
      {% for pub in year_group.items %}
      <tr>
        <td>
          <strong>{{ pub.title }}</strong><br/>
          <em>{{ pub.authors }}</em><br/>
          {{ pub.venue }}
          <br/>
          {% if pub.tags %}
          {% for tag in pub.tags %}
          <span style="display:inline-block;font-size:.75rem;padding:.1rem .5rem;border-radius:12px;background:#f4f4f4;margin:.2rem .2rem 0 0;">{{ tag }}</span>
          {% endfor %}
          {% endif %}
          <br/>
          {% if pub.arxiv and pub.arxiv != "" %}
          <a href="{{ pub.arxiv }}" class="button small" style="margin-top:.5rem;">arXiv</a>
          {% endif %}
          {% if pub.doi and pub.doi != "" %}
          <a href="{{ pub.doi }}" class="button small" style="margin-top:.5rem;">DOI</a>
          {% endif %}
        </td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>
{% endfor %}
