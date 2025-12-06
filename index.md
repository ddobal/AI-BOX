---
layout: default
title: Home
permalink: /
---

<style>
/* ===========================
   Global layout & header override
   =========================== */

/* 전체 배경과 기본 폰트 */
body {
  background: radial-gradient(circle at top, #050816 0, #02040a 45%, #000000 100%);
  color: #e4e4e4;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}

/* 페이지 전체 래퍼 */
.wrapper {
  max-width: 1120px;
  margin: 0 auto;
  padding: 0 24px 80px;
}

/* 기본 왼쪽 고정 헤더를 상단 네비게이션 바 형태로 변경 */
.wrapper > header {
  position: sticky;
  top: 16px;
  z-index: 30;

  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;

  padding: 14px 22px;
  margin: 0 0 12px;

  border-radius: 999px;
  background: radial-gradient(
    circle at top left,
    rgba(88, 101, 242, 0.26),
    rgba(3, 7, 18, 0.96)
  );
  border: 1px solid rgba(255,255,255,0.12);
  box-shadow: 0 12px 40px rgba(0,0,0,0.9);

  float: none !important;
  width: auto !important;
}

/* 사이트 타이틀 */
.wrapper > header h1 {
  margin: 0;
  font-size: 1.05rem;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  font-weight: 600;
}

.wrapper > header h1 a {
  color: #f5f5f5;
  text-decoration: none;
}

/* 부제(설명) */
.wrapper > header p {
  margin: 0;
  font-size: 0.8rem;
  color: #a8a8a8;
}

/* 프로필 이미지는 상단 바에서는 숨김 */
.wrapper > header img {
  display: none;
}

/* 네비게이션 링크 (About / Blog / Projects) */
.wrapper > header ul {
  list-style: none;
  display: flex;
  align-items: center;
  gap: 18px;
  margin: 0;
  padding: 0;
}

.wrapper > header ul li {
  margin: 0;
}

.wrapper > header ul a {
  font-size: 0.85rem;
  font-weight: 500;
  color: #d6d6d6;
  text-decoration: none;
  padding: 6px 12px;
  border-radius: 999px;
  border: 1px solid transparent;
  transition: all 0.18s ease-out;
}

.wrapper > header ul a:hover {
  color: #ffffff;
  border-color: rgba(255,255,255,0.3);
  background: rgba(0,0,0,0.4);
}

/* "View on GitHub" 같은 기본 문구는 숨기기 */
.wrapper > header .view {
  display: none;
}

/* 본문 영역 왼쪽 마진 제거 */
.wrapper > section {
  margin: 0;
}

/* 모바일 대응 */
@media (max-width: 768px) {
  .wrapper {
    padding: 0 12px 40px;
  }

  .wrapper > header {
    top: 8px;
    padding: 10px 14px;
    border-radius: 16px;
    flex-direction: column;
    align-items: flex-start;
    gap: 6px;
  }

  .wrapper > header ul {
    width: 100%;
    justify-content: flex-start;
    flex-wrap: wrap;
    row-gap: 4px;
  }
}

/* ===========================
   Hero Section Base
   =========================== */
.hero {
  max-width: 920px;
  margin: 120px auto 40px;  /* 상단 네비 아래에 적당히 떨어지도록 */
  padding: 40px 32px 36px;
  background: radial-gradient(circle at top, #202020 0, #101010 55%, #050505 100%);
  border-radius: 26px;
  border: 1px solid rgba(255,255,255,0.05);
  position: relative;
  overflow: hidden;
  box-shadow:
    0 18px 45px rgba(0,0,0,0.9),
    0 0 0 1px rgba(255,255,255,0.02);
  
  /* 등장 애니메이션 */
  opacity: 0;
  transform: translateY(24px) scale(0.98);
  animation: heroFadeIn 0.9s ease-out forwards;
}

/* 살짝 도는 그라디언트 오라 */
.hero::before {
  content: "";
  position: absolute;
  inset: -40%;
  background: conic-gradient(
    from 120deg,
    rgba(88, 101, 242, 0.0),
    rgba(88, 101, 242, 0.4),
    rgba(26, 188, 156, 0.35),
    rgba(155, 89, 182, 0.4),
    rgba(88, 101, 242, 0.0)
  );
  opacity: 0.25;
  filter: blur(40px);
  z-index: -1;
  animation: heroAuraSpin 22s linear infinite;
}

/* 카드 안 내용 영역 */
.hero-inner {
  position: relative;
  z-index: 1;
  text-align: center;
}

/* 상단 뱃지 */
.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 0.8rem;
  padding: 6px 14px;
  border-radius: 999px;
  background: rgba(0,0,0,0.35);
  border: 1px solid rgba(255,255,255,0.12);
  color: #ddd;
  letter-spacing: 0.03em;
  text-transform: uppercase;
  
  opacity: 0;
  transform: translateY(8px);
  animation: heroBadgeIn 0.8s ease-out 0.25s forwards;
}

/* 작은 아이콘, 살짝 떠있는 느낌 */
.hero-badge-icon {
  width: 18px;
  height: 18px;
  border-radius: 999px;
  background: radial-gradient(circle at 30% 30%, #fff, #5865F2);
  box-shadow: 0 0 12px rgba(88,101,242,0.9);
  animation: heroPulse 1.8s ease-in-out infinite;
}

/* 메인 타이틀 */
.hero-title {
  font-size: 2.6rem;
  font-weight: 800;
  margin: 20px 0 10px;
  color: #ffffff;
  letter-spacing: 0.03em;
  opacity: 0;
  transform: translateY(10px);
  animation: heroTitleIn 0.85s cubic-bezier(0.16, 1, 0.3, 1) 0.35s forwards;
}

.hero-subtitle {
  font-size: 1.05rem;
  font-weight: 500;
  color: #c7c7c7;
  margin-bottom: 24px;
  opacity: 0;
  transform: translateY(10px);
  animation: heroSubtitleIn 0.85s ease-out 0.4s forwards;
}

/* 하이라이트 텍스트 */
.hero-highlight {
  font-weight: 600;
  background: linear-gradient(120deg, #4facfe, #38f9d7);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

/* 설명 문단 */
.hero-description {
  font-size: 0.95rem;
  color: #b8b8b8;
  max-width: 520px;
  margin: 0 auto 26px;
  line-height: 1.6rem;
  
  opacity: 0;
  transform: translateY(10px);
  animation: heroDescIn 0.9s ease-out 0.5s forwards;
}

/* CTA 버튼 */
.hero-buttons {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-bottom: 18px;
  
  opacity: 0;
  transform: translateY(8px);
  animation: heroButtonsIn 0.8s ease-out 0.55s forwards;
}

.hero-btn {
  padding: 10px 20px;
  border-radius: 999px;
  font-size: 0.9rem;
  font-weight: 600;
  border: 1px solid rgba(255,255,255,0.12);
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  transition: all 0.22s ease;
}

.hero-btn-primary {
  background: linear-gradient(135deg, #5865F2, #3A7BD5);
  color: #fff;
  box-shadow: 0 8px 22px rgba(88,101,242,0.5);
}

.hero-btn-secondary {
  background: rgba(0,0,0,0.35);
  color: #e4e4e4;
}

.hero-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 26px rgba(0,0,0,0.6);
  border-color: rgba(255,255,255,0.35);
}

/* 아래 현재 관심 영역 스트립 */
.hero-footer {
  font-size: 0.78rem;
  color: #9c9c9c;
  margin-top: 8px;
  opacity: 0;
  transform: translateY(6px);
  animation: heroFooterIn 0.8s ease-out 0.7s forwards;
}

/* 흐르는 텍스트 느낌 */
.hero-footer span {
  background: linear-gradient(120deg, #4facfe, #38f9d7, #c471ed);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

/* ===========================
   Animations
   =========================== */
@keyframes heroFadeIn {
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

@keyframes heroAuraSpin {
  to {
    transform: rotate(360deg);
  }
}

@keyframes heroPulse {
  0%, 100% {
    transform: scale(1);
    box-shadow: 0 0 14px rgba(88,101,242,0.9);
  }
  50% {
    transform: scale(1.12);
    box-shadow: 0 0 24px rgba(88,101,242,1);
  }
}

@keyframes heroBadgeIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes heroTitleIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes heroSubtitleIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes heroDescIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes heroButtonsIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes heroFooterIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 모바일 대응 */
@media (max-width: 768px) {
  .hero {
    margin: 80px 12px 32px;
    padding: 26px 18px 22px;
  }
  
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-subtitle {
    font-size: 0.95rem;
  }
  
  .hero-buttons {
    flex-direction: column;
  }
}
</style>

<div class="hero">
  <div class="hero-inner">
    <div class="hero-badge">
      <div class="hero-badge-icon"></div>
      AI Major 2nd Year · Student Developer
    </div>

    <div class="hero-title">Hyun-seok Jung</div>

    <div class="hero-subtitle">
      <span class="hero-highlight">Computer Vision · Generative AI · Data Projects</span>
    </div>

    <p class="hero-description">
      인공지능학과 2학년으로, 수업에서 배운 내용과 개인적으로 궁금했던 주제를
      작은 프로젝트로 직접 만들어 보고 있습니다. 이 포트폴리오는 거창한 완성품보다는
      <strong>“실제로 코드를 짜 보면서 배운 과정”</strong>을 기록하는 데 더 가깝습니다.
      앞으로 연구나 실무로 이어질 수 있는 기본기를 차분히 쌓는 것을 목표로 합니다.
    </p>

    <div class="hero-buttons">
      <a href="{{ '/about/' | relative_url }}" class="hero-btn hero-btn-primary">
        About Me
      </a>
      <a href="{{ '/projects/' | relative_url }}" class="hero-btn hero-btn-secondary">
        View Projects
      </a>
      <a href="{{ '/blog/' | relative_url }}" class="hero-btn hero-btn-secondary">
        Blog
      </a>
    </div>

    <div class="hero-footer">
      요즘은 <span>Computer Vision, 생성형 AI, 자동화 실습</span> 위주로 공부하고 있습니다.
    </div>
  </div>
</div>
