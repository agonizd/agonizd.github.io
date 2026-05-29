---
layout: default
title: 首页
---

<section class="hero">
  <div class="container">
    <span class="badge">✨ Jekyll + Docker + GitHub Pages</span>
    <h1><span class="static-text">欢迎来到我的</span><br><span class="dynamic-text">数字空间</span></h1>
    <p>记录思考、分享技术、收藏灵感。这是一个用代码构建的未来感博客。</p>
    <div class="cta-buttons">
      <a href="#posts" class="btn btn-primary">浏览文章</a>
      <a href="https://github.com/{{ site.github_username }}" class="btn btn-secondary" target="_blank">GitHub</a>
    </div>
  </div>
</section>

<section id="posts" style="padding-bottom: 4rem;">
  <div class="container">
    <h2 class="section-title">最新文章</h2>
    <div class="posts-grid">
      {% for post in site.posts limit: 6 %}
      <a href="{{ post.url }}" class="post-card">
        <div class="post-date">{{ post.date | date: "%Y-%m-%d" }}</div>
        <h3 class="post-title">{{ post.title }}</h3>
        <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
        {% if post.tags %}
        <div class="post-tags">
          {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
        {% endif %}
      </a>
      {% else %}
      <p style="color: var(--text-muted); grid-column: 1 / -1; text-align: center; padding: 4rem;">
        还没有文章，去 _posts 目录创建你的第一篇文章吧！
      </p>
      {% endfor %}
    </div>
  </div>
</section>
