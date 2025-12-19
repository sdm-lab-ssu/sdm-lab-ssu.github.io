---
layout: page
title: Faculty
permalink: /faculty/
---

{% assign faculty = site.people | where: "role", "Professor" %}

<div class="row">
  {% for p in faculty %}
    <div class="col-12" style="margin-bottom:24px;">
      <div style="display:flex; gap:20px; align-items:flex-start; padding:18px; border:1px solid #eee; border-radius:16px;">
        <a href="{{ p.url | relative_url }}" style="flex:0 0 auto;">
          <img src="{{ p.photo | relative_url }}"
               alt="{{ p.title }}"
               style="width:220px; height:220px; object-fit:cover; border-radius:16px;">
        </a>

        <div style="flex:1 1 auto;">
          <div style="font-size:1.6em; font-weight:800; margin-bottom:6px;">
            <a href="{{ p.url | relative_url }}">{{ p.title }}</a>
          </div>

          {% if p.interests %}
            <div style="font-size:1.05em; color:#555; margin-bottom:10px;">
              {{ p.interests | join: ", " }}
            </div>
          {% endif %}

          {% if p.email %}
            <div style="font-size:1.0em;">
              <a href="mailto:{{ p.email }}">{{ p.email }}</a>
            </div>
          {% endif %}

          {% if p.links %}
            <div style="margin-top:10px;">
              {% for l in p.links %}
                <a href="{{ l[1] }}" target="_blank" rel="noopener" style="margin-right:12px;">{{ l[0] }}</a>
              {% endfor %}
            </div>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
