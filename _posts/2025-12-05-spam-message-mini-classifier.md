---
layout: post
title: "하루 동안 받은 스팸 메시지를 직접 분류해보는 미니 실험"
date: 2025-12-05
tags: [nlp, experiment, daily-log]
excerpt: "하루 동안 받은 문자들을 모아 간단한 규칙으로 스팸·정상 여부를 나눠 본 텍스트 분류 맛보기."
---

<style>
  .post-section-title{display:flex;align-items:center;gap:8px;margin:20px 0 8px;}
  .post-section-title svg{width:20px;height:20px;}
  .inline-diagram{margin:14px auto 20px;max-width:720px;border-radius:14px;background:#020617;
    border:1px solid rgba(148,163,184,0.45);padding:10px;}
  .inline-diagram svg{width:100%;display:block;}
  .inline-diagram-caption{text-align:center;margin-top:6px;font-size:0.8rem;color:#94a3b8;}
</style>

<div class="post-section-title">
  <svg viewBox="0 0 24 24"><path d="M3 12h18" stroke="#38bdf8" stroke-width="2"/></svg>
  <h2>실험 동기</h2>
</div>

<p>
  오늘 하루 동안 받은 문자·메시지 중에서  
  스팸 의심 문장들을 따로 모아 <strong>직접 분류</strong>해 보는 미니 실험을 했다.
  머신러닝 모델까지 돌리지는 않고, 규칙 기반 필터만으로
  어느 정도까지 걸러지는지 감만 보는 수준이다.
</p>

<div class="inline-diagram">
  <svg viewBox="0 0 820 150">
    <rect x="70" y="50" width="160" height="60" rx="12"
      fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="150" y="85" fill="#e5e7eb" font-size="12" text-anchor="middle">수신 메시지</text>

    <line x1="230" y1="80" x2="330" y2="80" stroke="#64748b" stroke-width="2"/>
    <polygon points="330,80 320,75 320,85" fill="#64748b"/>

    <rect x="330" y="40" width="200" height="80" rx="14"
      fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="430" y="75" fill="#e0e7ff" font-size="12" text-anchor="middle">규칙 기반 필터</text>

    <line x1="530" y1="80" x2="630" y2="80" stroke="#64748b" stroke-width="2"/>
    <polygon points="630,80 620,75 620,85" fill="#64748b"/>

    <rect x="630" y="50" width="150" height="60" rx="12"
      fill="#020617" stroke="#22c55e" stroke-width="2"/>
    <text x="705" y="85" fill="#bbf7d0" font-size="12" text-anchor="middle">스팸/정상 분류</text>
  </svg>
  <div class="inline-diagram-caption">간단한 분류 실험 흐름</div>
</div>

---

### 사용한 규칙

<ul>
  <li>“상담”, “대출”, “광고” 같은 특정 키워드 포함 여부</li>
  <li>매우 긴 링크 또는 수상한 도메인 포함 여부</li>
  <li>발신번호가 저장된 연락처인지, 아니면 이상한 패턴인지</li>
</ul>

<p>
  이 기준을 대략 적용해 보니, 생각보다 많은 메시지를
  “사실상 스팸”으로 분류할 수 있었다.
</p>

---

<div class="post-section-title">
  <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="8" stroke="#22c55e" stroke-width="2"/></svg>
  <h2>느낀 점</h2>
</div>

<p>
  단순한 규칙만으로도 <strong>스팸의 절반 정도</strong>는 걸러지는 것 같았다.
  다만, 애매한 홍보성 문자들은 사람이 봐도 애매해서
  “이걸 스팸으로 볼지 말지” 기준을 정하는 것 자체가 어렵다는 것도 느꼈다.
</p>
<p>
  다음에는 이 데이터를 조금 정리해서  
  진짜로 <strong>Naive Bayes 같은 간단한 텍스트 분류 모델</strong>을 돌려 보고,
  규칙 기반 필터와 성능을 비교해 보면 재미있을 것 같다.
</p>
