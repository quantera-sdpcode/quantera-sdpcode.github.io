---
layout: page
title: About
description: Meet the researchers of the QuantERA SDPCode consortium.
image: pics/background/dawid-labno-VbK9wD-hzqI-unsplash.jpg
nav-menu: true
show_tile: true
---

<div style="max-width:900px; margin: 2.5rem auto 2.5rem; padding: 0 1.5rem;">
  <p style="font-size:1.35rem; line-height:1.75;">
    The <strong>QuantERA SDPCode</strong> consortium unites research groups working at the
    intersection of quantum information theory, semidefinite programming, and algebraic methods.
    Together, we develop new mathematical tools for understanding the power and limits of
    quantum computation and communication.
  </p>
</div>

---

## Researchers

<style>
.researcher-card {
  display: flex;
  align-items: stretch;
  gap: 1.5rem;
  margin-bottom: 2.5rem;
  padding-bottom: 2.5rem;
  border-bottom: 1px solid #e0e0e0;
}
.researcher-card:last-child { border-bottom: none; }

/* Photo is a background-div so it stretches reliably in flexbox */
.researcher-photo {
  flex-shrink: 0;
  width: 220px;
  margin: -0.6rem 0;          /* extend slightly beyond the text column */
  background-size: cover;
  background-position: top center;
  background-color: #dde4ec;
  min-height: 260px;
}
.researcher-photo-placeholder {
  flex-shrink: 0;
  width: 220px;
  min-height: 260px;
  background: #dde4ec;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.5rem;
  color: #8a9bb0;
}
.researcher-info { flex: 1; }
.researcher-info h3 { margin: 0 0 .2rem; }
.researcher-role { font-size: .9rem; color: #555; margin-bottom: .1rem; }
.researcher-institution { font-size: .85rem; color: #777; margin-bottom: .75rem; }
@media (max-width: 600px) {
  .researcher-card { flex-direction: column; align-items: center; text-align: center; }
  .researcher-photo { width: 100%; margin: 0; min-height: 240px; }
}
</style>

{% for team in site.data.teams %}
<div class="researcher-card">
  {% if team.image and team.image != "" %}
  <div class="researcher-photo"
       style="background-image: url('{{ team.image | relative_url }}');
              background-position: {{ team.image_position | default: 'top center' }};"></div>
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
    {% if team.arxiv and team.arxiv != "" %}
    <a href="{{ team.arxiv }}" class="button small">arXiv</a>
    {% endif %}
  </div>
</div>
{% endfor %}
