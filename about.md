---
layout: default
title: About
permalink: /about/
---

<style>
  .section-heading {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.35rem;
    margin-bottom: 10px;
  }

  .section-heading-icon {
    width: 26px;
    height: 26px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }

  .section-heading-icon svg {
    width: 22px;
    height: 22px;
    display: block;
  }
</style>

<!-- 📌 미니 히어로 (상단 공통 HS 로고) -->
<div class="page-mini-hero">
  <div class="page-mini-hero-icon">
    <!-- HS 로고 SVG -->
    <svg
      width="40"
      height="40"
      viewBox="0 0 48 48"
      fill="none"
      role="img"
      aria-label="Hyun-seok Jung Portfolio Logo"
    >
      <defs>
        <!-- 배경 그라디언트 -->
        <radialGradient id="hsLogoBg" cx="30%" cy="20%" r="80%">
          <stop offset="0%" stop-color="#4facfe" />
          <stop offset="45%" stop-color="#4263eb" />
          <stop offset="100%" stop-color="#c471ed" />
        </radialGradient>

        <!-- 외곽선 그라디언트 -->
        <linearGradient id="hsLogoStroke" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#ffffff" stop-opacity="0.95" />
          <stop offset="100%" stop-color="#e5e5ff" stop-opacity="0.7" />
        </linearGradient>
      </defs>

      <!-- 바깥 원 + 글로우 -->
      <circle
        cx="24"
        cy="24"
        r="21"
        fill="url(#hsLogoBg)"
      />
      <circle
        cx="24"
        cy="24"
        r="21"
        fill="none"
        stroke="url(#hsLogoStroke)"
        stroke-width="1.4"
      />

      <!-- 안쪽 글로우 링 -->
      <circle
        cx="24"
        cy="24"
        r="14"
        fill="none"
        stroke="rgba(255,255,255,0.35)"
        stroke-width="1.2"
        stroke-dasharray="4 3"
      />

      <!-- H 세로 막대 -->
      <path
        d="M16 15 L18.5 15 C19.4 15 20 15.6 20 16.5 L20 31.5 C20 32.4 19.4 33 18.5 33 L16 33 Z"
        fill="rgba(255,255,255,0.96)"
      />

      <!-- H 오른쪽 세로 막대 -->
      <path
        d="M28 15 L30.5 15 C31.4 15 32 15.6 32 16.5 L32 31.5 C32 32.4 31.4 33 30.5 33 L28 33 Z"
        fill="rgba(255,255,255,0.96)"
      />

      <!-- H 가로 막대 -->
      <rect
        x="19.8"
        y="22.4"
        width="8.4"
        height="2.8"
        rx="1.2"
        fill="rgba(255,255,255,0.96)"
      />

      <!-- 작은 포인트 점 (AI / 아이디어 느낌) -->
      <circle
        cx="34.5"
        cy="13.5"
        r="2"
        fill="white"
        fill-opacity="0.95"
      />
      <circle
        cx="34.5"
        cy="13.5"
        r="3.1"
        stroke="rgba(255,255,255,0.5)"
        stroke-width="0.8"
        fill="none"
      />
    </svg>
  </div>

  <h1>Hyun-seok Jung</h1>
  <p class="mini-hero-sub">
    Vision · Generative AI · Automation 분야를 중심으로  
    <strong>실제로 동작하는 AI 시스템</strong>을 만드는 데 관심이 많은 엔지니어입니다.  
    이 포트폴리오는 실무와 실험을 병행하며 <strong>지식 축적 및 학습을 기록하기 위한 공간</strong>으로 운영하고 있습니다.
  </p>
</div>


