---
permalink: /
title: "Zehao Dang"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{% assign cv = site.data.cv %}

<section class="profile-hero" aria-labelledby="profile-intro-title">
  <p class="profile-eyebrow">Computer Engineering · Virginia Tech</p>
  <h2 id="profile-intro-title">Building intelligent tools for robotics and healthcare.</h2>
  <p>I am a rising senior in Computer Engineering focused on Control, Robotics and Autonomy. At Virginia Tech's HAIM Lab, I develop simulations for medical 3D-printing robotics using Python and Isaac Sim.</p>
  <div class="profile-actions">
    <a class="btn btn--primary" href="https://www.linkedin.com/in/zehaodang/">Connect on LinkedIn</a>
    <a class="btn btn--inverse" href="{{ '/cv/' | relative_url }}">View CV</a>
  </div>
</section>

<section class="profile-highlights" aria-label="Professional focus">
  <article>
    <p class="profile-card-label">Current role</p>
    <h3>Undergraduate Research Intern</h3>
    <p>HAIM Lab · Virginia Tech ISE</p>
  </article>
  <article>
    <p class="profile-card-label">Research focus</p>
    <h3>Medical robotics</h3>
    <p>Simulation, 3D printing, and autonomy</p>
  </article>
  <article>
    <p class="profile-card-label">Based in</p>
    <h3>Blacksburg, Virginia</h3>
    <p>Open to on-site and hybrid opportunities</p>
  </article>
</section>

<section class="profile-section" aria-labelledby="experience-title">
  <div class="profile-section-heading">
    <p class="profile-eyebrow">Experience</p>
    <h2 id="experience-title">Research and engineering</h2>
  </div>
  <div class="profile-timeline">
    {% for work in cv.work %}
    <article class="profile-entry">
      <p class="profile-entry-date">{{ work.startDate | date: "%b %Y" }}{% if work.endDate != "" %} – {{ work.endDate | date: "%b %Y" }}{% else %} – Present{% endif %}</p>
      <div>
        <h3>{{ work.position }}</h3>
        <p class="profile-entry-org">{{ work.name }}</p>
        <p>{{ work.summary }}</p>
        {% if work.highlights.size > 0 %}
        <ul class="profile-chip-list" aria-label="{{ work.position }} skills">
          {% for highlight in work.highlights %}<li>{{ highlight }}</li>{% endfor %}
        </ul>
        {% endif %}
      </div>
    </article>
    {% endfor %}
  </div>
</section>

<section class="profile-section profile-section--split" aria-label="Education and technical skills">
  <div>
    <div class="profile-section-heading">
      <p class="profile-eyebrow">Education</p>
      <h2>Academic path</h2>
    </div>
    {% for education in cv.education %}
    <article class="profile-education">
      <h3>{{ education.institution }}</h3>
      <p>{{ education.studyType }}, {{ education.area }}</p>
      <p class="profile-entry-date">{{ education.startDate | date: "%Y" }} – {{ education.endDate | date: "%Y" }}</p>
    </article>
    {% endfor %}
  </div>
  <div>
    <div class="profile-section-heading">
      <p class="profile-eyebrow">Technical toolkit</p>
      <h2>Skills</h2>
    </div>
    <ul class="profile-chip-list profile-chip-list--large">
      {% for skill in cv.skills %}{% for keyword in skill.keywords %}<li>{{ keyword }}</li>{% endfor %}{% endfor %}
    </ul>
    <p class="profile-language-line">Chinese — native or bilingual · English — professional working proficiency</p>
  </div>
</section>

{% if cv.awards.size > 0 %}
<section class="profile-recognition" aria-labelledby="recognition-title">
  <p class="profile-eyebrow">Recognition</p>
  {% for award in cv.awards %}
  <h2 id="recognition-title">{{ award.title }}</h2>
  <p>{{ award.summary }}</p>
  {% endfor %}
</section>
{% endif %}
