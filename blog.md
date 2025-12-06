---
layout: default
title: Blog
permalink: /blog/
---

<!-- 📌 새 미니 히어로 블록 -->
<div class="page-mini-hero">
  <div class="page-mini-hero-icon">📝</div>
  <h1>Blog</h1>
  <p class="mini-hero-sub">
    공부하면서 남기고 싶은 메모, 실험 로그, 프로젝트 회고 등을 기록하는 공간입니다.
  </p>
</div>

<div class="section-card-grid">
  {% for post in site.posts %}
  <section class="section-card">
    <h2>🗂 {{ post.title }}</h2>
    <p class="section-card-meta">{{ post.date | date: "%Y-%m-%d" }}</p>
    <p>{{ post.excerpt }}</p>
    <a href="{{ post.url | relative_url }}">Read more →</a>
  </section>
  {% endfor %}

  {% if site.posts == empty %}
  <section class="section-card">
    <h2>🗂 아직 포스트가 없습니다.</h2>
    <p>
      첫 번째 글은 "XGBoost 모델 튜닝 로그"나  
      "강화학습 환경 설계 팁" 같은 내용을 적어보는 것도 좋아요.
    </p>
  </section>
  {% endif %}
</div>
