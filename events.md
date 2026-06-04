---
layout: page
title: Events
description: Upcoming workshops, schools, and meetings.
image: pics/background/damian-karpinski-hfPcaJQQtuY-unsplash.jpg
nav-menu: true
show_tile: true
---

<div class="row">
  <div class="12u">
    <p>
      Upcoming events organised by or involving the Quantera SDP Code consortium.
      Check back regularly — this page is updated as new events are confirmed.
    </p>
  </div>
</div>

---

{% if site.data.events %}
{% assign sorted_events = site.data.events | sort: "date" %}
{% else %}
{% assign sorted_events = "" | split: "" %}
{% endif %}
{% if sorted_events.size == 0 %}
<p><em>No events scheduled yet. Check back soon.</em></p>
{% endif %}
{% for event in sorted_events %}
<div class="box" style="margin-bottom:2rem;">
  <div class="row">
    <div class="2u 12u$(small)" style="text-align:center;">
      {% assign d = event.date | split: "-" %}
      <div style="background:#2e3141;color:#fff;border-radius:8px;padding:.8rem .5rem;display:inline-block;min-width:64px;">
        <div style="font-size:.7rem;text-transform:uppercase;letter-spacing:.05em;">
          {{ event.date | date: "%b" }}
        </div>
        <div style="font-size:2rem;font-weight:700;line-height:1;">
          {{ event.date | date: "%-d" }}
        </div>
        <div style="font-size:.7rem;">
          {{ event.date | date: "%Y" }}
        </div>
      </div>
    </div>
    <div class="10u$ 12u$(small)">
      <h3 style="margin-top:0;">
        {% if event.url and event.url != "" %}
        <a href="{{ event.url }}">{{ event.title }}</a>
        {% else %}
        {{ event.title }}
        {% endif %}
      </h3>
      <p style="margin-bottom:.4rem;">
        <strong>Location:</strong> {{ event.location }}<br/>
        {% if event.end_date and event.end_date != event.date %}
        <strong>Dates:</strong> {{ event.date | date: "%B %-d" }}–{{ event.end_date | date: "%-d, %Y" }}
        {% else %}
        <strong>Date:</strong> {{ event.date | date: "%B %-d, %Y" }}
        {% endif %}
      </p>
      <p style="margin-bottom:.6rem;">{{ event.description }}</p>
      {% if event.tags %}
      {% for tag in event.tags %}
      <span style="display:inline-block;font-size:.75rem;padding:.1rem .5rem;border-radius:12px;background:#f4f4f4;margin:.2rem .2rem 0 0;">{{ tag }}</span>
      {% endfor %}
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}
