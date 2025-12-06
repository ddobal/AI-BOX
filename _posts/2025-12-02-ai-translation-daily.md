---
layout: post
title: "AI 자동 번역을 하루 동안 의식적으로 관찰해보기"
date: 2025-12-02
tags: [ai, translation, daily-log]
excerpt: "하루 동안 스마트폰·노트북에서 사용한 AI 번역 기능을 의식적으로 관찰해 본 기록."
---

<style>
  .post-section-title {
    display: flex;
    align-items: center;
    gap: 8px;
    margin: 20px 0 8px;
  }
  .post-section-title svg { width: 20px; height: 20px; }
  .inline-diagram {
    margin: 14px auto 20px;
    max-width: 720px;
    border-radius: 14px;
    background: #020617;
    border: 1px solid rgba(148,163,184,0.45);
    padding: 10px;
  }
  .inline-diagram svg { width: 100%; display: block; }
  .inline-diagram-caption {
    margin-top: 6px; font-size: 0.8rem; color: #94a3b8; text-align:center;
  }
</style>

<div class="post-section-title">
  <svg viewBox="0 0 24 24">
    <path d="M4 12h16M12 4v16" stroke="#38bdf8" stroke-width="2"/>
  </svg>
  <h2>오늘의 관찰</h2>
</div>

<p>
  오늘은 스마트폰과 노트북에서 자연스럽게 사용했던 <strong>AI 번역 기능</strong>을
  조금 더 의식하면서 살펴보았다. 평소엔 그냥 편해서 쓰지만,
  실제로는 여러 가지 모델이 동시에 돌아가고 있다는 점이 궁금했다.
</p>

<div class="inline-diagram">
  <svg viewBox="0 0 820 160">
    <rect x="70" y="50" width="160" height="70" rx="12"
      fill="#020617" stroke="#38bdf8" stroke-width="2"></rect>
    <text x="150" y="90" fill="#e5e7eb" font-size="12" text-anchor="middle">영문 텍스트</text>

    <line x1="230" y1="85" x2="330" y2="85" stroke="#64748b" stroke-width="2"/>
    <polygon points="330,85 320,80 320,90" fill="#64748b"/>

    <rect x="330" y="40" width="200" height="90" rx="14"
      fill="#020617" stroke="#6366f1" stroke-width="2"></rect>
    <text x="430" y="75" fill="#e0e7ff" font-size="12" text-anchor="middle">AI 번역 모델</text>

    <line x1="530" y1="85" x2="620" y2="85" stroke="#64748b" stroke-width="2"/>
    <polygon points="620,85 610,80 610,90" fill="#64748b"/>

    <rect x="620" y="50" width="160" height="70" rx="12"
      fill="#020617" stroke="#22c55e" stroke-width="2"></rect>
    <text x="700" y="90" fill="#bbf7d0" font-size="12" text-anchor="middle">한국어 번역 결과</text>
  </svg>
  <div class="inline-diagram-caption">번역 모델의 기본 흐름 개념도</div>
</div>

---

### 📱 스마트폰에서 만난 번역들

<ul>
  <li>영어 웹페이지를 열면 자동으로 뜨는 브라우저 번역 팝업</li>
  <li>카톡에서 외국어 메시지를 길게 눌렀을 때 나오는 “번역하기” 버튼</li>
  <li>사진 속 텍스트를 읽고 번역해 주는 이미지 번역(OCR + 번역)</li>
</ul>

### 💻 노트북에서 만난 번역들

<ul>
  <li>개발 문서나 깃허브 README를 페이지 전체 번역으로 읽기</li>
  <li>논문 초록을 복붙해서 번역기 돌려본 뒤, 다시 영어 원문과 비교</li>
  <li>PDF 번역 플러그인으로 긴 문서를 대충 흐름만 파악하기</li>
</ul>

---

<div class="post-section-title">
  <svg viewBox="0 0 24 24">
    <circle cx="12" cy="12" r="9" stroke="#22c55e" stroke-width="2" />
  </svg>
  <h2>느낀 점</h2>
</div>

<p>
  예전에는 번역기가 “대충 의미만 맞으면 다행” 수준이었는데,
  지금은 자연스러운 표현이 꽤 많이 나온다는 걸 다시 느꼈다.
  또, 텍스트·음성·이미지 번역이 전부 한 앱 안에서 자연스럽게 섞여 있다는 것도 신기했다.
</p>
<p>
  사용자 입장에서는 “번역 버튼 한 번 눌렀을 뿐”이지만,
  그 뒤에는 <strong>언어모델, OCR, 음성 인식</strong> 같은 여러 기술이 조합되어 있다는 걸
  의식하면서 보니까, 평소에 너무 당연하게 쓰고 있었던 것 같아 조금 반성(?)도 되었다.
</p>
