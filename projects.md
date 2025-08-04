---
layout: page
title: Projects
---

<style>
.project-card {
  background-color: #1a1a1a;
  border: 1px solid #333;
  border-radius: 12px;
  padding: 20px;
  margin: 20px 0;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
  transition: transform 0.2s, box-shadow 0.2s;
}
.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(255, 255, 255, 0.08);
}
.project-card h3 {
  margin-top: 0;
  font-size: 1.5rem;
  color: #e0e0e0;
}
.project-card h3 a {
  text-decoration: none;
  color: #9f79ff;
}
.project-card h3 a:hover {
  color: #ffffff;
}
.project-card p {
  color: #c5c5c5;
  line-height: 1.6;
}
</style>

<section>
  {% for project in site.data.projects %}
    <div class="project-card">
      <h3><a href="{{ project.url }}" target="_blank">{{ project.name }}</a></h3>
      <p>{{ project.description }}</p>
    </div>
  {% endfor %}
</section>
