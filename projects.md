---
layout: page
title: Projects
---

<style>
:root {
  color-scheme: light dark;
}

@media (prefers-color-scheme: dark) {
  body {
    background-color: #121212;
    color: #e0e0e0;
  }

  .project-card {
    background-color: #1a1a1a;
    border-color: #333;
    box-shadow: 0 6px 20px rgba(255, 255, 255, 0.08);
  }

  .project-card h3 { color: #ffffff; }
  .project-card p { color: #d0d0d0; }
  .project-tag { background-color: #2f2f2f; color: #c0c0c0; }
  .project-buttons a { background-color: #3a3a3a; color: #ffffff; }
  .project-buttons a:hover { background-color: #5f5fff; }
}

@media (prefers-color-scheme: light) {
  body {
    background-color: #f9f9f9;
    color: #111;
  }

  .project-card {
    background-color: #ffffff;
    border-color: #ddd;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.06);
  }

  .project-card h3 { color: #000000; }
  .project-card p { color: #333333; }
  .project-tag { background-color: #eeeeee; color: #333333; }
  .project-buttons a { background-color: #dddddd; color: #111111; }
  .project-buttons a:hover { background-color: #5555ff; color: #ffffff; }
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-top: 2.5rem;
  padding: 0 2rem;
  font-family: 'Inter', sans-serif;
}

.project-card {
  border: 1px solid;
  border-radius: 14px;
  padding: 2rem;
  transition: all 0.25s ease-in-out;
}

.project-card:hover {
  transform: translateY(-5px);
}

.project-card h3 {
  margin: 0 0 1rem;
  font-size: 2rem;
  font-weight: 700;
}

.project-card a.title-link {
  text-decoration: none;
}

.project-card a.title-link:hover {
  text-decoration: underline;
}

.project-card p {
  font-size: 1.35rem;
  line-height: 1.8;
  margin-top: 0.5rem;
}

.project-tags {
  margin-top: 1.2rem;
}

.project-tag {
  display: inline-block;
  padding: 0.5rem 1.1rem;
  font-size: 1.15rem;
  border-radius: 999px;
  margin-right: 0.6rem;
  margin-bottom: 0.5rem;
}

.project-buttons {
  margin-top: 1.6rem;
}

.project-buttons a {
  display: inline-block;
  padding: 0.75rem 1.4rem;
  font-size: 1.15rem;
  border-radius: 8px;
  text-decoration: none;
  transition: background 0.2s ease;
  margin-right: 0.6rem;
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
