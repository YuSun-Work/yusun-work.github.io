---
layout: archive
permalink: /blog/
title: "Blog"
author_profile: true
---

<style>
  .blog-wrap {
    max-width: 880px;
    margin: 0 auto;
  }

  /* ===== Hero ===== */
  .blog-hero {
    position: relative;
    margin: 0.5rem 0 2.4rem;
    padding: 2.4rem 2.4rem 2.2rem;
    border-radius: 20px;
    background: #fbfcfe;
    border: 1px solid #e9eef5;
    overflow: hidden;
  }
  .blog-hero::before {
    content: "";
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, #4f7cff 0%, #8b6cff 50%, #2bb6c4 100%);
  }
  .blog-hero-eyebrow {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 0.9rem;
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #6b7c93;
  }
  .blog-hero-eyebrow::before {
    content: "";
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #4f7cff;
  }
  .blog-hero h1 {
    margin: 0 0 0.7rem;
    font-size: 2rem;
    font-weight: 600;
    letter-spacing: -0.02em;
    color: #1a2235;
    line-height: 1.2;
  }
  .blog-hero p {
    margin: 0;
    font-size: 0.98rem;
    line-height: 1.7;
    color: #56657a;
    max-width: 640px;
  }
  .blog-hero-topics {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 1.4rem;
  }
  .blog-hero-topics span {
    font-size: 12px;
    padding: 4px 11px;
    border-radius: 999px;
    font-weight: 500;
  }
  .topic-medical   { background: #eef3fb; color: #2f5a9e; }
  .topic-foundation{ background: #f1edfb; color: #5a3fa3; }
  .topic-reasoning { background: #e7f5f3; color: #1d7a6a; }
  .topic-agents    { background: #fbeeea; color: #a64a2a; }
  .topic-science   { background: #f3f4f7; color: #4a5568; }

  /* ===== Section header ===== */
  .blog-section-head {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    margin-bottom: 1.2rem;
    padding: 0 0.2rem;
  }
  .blog-section-head h2 {
    margin: 0;
    font-size: 1.05rem;
    font-weight: 600;
    color: #1a2235;
    letter-spacing: -0.01em;
  }
  .blog-section-count {
    font-size: 0.82rem;
    color: #8a96a8;
    font-weight: 500;
  }

  /* ===== Grid ===== */
  .blog-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.1rem;
  }

  /* ===== Card ===== */
  .blog-card {
    position: relative;
    display: flex !important;
    flex-direction: column;
    padding: 1.5rem 1.5rem 1.3rem;
    border-radius: 16px;
    background: #ffffff;
    border: 1px solid #eaeef5;
    text-decoration: none !important;
    transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease;
    min-height: 240px;
    overflow: hidden;
  }
  .blog-card::before {
    content: "";
    position: absolute;
    top: 0;
    left: 1.5rem;
    right: 1.5rem;
    height: 2px;
    background: linear-gradient(90deg, #4f7cff, #8b6cff, #2bb6c4);
    border-radius: 0 0 2px 2px;
    opacity: 0.85;
  }
  .blog-card:hover {
    transform: translateY(-4px);
    border-color: #c8d8f5;
    box-shadow: 0 14px 32px rgba(30, 50, 90, 0.09);
  }
  .blog-card-meta {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 0.9rem;
    font-size: 0.76rem;
    color: #8a96a8;
    font-weight: 600;
    letter-spacing: 0.02em;
  }
  .blog-card-meta svg {
    flex-shrink: 0;
  }
  .blog-card-title {
    margin: 0 0 0.7rem;
    font-size: 1.08rem;
    font-weight: 600;
    color: #1a2235;
    line-height: 1.4;
    letter-spacing: -0.01em;
  }
  .blog-card-excerpt {
    margin: 0 0 1.1rem;
    color: #5d6b7e;
    font-size: 0.88rem;
    line-height: 1.65;
  }
  .blog-card-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.35rem;
    margin-top: auto;
    margin-bottom: 0.9rem;
  }
  .blog-tag {
    font-size: 0.7rem;
    padding: 3px 9px;
    border-radius: 999px;
    background: #f1f5fb;
    color: #49617d;
    font-weight: 500;
  }
  .blog-card-cta {
    display: flex;
    align-items: center;
    gap: 5px;
    color: #2f6fed;
    font-size: 0.84rem;
    font-weight: 600;
  }
  .blog-card-cta svg {
    transition: transform 0.25s ease;
  }
  .blog-card:hover .blog-card-cta svg {
    transform: translateX(3px);
  }

  /* ===== Empty state ===== */
  .blog-empty {
    grid-column: 1 / -1;
    padding: 3rem 1.5rem;
    text-align: center;
    border: 1px dashed #d8dee8;
    border-radius: 16px;
    color: #8a96a8;
    font-size: 0.95rem;
  }

  @media (max-width: 600px) {
    .blog-hero { padding: 1.8rem 1.5rem; }
    .blog-hero h1 { font-size: 1.6rem; }
    .blog-card { padding: 1.3rem 1.3rem 1.1rem; }
  }
</style>

<div class="blog-wrap">

  <div class="blog-hero">
    <div class="blog-hero-eyebrow">Research notes</div>
    <h1>Research Blog</h1>
    <p>Notes on medical AI, foundation models, LLM reasoning, embodied agents, AI for science, and research reflections.</p>
    <div class="blog-hero-topics">
      <span class="topic-medical">Medical AI</span>
      <span class="topic-foundation">Foundation Models</span>
      <span class="topic-reasoning">LLM Reasoning</span>
      <span class="topic-agents">Embodied Agents</span>
      <span class="topic-science">AI for Science</span>
    </div>
  </div>

  {% assign sorted_posts = site.blog | sort: "date" | reverse %}

  <div class="blog-section-head">
    <h2>Latest posts</h2>
    <span class="blog-section-count">{{ sorted_posts | size }} {% if sorted_posts.size == 1 %}article{% else %}articles{% endif %}</span>
  </div>

  <div class="blog-grid">
    {% if sorted_posts.size == 0 %}
      <div class="blog-empty">No posts yet — check back soon.</div>
    {% else %}
      {% for post in sorted_posts %}
      <a class="blog-card" href="{{ post.url | relative_url }}">
        <div class="blog-card-meta">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="3" y="4" width="18" height="18" rx="2"/>
            <line x1="16" y1="2" x2="16" y2="6"/>
            <line x1="8" y1="2" x2="8" y2="6"/>
            <line x1="3" y1="10" x2="21" y2="10"/>
          </svg>
          <span>
            {% if post.date %}{{ post.date | date: "%B %-d, %Y" }}{% else %}Research Note{% endif %}
          </span>
        </div>

        <h3 class="blog-card-title">{{ post.title }}</h3>

        {% if post.excerpt %}
          <p class="blog-card-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
        {% endif %}

        {% if post.tags %}
          <div class="blog-card-tags">
            {% for tag in post.tags limit: 4 %}
              <span class="blog-tag">{{ tag }}</span>
            {% endfor %}
          </div>
        {% endif %}

        <div class="blog-card-cta">
          <span>Read article</span>
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
            <line x1="5" y1="12" x2="19" y2="12"/>
            <polyline points="12 5 19 12 12 19"/>
          </svg>
        </div>
      </a>
      {% endfor %}
    {% endif %}
  </div>

</div>
