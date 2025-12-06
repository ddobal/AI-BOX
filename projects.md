---
layout: default
title: Projects
permalink: /projects/
---

<!-- 📌 미니 히어로 (SVG 로고 적용) -->
<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 로켓 SVG -->
    <svg width="38" height="38" viewBox="0 0 24 24" fill="none">
      <path d="M12 2c2.4 0 4.8.8 6.4 2.4l-4.8 4.8H8L12 2zM4 20l2.4-6.4h4.8l4.8 4.8A10 10 0 0 1 12 22c-2.4 0-4.8-.8-6.4-2.4z"
            fill="url(#rocketGrad)"/>
      <defs>
        <linearGradient id="rocketGrad">
          <stop offset="0%" stop-color="#ff6b6b"/>
          <stop offset="100%" stop-color="#f9d423"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>Projects</h1>
  <p class="mini-hero-sub">
    개인적으로 연구·개발한 프로젝트들을 정리합니다.  
    실제 실험 결과와 구현 중심으로 설명합니다.
  </p>
</div>

<!-- 📌 카드 목록 -->
<div class="section-card-grid--columns">

  <section class="section-card">
    <h2 class="section-card-title">AI Vision Automation</h2>
    <p class="section-card-meta">Computer Vision · Automation</p>
    <p>
      실시간 Object Detection + Tracking 기반  
      현장 자동화 시스템 구축 프로젝트.
    </p>
  </section>

  <section class="section-card">
    <h2 class="section-card-title">Diffusion-based Image Generator</h2>
    <p class="section-card-meta">Generative AI</p>
    <p>
      Stable Diffusion을 커스터마이즈하여  
      컨셉 아트 및 프로필 이미지 생성 파이프라인 제작.
    </p>
  </section>

  <section class="section-card">
    <h2 class="section-card-title">RL Trading Bot</h2>
    <p class="section-card-meta">Reinforcement Learning · Trading</p>
    <p>
      강화학습 기반 시뮬레이션 환경과  
      실제 거래소 API를 연결한 자동매매 에이전트 실험.
    </p>
  </section>

</div>
