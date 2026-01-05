---
layout: page
title: Students
subtitle:
permalink: /members/
members:

  # - name: PhD Students
  #   list:
  #     - full: true
  #       list:
  #          - name: Jaeseok Huh
  #            slug: jaeseok_huh
  #            photo_url: /img/people/jshuh.jpg
  #            interests: ["RL", "Scheduling"]
          

  - name: Master's Students
    list:
      - full: true
        list:
          - name: Coming Soon
            slug:
            photo_url: /img/people/person.png
            interests: ["Scheduling"]
            email: 

  - name: Undergraduate Students
    list:
      - full: true
        list:
          - name: Coming Soon
            slug:
            photo_url: /img/people/person.png
            interests: ["Simulation"]
            email: 2@ssu.ac.kr

          - name: Coming Soon
            slug:
            photo_url: /img/people/person.png
            interests: ["Simulation"]
            email: 2@ssu.ac.kr

          - name: Coming Soon
            slug:
            photo_url: /img/people/person.png
            interests: ["Simulation"]
            email: 2@ssu.ac.kr

  - name: Alumni
    list:
      - full: true
        list:
         - name: Geonwon Lee
           photo_url: /img/people/gwlee.png
           current: "Eonetechnology"

         - name: Hyungchan Shin
           photo_url: /img/people/hcshin.jpg
           current: "Neurocore"

         - name: Dasol Kim
           photo_url: /img/people/dskim.jpg
           current: "Protec"
           
         - name: Gwangjong Ko
           photo_url: /img/people/gjko.jpg
           current: "Korea University"
            
---

              
                
---
<div id="members-page">
  <div class="row">
    {% for big_group in page.members %}
      <h1>{{ big_group.name }}</h1>
      {% for group in big_group.list %}
        {% if group.list and group.list.size > 0 %}
          {% if group.name %}<h2 style="text-align:left; margin-bottom:20px;">{{ group.name }}</h2>{% endif %}

            {% if group.full %}
              <div class="member-list">
                {% for member in group.list %}
                  {% assign link_url = nil %}
                  {% if member.slug %}{% assign link_url = '/members/' | append: member.slug | append: '/' %}{% endif %}
                  {% if member.web_url and link_url == nil %}{% assign link_url = member.web_url %}{% endif %}

                  <div class="member-item">
                    <div class="member-photo">
                      {% if link_url %}<a href="{{ link_url | relative_url }}">{% endif %}
                        <img src="{{ member.photo_url | relative_url }}"
                            alt="{{ member.name }}">
                      {% if link_url %}</a>{% endif %}
                    </div>

                    <div class="member-info">
                      <div class="member-name">
                        {% if link_url %}<a href="{{ link_url | relative_url }}">{{ member.name }}</a>{% else %}{{ member.name }}{% endif %}
                      </div>

                      {% if member.email %}
                        <div class="member-email">
                          <a href="mailto:{{ member.email }}">{{ member.email }}</a>
                        </div>
                      {% endif %}

                      {% if big_group.name == "Alumni" %}
                        {% if member.current %}
                          <div class="member-meta"><b>Current:</b> {{ member.current }}</div>
                        {% elsif member.interests %}
                          <div class="member-meta"><b>Interest:</b> {{ member.interests | join: ", " }}</div>
                        {% endif %}
                      {% else %}
                        {% if member.interests %}
                          <div class="member-meta"><b>Interest:</b> {{ member.interests | join: ", " }}</div>
                        {% elsif member.current %}
                          <div class="member-meta"><b>Current:</b> {{ member.current }}</div>
                        {% endif %}
                      {% endif %}

                      {% if member.bio %}
                        <div class="member-bio">{{ member.bio }}</div>
                      {% endif %}
                    </div>
                  </div>
                {% endfor %}
              </div>
            {% endif %}
          
          <br>
        {% endif %}
      {% endfor %}
    {% endfor %}
  </div>
</div>


