---
layout: page
title: Home
permalink: /
---

<style>
  /* ===== Hero 영역 전체 배경 ===== */
  .hs-hero-wrapper {
    margin-top: 2rem;
    margin-bottom: 2.5rem;
  }

  .hs-hero {
    position: relative;
    padding: 3.5rem 3rem;
    border-radius: 24px;
    background: radial-gradient(circle at 0% 0%, rgba(93, 76, 255, 0.25), transparent 55%),
                radial-gradient(circle at 100% 0%, rgba(0, 200, 255, 0.20), transparent 55%),
                rgba(10, 10, 15, 0.92);
    box-shadow:
      0 18px 45px rgba(0, 0, 0, 0.7),
      0 0 0 1px rgba(255, 255, 255, 0.02);
    overflow: hidden;
  }

  /* 배경 그라디언트 장식 */
  .hs-hero::before,
  .hs-hero::after {
    content: "";
    position: absolute;
    border-radius: 999px;
    filter: blur(25px);
    opacity: 0.7;
    pointer-events: none;
  }

  .hs-hero::before {
    width: 240px;
    height: 240px;
    background: radial-gradient(circle, rgba(76, 113, 255, 0.7), transparent 60%);
    top: -60px;
    left: -60px;
  }

  .hs-hero::after {
    width: 260px;
    height: 260px;
    background: radial-gradient(circle, rgba(0, 207, 255, 0.65), transparent 60%);
    bottom: -80px;
    right: -40px;
  }

  .hs-hero-inner {
    position: relative;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    align-items: center;
    z-index: 2;
  }

  .hs-hero-left {
    flex: 1 1 260px;
    min-width: 260px;
  }

  .hs-hero-right {
    flex: 1 1 260px;
    min-width: 260px;
    display: flex;
    justify-content: flex-end;
  }

  /* ===== 텍스트 스타일 ===== */
  .hs-pill {
    display: inline-flex;
    align-items: center;
    gap: .55rem;
    padding: .32rem .85rem;
    border-radius: 999px;
    background: rgba(12, 12, 20, 0.9);
    border: 1px solid rgba(178, 132, 255, 0.5);
    font-size: .80rem;
    letter-spacing: .08em;
    text-transform: uppercase;
    color: #d2ccff;
  }

  .hs-pill-dot {
    width: .45rem;
    height: .45rem;
    border-radius: 50%;
    background: radial-gradient(circle, #4cffd7 0, #0aff9b 35%, transparent 65%);
    box-shadow: 0 0 12px rgba(74, 255, 215, .8);
  }

  .hs-hero-title {
    margin-top: 1.4rem;
    margin-bottom: .5rem;
    font-size: 2.4rem;
    font-weight: 700;
    letter-spacing: .03em;
  }

  .hs-hero-subtitle {
    font-size: 0.98rem;
    color: #b8c0ff;
    margin-bottom: 1.5rem;
  }

  .hs-hero-desc {
    font-size: 0.95rem;
    color: #d8ddff;
    max-width: 32rem;
    line-height: 1.6;
  }

  .hs-hero-desc b {
    color: #fff;
  }

  .hs-chip-row {
    margin-top: 1.6rem;
    display: flex;
    flex-wrap: wrap;
    gap: .5rem;
  }

  .hs-chip {
    font-size: .80rem;
    padding: .35rem .75rem;
    border-radius: 999px;
    border: 1px solid rgba(120, 130, 255, .55);
    background: rgba(12, 12, 24, 0.85);
    color: #d6dfff;
  }

  /* ===== 버튼들 ===== */
  .hs-btn-row {
    margin-top: 2rem;
    display: flex;
    flex-wrap: wrap;
    gap: .75rem;
  }

  .hs-btn-primary {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: .6rem 1.4rem;
    border-radius: 999px;
    background: linear-gradient(135deg, #4c6fff, #8c5bff);
    color: #fff !important;
    font-size: .9rem;
    border: none;
    box-shadow: 0 10px 22px rgba(0,0,0,.6);
    text-decoration: none;
  }

  .hs-btn-primary:hover {
    text-decoration: none;
    filter: brightness(1.08);
    transform: translateY(-1px);
  }

  .hs-btn-ghost {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: .55rem 1.2rem;
    border-radius: 999px;
    background: rgba(12, 12, 20, 0.9);
    border: 1px solid rgba(150, 160, 255, 0.65);
    color: #d7ddff !important;
    font-size: .86rem;
    text-decoration: none;
  }

  .hs-btn-ghost:hover {
    text-decoration: none;
    background: rgba(30, 30, 55, 0.95);
  }

  .hs-btn-ghost i {
    margin-right: .45rem;
  }

  /* ===== 오른쪽 카드 (상태/링크) ===== */
  .hs-sidecard {
    width: 100%;
    max-width: 320px;
    border-radius: 20px;
    background: rgba(5, 7, 15, 0.96);
    border: 1px solid rgba(210, 220, 255, 0.06);
    box-shadow: 0 16px 32px rgba(0, 0, 0, .80);
    padding: 1.15rem 1.25rem 1.1rem;
  }

  .hs-sidecard-title {
    font-size: .85rem;
    text-transform: uppercase;
    letter-spacing: .18em;
    color: #a6b0ff;
    margin-bottom: .6rem;
  }

  .hs-status-pill {
    display: inline-flex;
    align-items: center;
    gap: .4rem;
    padding: .35rem .7rem;
    border-radius: 999px;
    background: rgba(20, 240, 180, 0.07);
    color: #b4ffe7;
    font-size: .78rem;
  }

  .hs-status-dot {
    width: .42rem;
    height: .42rem;
    border-radius: 999px;
    background: radial-gradient(circle, #32ffb6, #0fd694);
    box-shadow: 0 0 8px rgba(50, 255, 182, .9);
  }

  .hs-side-section {
    margin-top: .85rem;
  }

  .hs-side-label {
    font-size: .72rem;
    text-transform: uppercase;
    letter-spacing: .16em;
    color: #7a83b8;
    margin-bottom: .25rem;
  }

  .hs-side-text {
    font-size: .84rem;
    color: #dadeff;
  }

  .hs-side-links {
    margin-top: .75rem;
    display: flex;
    flex-wrap: wrap;
    gap: .45rem;
  }

  .hs-side-tag {
    font-size: .78rem;
    padding: .28rem .7rem;
    border-radius: 999px;
    background: rgba(19, 22, 40, .98);
    border: 1px solid rgba(133, 144, 255, .6);
    color: #dadfff;
  }

  /* ===== 아래 섹션들 ===== */
  .hs-section {
    margin-bottom: 2.6rem;
  }

  .hs-section-title {
    display: flex;
    align-items: center;
    gap: .55rem;
    font-size: 1.05rem;
    font-weight: 600;
    margin-bottom: .85rem;
  }

  .hs-section-title span {
    font-size: .85rem;
    font-weight: 400;
    color: #b6bfe9;
  }

  .hs-section-icon {
    width: .9rem;
    height: .9rem;
    border-radius: 999px;
    background: linear-gradient(135deg, #ff4b9a, #ffb34b);
    box-shadow: 0 0 13px rgba(255, 139, 180, .85);
  }

  .hs-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1.1rem;
  }

  .hs-card {
    border-radius: 18px;
    padding: 1rem .95rem;
    background: rgba(10, 12, 22, 0.98);
    border: 1px solid rgba(210, 220, 255, 0.05);
    box-shadow: 0 10px 18px rgba(0, 0, 0, 0.75);
  }

  .hs-card-label {
    font-size: .78rem;
    text-transform: uppercase;
    letter-spacing: .16em;
    color: #7f8be0;
    margin-bottom: .45rem;
  }

  .hs-card-title {
    font-size: .95rem;
    font-weight: 600;
    margin-bottom: .35rem;
  }

  .hs-card-text {
    font-size: .84rem;
    color: #d2dcff;
  }

  @media (max-width: 900px) {
    .hs-hero {
      padding: 2.6rem 1.7rem;
    }
    .hs-hero-inner {
      flex-direction: column;
      align-items: flex-start;
    }
    .hs-hero-right {
      justify-content: flex-start;
    }
  }

  @media (max-width: 768px) {
    .hs-grid {
      grid-template-columns: 1fr;
    }
    .hs-hero-title {
      font-size: 2rem;
    }
  }
</style>

<div class="hs-hero-wrapper">
  <section class="hs-hero">
    <div class="hs-hero-inner">
      <!-- 왼쪽: 인트로 -->
      <div class="hs-hero-left">
        <div class="hs-pill">
          <span class="hs-pill-dot"></span>
          <span>AI Engineer &amp; Product Developer</span>
        </div>

        <h1 class="hs-hero-title">
          Hyun-seok Jung&apos;s AI-BOX
        </h1>

        <p class="hs-hero-subtitle">
          Computer Vision · Generative AI · Production ML · Automation
        </p>

        <p class="hs-hero-desc">
          실제 환경에서 돌아가는 <b>AI 제품과 자동화 시스템</b>에 관심이 많습니다.<br>
          모델 성능뿐 아니라, <b>사용자 경험과 운영 관점</b>까지 고민하며
          <b>&quot;끝까지 책임지는 엔지니어&quot;</b>를 목표로 하고 있습니다.
        </p>

        <div class="hs-chip-row">
          <span class="hs-chip">Vision &amp; Diffusion</span>
          <span class="hs-chip">Prompt Engineering</span>
          <span class="hs-chip">MLOps / Automation</span>
          <span class="hs-chip">Side Projects &amp; Experiments</span>
        </div>

        <div class="hs-btn-row">
          <a href="{{ '/about/' | relative_url }}" class="hs-btn-primary">
            About Me
          </a>
          <a href="{{ '/projects/' | relative_url }}" class="hs-btn-ghost">
            <i class="fas fa-rocket"></i> Projects
          </a>
          <a href="{{ '/blog/' | relative_url }}" class="hs-btn-ghost">
            <i class="fas fa-pen"></i> Blog
          </a>
        </div>
      </div>

      <!-- 오른쪽: 현재 상태/링크 카드 -->
      <div class="hs-hero-right">
        <div class="hs-sidecard">
          <div class="hs-sidecard-title">Now Playing</div>

          <div class="hs-status-pill">
            <span class="hs-status-dot"></span>
            <span>Building &amp; shipping small AI tools</span>
          </div>

          <div class="hs-side-section">
            <div class="hs-side-label">Current focus</div>
            <div class="hs-side-text">
              · Vision + Diffusion 기반 개인 프로젝트<br>
              · 실제 사용 가능한 자동매매 &amp; 자동화 워크플로우<br>
              · AI 서비스 기획 &amp; 프로덕트 디자인
            </div>
          </div>

          <div class="hs-side-section">
            <div class="hs-side-label">Stack</div>
            <div class="hs-side-links">
              <span class="hs-side-tag">Python</span>
              <span class="hs-side-tag">PyTorch</span>
              <span class="hs-side-tag">FastAPI / Flask</span>
              <span class="hs-side-tag">Pine Script</span>
              <span class="hs-side-tag">GitHub Actions</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ===== 아래 섹션들 ===== -->
<section class="hs-section">
  <h2 class="hs-section-title">
    <span class="hs-section-icon"></span>
    Focus Areas
    <span>어떤 문제를 좋아하는지 한 눈에</span>
  </h2>

  <div class="hs-grid">
    <article class="hs-card">
      <div class="hs-card-label">01 · Computer Vision &amp; Generative AI</div>
      <div class="hs-card-title">이미지를 이해하고, 새로 만들어내는 시스템</div>
      <p class="hs-card-text">
        Object Detection, Image Segmentation부터 Diffusion 기반 생성 모델까지 관심이 있습니다.
        단순 데모를 넘어서 <b>실제 워크플로우에 녹아드는 형태</b>의 사용 경험을 고민합니다.
      </p>
    </article>

    <article class="hs-card">
      <div class="hs-card-label">02 · Automation &amp; Trading</div>
      <div class="hs-card-title">사람의 반복 작업을 줄여주는 자동화</div>
      <p class="hs-card-text">
        Pine Script &amp; Python을 사용한 자동매매 봇, 데이터 파이프라인, 리포트 자동화 등
        <b>&quot;매번 수동으로 하던 일&quot;</b>을 줄이는 도구들을 만들어 보고 있습니다.
      </p>
    </article>

    <article class="hs-card">
      <div class="hs-card-label">03 · Product &amp; UX</div>
      <div class="hs-card-title">AI를 &quot;제품&quot; 관점에서 바라보기</div>
      <p class="hs-card-text">
        모델 성능뿐 아니라, <b>사용자가 실제로 계속 쓰고 싶은 경험</b>을 만드는 것에 관심이 있습니다.
        화면 구성, 온보딩, 피드백 루프까지 포함한 전체 플로우를 설계하고 싶습니다.
      </p>
    </article>
  </div>
</section>

<section class="hs-section">
  <h2 class="hs-section-title">
    <span class="hs-section-icon"></span>
    What you can find here
    <span>이 페이지에서 볼 수 있는 것들</span>
  </h2>

  <div class="hs-grid">
    <article class="hs-card">
      <div class="hs-card-label">Portfolio</div>
      <div class="hs-card-title">Projects</div>
      <p class="hs-card-text">
        지금까지 만들었던 실험적인 AI 서비스, 자동매매 전략, 데이터 분석 및 시각화 결과들을
        프로젝트 단위로 정리할 예정입니다.
      </p>
    </article>

    <article class="hs-card">
      <div class="hs-card-label">Notes</div>
      <div class="hs-card-title">Blog</div>
      <p class="hs-card-text">
        딥러닝/머신러닝 정리, 삽질 기록, 간단한 튜토리얼 등
        <b>&quot;나중에 다시 보려고 적어두는 메모&quot;</b>의 성격이 강한 글들을 모아둘 예정입니다.
      </p>
    </article>

    <article class="hs-card">
      <div class="hs-card-label">About</div>
      <div class="hs-card-title">Who I am</div>
      <p class="hs-card-text">
        공부해 온 것, 요즘 관심 있는 분야, 협업을 할 때 중요하게 생각하는 것들을 조금 더 자세히 적어두었습니다.
        궁금한 점이 있다면 언제든 연락 주세요.
      </p>
    </article>
  </div>
</section>
