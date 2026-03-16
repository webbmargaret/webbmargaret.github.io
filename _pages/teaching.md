---
layout: archive
title: "Teaching Portfolio"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

<div class="teaching-statement-link" style="margin-bottom: 2em;">
  <a href="{{ base_path }}/files/teaching_statement.pdf" class="btn btn--primary"><i class="fas fa-file-pdf"></i> Download Formal Teaching Statement (PDF)</a>
</div>

## Teaching Philosophy

My teaching is grounded in research on how people learn and become STEM practitioners, shaped by experience across industry, K-12, and higher education. I design learning environments centered on four core principles: **active learning through reflective practice**, **co-construction and collaborative learning**, **interdisciplinary competency development**, and **systems thinking and design approaches**.

I view students as whole persons whose knowledge, identities, and experiences are essential resources for their learning. My goal is to prepare students for the interconnected, collaborative realities of 21st-century STEM work — technically sound, contextually informed, and socially responsible.

---

## Teaching Narrative

Growing up in New Orleans, I watched engineers turn the power back on after Katrina. I was nine, displaced for eight months, and I knew then that I wanted to do that work — to restore things, fix systems, and make places whole again. When Hurricane Harvey flooded Houston during my junior year at Rice studying mechanical engineering, I watched the same disaster play out differently depending on where you lived and what you had. My car flooded and I had a campus with power to run to; my neighbors lost everything. The gap between my experience as a student at a private university and the vulnerability of the broader Houston community sharpened my understanding of what engineering education can actually be for. Not just technical competence, but preparing people to work at the intersection of systems, communities, and consequence. That conviction shapes **three commitments I bring to every classroom**: helping students **construct** visible knowledge together based on human experience, building in structured space for **reflection**, and teaching students to **integrate** across disciplinary and community boundaries.


### Construct
 
I design for students to make things — not just solve problems, but to produce artifacts that externalize their thinking, making their learning visible and applied. This works best when students feel known and when learning connects to what they already know. I use pre-assessments, getting-to-know-you surveys and community-building practices at every level I teach — from middle school geometry to graduate seminars — because learning is relational before it is technical. Students who feel seen and know who to ask questions take risks; students who feel anonymous or cannot see a pathway forward do not.
 
As a board member of the Rice University Engineering Association, I lead the Summer Engineering Experience (SEE) internship program based on these principles: we provide structured mentorship and real internship work, connecting engineering students with alumni sponsors, and tailoring professional development that scaffolds internship experiences to what students learn at Rice and where they want to go. This internship program is grounded in the understanding that students arrive with whole lives and abilities to contribute, not just skill gaps, and that learning happens through doing real-world problem solving.
 
This is also why I am intentional about generative AI in my courses — when the goal is visible, human-centered knowledge construction and the application of acquired skills (i.e. not rote recall), the question is not about whether to use AI but how to design assignments where students' reasoning remains irreplaceable. In my classrooms, this logic shapes assignments like collaborative Wikipedia pages on STEM case studies and redesigned lab experiences — like a strain gauge lab I rebuilt at Rice so students could spend their time reasoning about how gauges behave under tension and the uses of strain gauges in engineering design, rather than writing code (or copying AI-generated code) that was not a stated learning outcome. Students build things; they also build understanding of themselves as builders.
 
### Reflect
 
Learning that sticks requires metacognition — students need to know their thinking is changeable and changing, not just that the right answer appeared after thinking. I build structured reflective writing into courses at every level, not as add-on journaling but as the mechanism through which students connect new ideas to prior experience, track their own reasoning, and develop as lifelong learners. My current research on "critical tensions" — moments of cognitive dissonance that prompt graduate students, postdocs, and early-career faculty to notice the gap between their beliefs and their actual practice — is really an extension of this same principle into professional development. Change, whether in a student or a faculty member, begins with noticing.
 
### Integrate
 
National calls from ABET, the NAE's *Engineer of 2020*, and NSF's convergence research agenda share a common argument: the engineers we need are not just technically proficient, they are also collaborative, adaptive, and able to work across disciplinary and community boundaries on problems that do not have clean solutions. That is the engineer I am trying to help students become. In interdisciplinary disaster resilience courses at Virginia Tech, I developed activities where graduate students from engineering, social sciences, and humanities worked together on real crisis cases — navigating competing methods and knowledge frameworks toward solutions addressing both technical and social dimensions. In guest lectures for Virginia Tech's Rising Sophomore Abroad Program, I had second-year engineering students analyze international engineering contexts through cultural and organizational theoretical frameworks after analyzing their own experiences of culture in daily life at Tech. In both settings, the goal was the same: helping students recognize that technical expertise is embedded in human systems, and that integrating across those systems is itself a disciplinary skill worth developing.
 
My integration principle is also why my teaching and research are not separate projects. I study what I practice — undergraduate reflection, interdisciplinary graduate student development, faculty-driven instructional change — and bring findings back into my classrooms. Looking ahead, I want to build undergraduate courses in engineering fundamentals and design that are explicitly grounded in community context as well as graduate seminars in research methods, community-engaged STEM practice, and career development. My goal is not just to teach well, but to understand what teaching well requires — and to contribute that understanding to the field of discipline-based education research (DBER).
 
---

## Teaching Experience

The portfolio items below illustrate these commitments in practice — specific courses, workshops, and mentoring experiences where I have applied these principles of construction, reflection, and integration.

{% assign teaching_sorted = site.teaching | sort: 'date' | reverse %}
{% for post in teaching_sorted %}
  {% include archive-single.html %}
{% endfor %}
