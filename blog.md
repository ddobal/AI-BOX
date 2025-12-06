---
layout: default
title: Blog
permalink: /blog/
---

<style>
  .section-heading {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.2rem;
    margin-bottom: 10px;
  }

  .section-heading-icon {
    width: 26px;
    height: 26px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }

  .section-heading-icon svg {
    width: 22px;
    height: 22px;
    display: block;
  }
</style>

<!-- 📌 미니 히어로 (기존 블로그 펜 아이콘 유지) -->
<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 펜/글쓰기 아이콘 -->
    <svg width="38" height="38" viewBox="0 0 24 24" fill="none">
      <path d="M3 17.25V21h3.75l11-11.03-3.75-3.75L3 17.25zM20.71 7.04c.39-.39.39-1.02 0-1.41l-2.34-2.34a1 1 0 0 0-1.41 0l-1.83 1.83 3.75 3.75 1.83-1.83z"
            fill="url(#blogGrad)" />
      <defs>
        <linearGradient id="blogGrad">
          <stop offset="0%" stop-color="#38f9d7"/>
          <stop offset="100%" stop-color="#4facfe"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>Blog</h1>
  <p class="mini-hero-sub">
    AI 실험 과정, 학습 기록, 기술 정리, 그리고 시행착오를 남기는 공간입니다.  
    실제 연구·개발 과정에서 얻은 지식을 꾸준히 문서화하는 것이 목표입니다.
  </p>
</div>

<div class="section-card-grid">

  {% if site.posts == empty %}
    <!-- 포스트가 하나도 없을 때 표시 -->
    <section class="section-card">
      <h2 class="section-heading">
        <span class="section-heading-icon">
          <!-- 폴더 아이콘 SVG -->
          <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
            <path
              d="M4 7.5A1.5 1.5 0 0 1 5.5 6H9l2 2.5h7.5A1.5 1.5 0 0 1 20 10v7.5A1.5 1.5 0 0 1 18.5 19h-13A1.5 1.5 0 0 1 4 17.5v-10Z"
              stroke="white"
              stroke-width="1.6"
              fill="none"
            />
          </svg>
        </span>
        아직 포스트가 없습니다.
      </h2>
      <p>
        첫 번째 글을 작성하면 이 공간에 자동으로 표시됩니다.  
        예: “Diffusion 모델 구조 정리”, “강화학습 환경 설계 로그” 등.
      </p>
    </section>
  {% endif %}

  {% for post in site.posts %}
    <a class="section-card section-card-link" href="{{ post.url | relative_url }}">
      <h2 class="section-heading">
        <span class="section-heading-icon">
          <!-- 폴더 아이콘 SVG -->
          <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
            <path
              d="M4 7.5A1.5 1.5 0 0 1 5.5 6H9l2 2.5h7.5A1.5 1.5 0 0 1 20 10v7.5A1.5 1.5 0 0 1 18.5 19h-13A1.5 1.5 0 0 1 4 17.5v-10Z"
              stroke="white"
              stroke-width="1.6"
              fill="none"
            />
          </svg>
        </span>
        {{ post.title }}
      </h2>

      <p class="section-card-meta">
        {{ post.date | date: "%Y-%m-%d" }}
        {% if post.category %} · {{ post.category }}{% endif %}
        {% if post.tags %} · Tags: {{ post.tags | join: ", " }}{% endif %}
      </p>

      <p>
        {% if post.excerpt %}
          {{ post.excerpt | strip_html | truncate: 120 }}
        {% else %}
          {{ post.content | strip_html | truncate: 120 }}
        {% endif %}
      </p>
    </a>
  {% endfor %}

</div>
