---
layout: post
title: "수업에서 배운 피처 스케일링을 직접 테스트해본 미니 실험"
date: 2025-12-03
tags: [ml, study-log, experiment]
excerpt: "작은 숫자 데이터에 MinMaxScaler와 StandardScaler를 적용해 보며 차이를 직접 확인해 본 실험."
---

<style>
  .post-section-title { 
    display:flex; 
    align-items:center; 
    gap:8px; 
    margin:20px 0 8px;
  }
  .post-section-title svg { width:20px; height:20px; }
  .inline-diagram {
    margin:14px auto 20px;
    max-width:720px;
    border-radius:14px;
    background:#020617;
    border:1px solid rgba(148,163,184,0.45);
    padding:10px;
  }
  .inline-diagram svg {
    width:100%;
    display:block;
  }
  .inline-diagram-caption {
    text-align:center;
    margin-top:6px;
    font-size:0.8rem;
    color:#94a3b8;
  }
</style>

<div class="post-section-title">
  <svg viewBox="0 0 24 24"><path d="M3 12h18" stroke="#38bdf8" stroke-width="2"/></svg>
  <h2>실험 목적</h2>
</div>

<p>
  머신러닝 수업에서 <strong>피처 스케일링(StandardScaler, MinMaxScaler)</strong>을 배웠을 때  
  머리로는 이해했지만 실제 값이 어떻게 달라지는지는 잘 와닿지 않았다.  
  그래서 오늘은 아주 간단한 숫자 데이터를 가지고,  
  두 스케일러가 어떤 차이를 만들어내는지 직접 눈으로 확인해 보기로 했다.
</p>

<div class="inline-diagram">
  <svg viewBox="0 0 820 150">
    <!-- 원본 -->
    <rect x="70" y="50" width="160" height="60" rx="12"
      fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="150" y="85" fill="#e5e7eb" font-size="12" text-anchor="middle">원본 데이터</text>

    <!-- 화살표 -->
    <line x1="230" y1="80" x2="330" y2="80" stroke="#64748b" stroke-width="2"/>
    <polygon points="330,80 320,75 320,85" fill="#64748b"/>

    <!-- 스케일링 블록 -->
    <rect x="330" y="40" width="180" height="80" rx="14"
      fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="420" y="75" fill="#e5e7eb" font-size="12" text-anchor="middle">Scaling</text>

    <!-- 화살표2 -->
    <line x1="510" y1="80" x2="610" y2="80" stroke="#64748b" stroke-width="2"/>
    <polygon points="610,80 600,75 600,85" fill="#64748b"/>

    <!-- 결과 -->
    <rect x="610" y="50" width="150" height="60" rx="12"
      fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="685" y="85" fill="#bbf7d0" font-size="12" text-anchor="middle">스케일링 결과</text>
  </svg>
  <div class="inline-diagram-caption">피처 스케일링의 기본 처리 흐름</div>
</div>

---

## 📊 사용한 데이터 (아주 소박함)
<p>
  실험 데이터는 일부러 단순하게 선택했다.
[10, 12, 15, 20, 30]
</p>


<p>
  숫자가 커지거나 복잡해지면 직관적으로 비교하기 어렵기 때문에  
  이 정도가 딱 스케일링을 관찰하기 좋은 수준이라고 생각했다.
</p>

---

## 🔧 적용한 스케일링 방법

### 1) **MinMaxScaler**
- 최소값 → 0  
- 최대값 → 1  
- 나머지는 그 사이 비율에 따라 배치  
- 범위만 맞추고 싶을 때 사용

### 2) **StandardScaler**
- 평균 → 0  
- 표준편차 → 1  
- 값의 “얼마나 떨어져 있는지”가 중요할 때 사용  
- kNN, SVM 등 거리 기반 모델에 특히 중요

---

<div class="post-section-title">
  <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="8" stroke="#22c55e" stroke-width="2"/></svg>
  <h2>실험 과정에서 재미있던 점</h2>
</div>

<p>
  단순히 "값이 줄어드는 정도"의 차이가 아니라,  
  <strong>데이터가 어떤 분포를 갖도록 만들고 싶은지</strong>에 따라  
  스케일러 선택이 달라진다는 걸 다시 느끼게 되었다.
</p>

<ul>
  <li>MinMax는 전체 모양을 유지한 채 ‘0~1 범위로 압축’</li>
  <li>Standard는 중심(평균)을 기준으로 ‘얼마나 떨어져 있는지’를 강조</li>
</ul>

<p>
  그래서 같은 데이터여도,  
  스케일링 결과를 시각화해 보면 “성격 자체가 달라진 느낌”이 들었다.
</p>

---

## 📝 개인적인 깨달음

<p>
  이번 실험은 매우 작은 수준이었지만,  
  앞으로 머신러닝 모델을 쓸 때 스케일링을 “옵션” 정도로 보면 안 되겠다는 생각이 들었다.  
  특히 거리 기반 모델(kNN, K-means 등)을 다룰 때는  
  <strong>스케일링이 모델 성능의 절반 이상을 결정하기도 한다</strong>.
</p>

<p>
  다음에는 간단한 kNN 모델을 돌려서  
  스케일링 전·후 결과 차이를 더 명확히 비교해 보고 싶다.
</p>
