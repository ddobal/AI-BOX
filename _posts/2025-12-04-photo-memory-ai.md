---
layout: post
title: "갤러리의 ‘추억 자동 생성’ 기능 속 AI가 궁금해져서 분석해봄"
date: 2025-12-04
tags: [ai, clustering, daily-log]
excerpt: "사진 앱의 ‘추억 자동 생성’ 기능 뒤에서 어떤 AI가 돌고 있을지 추측해 본 관찰 노트."
---

<style>
  .post-section-title{
    display:flex;
    align-items:center;
    gap:8px;
    margin:20px 0 8px;
  }
  .post-section-title svg{width:20px;height:20px;}
  .inline-diagram{
    margin:14px auto 20px;
    max-width:720px;
    border-radius:14px;
    background:#020617;
    border:1px solid rgba(148,163,184,0.45);
    padding:10px;
  }
  .inline-diagram svg{width:100%;display:block;}
  .inline-diagram-caption{
    text-align:center;
    margin-top:6px;
    font-size:0.8rem;
    color:#94a3b8;
  }
</style>

<div class="post-section-title">
  <svg viewBox="0 0 24 24">
    <circle cx="12" cy="12" r="8" stroke="#38bdf8" stroke-width="2"/>
  </svg>
  <h2>무슨 기능인지?</h2>
</div>

<p>
  요즘 스마트폰 갤러리에서 자주 보이는 <strong>“추억 자동 생성”</strong> 기능이 있다.
  사진을 따로 고르지 않아도, 앱이 알아서 특정 기간이나 장소를 묶어서
  짧은 영상으로 만들어 주는 기능이다.  
  평소에는 그냥 “오 재밌네” 하고 넘어갔는데,
  오늘은 거기에 어떤 AI가 쓰였을지 조금 더 진지하게 생각해 봤다.
</p>

<div class="inline-diagram">
  <svg viewBox="0 0 820 170">
    <rect x="60" y="60" width="150" height="60" rx="12"
      fill="#020617" stroke="#38bdf8" stroke-width="2"></rect>
    <text x="135" y="95" fill="#e5e7eb" font-size="12" text-anchor="middle">사진들</text>

    <line x1="210" y1="90" x2="310" y2="90" stroke="#64748b" stroke-width="2"/>
    <polygon points="310,90 300,85 300,95" fill="#64748b"/>

    <rect x="310" y="40" width="220" height="100" rx="14"
      fill="#020617" stroke="#6366f1" stroke-width="2"></rect>
    <text x="420" y="75" fill="#e0e7ff" font-size="12" text-anchor="middle">AI 분석</text>
    <text x="420" y="92" fill="#94a3b8" font-size="10" text-anchor="middle">
      얼굴 · 장소 · 시간대 클러스터링
    </text>

    <line x1="530" y1="90" x2="630" y2="90" stroke="#64748b" stroke-width="2"/>
    <polygon points="630,90 620,85 620,95" fill="#64748b"/>

    <rect x="630" y="60" width="150" height="60" rx="12"
      fill="#020617" stroke="#22c55e" stroke-width="2"></rect>
    <text x="705" y="95" fill="#bbf7d0" font-size="12" text-anchor="middle">자동 생성 영상</text>
  </svg>
  <div class="inline-diagram-caption">사진 → 클러스터링 → 추억 영상</div>
</div>

---

### 관찰해본 기능

<ul>
  <li>비슷한 <strong>시간대</strong>에 찍힌 사진들을 하나의 묶음으로 정리해 준다.</li>
  <li>같은 <strong>사람 얼굴이 여러 번 등장</strong>하는 사진을 골라 하이라이트에 넣어 준다.</li>
  <li><strong>위치 정보(장소)</strong>를 이용해 “여행”, “카페” 같은 분위기별로 자동 분류하는 느낌이다.</li>
  <li>사진 전체 분위기에 맞는 <strong>BGM과 전환 효과</strong>를 자동으로 붙여 짧은 영상으로 만들어 준다.</li>
</ul>

---

<div class="post-section-title">
  <svg viewBox="0 0 24 24">
    <circle cx="12" cy="12" r="8" stroke="#22c55e" stroke-width="2"/>
  </svg>
  <h2>느낀 점</h2>
</div>

<p>
  단순히 “사진 슬라이드 쇼”를 만드는 기능이라고 생각했는데,
  실제로는 <strong>이미지 분류, 얼굴 인식, 클러스터링, 추천</strong> 같은 요소들이
  다 섞여 있는 작은 종합 AI 시스템처럼 느껴졌다.
</p>
<p>
  나중에 프로젝트를 할 때도, 이렇게 사용자가 직접 태그를 달지 않아도
  알아서 추억을 정리해 주는 기능처럼, <strong>“귀찮음을 줄여주는 AI”</strong>를
  한 번 만들어 보고 싶다는 생각이 들었다.
</p>
