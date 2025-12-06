---
layout: project
title: 간단한 규칙 기반 챗봇
permalink: /projects/basic-chatbot/
order: 5
---

<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- 챗봇 얼굴 아이콘 -->
    <svg viewBox="0 0 24 24" width="32" height="32">
      <rect x="4" y="5" width="16" height="12" rx="3" fill="url(#botGrad)"/>
      <circle cx="10" cy="11" r="1.3" fill="#0f172a"/>
      <circle cx="14" cy="11" r="1.3" fill="#0f172a"/>
      <defs>
        <linearGradient id="botGrad" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0%" stop-color="#38bdf8"/>
          <stop offset="100%" stop-color="#6366f1"/>
        </linearGradient>
      </defs>
    </svg>
  </div>

  <h1>간단한 규칙 기반 챗봇</h1>
  <p class="mini-hero-sub">
    패턴 매칭과 의도 분류를 이용해 FAQ를 처리하는 기본 챗봇 구현
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    이 프로젝트는 거창한 딥러닝 모델보다는, 간단한 규칙 기반 방법으로 챗봇을 만들어 보는 것이 목적이다.
    자주 나오는 질문 패턴을 정리하고, 그에 대한 고정 응답을 매핑하는 방식으로 동작한다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Intent & Rule Design</h2>
  <p>
    먼저 자주 등장할 만한 질문들을 몇 가지 의도(intent) 카테고리로 나누었다.
    예를 들어 “인사”, “운영시간 문의”, “위치 문의”, “기타 문의” 같은 형태다.
    각 의도에 대응하는 키워드 패턴을 정의하고, 정규식과 단순 문자열 포함 여부로 매칭했다.
  </p>
  <p>
    의도 분류가 안 되는 문장은 “죄송하지만 잘 이해하지 못했습니다” 같은
    기본 응답으로 처리해 예외 상황도 고려했다.
  </p>
</div>

<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Reflection</h2>
  <p>
    직접 규칙들을 하나씩 정의해보면서, 규칙 기반 시스템의 한계가 어떤 식으로 나타나는지 체감할 수 있었다.
    동시에, 이런 규칙 기반 구조 위에 나중에 머신러닝 모델을 올려서
    점점 더 스마트한 챗봇을 만들어갈 수 있겠다는 아이디어도 떠올랐다.
  </p>
</div>
