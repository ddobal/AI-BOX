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

<!-- Overview -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Overview</h2>
  <p>
    이 프로젝트는 거창한 딥러닝 모델보다는, 간단한 규칙 기반 방법으로 챗봇을 만들어 보는 것이 목적이다.
    자주 나오는 질문 패턴을 정리하고, 그에 대한 고정 응답을 매핑하는 방식으로 동작한다.
  </p>
  <p>
    아래 다이어그램은 사용자의 입력이 규칙 기반 챗봇 내부에서 어떤 흐름으로 처리되는지 한눈에 정리한 구조도이다.
  </p>
</div>

<!-- Diagram 1 : Chatbot Flow -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Chatbot Flow Diagram</h3>
  <p style="margin-bottom:12px;">
    사용자의 문장이 들어와서 패턴 매칭을 거친 뒤, 최종 응답으로 변환되는 과정을 단순화해 표현했다.
  </p>

  <svg width="100%" height="260" viewBox="0 0 800 260">
    <!-- User Input -->
    <rect x="40" y="80" width="160" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="120" y="115" font-size="16" fill="#e2e8f0" text-anchor="middle">사용자 입력</text>

    <!-- Arrow 1 -->
    <line x1="200" y1="110" x2="300" y2="110" stroke="#64748b" stroke-width="2"/>
    <polygon points="300,110 290,105 290,115" fill="#64748b"/>

    <!-- Pattern Matcher -->
    <rect x="300" y="60" width="200" height="100" rx="14" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="400" y="98" font-size="15" fill="#e2e8f0" text-anchor="middle">패턴 매칭 / 정규식 검사</text>
    <text x="400" y="120" font-size="12" fill="#94a3b8" text-anchor="middle">키워드 포함 여부 · 정규 표현식</text>

    <!-- Arrow 2 -->
    <line x1="500" y1="110" x2="600" y2="110" stroke="#64748b" stroke-width="2"/>
    <polygon points="600,110 590,105 590,115" fill="#64748b"/>

    <!-- Response -->
    <rect x="600" y="80" width="160" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="680" y="115" font-size="16" fill="#e2e8f0" text-anchor="middle">응답 선택 / 출력</text>

    <!-- Fallback -->
    <rect x="300" y="190" width="200" height="50" rx="10" fill="#020617" stroke="#f97316" stroke-width="1.8"/>
    <text x="400" y="215" font-size="13" fill="#fed7aa" text-anchor="middle">
      매칭 실패 → 기본 응답 처리
    </text>

    <!-- Arrow to fallback -->
    <line x1="400" y1="160" x2="400" y2="190" stroke="#64748b" stroke-dasharray="4 4" stroke-width="2"/>
  </svg>
</div>

<!-- Intent & Rule Design -->
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
  <p>
    아래 도표는 이번 프로젝트에서 사용한 대표적인 Intent 분류를 시각적으로 정리한 것이다.
  </p>
</div>

<!-- Diagram 2 : Intent Category Diagram -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Intent Category Diagram</h3>
  <svg width="100%" height="260" viewBox="0 0 820 260">
    <!-- Center Node -->
    <rect x="310" y="30" width="200" height="60" rx="12" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="410" y="60" fill="#e2e8f0" font-size="16" text-anchor="middle">INTENT 분류</text>
    <text x="410" y="80" fill="#94a3b8" font-size="12" text-anchor="middle">키워드 / 정규식 기반</text>

    <!-- Intent Boxes -->
    <rect x="80" y="150" width="160" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="160" y="180" font-size="15" fill="#e2e8f0" text-anchor="middle">인사</text>

    <rect x="260" y="150" width="160" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="340" y="176" font-size="14" fill="#e2e8f0" text-anchor="middle">운영시간</text>
    <text x="340" y="195" font-size="11" fill="#94a3b8" text-anchor="middle">오픈/마감 시간</text>

    <rect x="440" y="150" width="160" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="520" y="176" font-size="14" fill="#e2e8f0" text-anchor="middle">위치 문의</text>
    <text x="520" y="195" font-size="11" fill="#94a3b8" text-anchor="middle">지점 / 지도 링크</text>

    <rect x="620" y="150" width="160" height="60" rx="10" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="700" y="176" font-size="14" fill="#e2e8f0" text-anchor="middle">기타 문의</text>
    <text x="700" y="195" font-size="11" fill="#94a3b8" text-anchor="middle">FAQ 외 질문</text>

    <!-- connecting lines -->
    <line x1="410" y1="90" x2="160" y2="150" stroke="#64748b" stroke-width="2"/>
    <line x1="410" y1="90" x2="340" y2="150" stroke="#64748b" stroke-width="2"/>
    <line x1="410" y1="90" x2="520" y2="150" stroke="#64748b" stroke-width="2"/>
    <line x1="410" y1="90" x2="700" y2="150" stroke="#64748b" stroke-width="2"/>
  </svg>
</div>

<!-- Reflection -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h2>Reflection</h2>
  <p>
    직접 규칙들을 하나씩 정의해보면서, 규칙 기반 시스템의 한계가 어떤 식으로 나타나는지 체감할 수 있었다.
    동시에, 이런 규칙 기반 구조 위에 나중에 머신러닝 모델을 올려서
    점점 더 스마트한 챗봇을 만들어갈 수 있겠다는 아이디어도 떠올랐다.
  </p>
  <p>
    아래 비교 그림은 이번 프로젝트를 통해 느낀 규칙 기반 챗봇과
    머신러닝 기반 챗봇의 차이를 간단히 정리한 것이다.
  </p>
</div>

<!-- Diagram 3 : Rule-based vs ML-based -->
<div class="section-card" style="max-width:900px; margin:0 auto 24px;">
  <h3 style="margin-top:0;">Rule-based vs ML-based Chatbot</h3>

  <svg width="100%" height="260" viewBox="0 0 820 260">
    <!-- Rule Based -->
    <rect x="80" y="70" width="260" height="140" rx="14" fill="#020617" stroke="#38bdf8" stroke-width="2"/>
    <text x="210" y="105" fill="#e2e8f0" font-size="16" text-anchor="middle">Rule-based</text>
    <text x="210" y="135" fill="#94a3b8" font-size="12" text-anchor="middle">정해진 규칙 · 해석 용이</text>
    <text x="210" y="155" fill="#94a3b8" font-size="12" text-anchor="middle">작은 프로젝트 · FAQ에 적합</text>

    <!-- ML Based -->
    <rect x="480" y="70" width="260" height="140" rx="14" fill="#020617" stroke="#6366f1" stroke-width="2"/>
    <text x="610" y="105" fill="#e2e8f0" font-size="16" text-anchor="middle">ML-based</text>
    <text x="610" y="135" fill="#94a3b8" font-size="12" text-anchor="middle">데이터 기반 학습 · 유연한 응답</text>
    <text x="610" y="155" fill="#94a3b8" font-size="12" text-anchor="middle">도메인 확장 · 유지보수 난이도↑</text>

    <!-- VS -->
    <text x="410" y="150" fill="#cbd5f5" font-size="22" text-anchor="middle">VS</text>
  </svg>
</div>
