---
layout: archive
permalink: /blog/
title: "Blog"
author_profile: true
---

<style>
.blog-hero {
  margin-top: 0.5rem;
  margin-bottom: 2.2rem;
  padding: 2rem 2.2rem;
  border-radius: 22px;
  background: linear-gradient(135deg, #f8fbff 0%, #eef5ff 45%, #f7f8ff 100%);
  border: 1px solid #e6eef8;
  box-shadow: 0 12px 35px rgba(27, 39, 71, 0.08);
}

.blog-hero h1 {
  margin: 0 0 0.6rem 0;
  font-size: 2rem;
  letter-spacing: -0.02em;
}

.blog-hero p {
  margin: 0;
  font-size: 1rem;
  color: #526071;
  line-height: 1.75;
}

.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.25rem;
  margin-top: 1.5rem;
}

.blog-card {
  position: relative;
  display: block;
  padding: 1.35rem 1.35rem 1.2rem 1.35rem;
  border-radius: 20px;
  background: #ffffff;
  border: 1px solid #e9edf3;
  box-shadow: 0 8px 24px rgba(30, 42, 62, 0.06);
  text-decoration: none !important;
  transition: transform 0.22s ease, box-shadow 0.22s ease, border-color 0.22s ease;
  min-height: 210px;
  overflow: hidden;
}

.blog-card:hover {
  transform: translateY(-5px);
  border-color: #b8d3ff;
  box-shadow: 0 16px 38px rgba(30, 42, 62, 0.12);
}

.blog-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 5px;
  background: linear-gradient(90deg, #4f8cff, #8d6cff, #24c6dc);
}

.blog-card-date {
  font-size: 0.78rem;
  color: #7a8798;
  margin-bottom: 0.6rem;
  font-weight: 600;
}

.blog-card-title {
  font-size: 1.15rem;
  font-weight: 750;
  color: #1c2738;
  line-height: 1.45;
  margin-bottom: 0.65rem;
}

.blog-card-excerpt {
  color: #596779;
  font-size: 0.92rem;
  line-height: 1.65;
  margin-bottom: 1rem;
}

.blog-card-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-top: auto;
}

.blog-tag {
  display: inline-block;
  padding: 0.22rem 0.55rem;
  border-radius: 999px;
  background: #f1f5fb;
  color: #49617d;
  font-size: 0.72rem;
  font-weight: 600;
}

.blog-read-more {
  margin-top: 1rem;
  color: #2f6fed;
  font-size: 0.88rem;
  font-weight: 700;
}
</style>

<div class="blog-hero">
  <h1>Research Blog</h1>
  <p>
    Notes on medical AI, foundation models, LLM reasoning, embodied agents, AI for science, and research reflections.
  </p>
</div>

<div class="blog-grid">
{% assign sorted_posts = site.blog | sort: "date" | reverse %}
{% for post in sorted_posts %}
  <a class="blog-card" href="{{ post.url | relative_url }}">
    <div class="blog-card-date">
      {% if post.date %}
        {{ post.date | date: "%B %d, %Y" }}
      {% else %}
        Research Note
      {% endif %}
    </div>

    <div class="blog-card-title">
      {{ post.title }}
    </div>

    {% if post.excerpt %}
      <div class="blog-card-excerpt">
        {{ post.excerpt | strip_html | truncate: 150 }}
      </div>
    {% endif %}

    {% if post.tags %}
      <div class="blog-card-tags">
        {% for tag in post.tags limit: 4 %}
          <span class="blog-tag">{{ tag }}</span>
        {% endfor %}
      </div>
    {% endif %}

    <div class="blog-read-more">Read more →</div>
  </a>
{% endfor %}
</div>
