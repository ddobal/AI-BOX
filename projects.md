---
layout: default
title: Projects
permalink: /projects/
---

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
  margin-top: 40px;
}

.project-card {
  background: #161616;
  border-radius: 14px;
  padding: 22px;
  transition: all 0.25s ease;
  border: 1px solid #222;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.45);
  border-color: #444;
}

.project-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #fff;
}

.project-sub {
  color: #aaa;
  font-size: 0.9rem;
  margin-bottom: 12px;
}

.project-desc {
  color: #ccc;
  font-size: 0.95rem;
  line-height: 1.45rem;
}
</style>

# 🚀 Projects

<div class="projects-grid">

<div class="project-card">
  <div class="project-title">AI Vision Automation</div>
  <div class="project-sub">Computer Vision, Automation</div>
  <div class="project-desc">
    산업 현장 자동화를 위해 Object Detection + Tracking 파이프라인을 구축한 프로젝트입니다.
  </div>
</div>

<div class="project-card">
  <div class="project-title">Diffusion-based Image Generator</div>
  <div class="project-sub">Generative AI, Diffusion Model</div>
  <div class="project-desc">
    Stable Diffusion 기반으로 커스텀 파인튜닝한 이미지 생성 모델 제작 프로젝트입니다.
  </div>
</div>

<div class="project-card">
  <div class="project-title">RL Trading Bot</div>
  <div class="project-sub">Reinforcement Learning, Trading</div>
  <div class="project-desc">
    강화학습 기반으로 포지션 진입/청산 전략을 자동 학습하도록 설계한 알고리즘 트레이딩 프로젝트.
  </div>
</div>

</div>
