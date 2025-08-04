---
layout: page
title: Blog
---

<style>
:root {
  color-scheme: light dark;
}

@media (prefers-color-scheme: dark) {
  body {
    background-color: #121212;
    color: #e0e0e0;
    font-size: 18px;
  }

  .project-card {
    background-color: #1a1a1a;
    border-color: #333;
    box-shadow: 0 6px 20px rgba(255, 255, 255, 0.08);
  }

  .project-card h3 { color: #ffffff; font-size: 2.2rem; }
  .project-card p { color: #d0d0d0; font-size: 1.45rem; }
  .project-tag { background-color: #2f2f2f; color: #c0c0c0; font-size: 1.25rem; }
  .project-buttons a { background-color: #3a3a3a; color: #ffffff; font-size: 1.3rem; }
  .project-buttons a:hover { background-color: #5f5fff; }
}

@media (prefers-color-scheme: light) {
  body {
    background-color: #f9f9f9;
    color: #111;
    font-size: 18px;
  }

  .project-card {
    background-color: #ffffff;
    border-color: #ddd;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.06);
  }

  .project-card h3 { color: #000000; font-size: 2.2rem; }
  .project-card p { color: #333333; font-size: 1.45rem; }
  .project-tag { background-color: #eeeeee; color: #333333; font-size: 1.25rem; }
  .project-buttons a { background-color: #dddddd; color: #111111; font-size: 1.3rem; }
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

.project-card a.title-link {
  text-decoration: none;
}

.project-card a.title-link:hover {
  text-decoration: underline;
}

.project-tags {
  margin-top: 1.2rem;
}

.project-buttons {
  margin-top: 1.6rem;
}
</style>

<section class="blog-grid">
  {% for post in site.posts %}
    {% if post.category == 'blog' and post.hidden != true %}
      <div class="blog-card">
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <span class="blog-date">{{ post.date | date: "%B %d, %Y" }}</span>
        <p>{{ post.description | truncate: 100 }}</p>
        <a class="read-more" href="{{ post.url }}">Read more →</a>
      </div>
    {% endif %}
  {% endfor %}
</section>
