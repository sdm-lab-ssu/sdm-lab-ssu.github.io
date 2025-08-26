---
layout: page
title: Members
subtitle:
members:
  - name: Faculty
    list:
      - full: true
        list:
          - name: Jaeseok Huh
            slug: jaeseok_huh
            photo_url: /img/people/jshuh.jpg
            interests: ["RL", "Scheduling"]
  
  - name: PhD Students
    list:
      - full: true
        list:
           - name: Jaeseok Huh
             slug: jaeseok_huh
             photo_url: /img/people/jshuh.jpg
             interests: ["RL", "Scheduling"]
          
  - name: Master's Students
    list:
      - full: true
        list:
          - name: Jaeseok Huh
            slug: jaeseok_huh
            photo_url: /img/people/jshuh.jpg
            interests: ["RL", "Scheduling"]
         

  - name: Undergraduate Students
    list:
      - full: true
        list:
          - name: Jaeseok Huh
            slug: jaeseok_huh
            photo_url: /img/people/jshuh.jpg
            interests: ["RL", "Scheduling"]
          


  # - name: Alumni
  #   web_url: https://slurm-lab-usc.github.io/alumni/

  - name: Alumni
    list:
      - name: Jaeseok Huh
        photo_url: /img/people/jshuh.jpg
        current: "AutoX"
        slug: jaeseok_huh   # (선택) 내부 상세를 만들려면 추가
          

     
          

      
---

<div class="row">
  {% for big_group in page.members %}
    <h1>{{ big_group.name }}</h1>
    {% for group in big_group.list %}
      {% if group.list and group.list.size > 0 %}
        {% if group.name %}<h2 style="text-align:left; margin-bottom:20px;">{{ group.name }}</h2>{% endif %}

        {% if group.full %}
          <div class="row member-row">
            {% for member in group.list %}
              {% assign link_url = nil %}
              {% if member.slug %}{% assign link_url = '/members/' | append: member.slug | append: '/' %}{% endif %}
              {% if member.web_url and link_url == nil %}{% assign link_url = member.web_url %}{% endif %}

              <div class="col-xl-3 col-lg-3 col-md-3 text-center col-sm-6 col-xs-6 member-col" style="margin-bottom:22px;">
                {% if link_url %}<a href="{{ link_url | relative_url }}">{% endif %}
                  <img class="img-responsive"
                       src="{{ member.photo_url | relative_url }}"
                       alt="{{ member.name }}"
                       style="width:180px; height:180px; object-fit:cover; border-radius:12px;">
                {% if link_url %}</a>{% endif %}

                <div style="margin-top:8px; font-weight:700;">{{ member.name }}</div>

                {%- comment -%}
                  Alumni면 'Current'를, 그 외면 'interests'를 우선 표시.
                  예외적으로 Alumni에도 interests가 있으면 current 없을 때 대체 표시.
                {%- endcomment -%}
                {% if big_group.name == "Alumni" %}
                  {% if member.current %}
                    <div style="font-size:0.95em; color:#666;">Current: {{ member.current }}</div>
                  {% elsif member.interests %}
                    <div style="font-size:0.95em; color:#666;">{{ member.interests | join: ", " }}</div>
                  {% endif %}
                {% else %}
                  {% if member.interests %}
                    <div style="font-size:0.95em; color:#666;">{{ member.interests | join: ", " }}</div>
                  {% elsif member.current %}
                    <div style="font-size:0.95em; color:#666;">Current: {{ member.current }}</div>
                  {% endif %}
                {% endif %}
              </div>
            {% endfor %}
          </div>
        {% endif %}
        <br>
      {% endif %}
    {% endfor %}
  {% endfor %}
</div>


