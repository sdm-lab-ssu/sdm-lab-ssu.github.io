---
layout: page
title: Photos
subtitle:
permalink: /photos/
---

<div id="photos-page">
  {% for event in site.data.photos %}
  <div class="photo-event">
    <h2 class="photo-event-title">{{ event.title_kr }}</h2>
    <p class="photo-event-meta">{{ event.title }} &middot; {{ event.date }}</p>
    <div class="photo-grid">
      {% for photo in event.photos %}
      <div class="photo-grid-item">
        <a href="/img/photos/{{ event.id }}/{{ photo.file }}" target="_blank">
          <img src="/img/photos/{{ event.id }}/{{ photo.file }}" alt="{{ photo.caption | default: event.title_kr }}">
        </a>
        {% if photo.caption and photo.caption != "" %}
        <p class="photo-grid-caption">{{ photo.caption }}</p>
        {% endif %}
      </div>
      {% endfor %}
    </div>
  </div>
  {% endfor %}
</div>
