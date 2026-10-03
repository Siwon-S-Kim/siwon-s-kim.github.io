---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

[Download my CV as a PDF]({{ base_path }}/files/CV.pdf)

Education
======
* Ph.D. in Mathematical Sciences (Integrated), Seoul National University, 2026
  * Advisor: Woong Kook
* B.S., Double major in Physics and Mathematics, Konkuk University, 2021

Experience
======
* Mar 2026 -- Present: Postdoctoral Researcher
  * Research Institute of Basic Sciences, Seoul National University

Skills
======
* Programming languages
  * Python (proficient)
  * Rust, TypeScript, Lua (novice)
* Data science & machine learning
  * Self-supervised learning, JEPA, Vision Transformer, U-Net
* Domain expertise
  * Electrocardiogram (EKG/ECG) analysis
* DevOps & version control
  * Git, GitHub, Codeberg (branching, merge conflict resolution, overall maintenance)
* Other tools
  * GUI development with PyQt

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Languages
======
* Korean (native)
* English (fluent)
