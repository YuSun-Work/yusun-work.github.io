---
layout: archive
permalink: /blog/
title: "Blog"
author_profile: true
---

<style>
  .blog-wrap { max-width: 880px; margin: 0 auto; }

  /* ===== Hero ===== */
  .blog-hero {
    position: relative;
    margin: 0.5rem 0 1.8rem;
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
    display: flex; align-items: center; gap: 10px;
    margin-bottom: 0.9rem;
    font-size: 12px; font-weight: 600;
    letter-spacing: 0.12em; text-transform: uppercase;
    color: #6b7c93;
  }
  .blog-hero-eyebrow::before {
    content: ""; width: 6px; height: 6px;
    border-radius: 50%; background: #4f7cff;
  }
  .blog-hero h1 {
    margin: 0 0 0.7rem;
    font-size: 2rem; font-weight: 600;
    letter-spacing: -0.02em; color: #1a2235; line-height: 1.2;
  }
  .blog-hero p {
    margin: 0; font-size: 0.98rem; line-height: 1.7;
    color: #56657a; max-width: 640px;
  }

  /* ===== Filter Bar ===== */
  .blog-filter {
    background: #ffffff;
    border: 1px solid #eaeef5;
    border-radius: 14px;
    padding: 1rem 1.2rem;
    margin-bottom: 1.5rem;
  }
  .blog-filter-label {
    display: flex; align-items: center; gap: 8px;
    margin-bottom: 0.8rem;
    font-size: 0.78rem; color: #6b7c93;
    font-weight: 600; letter-spacing: 0.04em; text-transform: uppercase;
  }
  .blog-filter-buttons {
    display: flex; flex-wrap: wrap; gap: 0.45rem;
  }
  .filter-btn {
    font-size: 0.82rem;
    padding: 6px 14px;
    border-radius: 999px;
    font-weight: 500;
    border: 1px solid transparent;
    cursor: pointer;
    transition: all 0.18s ease;
    font-family: inherit;
  }
  .filter-btn:hover { transform: translateY(-1px); }
  .filter-btn .count { opacity: 0.55; margin-left: 5px; font-size: 0.78em; }

  /* default colors per topic */
  .filter-btn.f-all        { background: #f1f4f9; color: #3a4a63; }
  .filter-btn.f-medical    { background: #eef3fb; color: #2f5a9e; }
  .filter-btn.f-foundation { background: #f1edfb; color: #5a3fa3; }
  .filter-btn.f-reasoning  { background: #e7f5f3; color: #1d7a6a; }
  .filter-btn.f-agents     { background: #fbeeea; color: #a64a2a; }
  .filter-btn.f-science    { background: #f3f4f7; color: #4a5568; }
  .filter-btn.f-default    { background: #f3f4f7; color: #4a5568; }

  /* active state — solid dark */
  .filter-btn.active {
    background: #1a2235 !important;
    color: #ffffff !important;
    border-color: #1a2235;
  }
  .filter-btn.active .count { opacity: 0.6; }

  /* ===== Section header ===== */
  .blog-section-head {
    display: flex; align-items: baseline; justify-content: space-between;
    margin-bottom: 1.2rem; padding: 0 0.2rem;
  }
  .blog-section-head h2 {
    margin: 0; font-size: 1.05rem; font-weight: 600;
    color: #1a2235; letter-spacing: -0.01em;
  }
  .blog-section-count { font-size: 0.82rem; color: #8a96a8; font-weight: 500; }

  /* ===== Grid ===== */
  .blog-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.1rem;
  }

  /* ===== Card ===== */
  .blog-card {
    position: relative;
    display: flex !important; flex-direction: column;
    padding: 1.5rem 1.5rem 1.3rem;
    border-radius: 16px;
    background: #ffffff;
    border: 1px solid #eaeef5;
    text-decoration: none !important;
    transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease;
    min-height: 240px; overflow: hidden;
  }
  .blog-card::before {
    content: "";
    position: absolute;
    top: 0; left: 1.5rem; right: 1.5rem;
    height: 2px;
    background: linear-gradient(90deg, #4f7cff, #8b6cff, #2bb6c4);
    opacity: 0.85;
  }
  .blog-card:hover {
    transform: translateY(-4px);
    border-color: #c8d8f5;
    box-shadow: 0 14px 32px rgba(30, 50, 90, 0.09);
  }
  .blog-card.hidden { display: none !important; }
  .blog-card-meta {
    display: flex; align-items: center; gap: 8px;
    margin-bottom: 0.9rem;
    font-size: 0.76rem; color: #8a96a8; font-weight: 600;
  }
  .blog-card-title {
    margin: 0 0 0.7rem;
    font-size: 1.08rem; font-weight: 600;
    color: #1a2235; line-height: 1.4; letter-spacing: -0.01em;
  }
  .blog-card-excerpt {
    margin: 0 0 1.1rem;
    color: #5d6b7e; font-size: 0.88rem; line-height: 1.65;
  }
  .blog-card-tags {
    display: flex; flex-wrap: wrap; gap: 0.35rem;
    margin-top: auto; margin-bottom: 0.9rem;
  }
  .blog-tag {
    font-size: 0.7rem; padding: 3px 9px;
    border-radius: 999px; font-weight: 500;
  }
  /* tag colors mirror filter buttons */
  .tag-medical    { background: #eef3fb; color: #2f5a9e; }
  .tag-foundation { background: #f1edfb; color: #5a3fa3; }
  .tag-reasoning  { background: #e7f5f3; color: #1d7a6a; }
  .tag-agents     { background: #fbeeea; color: #a64a2a; }
  .tag-science    { background: #f3f4f7; color: #4a5568; }
  .tag-default    { background: #f1f5fb; color: #49617d; }

  .blog-card-cta {
    display: flex; align-items: center; gap: 5px;
    color: #2f6fed; font-size: 0.84rem; font-weight: 600;
  }
  .blog-card-cta svg { transition: transform 0.25s ease; }
  .blog-card:hover .blog-card-cta svg { transform: translateX(3px); }

  /* ===== Empty state ===== */
  .blog-empty {
    grid-column: 1 / -1;
    padding: 3rem 1.5rem; text-align: center;
    border: 1px dashed #d8dee8; border-radius: 16px;
    color: #8a96a8; font-size: 0.95rem;
  }

  @media (max-width: 600px) {
    .blog-hero { padding: 1.8rem 1.5rem; }
    .blog-hero h1 { font-size: 1.6rem; }
  }
</style>

{% comment %} ---- helper: map tag string -> css slug ---- {% endcomment %}
{% capture tag_map %}
  Medical AI=medical|Foundation Models=foundation|LLM Reasoning=reasoning|Embodied Agents=agents|AI for Science=science
{% endcapture %}

<div class="blog-wrap">

  <div class="blog-hero">
    <div class="blog-hero-eyebrow">Research notes</div>
    <h1>Research Blog</h1>
    <p>Notes on medical AI, foundation models, LLM reasoning, embodied agents, AI for science, and research reflections.</p>
  </div>

  {% assign sorted_posts = site.blog | sort: "date" | reverse %}

  <!-- ===== Filter bar ===== -->
  <div class="blog-filter">
    <div class="blog-filter-label">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <polygon points="22 3 2 3 10 12.46 10 19 14 21 14 12.46 22 3"/>
      </svg>
      Filter by topic
    </div>
    <div class="blog-filter-buttons">
      <button class="filter-btn f-all active" data-filter="all">
        All <span class="count">{{ sorted_posts | size }}</span>
      </button>
      <button class="filter-btn f-medical"    data-filter="Medical AI">Medical AI</button>
      <button class="filter-btn f-foundation" data-filter="Foundation Models">Foundation Models</button>
      <button class="filter-btn f-reasoning"  data-filter="LLM Reasoning">LLM Reasoning</button>
      <button class="filter-btn f-agents"     data-filter="Embodied Agents">Embodied Agents</button>
      <button class="filter-btn f-science"    data-filter="AI for Science">AI for Science</button>
    </div>
  </div>

  <div class="blog-section-head">
    <h2>Latest posts</h2>
    <span class="blog-section-count" id="blog-count">Showing all {{ sorted_posts | size }}</span>
  </div>

  <div class="blog-grid" id="blog-grid">
    {% if sorted_posts.size == 0 %}
      <div class="blog-empty">No posts yet — check back soon.</div>
    {% else %}
      {% for post in sorted_posts %}
        {% assign tag_string = post.tags | join: "||" %}
        <a class="blog-card" href="{{ post.url | relative_url }}" data-tags="{{ tag_string }}">
          <div class="blog-card-meta">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <rect x="3" y="4" width="18" height="18" rx="2"/>
              <line x1="16" y1="2" x2="16" y2="6"/>
              <line x1="8" y1="2" x2="8" y2="6"/>
              <line x1="3" y1="10" x2="21" y2="10"/>
            </svg>
            <span>{% if post.date %}{{ post.date | date: "%B %-d, %Y" }}{% else %}Research Note{% endif %}</span>
          </div>

          <h3 class="blog-card-title">{{ post.title }}</h3>

          {% if post.excerpt %}
            <p class="blog-card-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
          {% endif %}

          {% if post.tags %}
            <div class="blog-card-tags">
              {% for tag in post.tags limit: 4 %}
                {% assign slug = "default" %}
                {% if tag == "Medical AI" %}{% assign slug = "medical" %}{% endif %}
                {% if tag == "Foundation Models" %}{% assign slug = "foundation" %}{% endif %}
                {% if tag == "LLM Reasoning" %}{% assign slug = "reasoning" %}{% endif %}
                {% if tag == "Embodied Agents" %}{% assign slug = "agents" %}{% endif %}
                {% if tag == "AI for Science" %}{% assign slug = "science" %}{% endif %}
                <span class="blog-tag tag-{{ slug }}">{{ tag }}</span>
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
      <div class="blog-empty" id="blog-no-results" style="display:none;">No posts match this topic yet.</div>
    {% endif %}
  </div>

</div>

<script>
(function() {
  var buttons = document.querySelectorAll('.filter-btn');
  var cards   = document.querySelectorAll('.blog-card');
  var countEl = document.getElementById('blog-count');
  var noEl    = document.getElementById('blog-no-results');
  var total   = cards.length;

  function applyFilter(filter) {
    var visible = 0;
    cards.forEach(function(card) {
      var tags = (card.getAttribute('data-tags') || '').split('||');
      var show = (filter === 'all') || tags.indexOf(filter) !== -1;
      card.classList.toggle('hidden', !show);
      if (show) visible++;
    });
    if (countEl) {
      countEl.textContent = (filter === 'all')
        ? 'Showing all ' + total
        : 'Showing ' + visible + ' of ' + total;
    }
    if (noEl) noEl.style.display = visible === 0 ? 'block' : 'none';
  }

  buttons.forEach(function(btn) {
    btn.addEventListener('click', function() {
      buttons.forEach(function(b) { b.classList.remove('active'); });
      btn.classList.add('active');
      applyFilter(btn.getAttribute('data-filter'));
    });
  });
})();
</script>
