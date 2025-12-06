---
layout: post
title: "수업에서 배운 피처 스케일링을 직접 테스트해본 미니 실험"
date: 2025-12-03
tags: [ml, study-log, experiment]
excerpt: "MinMaxScaler와 StandardScaler를 작은 예시 데이터에 적용해 보며 감을 잡아본 실험 로그."
---

<style>
  .post-section-title { display:flex;align-items:center;gap:8px;margin:20px 0 8px;}
  .post-section-title svg{width:20px;height:20px;}
  .inline-diagram{margin:14px auto 20px;max-width:720px;border-radius:14px;background:#020617;
    border:1px solid rgba(148,163,184,0.45);padding:10px;}
  .inline-diagram svg{width:100%;display:block;}
  .inline-diagram-caption{text-align:center;margin-top:6px;font-size:0.8rem;color:#94a3b8;}
</style>

<div class="post-section-title">
  <svg viewBox="0 0 24 24"><path d="M3 12h18" stroke="#38bdf8" stroke-width="2"/></svg>
  <h2>실험 목적</h2>
</div>

<p>
  머신러닝 수업에서 <strong>피처 스케일링</strong>을 배웠을 때,
  “어차피 수식만 바꾸는 거 아닌가?”라는 생각이 조금 들었다.
  그래서 아주 작은 숫자 데이터에 직접 스케일러를 적용해 보고
  값이 어떻게 바뀌는지 눈으로 확인해 보기로 했다.
</p>

<div class="inline-diagram">
  <svg viewBox="0 0 820 150">
    <rect x="70" y="50" width="160" height="60" rx="12"
      fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="150" y="85" fill="#e5e7eb" font-size="12" text-anchor="middle">원본 데이터</text>

    <line x1="230" y1="80" x2="330" y2="80" stroke="#64748b" stroke-width="2"/>
    <polygon points="330,80 320,75 320,85" fill="#64748b"/>

    <rect x="330" y="40" width="180" height="80" rx="14"
      fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="420" y="75" fill="#e5e7eb" font-size="12" text-anchor="middle">Scaling</text>

    <line x1="510" y1="80" x2="610" y2="80" stroke="#64748b" stroke-width="2"/>
    <polygon points="610,80 600,75 600,85" fill="#64748b"/>

    <rect x="610" y="50" width="150" height="60" rx="12"
      fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="685" y="85" fill="#bbf7d0" font-size="12" text-anchor="middle">스케일링 결과</text>
  </svg>
  <div class="inline-diagram-caption">피처 스케일링 기본 흐름</div>
</div>

---

### 📊 실험에 사용한 작은 데이터

<p>
  예시로 사용한 1차원 데이터는 다음과 같다.
</p>

```text
[10, 12, 15, 20, 30]
