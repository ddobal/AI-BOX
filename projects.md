---
layout: default
title: Projects
permalink: /projects/
---

<style>
/* ===== 프로젝트 페이지 전체 정렬 ===== */
.projects-wrapper {
  margin-top: 40px;
}

/* ===== 카드 그리드 ===== */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 28px;
  margin-top: 32px;
}

/* ===== 카드 기본 ===== */
.project-card {
  background: #161616;
  border-radius: 16px;
  padding: 24px;
  border: 1px solid rgba(255,255,255,0.06);
  box-shadow: 0 12px 28px rgba(0,0,0,0.55);
  transition: all 0.3s ease;

  /* 기본 플로팅 애니메이션 */
  animation: floatCard 4.5s ease-in-out infinite;
}

/* ===== 카드에 서로 다른 딜레이 적용 (자연스러운 무브먼트) ===== */
.project-card:nth-child(1) { animation-delay: 0s; }
.project-card:nth-child(2) { animation-delay: .7s; }
.project-card:nth-child(3) { animation-delay: 1.4s; }
.project-card:nth-child(4) { animation-delay: 2.1s; }
.project-card:nth-child(5) { animation-delay: 2.8s; }
.project-card:nth-child(6) { animation-delay: 3.5s; }

/* ===== hover 효과 ===== */
.project-card:hover {
  transform: translateY(-8px) scale(1.015);
  box-shadow: 0 16px 32px rgba(0,0,0,0.75);
  border-color: rgba(255,255,255,0.14);
}

/* ===== 카드 내부 텍스트 ===== */
.project-title {
  font-size: 1.3rem;
  font-weight: 700;
  color: #fff;
  margin-bottom: 6px;
}

.project-sub {
  color: #aaa;
  font-size: 0.88rem;
  margin-bottom: 12px;
}

.project-desc {
  color: #ccc;
  font-size: 0.95rem;
  line-height: 1.45rem;
}

/* ===== Keyframes: 부드럽게 떠다니는 플로팅 ===== */
@keyframes floatCard {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-9px);
  }
  100% {
    transform: translateY(0px);
  }
}
</style>

<div class="projects-wrapper">
  <h1>🚀 Projects</h1>

  <div class="projects-grid">

    <div class="project-card">
      <div class="project-title">AI Vision Automation</div>
      <div class="project-sub">Computer Vision, Automation</div>
      <div class="project-desc">
        산업 현장 자동화를 위한 Object Detection + Tracking 기반의 비전 시스템 구축 프로젝트.
      </div>
    </div>

    <div class="project-card">
      <div class="project-title">Diffusion-based Image Generator</div>
      <div class="project-sub">Generative AI</div>
      <div class="project-desc">
        Stable Diffusion을 커스텀 데이터로 파인튜닝하여 특정 스타일 이미지 생성 모델 구현.
      </div>
    </div>

    <div class="project-card">
      <div class="project-title">RL Trading Bot</div>
      <div class="project-sub">Reinforcement Learning, Trading</div>
      <div class="project-desc">
        강화학습 기반으로 자동 진입/청산 전략을 스스로 학습하는 트레이딩 에이전트 개발 프로젝트.
      </div>
    </div>

  </div>
</div>
