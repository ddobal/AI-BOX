---
layout: default
title: About
permalink: /about/
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 사람 아이콘 -->
    <svg viewBox="0 0 24 24" width="36" height="36" aria-hidden="true">
      <path d="M12 2a5 5 0 1 1 0 10 5 5 0 0 1 0-10zm0 12c4.4 0 8 2 8 4.5V22H4v-3.5C4 16 7.6 14 12 14z"
            fill="url(#aboutGrad)"/>
      <defs>
        <linearGradient id="aboutGrad" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0%" stop-color="#4facfe"/>
          <stop offset="100%" stop-color="#38f9d7"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>About Me</h1>
  <p class="mini-hero-sub">
    AI·컴퓨터비전·자동화 분야를 공부하고 실험한 내용을 정리하는 공간
  </p>
</div>

<style>
  .about-section-title {
    display:flex;
    align-items:center;
    gap:10px;
    margin-bottom:12px;
  }
  .about-section-title svg {
    width:20px;
    height:20px;
  }
</style>

<!-- 소개 -->
<div class="section-card" style="max-width:900px; margin:0 auto 32px;">
  <div class="about-section-title">
    <!-- 아이콘: info -->
    <svg viewBox="0 0 24 24" fill="none">
      <circle cx="12" cy="12" r="10" stroke="#7dd3fc" stroke-width="1.4"/>
      <path d="M12 8.5v.01" stroke="#7dd3fc" stroke-width="2" stroke-linecap="round"/>
      <path d="M12 11v5" stroke="#7dd3fc" stroke-width="2" stroke-linecap="round"/>
    </svg>
    <h2>소개</h2>
  </div>

  <p>
    AI 기술을 공부하면서 실험 과정 하나하나를 정리해두기 위해 이 포트폴리오(AI-BOX)를 만들었다.
    처음엔 과제 때문이었지만, 구조를 구축하다 보니 나중에도 오래 쓸 수 있는 공간이면 좋겠다는 생각이 들었다.
  </p>
  <p>
    현재는 컴퓨터비전, 생성형 모델, 자동화 시스템 쪽을 중심으로 공부하고 있고,
    시행착오나 실험 결과를 블로그 형태로 남기고 있다.
  </p>
</div>

<!-- 관심 분야 -->
<div class="section-card" style="max-width:900px; margin:0 auto 32px;">
  <div class="about-section-title">
    <!-- 아이콘: target -->
    <svg viewBox="0 0 24 24" fill="none">
      <circle cx="12" cy="12" r="9" stroke="#a78bfa" stroke-width="1.4"/>
      <circle cx="12" cy="12" r="5" stroke="#a78bfa" stroke-width="1.4"/>
    </svg>
    <h2>관심 분야</h2>
  </div>

  <ul>
    <li>Computer Vision (Object Detection, Pose Tracking 등)</li>
    <li>Generative AI (Diffusion, Style Transfer, Image2Image)</li>
    <li>Reinforcement Learning 실험 및 자동매매 전략 연구</li>
    <li>AI 기반 자동화 시스템 구조 설계</li>
  </ul>
</div>

<!-- 포트폴리오 구성 목적 -->
<div class="section-card" style="max-width:900px; margin:0 auto 32px;">
  <div class="about-section-title">
    <!-- 아이콘: layers -->
    <svg viewBox="0 0 24 24" fill="none">
      <path d="M12 3l8 4-8 4-8-4 8-4z" stroke="#f9a8d4" stroke-width="1.4" />
      <path d="M4 12l8 4 8-4" stroke="#f9a8d4" stroke-width="1.4" />
      <path d="M4 16l8 4 8-4" stroke="#f9a8d4" stroke-width="1.4" />
    </svg>
    <h2>포트폴리오 구성 목적</h2>
  </div>

  <p>
    단순히 결과물을 모아두는 게 아니라, 공부 과정에서 겪은 시행착오와 실험 기록을 함께 남겨
    나중에 다시 참고할 수 있는 개인 연구 공간을 만드는 것이 목적이다.
  </p>
  <p>
    지금은 구조 중심이지만, 시간이 지나면서 실제 프로젝트와 연구 내용으로 점점 채워질 예정이다.
  </p>
</div>

<!-- 향후 계획 -->
<div class="section-card" style="max-width:900px; margin:0 auto 32px;">
  <div class="about-section-title">
    <!-- 아이콘: roadmap -->
    <svg viewBox="0 0 24 24" fill="none">
      <path d="M5 3h14v4H5z" stroke="#c084fc" stroke-width="1.4"/>
      <circle cx="7" cy="14" r="2" stroke="#c084fc" stroke-width="1.4"/>
      <circle cx="17" cy="18" r="2" stroke="#c084fc" stroke-width="1.4"/>
      <path d="M7 14v-7h10v11" stroke="#c084fc" stroke-width="1.4" />
    </svg>
    <h2>향후 계획</h2>
  </div>

  <p>
    - 새로운 프로젝트가 생길 때마다 Projects 페이지에 추가  
    - 실험 과정과 학습 내용을 Blog에 계속 기록  
    - 필요하면 태그·검색 기능처럼 탐색성을 높이는 기능도 적용  
  </p>
</div>
