---
layout: page
title: Research
subtitle:
permalink: /research/
---

<div class="sim-callout">
  <b>핵심 철학 (Core Philosophy):</b> <b>시뮬레이션 기반 의사결정 연구실(SDM Lab)</b>의 모든 연구는 시뮬레이션에서 출발합니다. 
  이론적 아이디어가 실제 현장의 복잡한 의사결정을 효과적으로 지원할 수 있도록, 가상 환경에서 철저한 검증 과정을 거치는 것을 원칙으로 합니다.
</div>

본 연구실은 현대의 복잡한 산업 시스템을 위한 <b>지능형 의사결정 방법론(Intelligent Decision-making)</b>을 전문적으로 연구합니다. 
<b>최적화 및 메타휴리스틱(Optimization & Metaheuristics)</b>, <b>강화학습(Reinforcement Learning)</b>, 그리고 <b>데이터 기반 머신러닝(Data-driven ML)</b> 기술을 유기적으로 결합하여, 
일정계획(Scheduling) 및 운영 효율화를 위한 실무 중심의 해법을 제시합니다.

<div class="areas-grid">
{% for area in site.data.areas %}
  {% include area.html %}
{% endfor %}
</div>

---

# Selected Projects

<div class="projects-grid">
{% for project in site.data.projects %}
  {% include project.html %}
{% endfor %}
</div>

<!-- ---
layout: page
title: Research Areas
subtitle:
---

Many of our research projects are in one of the following general themes. Note that this page is still being updated to include [all publications](../publications). 

<div>
{% for area in site.data.areas %}
    {% include area.html %}
{% endfor %}
</div>

# Previous Directions

## Object tracking

Tracking involves consistently locating an object as it moves across a scene, or consistently locating a point on an object as it moves.  In order to understand how robots should interact with objects, the robot must be able to track them as they change in position, viewpoint, lighting, occlusions, and other factors.  Improvements in this area should enable autonomous vehicles to interact more safely around dynamic objects (e.g. pedestrians, bicyclists, and other vehicles).

<details>
<summary style="display: list-item;"><b>Relevant Publications</b></summary>
<div>
    <table cellpadding="10" width="100%">
        {% assign pubs = site.data.pubs | where: 'tags', 'tracking' %}
        {% for pub in pubs %}
            {% include pub.html %}
        {% endfor %}
    </table>
    </div>
</details> -->