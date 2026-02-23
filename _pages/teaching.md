---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

<div class="teaching-statement-link" style="margin-bottom: 2em;">
  <a href="{{ base_path }}/files/teaching_statement.pdf" class="btn btn--primary"><i class="fas fa-file-pdf"></i> Download Teaching Statement (PDF)</a>
</div>

## Teaching Philosophy

My teaching is grounded in research on how people learn and become STEM practitioners, shaped by experience across industry, K-12, and higher education. I design learning environments centered on four core principles: **active learning through reflective practice**, **co-construction and collaborative learning**, **interdisciplinary competency development**, and **systems thinking and design approaches**.

I view students as whole persons whose knowledge, identities, and experiences are essential resources for their learning. My goal is to prepare students for the interconnected, collaborative realities of 21st-century STEM work — technically sound, contextually informed, and socially responsible.

---

## Teaching Experience

{% assign teaching_sorted = site.teaching | sort: 'date' | reverse %}
{% for post in teaching_sorted %}
  {% include archive-single.html %}
{% endfor %}
