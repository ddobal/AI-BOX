---
layout: default
title: AI Food Calorie Estimation
permalink: /projects/ai-food-calorie-estimation/
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 음식 아이콘 -->
    <svg width="40" height="40" viewBox="0 0 24 24" fill="none">
      <circle cx="12" cy="12" r="7" stroke="white" stroke-width="1.7"/>
      <circle cx="12" cy="12" r="2.5" fill="white"/>
    </svg>
  </div>

  <h1>AI 기반 음식 칼로리 추정</h1>
  <p class="mini-hero-sub">음식 이미지 → 종류/양 → 칼로리 예측</p>
</div>

<div class="section-card-grid">

<section class="section-card"><h2>Overview</h2>
<p>음식 이미지를 기반으로 음식 종류와 대략적인 양을 예측해 칼로리를 계산하는 모델을 구축했습니다.</p>
</section>

<section class="section-card"><h2>Architecture</h2>
<p>Classifier + 회귀 모델을 결합해량·종류를 동시에 추정하는 구조를 사용했습니다.</p>
</section>

<section class="section-card"><h2>Key Technologies</h2>
<ul><li>EfficientNet</li><li>Regression Head</li><li>Food Dataset</li></ul>
</section>

<section class="section-card"><h2>Outcome & Learnings</h2>
<p>실제 데이터 분포의 편향과 음식 종류별 특징 차이를 학습했습니다.</p>
</section>

</div>
