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

<style>
.researcher-card {
  display: flex;
  align-items: flex-start;
  gap: 1.5rem;
  margin-bottom: 2.5rem;
  padding-bottom: 2.5rem;
  border-bottom: 1px solid #e0e0e0;
}
.researcher-card:last-child { border-bottom: none; }
.researcher-photo {
  flex-shrink: 0;
  width: 130px;
  height: 130px;
  border-radius: 50%;
  object-fit: cover;
  object-position: top;
  background: #dde4ec;
}
.researcher-photo-placeholder {
  flex-shrink: 0;
  width: 130px;
  height: 130px;
  border-radius: 50%;
  background: #dde4ec;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.5rem;
  color: #8a9bb0;
}
.researcher-info h3 { margin: 0 0 .2rem; }
.researcher-role { font-size: .9rem; color: #555; margin-bottom: .1rem; }
.researcher-institution { font-size: .85rem; color: #777; margin-bottom: .75rem; }
@media (max-width: 600px) {
  .researcher-card { flex-direction: column; align-items: center; text-align: center; }
}
</style>

{% for team in site.data.teams %}
<div class="researcher-card">
  {% if team.image and team.image != "" %}
  <img class="researcher-photo" src="{{ team.image | relative_url }}" alt="{{ team.name }}" />
  {% else %}
  <div class="researcher-photo-placeholder">&#9786;</div>
  {% endif %}
  <div class="researcher-info">
    <h3>{{ team.name }}</h3>
    <p class="researcher-role">{{ team.role }}</p>
    <p class="researcher-institution">{{ team.institution }}</p>
    <p>{{ team.description }}</p>
    {% if team.website and team.website != "" %}
    <a href="{{ team.website }}" class="button small">Website</a>
    {% endif %}
  </div>
</div>
{% endfor %}
