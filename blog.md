---
layout: page
title: Blog
---

<style>
:root {
  color-scheme: light dark;
  --transition: all 0.2s ease-in-out;
}

@media (prefers-color-scheme: dark) {
  body {
    background-color: #121212;
    color: #e0e0e0;
  }

  .blog-card {
    background-color: #1a1a1a;
    border-color: #333;
    box-shadow: 0 6px 20px rgba(255, 255, 255, 0.06);
  }

  .blog-card h2 {
  margin: 0 0 0.6rem;
  font-size: 3rem;
  font-weight: 700;
}

 .blog-date {
 font-size: 1.5rem;
  margin-bottom: 1rem;
  display: block;
}

 .blog-card p {
  font-size: 2rem;
  line-height: 1.7;
}

 .read-more {
  display: inline-block;
  margin-top: 1.5rem;
  padding: 0.6rem 1.2rem;
  border-radius: 8px;
  font-size: 2rem;
  font-weight: 500;
  text-decoration: none;
  transition: var(--transition);
}
}

@media (prefers-color-scheme: light) {
  body {
    background-color: #f9f9f9;
    color: #111;
  }

  .blog-card {
    background-color: #ffffff;
    border-color: #ddd;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.06);
  }

  .blog-card h2 {
    color: #111111;
  }

  .blog-card .blog-date {
    color: #666666;
  }

  .blog-card p {
    color: #333333;
  }

  .read-more {
    background-color: #dddddd;
    color: #111111;
  }

  .read-more:hover {
    background-color: #5555ff;
    color: #ffffff;
  }
}

.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-top: 2.5rem;
  padding: 0 2rem;
  font-family: 'Inter', sans-serif;
}

.blog-card {
  border: 1px solid;
  border-radius: 14px;
  padding: 2rem;
  transition: var(--transition);
}

.blog-card:hover {
  transform: translateY(-5px);
}

.blog-card h2 {
  margin: 0 0 0.6rem;
  font-size: 1.6rem;
  font-weight: 700;
}

.blog-date {
  font-size: 0.85rem;
  margin-bottom: 1rem;
  display: block;
}

.blog-card p {
  font-size: 1rem;
  line-height: 1.6;
}

.read-more {
  display: inline-block;
  margin-top: 1.5rem;
  padding: 0.6rem 1.2rem;
  border-radius: 8px;
  font-size: 0.95rem;
  font-weight: 500;
  text-decoration: none;
  transition: var(--transition);
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
