---
layout: page
title: About
description: Meet the researchers of the Quantera SDP Code consortium.
image: assets/images/about-banner.jpg
nav-menu: true
show_tile: true
---

<div class="row">
  <div class="12u">
    <p>
      The <strong>Quantera SDP Code</strong> consortium unites research groups working at the
      intersection of quantum information theory, semidefinite programming, and algebraic methods.
      Together, we develop new mathematical tools for understanding the power and limits of
      quantum computation and communication.
    </p>
  </div>
</div>

---

## Researchers

{% for team in site.data.teams %}
<div class="box" style="margin-bottom:2rem;">
  <h3>{{ team.name }}</h3>
  <p><strong>{{ team.role }}</strong><br/>{{ team.institution }}</p>
  <p>{{ team.description }}</p>
  {% if team.website and team.website != "" %}
  <p><a href="{{ team.website }}" class="button small">Website</a></p>
  {% endif %}
</div>
{% endfor %}
