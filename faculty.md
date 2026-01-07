---
layout: page
title: Faculty
permalink: /faculty/
---

<div id="faculty-page">
  <div class="faculty-card">
    <div class="faculty-top">
      <div class="faculty-photo">
        <img src="{{ '/img/people/jshuh.jpg' | relative_url }}"
             alt="Jaeseok Huh">
      </div>

      <div class="faculty-info">
        <div class="faculty-name">Jaeseok Huh (허재석)</div>

        <div class="faculty-interests">
          <b>Interests:</b> Scheduling, Simulation, Reinforcement Learning, Metaheuristics, Optimization
        </div>

        <div class="faculty-email">
          <a href="mailto:jshuh@ssu.ac.kr">jshuh@ssu.ac.kr</a>
        </div>

        <div class="faculty-links">
          <!-- 필요 없으면 지우셔도 됨 -->
          <a class="faculty-link" href="https://scholar.google.com/citations?user=0Xzd2f8AAAAJ" target="_blank" rel="noopener">Google Scholar</a>
          <!-- <a class="faculty-link" href="https://laonhjs.github.io/" target="_blank" rel="noopener">GitHub</a>           -->
        </div>
      </div>
    </div>

    <div class="faculty-sections">
      <div class="faculty-section">
        <h2>Education</h2>
        <ul>
          <li><b>Ph.D. Industrial Engineering</b>, Seoul National University (2013–2019)</li>
          <li><b>B.S. Industrial Engineering</b>, Seoul National University (2007–2013)</li>
        </ul>
      </div>

      <div class="faculty-section">
        <h2>Experience</h2>
        <ul>
          <li><b>Assistant Professor</b>, Department of Industrial and Information Systems Engineering, Soongsil University (2025–Current)</li>
          <li><b>Assistant Professor</b>, Department of Business Administration, Tech University of Korea (2019–2025)</li>
          <li><b>Applied Scientist (Consulting)</b>, Gausslabs Inc. (2021–2023)</li>
          <li><b>Advisory Committee Member</b>, Republic of Korea Army (2021–Current)</li>
        </ul>
      </div>

      <div class="faculty-section">
        <h2>Teaching</h2>

        <p class="faculty-note">(Tech University of Korea, 2019–2025)</p>
        <ul>
          <li>Python Programming</li>
          <li>Introduction to Smart Factory</li>
          <li>Operation Research</li>
          <li>Simulation</li>
          <li>Operations Management</li>
        </ul>

        <p class="faculty-note">(Korea Data Agency, 2019–2020)</p>
        <ul>
          <li>Python Programming</li>
          <li>Introduction to Machine Learning</li>
          <li>AI Techniques for Smart Manufacturing</li>
        </ul>

        <p class="faculty-note">(Seoul National University)</p>
        <ul>
          <li>Computer Programming Course (Teacher, Spring 2017)</li>
          <li>Computer Programming Course (TA, Spring 2016)</li>
          <li>Data Management and Analysis (TA, Fall 2014, Fall 2015)</li>
        </ul>
      </div>
      
    </div>
  </div>
</div>








<!-- <div class="row">
  {% for p in faculty %}
    <div class="col-12" style="margin-bottom:24px;">
      <div style="display:flex; gap:20px; align-items:flex-start; padding:18px; border:1px solid #eee; border-radius:16px;">
        <a href="{{ p.url | relative_url }}" style="flex:0 0 auto;">
          <img src="{{ p.photo | relative_url }}"
               alt="{{ p.d }}"
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
</div> -->
