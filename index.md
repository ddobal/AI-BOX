---
layout: default
title: Home
permalink: /
---

<style>
/* ===========================
   Hero Section Base
   =========================== */
.hero {
  max-width: 920px;
  margin: 80px auto 40px;
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
    margin: 40px 12px 32px;
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
      AI Engineer & Product Developer
    </div>

    <div class="hero-title">Hyun-seok Jung</div>

    <div class="hero-subtitle">
      <span class="hero-highlight">Computer Vision · Generative AI · Automation</span>
    </div>

    <p class="hero-description">
      모델 정확도와 Latency, 그리고 운영 난이도까지 동시에 고려하는
      <strong>“실제로 돌릴 수 있는 AI 시스템”</strong>에 집중하고 있습니다.
      프로덕트 고민과 연구를 함께 가져가는 엔지니어를 지향합니다.
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
      Currently exploring <span>Vision · Diffusion · Production ML · Automation</span>
    </div>
  </div>
</div>
