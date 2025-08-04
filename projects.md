---
layout: page
title: Projects
---

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.75rem;
  margin-top: 2rem;
  padding: 0 1.5rem;
}

.project-card {
  background-color: #1a1a1a;
  border: 1px solid #333;
  border-radius: 12px;
  padding: 1.75rem;
  box-shadow: 0 4px 14px rgba(255, 255, 255, 0.05);
  transition: all 0.25s ease-in-out;
  font-family: 'Inter', sans-serif;
}

.project-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 24px rgba(255, 255, 255, 0.08);
}

.project-card h3 {
  margin: 0 0 0.75rem;
  font-size: 1.6rem;
  color: #ffffff;
}

.project-card a.title-link {
  color: #a479ff;
  text-decoration: none;
}

.project-card a.title-link:hover {
  color: #ffffff;
  text-decoration: underline;
}

.project-card p {
  color: #d0d0d0;
  font-size: 1.1rem;
  line-height: 1.75;
}

.project-tags {
  margin-top: 1rem;
}

.project-tag {
  display: inline-block;
  background-color: #2f2f2f;
  color: #c0c0c0;
  padding: 0.4rem 0.9rem;
  font-size: 0.85rem;
  border-radius: 999px;
  margin-right: 0.4rem;
  margin-bottom: 0.3rem;
}

.project-buttons {
  margin-top: 1.2rem;
}

.project-buttons a {
  display: inline-block;
  background-color: #3a3a3a;
  color: #fff;
  padding: 0.6rem 1.1rem;
  font-size: 1rem;
  border-radius: 8px;
  text-decoration: none;
  transition: background 0.2s ease;
  margin-right: 0.5rem;
}

.project-buttons a:hover {
  background-color: #5f5fff;
}
</style>

<section class="projects-grid">
  {% for project in site.data.projects %}
    <div class="project-card">
      <h3><a class="title-link" href="{{ project.url }}" target="_blank">{{ project.name }}</a></h3>
      <p>{{ project.description }}</p>
      
      {% if project.tags %}
        <div class="project-tags">
          {% for tag in project.tags %}
            <span class="project-tag">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}

      <div class="project-buttons">
        <a href="{{ project.url }}" target="_blank">View on GitHub</a>
      </div>
    </div>
  {% endfor %}
</section>
