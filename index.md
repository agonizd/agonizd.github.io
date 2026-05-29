---
layout: default
title: 首页
---
<section class="hero">
  <div class="container">
    <span class="badge">✨ Jekyll + GitHub Pages</span>
    <h1>欢迎来到我的 <span>数字空间</span></h1>
    <p>记录思考、分享技术、收藏灵感。这是一个用代码构建的个人博客。</p>
  </div>
</section>

<section style="padding-bottom: 4rem;">
  <div class="container">
    <h2 class="section-title">最新文章</h2>
    <div class="posts-grid">
      {% for post in site.posts limit: 6 %}
      <a href="{{ post.url }}" class="post-card">
        <div class="post-date">{{ post.date | date: "%Y-%m-%d" }}</div>
        <h3 class="post-title">{{ post.title }}</h3>
        <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 100 }}</p>
        {% if post.tags %}
        <div class="post-tags">
          {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
        {% endif %}
      </a>
      {% else %}
      <p style="color: var(--text-muted); grid-column: 1 / -1; text-align: center; padding: 3rem;">
        还没有文章，去 _posts 目录创建你的第一篇文章吧！
      </p>
      {% endfor %}
    </div>
  </div>
</section>
