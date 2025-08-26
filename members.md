---
layout: page
title: Members
subtitle:
members:
  - name: Faculty
    list:
      - full: true
        list:
          - name: Daniel Seita
            photo_url: https://slurm-lab-usc.github.io/img/people/Daniel_2023_square.png
            web_url: https://danielseita.github.io/


  - name: Master's Students
    list:
      - full: true
        list:
          - name: Charlene Yuen
            photo_url: https://slurm-lab-usc.github.io/img/people/Charlene.jpg
            web_url: https://lazerbird.github.io/
         

  - name: Undergraduate Students
    list:
      - full: true
        list:
          - name: Oluwatobiloba Adesanya
            photo_url: https://slurm-lab-usc.github.io/img/people/TobiAdesanya.jpeg
            web_url: https://www.linkedin.com/in/oluwatobilobaadesanya
          


  # - name: Alumni
  #   web_url: https://slurm-lab-usc.github.io/alumni/

  - name: Alumni
    list:
      - name: Undergraduate Students
        full: False
        list:
          - name: Hao Jiang
            web_url: https://haojiang4400.github.io/
            period: 2023-2025 (CS & AM)
            next_step: University of Southern California, PhD in CS
          

      - name: Master's Students
        full: False
        list:
          - name: Hanyang Zhou
            web_url: https://hanyang-zhou.github.io/
            period: 2024-2025 (CS)
            next_step: 
          - name: Vedant Raval
            web_url: https://vedant2311.github.io
            period: 2023-2025 (CS)
            next_step: AutoX
          

      
---

<div class="row">
  {% for big_group in page.members %}
    {% if big_group.web_url %}
      <h1> <a href="{{big_group.web_url}}"> {{big_group.name}} </a> </h1>
    {% else %}
      <h1> {{big_group.name}} </h1>
      {% for group in big_group.list %}
        {% if group.list.size > 0 %}
          {% if group.name %}
            <h2 style="text-align: left; margin-bottom: 20px;"> {{ group.name }} </h2>
          {% endif %}
          {% if group.full %}
          <div class="row member-row">
            {% for member in group.list %}
              <div class="col-xl-3 col-lg-3 col-md-3 text-center col-sm-6 col-xs-6 member-col">
                <a target="_blank" href="{{ member.web_url }}">
                  <img class="img-responsive" src="{{ member.photo_url }}" alt="{{member.name}}">
                </a>
                <a target="_blank" href="{{ member.web_url }}">
                  {{ member.name }}
                </a>
              </div>
            {% endfor %}
          </div>
          {% else %}
            <ul>
              {% if big_group.name == 'Alumni' %}
                <!-- {% if member.web_url %}
                  <li><a href="{{member.web_url}}"> {{member.name}} </a></li>
                {% else %}
                  <li><a> {{member.name}} </a></li>
                {% endif %} -->
                <div id="alumni">
                  <!-- <h2 class="row-label" id="alumni-label">Alumni</h2> -->
                  <div class="alumni-entries">
                    <div class="alumni-names grid-child">{{ "Name" }}</div>
                    <div class="alumni-period grid-child" style="font-weight: bold;">{{ "Period" }}</div>
                    <div class="alumni-next_step grid-child" style="font-weight: bold;">{{ "Next step (known)" }}</div>
                  </div>
                  {% for member in group.list %}
                  <div class="alumni-entries">
                    <div class="alumni-names grid-child">
                      {% if member.web_url != "" %}
                      <a href="{{ member.web_url }}" target="_blank">{{ member.name }}</a>
                      {% else %} {{ member.name }} {% endif %}
                    </div>
                    <div class="alumni-period grid-child">{{ member.period }}</div>
                    <div class="alumni-next_step grid-child">{{ member.next_step }}</div>
                  </div>
                  {% endfor %}
                </div>
              {% endif %}
            </ul>
          {% endif %}
        <br>
        {% endif %}
      {% endfor %}
    {% endif %}
  {% endfor %}
</div>