<div class="section-card-grid">

  <!-- 1. Focus Areas -->
  <section class="section-card">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        <!-- 🎯 Target 아이콘 -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <circle cx="12" cy="12" r="9" stroke="white" stroke-width="1.8" />
          <circle cx="12" cy="12" r="5" stroke="white" stroke-width="1.6" />
          <circle cx="12" cy="12" r="2" fill="white" />
        </svg>
      </span>
      Focus Areas
    </h2>
    <p>
      연구 및 프로젝트는 “직접 만들 수 있는 기술”을 핵심 가치로 삼고 진행합니다.  
      단순한 이론 정리가 아닌, 실제 코드·모델·프로덕트 구현 중심으로 학습을 이어가고 있습니다.
    </p>
    <ul>
      <li><strong>Generative AI</strong> – Diffusion, LLM 모델 구조 이해 및 튜닝</li>
      <li><strong>Computer Vision</strong> – Detection, Pose, Segmentation 기반 실시간 시스템</li>
      <li><strong>Automation / Tools</strong> – 업무 자동화·데이터 처리 파이프라인 구현</li>
      <li><strong>Product Development</strong> – 실제로 사용할 수 있는 AI 기능 설계</li>
    </ul>
  </section>


  <!-- 2. Learning Purpose -->
  <section class="section-card">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        <!-- 📘 Book 아이콘 -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <path
            d="M6 5.5C6 4.67 6.67 4 7.5 4H18v14.5H8c-1.1 0-2 .9-2 2V5.5Z"
            stroke="white"
            stroke-width="1.6"
            fill="none"
          />
          <path
            d="M6 6h11.5"
            stroke="white"
            stroke-width="1.4"
            stroke-linecap="round"
          />
          <path
            d="M8 18.5H18"
            stroke="white"
            stroke-width="1.4"
            stroke-linecap="round"
          />
        </svg>
      </span>
      Learning &amp; Purpose
    </h2>
    <p>
      이 페이지는 <strong>학습 과정 자체를 기록하고 정리하는 목적</strong>으로 운영됩니다.
      단순한 포트폴리오가 아니라,
      스스로 개념을 정리하고 기술을 체계적으로 쌓기 위한 “학습 아카이브”에 가깝습니다.
    </p>
    <ul>
      <li>새로운 모델/기술 학습 시 정리 기록</li>
      <li>실험 로그 및 시행착오 문서화</li>
      <li>프로토타입 제작 경험 아카이빙</li>
      <li>더 나은 구조·아키텍처 설계 연습</li>
    </ul>
    <p>
      하나의 프로젝트를 단순히 완성하는 데 끝나지 않고,  
      <strong>“왜 이렇게 설계했는가”</strong>와 같은 사고 과정을 남기는 데 집중하고 있습니다.
    </p>
  </section>


  <!-- 3. Tech Stack -->
  <section class="section-card">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        <!-- 🛠 Tools 아이콘 -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <path
            d="M14.5 4.5a3.5 3.5 0 0 1 4.2 4.2l-3 3-3.4-3.4 2.2-2.2Z"
            stroke="white"
            stroke-width="1.6"
            stroke-linejoin="round"
          />
          <path
            d="M10.3 9.3 5 14.6V19h4.4l5.3-5.3-4.4-4.4Z"
            stroke="white"
            stroke-width="1.6"
            stroke-linejoin="round"
          />
        </svg>
      </span>
      Tech Stack
    </h2>
    <p>AI 실험 및 자동화 시스템 개발에 주로 사용하는 기술입니다.</p>
    <ul>
      <li><strong>Python, C++</strong> · 알고리즘/모델링</li>
      <li><strong>PyTorch, TensorFlow</strong> · 모델 구현 및 실험</li>
      <li><strong>OpenCV</strong> · 실시간 비전 시스템 프로토타이핑</li>
      <li><strong>Docker, Linux</strong> · 실험 환경 세팅 및 배포</li>
      <li><strong>ML Ops</strong> · 모델 최적화 및 실행 환경 관리</li>
    </ul>
  </section>


  <!-- 4. Research Style / Philosophy -->
  <section class="section-card">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        <!-- 🔍 Magnifier 아이콘 -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <circle
            cx="11"
            cy="11"
            r="6"
            stroke="white"
            stroke-width="1.8"
          />
          <line
            x1="15"
            y1="15"
            x2="20"
            y2="20"
            stroke="white"
            stroke-width="1.8"
            stroke-linecap="round"
          />
        </svg>
      </span>
      Research Style
    </h2>
    <p>
      단순히 “작동하는 코드” 보다는  
      <strong>성능·구조·사용성 측면에서 실제 가치가 있는 AI 기능</strong>을 만드는 것을 목표로 합니다.
    </p>
    <ul>
      <li>문제 → 구조 설계 → 모델 → 실험 → 개선 → 결과 해석 흐름을 중시</li>
      <li>재사용 가능한 코드 구조 선호</li>
      <li>데이터 기반 설계 &amp; 실측 결과 분석을 강조</li>
    </ul>
    <p>A/B 테스트와 반복 개선 과정에서 배우는 것을 가장 즐깁니다.</p>
  </section>


  <!-- 5. Contact -->
  <section class="section-card">
    <h2 class="section-heading">
      <span class="section-heading-icon">
        <!-- 📫 Mail 아이콘 -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <rect
            x="3"
            y="6"
            width="18"
            height="12"
            rx="2"
            stroke="white"
            stroke-width="1.8"
          />
          <path
            d="M4 7.5 12 12.5 20 7.5"
            stroke="white"
            stroke-width="1.6"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </span>
      Contact
    </h2>
    <p>
      프로젝트나 기술 관련해서 의견 교환이 필요하면 언제든 연락 주세요.
    </p>
    <p><strong>Email:</strong> ddobal@gmail.com</p>
  </section>

</div>
