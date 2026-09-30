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
  <h2 id="profile-intro-title">Building intelligent systems for industrial robotics.</h2>
  <p>I am a senior in Computer Engineering (Control, Robotics and Autonomy) focused on industrial robotics, smart manufacturing, digital twins, and robotics learning. As a Research Assistant in Virginia Tech's Grado Department of Industrial and Systems Engineering, I lead a vision-based adaptive 3D-printing system for deforming surfaces and a UR5e robotic additive manufacturing pipeline validated in NVIDIA Isaac Sim. I also build ROS2/Gazebo simulation for VT's AutoNav team in the Intelligent Ground Vehicle Competition.</p>
  <div class="profile-actions">
    <a class="btn btn--primary" href="https://www.linkedin.com/in/zehaodang/">Connect on LinkedIn</a>
    <a class="btn btn--inverse" href="{{ '/cv/' | relative_url }}">View CV</a>
  </div>
</section>

<section class="profile-highlights" aria-label="Professional focus">
  <article>
    <p class="profile-card-label">Current role</p>
    <h3>Research Assistant</h3>
    <p>Grado Department of ISE · Virginia Tech</p>
  </article>
  <article>
    <p class="profile-card-label">Research interests</p>
    <h3>Industrial robotics</h3>
    <p>Smart manufacturing, digital twins, and robotics learning</p>
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
    {% assign timeline = cv.work | concat: cv.experience | sort: "startDate" | reverse %}
    {% for work in timeline %}
    <article class="profile-entry">
      <p class="profile-entry-date">{{ work.startDate | date: "%b %Y" }}{% if work.endDate != "" %} – {{ work.endDate | date: "%b %Y" }}{% else %} – Present{% endif %}</p>
      <div>
        <h3>{{ work.position }}</h3>
        <p class="profile-entry-org">{{ work.name }}</p>
        <p>{{ work.summary }}</p>
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
